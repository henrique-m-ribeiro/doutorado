# Ciclo 4: Retomada do Sistema, Audiencias Publicas e Validacao Territorial

**Periodo previsto:** Fevereiro — Dezembro 2026 (antecipado de Jul-Dez)
**Status:** Em andamento (Fase 4A' concluida)
**Data de formalizacao:** 12 de Fevereiro de 2026
**Ultima atualizacao:** 14 de Fevereiro de 2026 (v2.0 — pivot MVP)
**Autor:** Henrique M. Ribeiro

---

## NOTA DE VERSAO v2.0 — Pivot MVP (14 Fev 2026)

> **Decisao estrategica (ADR-006):** A demanda urgente da campanha eleitoral motivou a antecipacao da Fase 4D (Retomada do Sistema) para o inicio do ciclo, antes da fundamentacao teorica (Fase 4A) e das audiencias (Fase 4B). O MVP do dashboard tocantins-integrado foi implementado com dados estaticos parseados das fichas do caderno-tocantins-2026, eliminando dependencias de backend/Supabase. A hipotese H4.4 foi parcialmente validada: 139/139 municipios parseados, 137/139 com populacao, 139/139 com IDHM.
>
> **Implicacao para PA:** O pivot e, em si, dado de pesquisa — demonstra que a pesquisa-acao responde adaptativamente a demandas do contexto (PS1). A reordenacao das fases preserva todos os objetivos e hipoteses, alterando apenas a sequencia.
>
> **Referencia:** `02-pesquisa-acao/03-dados/adrs/ADR-006-mvp-dados-caderno-estatico.md`

---

## 1. Pergunta-Guia

> Como sistemas de inteligencia territorial mediados por IA podem ser validados por atores territoriais, e quais transformacoes emergem quando esses sistemas sao confrontados com a realidade da gestao publica?

### Perguntas de pesquisa enderecadas
- **PS2** (Fundamentacao teorica de IT) — revisao e aprofundamento
- **PS3** (Transformacoes na gestao publica) — observacao empirica
- **PS4** (Padroes de colaboracao H-IA) — sistematizacao
- **PS5** (Etica, governanca, participacao democratica) — via audiencias publicas

### Objetivos especificos vinculados
- **OE2** (Fundamentacao teorica) — Revisao sistematica de IT
- **OE3** (Transformacoes na gestao) — Dados primarios de campo
- **OE4** (Padroes H-IA) — Framework teorico
- **OE5** (Etica e governanca) — Audiencias como espaco de debate

---

## 2. Hipoteses Testaveis

### H4.1: Compreensibilidade das fichas
**Enunciado:** Fichas municipais V2 do Caderno Tocantins serao compreendidas por tecnicos municipais sem explicacao adicional, com taxa de compreensao >= 70% em teste com 10+ tecnicos.

**Criterio de sucesso:** >= 70% dos tecnicos classificam as fichas como "compreensivel" ou "muito compreensivel" em escala Likert 5 pontos.

**Criterio de fracasso:** < 50% de compreensao, indicando necessidade de redesign significativo.

**Metodo de coleta:** Questionario estruturado pos-leitura + entrevista semi-estruturada.

### H4.2: Utilidade pratica dos volumes
**Enunciado:** Ao menos 3 dos 9 volumes serao considerados "uteis" ou "muito uteis" para subsidiar decisoes de politica publica por gestores que os utilizarem.

**Criterio de sucesso:** >= 3 volumes avaliados como uteis; >= 1 exemplo documentado de uso em decisao real.

**Criterio de fracasso:** Nenhum gestor relata utilidade pratica; volumes percebidos como "exercicio academico".

**Metodo de coleta:** Entrevistas com gestores apos 30 dias de uso; diario de uso.

### H4.3: Legitimidade via audiencia publica
**Enunciado:** A realizacao de audiencia(s) publica(s) na CDR sobre inteligencia territorial aumentara a percepcao de legitimidade do conceito de IT entre os participantes.

**Criterio de sucesso:** >= 60% dos participantes que responderem a survey pos-audiencia concordam que IT e relevante para desenvolvimento regional.

**Criterio de fracasso:** < 40% de concordancia; resistencia significativa ao conceito.

**Metodo de coleta:** Survey pos-audiencia; transcricao e analise de conteudo das falas.

### H4.4: Retomada tecnica viavel — PARCIALMENTE VALIDADA (Fev 2026)
**Enunciado:** Os dados dos cadernos manuais (139 municipios, 9 dimensoes) podem alimentar a Camada 1 do tocantins-integrado com perda de informacao < 10%.

**Criterio de sucesso:** >= 90% dos dados presentes nas fichas sao capturados no sistema.

**Criterio de fracasso:** Necessidade de reformatacao extensiva (> 30% das fichas) para upload.

**Metodo de coleta:** Log de processamento de dados; contagem de campos mapeados vs. nao mapeados.

**Resultado parcial (14 Fev 2026):** Parser `parse-caderno.cjs` processou 139/139 fichas municipais. Metricas: 139/139 com codigo IBGE, 137/139 com populacao, 139/139 com IDHM, 138/139 com PIB per capita, 139/139 com alertas. Cobertura estimada de ~60-80 indicadores por municipio. Resultado sugere sucesso (perda < 10% para campos estruturados), mas validacao formal completa pendente. Ver ADR-006.

---

## 3. Acoes Planejadas (reordenadas apos pivot — v2.0)

### Fase 4A': Conclusao do MVP e Deploy (Fev-Mar 2026) — ✅ MVP CONCLUIDO

> **Nota v2.0:** Esta fase antecipa e substitui a antiga Fase 4D. Motivada pela urgencia da campanha (ADR-006).

1. ~~Upload de dados dos cadernos para Camada 1~~ → ✅ Parser criado (`parse-caderno.cjs`), JSON estatico gerado
2. ~~Testar pipeline de processamento (H4.4)~~ → ✅ 139/139 municipios parseados com sucesso
3. Reescrita dos 6 componentes do dashboard com dados reais → ✅ Concluido
4. Deploy do MVP (Replit/Next.js) → Em andamento
5. Coleta de feedback de usuarios da campanha → Pendente
6. Avaliar qualidade das analises automatizadas vs. manuais → Pendente (requer usuarios)
7. Iniciar prototipo da Camada 2 (sistema multiagentes) → Adiado para fase posterior

### Fase 4B: Preparacao e Realizacao de Audiencias (quando aprovadas)
1. Preparar proposta formal de audiencia para CDR
2. Elaborar material de apresentacao (slides + **demo funcional do dashboard**)
3. Realizar audiencia(s) publica(s)
4. Transcrever e analisar audiencias
5. Elaborar Relatorio para Senado Federal

### Fase 4C: Validacao Territorial (apos deploy e uso inicial)
1. Selecionar 3 municipios-piloto (diferentes portes e microrregioes)
2. Identificar interlocutores locais (prefeitos, secretarios, tecnicos)
3. Apresentar volumes relevantes **e dashboard** a atores locais
4. Coletar dados via questionario + entrevista semi-estruturada
5. Aplicar teste de compreensibilidade (H4.1)
6. Documentar reacoes, criticas e sugestoes

### Fase 4D: Fundamentacao Teorica (em paralelo)

> **Nota v2.0:** Movida de primeira para quarta fase. Pode ocorrer em paralelo com as fases B e C.

1. Revisao sistematica de literatura sobre IT (15-20 referencias-chave)
2. Fichar textos fundacionais (Girardot, Bertacchini, Masselot)
3. Mapear adaptacoes de IT ao contexto brasileiro
4. Redigir rascunho do Capitulo 2 (Fundamentacao Teorica)

### Fase 4E: Entrevistas e Coleta de Dados (Continua)
1. Realizar 5-8 entrevistas com gestores publicos
2. Realizar 5-8 entrevistas com especialistas em IT/IA
3. Transcrever e codificar entrevistas
4. Iniciar analise tematica (Braun & Clarke)

---

## 4. Metodos de Coleta de Dados

| Metodo | Publico-alvo | Quantidade estimada | Dados coletados |
|--------|-------------|---------------------|----------------|
| Entrevista semi-estruturada | Gestores municipais e estaduais | 8-10 | Percepcoes sobre IT, utilidade, barreiras |
| Entrevista semi-estruturada | Senadores, assessores CDR | 3-5 | Viabilidade politica, interesse institucional |
| Questionario estruturado | Tecnicos municipais (teste fichas) | 10-15 | Compreensibilidade, utilidade percebida |
| Survey pos-audiencia | Participantes audiencia CDR | 20-50 | Percepcao de legitimidade, relevancia |
| Observacao participante | Audiencia publica, reunioes | 3-5 ocasioes | Notas de campo, dinamicas de interacao |
| Grupo focal | Gestores usuarios dos volumes | 1-2 grupos | Experiencias coletivas, padroes |
| Analise documental | Transcricoes, proposicoes | Variavel | Temas, posicionamentos, argumentos |
| Log de sistema | Camada 1 do tocantins-integrado | Continuo | Metricas de processamento e qualidade |

---

## 5. Cronograma com Marcos (revisado v2.0)

| Mes | Marco | Entrega | Status |
|-----|-------|---------|--------|
| Fev 2026 | MVP concluido (Fase 4A') | Dashboard com dados estaticos | ✅ |
| Mar 2026 | Deploy e primeiros usuarios | Dashboard online, feedback inicial | Em andamento |
| Abr-Jun 2026 | Uso na campanha + coleta de feedback | Metricas de uso, percepcoes iniciais | Pendente |
| Jul-Ago 2026 | Fundamentacao teorica (Fase 4D) | 5 fichamentos concluidos | Pendente |
| Ago-Set 2026 | Audiencia CDR (Fase 4B) | Transcricao disponivel | Pendente |
| Set-Nov 2026 | Validacao territorial (Fase 4C) | 3 municipios visitados | Pendente |
| Out-Dez 2026 | Entrevistas (Fase 4E) | 10+ entrevistas transcritas | Pendente |
| Dez 2026 | Encerramento Ciclo 4 | Relatorio do ciclo + reflexao PA | Pendente |

---

## 6. Criterios de Avaliacao do Ciclo

### O ciclo sera bem-sucedido se:
1. ✅ >= 2 das 4 hipoteses confirmadas (ou refutadas com aprendizado documentado)
2. ✅ >= 10 entrevistas realizadas e transcritas
3. ✅ >= 1 audiencia publica realizada
4. ✅ >= 3 municipios-piloto visitados
5. ✅ Camada 1 do sistema alimentada com dados dos cadernos — **CONCLUIDO (Fev 2026, MVP)**
6. ✅ Capitulo 2 (Fundamentacao) em rascunho avancado
7. ✅ Artigo 1 sobre ia-collab-os submetido a periodico

### O ciclo tera falhado se:
1. ❌ Nenhuma audiencia publica realizada (buscar alternativas)
2. ❌ Nenhum ator territorial consultado (comprometeria PS3, PS5)
3. ❌ Nenhuma entrevista realizada (comprometeria evidencias qualitativas)

---

## 7. Riscos e Mitigacoes

| Risco | Probabilidade | Mitigacao |
|-------|--------------|-----------|
| Audiencia CDR nao aprovada | Media | Buscar audiencias alternativas (comissoes estaduais, eventos academicos) |
| Gestores municipais indisponiveis | Media | Contatar via gabinete do senador; oferecer flexibilidade de horario |
| ~~Sistema tocantins-integrado com problemas tecnicos~~ | ~~Baixa-Media~~ | ✅ Mitigado — MVP com dados estaticos implementado (ADR-006) |
| CEP nao aprovado a tempo | Baixa | Iniciar submissao em Mai 2026; usar dados publicos enquanto aguarda |
| Producao (Caderno Vol 2) priorizada sobre pesquisa | Media | Checklist pre-sessao; regra 70/30 producao/reflexao |

---

## 8. Vinculacao com Etapas Anteriores

- **Depende de Etapa 1:** Diarios centralizados (✅ concluida)
- **Depende de Etapa 2:** Este plano e parte da Etapa 2
- **Depende de Etapa 3:** Estrategia de validacao territorial (a desenvolver)
- **Depende de Etapa 5:** Clareza sobre o que e produto vs. dado de pesquisa

---

**Versao:** 2.0
**Data:** 12 de Fevereiro de 2026
**Historico:**
- v1.0 (12 Fev 2026): Plano original com fases 4A-4E sequenciais (Jul-Dez 2026)
- v2.0 (14 Fev 2026): Pivot MVP — Fase 4D antecipada para 4A' (Fev 2026); cronograma revisado; H4.4 parcialmente validada; ADR-006 referenciado
**Proxima revisao:** Apos deploy do MVP e primeiros dados de uso
