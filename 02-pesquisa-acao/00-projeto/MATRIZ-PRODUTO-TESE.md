# Matriz de Dupla Leitura: Produto Pratico x Dado de Pesquisa

**Data:** 12 de Fevereiro de 2026
**Ultima atualizacao:** 14 de Fevereiro de 2026 (v2.2 — pos-pivot MVP tocantins-integrado)
**Objetivo:** Explicitar a relacao entre cada artefato produzido e sua dupla funcao — como produto pratico (para o senador/equipe) e como dado de pesquisa (para a tese de doutorado).
**Referencia:** Plano de Fortalecimento Metodologico, Etapas 4 e 5

> **Nota v2.0:** Esta versao incorpora artefatos descobertos na analise transversal dos 5 repositorios (ver `04-repositorios/ANALISE-TRANSVERSAL-REPOSITORIOS.md`), incluindo o artigo "The Mediator Effect", analises dimensionais, ADRs, piloto Palmas, e prompts de sessao.

> **Nota v2.1:** Secao 2.2 (ia-collab-os) atualizada para refletir fortalecimento v2.2: metricas operacionais, modos de falha, fundamentacao teorica com 12 fontes academicas, integracao de Tomasev et al. (2025) "Intelligent AI Delegation" como referencia primordial, e argumento de convergencia independente.

---

## 1. Principio Orientador

> Todo artefato produzido deve ser lido em duas chaves: como **produto pratico** que resolve um problema real e como **dado de pesquisa** que gera evidencias para a tese. Nenhuma chave substitui a outra.

### O que a dupla leitura resolve:
- Evita que a producao pratica substitua o trabalho academico
- Evita que a reflexao academica paralise a producao pratica
- Cada sessao de trabalho gera valor em ambas as dimensoes
- Explicita lacunas academicas que o produto nao cobre

---

## 2. Matriz de Artefatos

### 2.1 Caderno Tocantins 2026 — 9 Volumes

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Volume 1 (Estadual)** | Panorama geral do Tocantins para equipe de campanha; subsidia discurso e estrategia | Demonstracao de capacidade de analise territorial com IA (OE3); artefato de referencia | Nao demonstra COMO a IA transformou o processo; nao tem feedback de usuarios |
| **Volumes 2-9 (Regionais)** | 8 cadernos por microrregiao para uso em campo; fichas municipais para visitas | Evidencia de producao em escala (213 agentes); base para teste de compreensibilidade com gestores | Producao "de gabinete"; sem validacao territorial; dados nao conferidos contra fontes primarias |
| **Fichas municipais V2** | Perfil de cada municipio (139) para consulta rapida | Padrao replicavel de analise territorial; base para comparacao manual vs. automatizado | Sem voz dos municipios; estrutura definida pelo pesquisador/IA, nao por usuarios |

### 2.2 Framework ia-collab-os — ATUALIZADO v2.2

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Framework v2.2** | Guia para equipes que trabalham com IA; principios de handoff e orquestracao; vocabulario de delegacao inteligente | Contribuicao metodologica central (OE1, OE4); framework de colaboracao H-IA extraido da pratica e fundamentado teoricamente; 12 fontes academicas; convergencia independente com Tomasev et al. (2025) | Sem validacao externa ao contexto Tocantins; artigo nao submetido |
| **13 metricas operacionais** (NOVO v2.2) | KPIs para equipes medirem qualidade da colaboracao H-IA | Baselines empiricos de 4 ciclos PA; criterios quantificaveis para avaliacao (OE1) | Baselines de um unico projeto; sem benchmarks externos |
| **12 modos de falha** (NOVO v2.2) | Taxonomia para prevenir e mitigar falhas em colaboracao H-IA | Evidencia empirica catalogada; cada modo mapeado para conceito de delegacao (OE4) | Sem frequencia estatistica; catalogados por um unico pesquisador |
| **Fundamentacao teorica** (NOVO v2.2) | Conexao com 12 fontes academicas; posicionamento na literatura | Dialogo com Sein et al. (ADR), Dellermann (Hybrid Intelligence), Jarrahi (Symbiosis), Seeber (Machines as Teammates), Tomasev et al. (Delegacao Inteligente) — OE1, OE4 | Revisao de literatura nao exaustiva; falta HCI mais amplo |
| **Convergencia independente** (NOVO v2.2) | Argumento para credibilidade do framework | Pratica bottom-up (ia-collab-os) converge com teoria top-down (Tomasev et al., 2025, Google DeepMind): 21 conceitos mapeados 1:1, 5 pilares validados empiricamente — argumento central para a tese | Convergencia demonstrada, nao testada estatisticamente |
| **Templates (handoff, etc.)** | Ferramentas reutilizaveis para qualquer projeto H-IA | Evidencia de como padronizar colaboracao H-IA (OE4); reframed como Delegation State Transfer | Ainda nao testados fora do contexto Tocantins |
| **Principios (5)** | Diretrizes praticas para equipes; cada principio com "lente de delegacao" | Categorias analiticas com fundamentacao teorica (OE4); cada principio mapeado para conceito de delegacao (Authority Gradient, Boundary Violation, etc.) | Sem validacao por praticantes externos |
| **Skeleton Artigo 1** (NOVO v2.2) | Base para publicacao academica (Jun 2026) | Estrutura completa com 7 secoes, 5 Design Principles, 2 case studies, placeholders substantivos | Rascunho; requer expansao e revisao |

### 2.3 Sistema tocantins-integrado — ATUALIZADO v2.2 (pos-pivot MVP)

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **MVP Dashboard (Camada 1)** | Dashboard funcional com dados reais de 139 municipios; 6 tabs tematicas; pronto para deploy | Demonstracao de como IT baseada em IA pode ser entregue (OE2, OE3); H4.4 parcialmente validada | ✅ Funcional — mas ainda sem usuarios externos; metricas de uso pendentes |
| **Parser parse-caderno.cjs** (NOVO) | Extracao automatica de dados estruturados de fichas markdown | Evidencia de integracao caderno→sistema (H4.4); 139/139 municipios, alta fidelidade | Sem auditoria formal de qualidade; cobertura limitada a indicadores das fichas |
| **ADR-006** (NOVO) | Documentacao da decisao de pivot com alternativas | Dado de PA: resposta adaptativa a demandas do contexto (OE1); lente de delegacao aplicada | Um unico caso; sem comparacao com outras decisoes de pivot |
| **Camada 2 (Multiagentes)** | Analises sob demanda; atualizacao automatica | Dado central para comparacao manual vs. automatizado (OE3) | 0% implementado; adiado para fase posterior |
| **Backend legado** | Codigo preservado (coletores, API, Supabase, n8n) para uso futuro | Registro de arquitetura tecnica completa vs. MVP simplificado (OE6) | Inativo no MVP; transicao incremental planejada |
| **Arquitetura tecnica** | Modelo replicavel para outros estados | Evidencia de design de sistema de IT (OE6); duas estrategias documentadas (dinamica vs. estatica) | Sem validacao tecnica por pares |

### 2.4 Acervo do framework-v6-mvp (Ciclos 0-1) — NOVO v2.0

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Artigo "The Mediator Effect"** (~165 KB, ~40 pag) | Base para publicacao futura; demonstra capacidade analitica | Rascunho cientifico completo com metodos, resultados e discussao (OE1, OE4); pode ser base para Artigo 1 do Ciclo 5 | Nao submetido; nao revisado por pares; escrito com IA (circularidade) |
| **4 analises dimensionais** (~345 KB) | Fundamentacao para cadernos territoriais; subsidio tecnico | Base empirica para fundamentacao de IT (OE2); analises Ambiental, Economica, Social e Territorial do Tocantins | Sem revisao sistematica; analises proprias, nao dialogam com literatura |
| **11+ prompts de sessao** | Tutorial sobre como instruir agentes IA | Evidencia direta de evolucao da capacidade de orquestracao H-IA (PS4, OE4); unica fonte deste tipo | Nao analisados sistematicamente; nao categorizados |
| **Sistema de continuidade** (~52 KB) | Modelo para manter contexto entre sessoes | Precursor do ia-collab-os; evidencia da genese do framework (OE1) | Superado pelo ia-collab-os; valor e historico |
| **21 diarios PA (Ciclos 0-1)** (~550 KB) | Memoria completa do periodo formativo | Dados primarios insubstituiveis da genese do projeto (OE1); 15 sessoes documentadas | Escritos com IA; falta voz do pesquisador; nao centralizados (referenciados) |

### 2.5 ADRs e Governanca (Ciclo 2) — NOVO v2.0

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **5 ADRs** (~46 KB) | Registro de decisoes tecnicas para continuidade | Evidencia de processo decisorio formal (OE1, OE4); alternativas consideradas documentadas | Sem dialogo com literatura de ADR; focados em decisoes tecnicas, nao metodologicas |
| **Governanca (METHODOLOGY + ROLES)** (~20 KB) | Modelo de governanca para equipes H-IA | Formalizacao de roles CEO/CTO/DEV (OE4); governanca emergente da pratica | Sem fundamentacao teorica; sem validacao externa |
| **Piloto Palmas** (~12 KB) | Primeiro teste empirico do sistema | Unico resultado empirico com dados reais (OE3); evidencia de viabilidade | Sem analise formal publicada; um unico caso; sem generalizacao |
| **Handoffs CEO↔CTO↔DEV** (8+ documentos) | Continuidade entre sessoes e agentes | Registro de padroes de handoff (OE4); evidencia de pratica de governanca | Sem categorizacao sistematica |

### 2.6 Documentacao de Processo

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Diarios de PA (23 unicos)** | Memoria institucional; onboarding de novos agentes | Dados primarios sobre reflexividade e aprendizagem (OE1); cobrem Ciclos 0-3.5 inteiros | Escritos com IA (circularidade); falta voz do pesquisador em 1a pessoa |
| **Handoffs (15+)** | Continuidade entre sessoes de trabalho | Registro contemporaneo de decisoes e estado (OE1, OE4) | Foco em "o que foi feito", pouco "por que" e "o que significa" |
| **Relato de orquestracao** | Tutorial para orquestracao de agentes | Dado unico sobre 213 lancamentos de agentes (OE4) | Baseado em um unico transcript; sem triangulacao |
| **Caminhos percorridos** (3 docs, ~43 KB) | Narrativa de processo para equipe | Dados para capitulo metodologico da tese (OE1) | Sem distanciamento critico |
| **Relatorio de revisao de decisoes** (~54 KB) | Revisao critica de todas as decisoes | Meta-reflexao sobre o processo decisorio (OE1, OE4) | Documento unico; sem comparacao |
| **Cronologia dos repos** | Referencia para entender relacoes entre artefatos | Narrativa historico-continuativa da pesquisa (validacao Heikkinen) | Falta distanciamento critico; muito descritivo |
| **Analise transversal dos 5 repos** | Mapa completo do ecossistema | Inventario de evidencias; base para triangulacao (OE1) | Produzida com IA; dados quantitativos nao verificados manualmente |

---

## 3. Mapeamento: OEs x Evidencias Existentes x Lacunas

| OE | Evidencias que JA existem | O que FALTA para sustentar na tese |
|----|--------------------------|-----------------------------------|
| **OE1** (Framework PA para IA) | ia-collab-os v1.0; **23 diarios PA** (Ciclos 0-3.5); **5 ADRs**; sistema de continuidade (precursor, ~52 KB); governanca (METHODOLOGY+ROLES, 20 KB); protocolo de registro; mapeamento ciclos-evidencias; artigo "The Mediator Effect" (rascunho) | Metricas operacionais para os 5 principios; validacao externa; dialogo com literatura de ADR (Sein et al.) |
| **OE2** (Fundamentacao IT) | **4 analises dimensionais** (~345 KB: Ambiental, Economica, Social, Territorial); revisao incipiente no projeto v2.0; secao 4.1 do projeto | Revisao sistematica (15-20 refs); fichar Girardot, Bertacchini, Masselot; adaptar ao Brasil; as analises dimensionais sao base empirica mas nao dialogam com literatura |
| **OE3** (Transformacoes gestao) | 9 volumes produzidos; fichas V2; 139 municipios analisados; **piloto Palmas** (12 KB — primeiro dado empirico); **MVP dashboard funcional** (139 municipios, dados reais, 6 tabs); ADR-006 | Dashboard pronto mas sem usuarios externos; piloto Palmas sem analise formal; entrevistas pendentes |
| **OE4** (Padroes H-IA) | Split strategy documentada; padroes de orquestracao; relato de 213 agentes; **11+ prompts de sessao** (evolucao H-IA); **handoffs CEO↔CTO↔DEV** (8+); roles formalizados; conceitos teoricos emergentes (sessao 5) | Framework teorico nao sistematizado; sem dialogo com Dellermann, Jarrahi, Seeber; sem tipologia formal; prompts nao categorizados |
| **OE5** (Etica/governanca) | Reflexoes nos diarios sobre vieses, completude, validacao | Nenhuma audiencia publica realizada; nenhuma entrevista; nenhum grupo focal; CEP pendente |
| **OE6** (Escalabilidade) | Arquitetura modular do sistema; ia-collab-os como framework transferivel; **producao em escala** (213 agentes, 9 volumes, 139 municipios em 4 meses) | Sem teste em outro contexto; sem analise de barreiras; sem entrevistas com gestores de outros estados |

---

## 4. Artefatos Academicos Faltantes (priorizados por dependencia)

### Prioridade 1: Pre-requisitos (Fev-Jun 2026)
| # | Artefato | OE | Depende de | Responsavel |
|---|---------|-----|-----------|-------------|
| A1 | Metricas operacionais para ia-collab-os | OE1 | Etapa 4 do Plano | Pesquisador + IA |
| A2 | Revisao sistematica de IT (15-20 refs) | OE2 | Nenhum | Pesquisador |
| A3 | Submissao ao CEP | OE3-OE6 | Nenhum | Pesquisador |
| A4 | Artigo 1: ia-collab-os (ADR) | OE1 | A1 | Pesquisador |

### Prioridade 2: Coleta de dados (Jul-Dez 2026)
| # | Artefato | OE | Depende de | Responsavel |
|---|---------|-----|-----------|-------------|
| B1 | Validacao territorial (3 municipios) | OE3 | A3 (CEP) | Pesquisador (campo) |
| B2 | Audiencia(s) publica(s) CDR | OE5 | Proposta formal | Pesquisador + equipe senador |
| B3 | 15+ entrevistas transcritas | OE3-OE6 | A3 (CEP), B1, B2 | Pesquisador |
| B4 | Upload dados para Camada 1 | OE3 | Nenhum | Pesquisador + IA |

### Prioridade 3: Analise e escrita (2027-2028)
| # | Artefato | OE | Depende de | Responsavel |
|---|---------|-----|-----------|-------------|
| C1 | Framework teorico H-IA para gestao publica | OE4 | A2, B3 | Pesquisador |
| C2 | Analise transversal dos 5 ciclos PA | OE1 | Todos os anteriores | Pesquisador |
| C3 | Capitulos 2-7 da tese | Todos | C1, C2 | Pesquisador |
| C4 | Artigos 2-3 | OE2-OE4 | C1, C2 | Pesquisador |

---

## 5. Regra de Ouro para Proximas Sessoes

### Proporcao 70/30
> Cada sessao de producao de artefatos deve ser acompanhada de registro reflexivo.
> **70% producao** (artefatos, codigo, documentos) + **30% reflexao/documentacao** (diario, observacoes, padroes)

### Dupla leitura obrigatoria
> Antes de iniciar a producao de qualquer novo artefato, responder:
> 1. **Que valor pratico este artefato tem?** (para quem, para que)
> 2. **Que valor academico este artefato tem?** (para qual OE, qual PS)
> 3. **Que dados de pesquisa posso coletar DURANTE a producao?** (padroes, decisoes, metricas)

### Teste do "e so isso?"
> Apos produzir um artefato pratico, perguntar: "Se eu so tivesse este artefato, seria suficiente para sustentar o OE correspondente na tese?"
> Se a resposta for NAO, identificar o que falta e planejar coleta.

---

## 6. Diagrama: Tensao Produto-Tese

```
PRODUTO PRATICO                          DADO DE PESQUISA
(valor para o senador/equipe)            (valor para a tese)

  Cadernos Tocantins  ←——→  Evidencia de capacidade IT-IA (OE3)
                             MAS: sem uso real, sem feedback

  ia-collab-os        ←——→  Framework metodologico (OE1, OE4)
                             MAS: sem metricas, sem validacao

  tocantins-integrado ←——→  MVP funcional com dados reais (OE2, OE3, OE6)
                             MAS: sem usuarios externos ainda

  Audiencias CDR      ←——→  Dados qualitativos (OE5)
                             MAS: nao realizadas ainda

       O PRODUTO NAO SUBSTITUI A PESQUISA.
       A PESQUISA NAO INVALIDA O PRODUTO.
       AMBOS SE COMPLEMENTAM QUANDO PLANEJADOS EM CONJUNTO.
```

---

**Versao:** 2.2
**Data:** 14 de Fevereiro de 2026
**Historico:**
- v1.0 (12 Fev 2026): Matriz inicial com artefatos conhecidos
- v2.0 (12 Fev 2026): Incorporacao de artefatos descobertos na analise transversal (artigo "The Mediator Effect", analises dimensionais, ADRs, piloto Palmas, prompts de sessao, governanca). Novas secoes 2.4 e 2.5. Secao 2.6 expandida. OEs atualizados.
- v2.1 (13 Fev 2026): Secao 2.2 (ia-collab-os) expandida com v2.2 do framework.
- v2.2 (14 Fev 2026): Secao 2.3 (tocantins-integrado) atualizada pos-pivot MVP. Dashboard de "90% incompleto" para "MVP funcional". Parser, ADR-006, backend legado adicionados. OE3 e diagrama atualizados.
**Proxima revisao:** Apos deploy e primeiros dados de uso do dashboard
