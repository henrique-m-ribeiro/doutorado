# ADR 003: Simplificar Workflow de Coleta IBGE para MVP

**Status**: Aceito
**Data**: 2026-01-15
**Decisor**: CEO (Henrique) + CTO (Claude)
**Contexto**: Implementação dos agentes de coleta de dados no n8n

---

## Contexto

Durante a implementação dos workflows de coleta de dados do n8n, identificamos uma **discrepância entre o schema do banco de dados em produção (Supabase) e as dependências dos workflows**:

### Situação Encontrada

**Workflows originais** (`data-collection-ibge.json`):
- Dependem de 3 tabelas auxiliares: `data_sources`, `collection_jobs`, `collection_logs`
- Total de 12 nós no workflow
- Complexidade alta com logging e rastreamento completo

**Schema em produção** (Supabase):
- ✅ Tabelas principais existem: `municipalities`, `indicator_definitions`, `indicator_values`
- ❌ Tabelas de coleta NÃO existem: `data_sources`, `collection_jobs`, `collection_logs`

**Migration local** (`007_data_collection.sql`):
- ✅ Define as 3 tabelas de coleta
- ⚠️ Usa UUID como tipo de ID
- ❌ Não foi executada no Supabase em produção

**Incompatibilidade de tipos**:
- Migration local usa `UUID` para IDs
- Workflow espera `SERIAL (INTEGER)` para IDs

---

## Decisão

**Optamos por criar uma versão simplificada do workflow (`data-collection-ibge-simplified.json`) que funciona SEM as tabelas auxiliares de coleta.**

### Mudanças Implementadas

| Aspecto | Original | Simplificado |
|---------|----------|--------------|
| **Nós totais** | 12 | 10 |
| **Tabelas usadas** | 6 (municipalities, indicator_definitions, indicator_values, data_sources, collection_jobs, collection_logs) | 3 (municipalities, indicator_definitions, indicator_values) |
| **Logging** | Banco de dados (collection_logs) | Console do n8n |
| **Rastreamento de jobs** | Banco de dados (collection_jobs) | Executions do n8n |
| **Configuração de fontes** | Banco de dados (data_sources) | Hardcoded no workflow |
| **Complexidade** | Alta | Média |
| **Setup requerido** | SQL para criar 3 tabelas + seeds | SQL para criar 2 indicadores |

### Nós Removidos

1. **Buscar Config Fonte** (SELECT em `data_sources`)
2. **Criar Job de Coleta** (INSERT em `collection_jobs`)
3. **Registrar Progresso** (INSERT em `collection_logs`)
4. **Finalizar Job** (UPDATE em `collection_jobs`)
5. **Atualizar Fonte** (UPDATE em `data_sources`)

### Nós Mantidos/Ajustados

1. ✅ **Agendamento Mensal** (Schedule Trigger)
2. ✅ **Buscar Municípios** (SELECT em `municipalities`)
3. ✅ **Processar em Lotes** (Split in Batches)
4. ✅ **Buscar PIB Municipal** (HTTP Request - IBGE API)
5. ✅ **Buscar População** (HTTP Request - IBGE API)
6. ✅ **Processar Dados** (Code node - ajustado para logging via console)
7. ✅ **Inserir/Atualizar Indicadores** (Postgres upsert em `indicator_values`)
8. ✅ **Verificar Sucesso** (If node)
9. ✅ **Consolidar Estatísticas** (Code node - novo)

---

## Alternativas Consideradas

### Opção A: Simplificar Workflow (ESCOLHIDA)

**Vantagens**:
- ✅ Funciona imediatamente com schema atual
- ✅ Menos pontos de falha
- ✅ Alinhado com princípio "Limited Scope" do IA Collab OS
- ✅ Logging nativo do n8n é suficiente para MVP
- ✅ Mais fácil de debugar e manter

**Desvantagens**:
- ❌ Menos rastreamento histórico no banco
- ❌ Configuração hardcoded (menos flexível)
- ❌ Estatísticas de coleta não ficam persistidas

---

### Opção B: Adicionar Tabelas de Coleta

**Vantagens**:
- ✅ Mantém arquitetura completa do workflow original
- ✅ Histórico de coletas no banco de dados
- ✅ Configuração centralizada de fontes
- ✅ Estatísticas e métricas persistidas

**Desvantagens**:
- ❌ Requer executar migration adicional
- ❌ Incompatibilidade de tipos (UUID vs INTEGER) a resolver
- ❌ Complexidade adicional para MVP
- ❌ Mais pontos de falha
- ❌ Over-engineering para estágio atual

---

## Consequências

### Positivas

1. **Time to Market**: Workflow funcional em minutos, não horas
2. **Simplicidade**: Apenas 3 tabelas principais necessárias
3. **Debugging**: Logs no console do n8n são mais acessíveis
4. **Manutenção**: Menos código SQL para manter
5. **Evolução**: Fácil adicionar tabelas de coleta depois quando necessário

### Negativas

1. **Histórico limitado**: Dependente de executions do n8n (retenção de 30-90 dias)
2. **Estatísticas**: Queries para métricas de coleta são mais complexas
3. **Auditoria**: Menos rastreabilidade de quando/como dados foram coletados
4. **Configuração**: Mudanças em URLs/parâmetros requerem editar workflow

### Mitigações

1. **Histórico**: n8n Cloud tem retenção de 90 dias de executions
2. **Estatísticas**: Podem ser calculadas a partir de `indicator_values.created_at` e `updated_at`
3. **Auditoria**: Campo `notes` em `indicator_values` registra origem dos dados
4. **Configuração**: Workflow é versionado no Git para rastreamento de mudanças

---

## Implementação

### Arquivos Criados

1. **`n8n/workflows/data-collection-ibge-simplified.json`**
   - Workflow simplificado (10 nós)
   - Funciona com schema atual
   - Logging via console

2. **`n8n/workflows/setup-ibge-indicators.sql`**
   - Cria indicadores `ECON_PIB_TOTAL` e `SOCIAL_POPULACAO`
   - Cria categorias necessárias se não existirem
   - Idempotente (pode executar múltiplas vezes)

3. **`n8n/workflows/GUIA-COLETA-IBGE.md`**
   - Guia completo de configuração
   - Troubleshooting
   - Queries de monitoramento

4. **`docs/adr/003-simplificar-workflow-coleta-ibge.md`** (este arquivo)
   - Documentação da decisão técnica

### Próximos Passos

1. **Imediato**: Executar setup e testar workflow simplificado
2. **Curto prazo** (1-2 sprints):
   - Adicionar mais indicadores IBGE (IDEB, IDH, etc.)
   - Criar workflows para outras fontes (INEP, DataSUS)
3. **Médio prazo** (3-6 sprints):
   - Avaliar se logging/rastreamento via banco se tornou necessário
   - Se sim, executar migration `007_data_collection.sql` e migrar para workflow completo
4. **Longo prazo**:
   - Implementar data quality checks
   - Criar alertas de falha de coleta
   - Dashboard de monitoramento de coletas

---

## Referências

- **Workflow original**: `n8n/workflows/data-collection-ibge.json`
- **Migration não executada**: `src/database/migrations/007_data_collection.sql`
- **Schema em produção**: Query fornecida pelo CEO (27 tabelas)
- **Princípio aplicado**: "Limited Scope" do IA Collab OS Framework

---

## Notas de Revisão

- **2026-01-15**: Decisão inicial (CTO + CEO via análise)
- Próxima revisão sugerida: Após 3 meses de uso em produção (2026-04-15)

---

**Aprovado por**: Henrique (CEO)
**Implementado por**: Claude (CTO)
