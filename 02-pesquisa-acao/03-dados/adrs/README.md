# Architecture Decision Records (ADRs)

Registros formais de decisoes arquiteturais do sistema tocantins-integrado. Seguem o formato ADR padrao: contexto, decisao, alternativas consideradas, consequencias. ADRs 001-005 produzidos durante o Ciclo 2 (Jan 2026). ADR-006 produzido no pivot para MVP (Fev 2026).

## Indice de ADRs

| # | Titulo | Decisao Principal |
|---|--------|-------------------|
| [ADR-001](./ADR-001-metodologia-ia-distribuida.md) | Metodologia IA Distribuida | Usar multiplos modelos de IA em papeis complementares |
| [ADR-002](./ADR-002-dados-apenas-oficiais.md) | Dados Apenas Oficiais | Restringir fontes a dados oficiais (motivado pelo piloto Palmas: 50.6% estimados) |
| [ADR-003](./ADR-003-simplificar-workflow-coleta-ibge.md) | Simplificar Workflow Coleta IBGE | Simplificar pipeline de coleta de dados do IBGE |
| [ADR-004](./ADR-004-sistema-coleta-orientado-metadados.md) | Sistema Orientado a Metadados | Coleta guiada por metadados, nao por dados brutos |
| [ADR-005](./ADR-005-granularidade-territorial-temporal.md) | Granularidade Territorial-Temporal | Definir niveis de analise: municipal, microrregional, estadual |
| [ADR-006](./ADR-006-mvp-dados-caderno-estatico.md) | MVP com Dados Estaticos do Caderno | Alimentar dashboard com dados parseados das fichas municipais, eliminando dependencia do backend |

## Origem

ADRs 001-005: Centralizados a partir de `tocantins-integrado/docs/01-research/decisions/`.
ADR-006: Centralizado a partir de `tocantins-integrado/docs/adr/006-mvp-dados-caderno-estatico.md`.

## Relevancia para a Tese

- **OE1**: Evidencia de processo decisorio formal em pesquisa-acao
- **OE4**: Registro de alternativas e justificativas como padrao de colaboracao H-IA
- ADRs documentam decisoes com contexto, alternativas e consequencias — pratica de governanca emergente

---

*Ultima atualizacao: 2026-02-14*
