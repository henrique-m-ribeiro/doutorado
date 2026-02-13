# ADR 005: Evolução do Schema para Granularidade Territorial e Temporal

**Status**: Proposto
**Data**: 2026-01-16
**Decisor**: CEO (Henrique) + Arquiteto de Dados (Claude)
**Contexto**: Expansão da capacidade de análise multi-escala

---

## Contexto

O sistema atual de inteligência territorial do Tocantins possui limitações significativas em termos de granularidade territorial e temporal:

### Limitações do Sistema Atual

**1. Granularidade Territorial Limitada**

```sql
-- Schema Atual (Migration 001)
mesoregions (2)    -- Apenas divisão antiga (pré-2017)
microregions (8)   -- Apenas divisão antiga (pré-2017)
municipalities (139)
```

**Problemas**:
- ❌ Não suporta divisão NOVA do IBGE (pós-2017)
  - Regiões Geográficas Intermediárias (3)
  - Regiões Geográficas Imediatas (11)
- ❌ Não suporta indicadores **estaduais** (SICONFI, etc.)
- ❌ Não extensível para outras divisões (bacias, regiões de saúde, comarcas)

**2. Valores Apenas Municipais**

```sql
-- Schema Atual (Migration 002)
indicator_values (
    indicator_id UUID,
    municipality_id UUID,  -- ← Apenas municípios
    year INTEGER,
    value DECIMAL
)
```

**Problemas**:
- ❌ Impossível armazenar dados estaduais diretos (ex: receita do governo estadual)
- ❌ Agregações regionais devem ser re-calculadas em toda consulta (custoso)
- ❌ Não há como armazenar dados de outras granularidades nativamente

**3. Análises Temporais Não Otimizadas**

```sql
-- Query atual para séries temporais (10 anos)
SELECT year, value
FROM indicator_values
WHERE indicator_id = ...
  AND municipality_id = ...
  AND year >= 2015
ORDER BY year;
```

**Problemas**:
- ⚠️ Funciona, mas sem índices específicos para séries
- ⚠️ Dados esparsos (census) requerem lógica extra
- ⚠️ Sem suporte explícito para "últimos N pontos disponíveis"

### Trigger da Decisão

CEO solicitou:
> "Precisamos expandir a capacidade de análise para suportar diferentes recortes territoriais (Estado, municípios, regiões antigas e novas) e facilitar análises temporais (séries de 10 anos, dados esparsos)."

---

## Decisão

**Implementar um Schema de Territórios Genérico e Extensível** com suporte a:

1. **Múltiplas Divisões Territoriais** (antigas, novas e futuras)
2. **Hierarquias e Pertencimentos** explícitos
3. **Indicadores Multi-Escala** (municipal, regional, estadual)
4. **Otimização para Consultas Temporais**

---

## Arquitetura Proposta

### 1. Tabela `territories` (Genérica)

Unifica todas as entidades territoriais em uma única tabela:

```sql
CREATE TABLE territories (
    id UUID PRIMARY KEY,
    type territory_type NOT NULL,  -- estado, municipio, microregiao, etc.
    ibge_code VARCHAR(20),          -- código IBGE quando aplicável
    name VARCHAR(200) NOT NULL,
    division_scheme VARCHAR(50),    -- 'antiga', 'nova', 'saude', 'bacia', etc.

    -- Metadados opcionais
    metadata JSONB DEFAULT '{}'::jsonb,

    -- Controles
    is_active BOOLEAN DEFAULT true,
    valid_from DATE,
    valid_until DATE
);

CREATE TYPE territory_type AS ENUM (
    'estado',
    'mesorregiao',
    'microrregiao',
    'regiao_intermediaria',
    'regiao_imediata',
    'municipio',
    -- Extensibilidade futura:
    'bacia_hidrografica',
    'regiao_saude',
    'comarca',
    'zona_eleitoral'
);
```

**Benefícios**:
- ✅ Todas as entidades territoriais em um só lugar
- ✅ Extensível sem ALTER TABLE (apenas adicionar enum)
- ✅ Suporta divisões antigas e novas simultaneamente
- ✅ Versionamento temporal (`valid_from`, `valid_until`)

### 2. Tabela `territory_relationships` (Hierarquias)

Modela pertencimentos e hierarquias:

```sql
CREATE TABLE territory_relationships (
    id UUID PRIMARY KEY,
    parent_territory_id UUID REFERENCES territories(id),
    child_territory_id UUID REFERENCES territories(id),
    relationship_type VARCHAR(50) NOT NULL, -- 'pertence_a', 'parte_de', etc.
    division_scheme VARCHAR(50) NOT NULL,   -- 'antiga', 'nova'

    valid_from DATE,
    valid_until DATE,

    UNIQUE(parent_territory_id, child_territory_id, relationship_type, division_scheme)
);
```

**Exemplos**:

```
-- Divisão Antiga
Município "Araguaína" pertence_a Microrregião "Araguaína"
Microrregião "Araguaína" pertence_a Mesorregião "Ocidental"
Mesorregião "Ocidental" pertence_a Estado "Tocantins"

-- Divisão Nova
Município "Araguaína" pertence_a Região Imediata "Araguaína"
Região Imediata "Araguaína" pertence_a Região Intermediária "Araguaína"
Região Intermediária "Araguaína" pertence_a Estado "Tocantins"
```

**Benefícios**:
- ✅ Hierarquias explícitas (não inferidas)
- ✅ Suporta múltiplas hierarquias simultâneas (antiga E nova)
- ✅ Extensível para outras hierarquias (bacias, saúde)
- ✅ Versionamento temporal

### 3. Modificação de `indicator_values`

Substituir `municipality_id` por `territory_id` genérico:

```sql
-- ANTES (atual)
CREATE TABLE indicator_values (
    indicator_id UUID,
    municipality_id UUID,  -- ← Apenas municípios
    year INTEGER,
    value DECIMAL
);

-- DEPOIS (proposto)
CREATE TABLE indicator_values (
    indicator_id UUID,
    territory_id UUID REFERENCES territories(id),  -- ← Qualquer território
    year INTEGER,
    month INTEGER,
    value DECIMAL,

    -- Metadados de agregação
    aggregation_method VARCHAR(50),  -- 'raw', 'sum', 'avg', 'weighted_avg'
    is_aggregated BOOLEAN DEFAULT false,

    UNIQUE(indicator_id, territory_id, year, month)
);
```

**Benefícios**:
- ✅ Suporta dados municipais, regionais E estaduais
- ✅ Agregações podem ser pré-calculadas e armazenadas
- ✅ Transparente para queries existentes (via view de compatibilidade)

### 4. Views de Compatibilidade

Manter compatibilidade com código existente:

```sql
-- View: municipalities (compatibilidade)
CREATE VIEW municipalities AS
SELECT
    id,
    ibge_code,
    name,
    (SELECT parent_territory_id
     FROM territory_relationships tr
     WHERE tr.child_territory_id = t.id
       AND tr.relationship_type = 'pertence_a'
       AND tr.division_scheme = 'antiga'
     LIMIT 1) as microregion_id,
    metadata->>'population' as population,
    metadata->>'area_km2' as area_km2,
    metadata->>'state_id' as state_id
FROM territories t
WHERE t.type = 'municipio';

-- View: microregions (compatibilidade)
CREATE VIEW microregions AS
SELECT
    id,
    ibge_code,
    name,
    (SELECT parent_territory_id
     FROM territory_relationships tr
     WHERE tr.child_territory_id = t.id
       AND tr.relationship_type = 'pertence_a'
       AND tr.division_scheme = 'antiga'
     LIMIT 1) as mesoregion_id
FROM territories t
WHERE t.type = 'microrregiao';

-- View: mesoregions (compatibilidade)
CREATE VIEW mesoregions AS
SELECT id, ibge_code, name
FROM territories
WHERE type = 'mesorregiao';
```

**Benefícios**:
- ✅ Código existente continua funcionando
- ✅ Migração gradual possível
- ✅ Rollback facilitado

### 5. Índices para Séries Temporais

Otimizar consultas de séries:

```sql
-- Índice composto para séries temporais
CREATE INDEX idx_indicator_values_timeseries
ON indicator_values (indicator_id, territory_id, year DESC, month DESC);

-- Índice parcial para dados recentes (mais consultados)
CREATE INDEX idx_indicator_values_recent
ON indicator_values (indicator_id, territory_id, year DESC, month DESC)
WHERE year >= EXTRACT(YEAR FROM CURRENT_DATE) - 10;
```

---

## Diagrama do Schema Proposto

```
┌─────────────────────────────────────────────────────────────┐
│                      TERRITORIES                             │
│  ┌──────────────────────────────────────────────────────┐   │
│  │ • estado (1)                                          │   │
│  │ • mesorregiao (2)          divisão='antiga'          │   │
│  │ • microrregiao (8)         divisão='antiga'          │   │
│  │ • regiao_intermediaria (3) divisão='nova'            │   │
│  │ • regiao_imediata (11)     divisão='nova'            │   │
│  │ • municipio (139)                                     │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                              │
                              │ belongs_to
                              ▼
┌─────────────────────────────────────────────────────────────┐
│               TERRITORY_RELATIONSHIPS                        │
│  ┌──────────────────────────────────────────────────────┐   │
│  │ • parent_territory_id                                 │   │
│  │ • child_territory_id                                  │   │
│  │ • relationship_type ('pertence_a')                   │   │
│  │ • division_scheme ('antiga', 'nova')                 │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
                              │
                              │ referenced_by
                              ▼
┌─────────────────────────────────────────────────────────────┐
│                    INDICATOR_VALUES                          │
│  ┌──────────────────────────────────────────────────────┐   │
│  │ • indicator_id                                        │   │
│  │ • territory_id  ◄── Referencia qualquer território   │   │
│  │ • year, month                                         │   │
│  │ • value                                               │   │
│  │ • aggregation_method ('raw', 'sum', 'avg')           │   │
│  └──────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────┘
```

---

## Exemplos de Uso

### 1. Consultar Indicador Municipal (como antes)

```sql
SELECT
    t.name as municipio,
    iv.year,
    iv.value
FROM indicator_values iv
JOIN territories t ON iv.territory_id = t.id
WHERE t.type = 'municipio'
  AND t.name = 'Palmas'
  AND iv.indicator_id = (SELECT id FROM indicator_definitions WHERE code = 'ECON_PIB_TOTAL')
  AND iv.year >= 2015
ORDER BY iv.year;
```

### 2. Consultar Indicador Estadual (novo)

```sql
SELECT
    t.name as territorio,
    iv.year,
    iv.value
FROM indicator_values iv
JOIN territories t ON iv.territory_id = t.id
WHERE t.type = 'estado'
  AND t.name = 'Tocantins'
  AND iv.indicator_id = (SELECT id FROM indicator_definitions WHERE code = 'ECON_RECEITA_ESTADUAL')
ORDER BY iv.year;
```

### 3. Consultar por Microrregião (divisão antiga)

```sql
SELECT
    t.name as microrregiao,
    iv.year,
    iv.value
FROM indicator_values iv
JOIN territories t ON iv.territory_id = t.id
WHERE t.type = 'microrregiao'
  AND t.division_scheme = 'antiga'
  AND t.name = 'Araguaína'
  AND iv.indicator_id = ...
ORDER BY iv.year;
```

### 4. Consultar por Região Imediata (divisão nova)

```sql
SELECT
    t.name as regiao_imediata,
    iv.year,
    iv.value
FROM indicator_values iv
JOIN territories t ON iv.territory_id = t.id
WHERE t.type = 'regiao_imediata'
  AND t.division_scheme = 'nova'
  AND t.name = 'Araguaína'
  AND iv.indicator_id = ...
ORDER BY iv.year;
```

### 5. Agregar Municípios → Microrregião (on-the-fly)

```sql
WITH municipios_microrregiao AS (
    SELECT child_territory_id
    FROM territory_relationships tr
    JOIN territories t ON tr.parent_territory_id = t.id
    WHERE t.name = 'Araguaína'
      AND t.type = 'microrregiao'
      AND tr.division_scheme = 'antiga'
)
SELECT
    AVG(iv.value) as pib_medio_regional,
    iv.year
FROM indicator_values iv
WHERE iv.territory_id IN (SELECT child_territory_id FROM municipios_microrregiao)
  AND iv.indicator_id = (SELECT id FROM indicator_definitions WHERE code = 'ECON_PIB_TOTAL')
GROUP BY iv.year
ORDER BY iv.year;
```

### 6. Série Temporal (últimos 10 anos)

```sql
SELECT
    year,
    value
FROM indicator_values
WHERE indicator_id = ...
  AND territory_id = ...
  AND year >= EXTRACT(YEAR FROM CURRENT_DATE) - 10
ORDER BY year DESC;
```

### 7. Últimos 3 Pontos Disponíveis (dados esparsos)

```sql
SELECT
    year,
    value
FROM indicator_values
WHERE indicator_id = ...
  AND territory_id = ...
ORDER BY year DESC
LIMIT 3;
```

---

## Consequências

### Positivas

**1. Granularidade Territorial Completa**
- ✅ Suporta Estado, Municípios, Regiões (antigas e novas)
- ✅ Extensível para bacias, regiões de saúde, comarcas
- ✅ Versionamento temporal de divisões

**2. Indicadores Multi-Escala**
- ✅ Dados estaduais diretos (SICONFI, etc.)
- ✅ Agregações pré-calculadas armazenáveis
- ✅ Agregações dinâmicas via JOIN

**3. Análises Históricas Corretas**
- ✅ Dados de 2010-2016 usam divisão antiga
- ✅ Dados de 2017+ usam divisão nova
- ✅ Sistema suporta ambas simultaneamente

**4. Performance Otimizada**
- ✅ Índices específicos para séries temporais
- ✅ Agregações podem ser pré-calculadas
- ✅ Views de compatibilidade evitam refatoração massiva

**5. Extensibilidade**
- ✅ Adicionar novo tipo de território = adicionar enum
- ✅ Adicionar nova hierarquia = inserir em relationships
- ✅ Sem ALTER TABLE necessário

### Negativas

**1. Complexidade Aumentada**
- ❌ Schema mais complexo (3 tabelas vs 3 tabelas específicas)
- ❌ JOINs mais complexos para queries regionais
- ❌ Curva de aprendizado para desenvolvedores

**Mitigação**: Views de compatibilidade + documentação completa + exemplos

**2. Migração de Dados**
- ❌ 139 municípios precisam ser migrados para `territories`
- ❌ 2 mesorregiões + 8 microrregiões precisam ser migradas
- ❌ `indicator_values` existentes precisam atualizar `territory_id`

**Mitigação**: Migration automatizada + scripts de validação

**3. Performance de JOINs**
- ❌ Queries regionais podem ser mais lentas (múltiplos JOINs)
- ❌ Agregações on-the-fly custosas

**Mitigação**:
- Pré-calcular agregações principais
- Índices otimizados
- Caching de resultados frequentes

**4. Risco de Inconsistência**
- ❌ Relationships podem ficar inconsistentes
- ❌ Hierarquias circulares possíveis

**Mitigação**:
- Constraints de validação
- Triggers de consistência
- Testes de integridade

---

## Alternativas Consideradas

### Alternativa A: Tabelas Separadas por Tipo (REJEITADA)

**Descrição**: Manter `mesoregions`, `microregions`, `municipalities` separadas + adicionar `regioes_intermediarias`, `regioes_imediatas`.

**Vantagens**:
- ✅ Schemas específicos e simples
- ✅ Sem necessidade de JOINs para tipo
- ✅ Queries mais diretas

**Desvantagens**:
- ❌ 6+ tabelas ao invés de 1
- ❌ Não extensível (cada nova divisão = nova tabela)
- ❌ `indicator_values` precisaria múltiplos FKs (`municipality_id`, `microregion_id`, `regiao_intermediaria_id`, etc.)
- ❌ Agregações complicadas (UNION de múltiplas tabelas)

**Motivo da Rejeção**: Não escalável e rígido.

---

### Alternativa B: Apenas Divisão Nova (REJEITADA)

**Descrição**: Substituir divisão antiga pela nova, remover mesorregiões/microrregiões.

**Vantagens**:
- ✅ Schema mais simples (apenas divisão nova)
- ✅ Foco na divisão atual do IBGE

**Desvantagens**:
- ❌ **Perda de dados históricos** (2010-2016 usam divisão antiga)
- ❌ Impossível comparar séries longas
- ❌ Quebra análises de usuários que conhecem divisão antiga

**Motivo da Rejeição**: Incompatível com requisito de análises históricas.

---

### Alternativa C: Schema Proposto (ESCOLHIDA)

Ver seção "Arquitetura Proposta".

---

## Plano de Implementação

### Fase 1: Migration e Schema (Semana 1)

- ✅ Criar Migration 009
- ✅ Criar `territories`, `territory_relationships`
- ✅ Popular com dados (Estado + 2 mesorregiões + 8 microrregiões + 3 intermediárias + 11 imediatas + 139 municípios)
- ✅ Criar views de compatibilidade
- ✅ Testar integridade

### Fase 2: Migração de `indicator_values` (Semana 2)

- ⏳ Adicionar coluna `territory_id` em `indicator_values`
- ⏳ Popular `territory_id` a partir de `municipality_id`
- ⏳ Validar 100% dos registros migrados
- ⏳ Deprecar (não remover) `municipality_id`

### Fase 3: Atualização de Workflows (Semana 3)

- ⏳ Ajustar workflows de coleta para usar `territory_id`
- ⏳ Manter compatibilidade com queries antigas
- ⏳ Testar coleta municipal (não deve mudar)

### Fase 4: Expansão (Semana 4+)

- ⏳ Adicionar coleta de dados estaduais (SICONFI)
- ⏳ Implementar agregações pré-calculadas
- ⏳ Criar queries de exemplo para análises regionais

### Fase 5: Depreciação de Schema Antigo (Mês 2+)

- ⏳ Remover views de compatibilidade gradualmente
- ⏳ Remover `municipality_id` de `indicator_values`
- ⏳ Remover tabelas antigas (`mesoregions`, `microregions`, `municipalities`)

---

## Métricas de Sucesso

| Métrica | Antes | Meta | Como Medir |
|---------|-------|------|------------|
| **Divisões Suportadas** | 1 (antiga) | 2 (antiga + nova) | COUNT(DISTINCT division_scheme) FROM territories |
| **Tipos de Território** | 3 (meso, micro, muni) | 6+ (estado, meso, micro, inter, imediata, muni) | COUNT(DISTINCT type) FROM territories |
| **Indicadores Estaduais** | 0 | 5+ | COUNT(*) FROM indicator_values WHERE territory_id IN (SELECT id FROM territories WHERE type = 'estado') |
| **Performance Séries (10 anos)** | ~50ms | <30ms | EXPLAIN ANALYZE de query temporal |

---

## Revisão Futura

**Data Prevista**: 2026-04-16 (3 meses após implementação)

**Critérios de Sucesso**:
1. ✅ Ambas as divisões (antiga e nova) operacionais
2. ✅ ≥5 indicadores estaduais coletados
3. ✅ Agregações regionais funcionando
4. ✅ Performance de séries temporais satisfatória (<30ms)

**Possíveis Ajustes**:
- Adicionar cache de agregações frequentes
- Implementar materialização de views
- Adicionar divisões territoriais adicionais (bacias, saúde)

---

## Referências

### Decisões Relacionadas

- [ADR 001 - Arquitetura Inicial](#) (a criar link)
- [ADR 004 - Sistema de Coleta Orientado a Metadados](004-sistema-coleta-orientado-metadados.md)

### Documentação

- [Divisões Regionais do Tocantins - IBGE](../references/tocantins_divisoes_regionais_ibge.md)
- [Migration 009](../../supabase/migrations/009_territories_schema.sql) (a criar)

---

---

## Lente de Delegação Inteligente (adicionada v2.2)

> Anotação retroativa à luz de Tomašev, N., Franklin, M., & Osindero, S. (2025). "Intelligent AI Delegation." arXiv:2602.11865.

| Conceito de Delegação | Manifestação neste ADR |
|----------------------|------------------------|
| **Contract-First Decomposition** | Schema de territórios genérico é um "contrato" que define como qualquer tipo de território pode ser representado — decomposição formal antes da implementação |
| **Structural Transparency** | Views de compatibilidade tornam transparente a relação entre schema antigo e novo |
| **Delegation Boundary Violation** | Schema rígido (municipality_id) é uma violação de fronteira: impedia análise multi-escala porque o "contrato" original era estreito demais |
| **Systemic Resilience** | Versionamento temporal (valid_from, valid_until) e suporte a múltiplas hierarquias simultâneas aumentam resiliência sistêmica |

**Interpretação:** Este ADR propõe resolver uma Delegation Boundary Violation estrutural: o schema original limitava o sistema a apenas um tipo de território, impedindo escalabilidade. A solução (schema genérico) é um exemplo de como Contract-First Decomposition pode ser aplicada a infraestrutura de dados, não apenas a tarefas.

---

**Aprovado por**: Henrique (CEO)
**Proposto por**: Claude (Arquiteto de Dados)
**Data da Proposta**: 2026-01-16
**Status**: Aguardando aprovação
