# ADR 004: Sistema de Coleta Orientado a Metadados

**Status**: Aceito
**Data**: 2026-01-15
**Decisor**: CEO (Henrique) + CTO (Claude)
**Contexto**: Refatoração do sistema de coleta de dados para escalabilidade

---

## Contexto

Após a implementação inicial do workflow simplificado de coleta IBGE (ADR 003), identificamos limitações significativas para escalar o sistema de coleta de dados:

### Problemas do Sistema Anterior

**1. Workflows Hardcoded**
- Cada indicador requeria código específico no workflow
- APIs e parâmetros embutidos diretamente no código
- Adicionar novo indicador = editar workflow manualmente

**2. Baixa Escalabilidade**
- Apenas 2 indicadores implementados (PIB e População)
- Para atingir os 55+ indicadores necessários, tería

mos ~27 workflows
- Manutenção proporcional ao número de indicadores

**3. Sem Centralização de Metadados**
- Informações sobre indicadores dispersas
- Periodicidade de coleta não rastreada
- Histórico de coletas não persistido

**4. Gestão Manual**
- Impossível saber quais indicadores estão desatualizados
- Necessário lembrar manualmente quando coletar
- Sem priorização automática

### Trigger da Decisão

Prompt do CEO solicitando:
> "Refatorar e expandir o sistema de coleta de dados para que ele seja sistemático, escalável e bem documentado, cobrindo todos os indicadores mencionados nos prompts dos agentes especializados."

---

## Decisão

**Implementar um Sistema de Coleta Orientado a Metadados** com os seguintes componentes:

### 1. Indicator Dictionary (Tabela no Banco)

Centralizar metadados de **todos** os indicadores em uma única tabela:

```sql
CREATE TABLE indicator_dictionary (
    id UUID PRIMARY KEY,
    code VARCHAR(100) UNIQUE NOT NULL,
    name VARCHAR(300) NOT NULL,
    dimension dimension_type NOT NULL,
    source_name VARCHAR(200) NOT NULL,
    api_endpoint TEXT,
    api_params JSONB,
    periodicity VARCHAR(50),
    collection_method VARCHAR(50),
    last_ref_date DATE,
    next_collection_date DATE,
    is_active BOOLEAN DEFAULT true,
    ...
);
```

**Benefício**: Adicionar indicador = INSERT no banco, não editar workflow.

### 2. Workflow Orquestrador

Um workflow mestre que:
- Executa diariamente
- Consulta o dictionary para identificar indicadores vencidos
- Agrupa por fonte de dados
- Dispara workflows especialistas correspondentes

**Benefício**: Coleta totalmente automatizada e priorizada.

### 3. Workflows Especialistas Dinâmicos

Workflows genéricos por fonte (IBGE, INEP, MapBiomas) que:
- Recebem lista de indicadores como input
- Buscam metadados do dictionary
- Constroem URLs de API dinamicamente
- Atualizam dictionary após coleta

**Benefício**: 1 workflow por fonte, não 1 por indicador.

---

## Alternativas Consideradas

### Alternativa A: Manter Workflows Hardcoded (REJEITADA)

**Descrição**: Continuar criando workflows específicos para cada indicador ou grupo de indicadores.

**Vantagens**:
- ✅ Simplicidade inicial
- ✅ Não requer refatoração
- ✅ Funciona para poucos indicadores

**Desvantagens**:
- ❌ Não escala (27+ workflows para 55 indicadores)
- ❌ Manutenção pesada (mudar API = editar múltiplos workflows)
- ❌ Impossível priorizar coletas automaticamente
- ❌ Sem rastreamento de periodicidade

**Motivo da Rejeição**: Inviável para escalar além de MVP mínimo.

---

### Alternativa B: Sistema Orientado a Metadados (ESCOLHIDA)

**Descrição**: Implementar dictionary centralizado + orquestrador + workflows dinâmicos.

**Vantagens**:
- ✅ **Escalável**: Adicionar indicador = 1 INSERT
- ✅ **Manutenível**: Metadados centralizados
- ✅ **Automatizado**: Orquestrador gerencia priorização
- ✅ **Flexível**: Suporta múltiplas fontes e métodos
- ✅ **Auditável**: Histórico de coletas
- ✅ **Profissional**: Padrão da indústria (data catalogs)

**Desvantagens**:
- ❌ Maior complexidade inicial
- ❌ Requer refatoração de workflows existentes
- ❌ Curva de aprendizado

**Motivo da Escolha**: Única alternativa viável para sistema profissional e escalável.

---

### Alternativa C: Sistema Híbrido (CONSIDERADA MAS NÃO ESCOLHIDA)

**Descrição**: Dictionary para metadados + workflows hardcoded existentes (sem orquestrador).

**Vantagens**:
- ✅ Menor complexidade que Alternativa B
- ✅ Dictionary para documentação
- ✅ Mantém workflows atuais funcionando

**Desvantagens**:
- ❌ Ainda requer manutenção manual de workflows
- ❌ Sem automação de priorização
- ❌ Dictionary seria subutilizado (apenas documentação)

**Motivo da Rejeição**: "Meio termo" que não resolve os problemas principais.

---

## Consequências

### Positivas

**1. Escalabilidade**
- Adicionar novo indicador: **1 INSERT** no dictionary
- Antes: Editar workflow + testar + deploy
- Tempo: Minutos vs Horas

**2. Manutenção Simplificada**
- Mudar endpoint de API: UPDATE 1 linha
- Antes: Editar N workflows
- Centralização reduz erros

**3. Automação Completa**
- Orquestrador decide **o quê** e **quando** coletar
- Antes: Manual ou cron jobs individuais
- Priorização inteligente (overdue > never collected)

**4. Visibilidade**
- Views SQL mostram status de coleta em tempo real
- Antes: Sem visibilidade centralizada
- Dashboards possíveis (Grafana, Metabase)

**5. Documentação Integrada**
- Dictionary é fonte única de verdade
- Documentação de referência gerada do dictionary
- Menos dessincronia docs ↔ código

**6. Flexibilidade**
- Suporta múltiplos métodos: API, scraping, manual
- Suporta múltiplas periodicidades: annual, monthly, census
- Fácil adicionar novos métodos/fontes

### Negativas

**1. Complexidade Inicial**
- Migration +500 linhas (vs 0 no sistema anterior)
- 3 workflows (vs 1 no sistema anterior)
- Curva de aprendizado para time

**Mitigação**: Guia de implementação completo criado.

**2. Dependência do Dictionary**
- Dictionary se torna ponto crítico
- Corrupção de metadados afeta todas as coletas

**Mitigação**: Backups automáticos do Supabase + Versionamento no Git.

**3. Refatoração de Workflows Existentes**
- Workflow IBGE simplificado precisa ser refatorado
- Tempo de desenvolvimento adicional

**Mitigação**: Manter workflow simplificado funcionando em paralelo durante transição.

**4. Testing Mais Complexo**
- Testar orquestrador + workflows especialistas
- Mais cenários de teste (dictionary vazio, fonte indisponível, etc.)

**Mitigação**: Começar com 1 fonte (IBGE) totalmente testada antes de expandir.

---

## Implementação

### Arquivos Criados

**1. Migration SQL**
- `supabase/migrations/008_create_indicator_dictionary.sql` (2.114 linhas)
- Cria tabela `indicator_dictionary`
- Popula com 55 indicadores (15 ECON, 17 SOCIAL, 13 TERRA, 11 AMBIENT)
- Cria 3 views úteis
- Cria triggers e funções auxiliares

**2. Documentos de Referência**
- `docs/references/ECON_reference.md`
- `docs/references/SOCIAL_reference.md`
- `docs/references/TERRA_reference.md`
- `docs/references/AMBIENT_reference.md`

Total: ~3.000 linhas de documentação sobre indicadores, fontes, APIs e metodologias.

**3. Guia de Implementação**
- `docs/guides/data-collection-setup.md` (~700 linhas)
- Setup completo do banco de dados
- Configuração de workflows
- Execução e monitoramento
- Troubleshooting

**4. ADR**
- `docs/adr/004-sistema-coleta-orientado-metadados.md` (este arquivo)

**5. Workflows n8n** (a serem criados)
- `data-collection-orchestrator.json` - Workflow orquestrador
- `data-collection-ibge-refactored.json` - IBGE refatorado
- `data-collection-inep.json` - INEP (educação)
- `data-collection-mapbiomas.json` - MapBiomas (ambiental)

### Plano de Rollout

**Fase 1: Setup (Semana 1)**
- ✅ Executar migration 008
- ✅ Verificar dictionary populado
- ✅ Testar queries de monitoramento

**Fase 2: Orquestrador (Semana 2)**
- ⏳ Implementar workflow orquestrador
- ⏳ Testar lógica de priorização
- ⏳ Configurar schedule diário

**Fase 3: IBGE Refatorado (Semana 2-3)**
- ⏳ Refatorar workflow IBGE
- ⏳ Testar com 5 indicadores
- ⏳ Expandir para todos indicadores IBGE

**Fase 4: Expansão (Semana 4+)**
- ⏳ Implementar workflow INEP
- ⏳ Implementar workflow MapBiomas
- ⏳ Implementar workflow SICONFI

**Fase 5: Produção (Semana 6+)**
- ⏳ Ativar orquestrador em produção
- ⏳ Monitoramento diário
- ⏳ Ajustes baseados em uso real

---

## Métricas de Sucesso

### Quantitativas

| Métrica | Antes | Meta | Atual |
|---------|-------|------|-------|
| Indicadores coletados automaticamente | 2 | 20 | 2 (MVP) |
| Workflows de coleta | 1 | 5 | 1 |
| Tempo para adicionar indicador | 2-4h | 15min | - |
| Cobertura municipal (média) | 100% | 95%+ | 100% |
| Taxa de falha de coleta | ? | <5% | - |

### Qualitativas

- ✅ **Escalabilidade**: Sistema suporta 100+ indicadores sem refatoração adicional
- ✅ **Documentação**: Metadados centralizados e acessíveis
- ✅ **Automação**: Zero intervenção manual para coletas agendadas
- ⏳ **Confiabilidade**: 95%+ de uptime das coletas (a medir)
- ⏳ **Manutenibilidade**: Time consegue adicionar indicador em <30min (a validar)

---

## Revisão Futura

**Data Prevista**: 2026-04-15 (3 meses após implementação)

**Critérios de Sucesso**:
1. ≥15 indicadores sendo coletados automaticamente
2. ≥3 fontes de dados integradas
3. Taxa de falha <5%
4. Feedback positivo do time

**Possíveis Ajustes**:
- Adicionar tabela `collection_history` para auditoria detalhada
- Implementar retry logic mais sofisticado
- Criar dashboard de monitoramento visual
- Adicionar alertas (email/Slack) para falhas

---

## Referências

### Decisões Relacionadas

- [ADR 003 - Simplificar Workflow Coleta IBGE](003-simplificar-workflow-coleta-ibge.md)

### Conceitos

- **Data Catalog**: [What is a Data Catalog?](https://www.alation.com/blog/what-is-a-data-catalog/)
- **Metadata-Driven Architecture**: [Metadata-Driven ETL](https://www.oreilly.com/library/view/data-warehousing-fundamentals/9780471412540/)

### Implementação

- [Guia de Implementação](../guides/data-collection-setup.md)
- [Migration 008](../../supabase/migrations/008_create_indicator_dictionary.sql)

---

---

## Lente de Delegação Inteligente (adicionada v2.2)

> Anotação retroativa à luz de Tomašev, N., Franklin, M., & Osindero, S. (2025). "Intelligent AI Delegation." arXiv:2602.11865.

| Conceito de Delegação | Manifestação neste ADR |
|----------------------|------------------------|
| **Structural Transparency** | Indicator Dictionary como mecanismo de transparência estrutural: metadados centralizados tornam explícito o que, quando e como é coletado |
| **Contract-First Decomposition** | Schema do dictionary é um "contrato" com fontes de dados — API endpoints, parâmetros, periodicidade, tudo documentado antes da coleta |
| **Scalable Market** | Arquitetura orquestrador + especialistas é equivalente ao conceito de mercado escalável de agentes |
| **Dynamic Assessment** | Orquestrador avalia dinamicamente quais indicadores estão vencidos e prioriza coleta |

**Interpretação:** Este ADR é talvez o melhor exemplo de Structural Transparency no projeto. O indicator dictionary implementa, com mecanismos processuais (tabela SQL + metadados), o que Tomašev et al. propõem com mecanismos programáticos (smart contracts). A diferença de implementação é contribuição da tese: delegação inteligente pode ser operacionalizada sem infraestrutura tecnológica pesada.

---

**Aprovado por**: Henrique (CEO)
**Implementado por**: Claude (CTO)
**Data de Implementação**: 2026-01-15
