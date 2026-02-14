# ADR 006: MVP com Dados Estaticos do Caderno Tocantins 2026

**Status**: Aceito
**Data**: 2026-02-14
**Decisor**: CEO (Henrique) + CTO (Claude)
**Contexto**: Pivot estrategico para deploy do dashboard antes da campanha
**Origem**: Centralizado de `tocantins-integrado/docs/adr/006-mvp-dados-caderno-estatico.md`

---

## Contexto

O dashboard tocantins-integrado (Camada 1) estava 90% completo, mas todos os componentes usavam dados mock hardcoded. A integracao completa exigiria:

1. Executar migracoes Supabase
2. Rodar pipeline de 8 coletores de dados
3. Popular banco com 139 municipios
4. Integrar frontend com API backend

Ao mesmo tempo, o `caderno-tocantins-2026` continha 139 fichas municipais (formato Markdown V2) com dados estruturados cobrindo 8 dimensoes tematicas, produzidos no Ciclo 3.

Uma campanha eleitoral demandou funcionalidade rapida do dashboard.

---

## Decisao

**Alimentar o MVP do dashboard com dados parseados das fichas do Caderno Tocantins 2026**, eliminando dependencia do backend/banco de dados para a primeira versao publica.

### Implementacao:

1. **Parser script** (`scripts/parse-caderno.cjs`): Extrai dados estruturados de 139 fichas markdown
2. **JSON estatico** (`public/data/municipalities.json`): ~1.9 MB com todos os dados parseados
3. **Camada de dados** (`lib/caderno-data.ts` + `hooks/useCadernoData.ts`): React hook com acesso tipado
4. **Componentes reescritos**: 6 tabs + TerritorySelector usam dados reais em vez de mocks
5. **Deploy**: Replit com Next.js (sem necessidade de Supabase/Express para MVP)

---

## Alternativas Consideradas

### A1: Completar pipeline backend (descartada)

- **Pros**: Dados sempre atualizados, arquitetura original
- **Contras**: 15-20 horas adicionais, dependencias de APIs externas, complexidade de deploy
- **Motivo da rejeicao**: Timeline da campanha incompativel

### A2: SSG (Static Site Generation) com fetch no build (descartada)

- **Pros**: Dados atualizados por build
- **Contras**: Necessidade de configurar APIs e credenciais
- **Motivo da rejeicao**: Mesma complexidade da A1 para configurar fontes

### A3: Dados estaticos do caderno (aceita)

- **Pros**: Dados ja existem e foram validados, implementacao rapida (~4 horas), zero dependencias externas
- **Contras**: Dados nao atualizam automaticamente; requer re-parse manual para mudancas
- **Motivo da aceitacao**: Equilibrio velocidade-qualidade; dados do caderno sao oficiais e recentes

---

## Consequencias

### Positivas

- Dashboard funcional com dados reais de 139 municipios
- Testa hipotese H4.4: "dados do caderno alimentam Camada 1 com perda < 10%"
- Elimina dependencias de infraestrutura (Supabase, n8n, Express) para MVP
- Deploy simplificado (Next.js estatico)

### Negativas

- Dados nao atualizam automaticamente (re-parse manual necessario)
- Cobertura de indicadores limitada ao que esta nas fichas (~60-80 por municipio)
- Desafios de precisao na extracao de valores numericos do markdown

### Neutras

- Backend e pipeline de coleta permanecem intactos para uso futuro (Camada 1 completa)
- Transicao para dados dinamicos pode ocorrer incrementalmente

---

## Dados de Qualidade do Parse

| Metrica | Resultado |
|---------|-----------|
| Municipios parseados | 139/139 |
| Com codigo IBGE | 139/139 |
| Com populacao | 137/139 |
| Com IDHM | 139/139 |
| Com PIB per capita | 138/139 |
| Com alertas | 139/139 |

---

## Relacao com Pesquisa

- **OE1** (Pesquisa-acao): O pivot e dado de pesquisa — PA responde a demandas do contexto
- **OE2** (Transformacoes): Dashboard funcional permite coleta de dados de uso real
- **H4.4**: Teste empirico direto — dados do caderno alimentam Camada 1
- **Ciclo PA**: Reordenamento das fases 4A-4D conforme plano adaptado

---

## Lente de Delegacao (Tomasev et al., 2025)

- **Tipo de delegacao**: Delegacao tecnica completa (parser e integracao pela IA)
- **Supervisao humana**: Decisao estrategica (pivot) pelo pesquisador; validacao dos dados parseados contra fichas originais
- **Risco de autonomia**: Baixo — dados de entrada sao artefatos pre-validados
- **Transparencia**: Codigo do parser e integracao totalmente documentados e auditaveis

---

**Proximos passos**: Deploy no Replit, coletar metricas de uso, validar com usuarios da campanha.
