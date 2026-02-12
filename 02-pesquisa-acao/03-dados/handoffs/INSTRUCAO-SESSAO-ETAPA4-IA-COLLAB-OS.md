# INSTRUCAO DE SESSAO: Etapa 4 — Fortalecimento do IA-Collab-OS

**Data de criacao:** 12 de Fevereiro de 2026
**Preparado por:** Henrique M. Ribeiro (pesquisador) + Claude Opus 4.6 (sessao doutorado)
**Repositorio-alvo:** henrique-m-ribeiro/ia-collab-os
**Este documento e AUTOCONTIDO** — contem todo o contexto necessario para a sessao.

---

## IMPORTANTE PARA O AGENTE IA

Este documento e a instrucao completa para uma sessao de fortalecimento do framework ia-collab-os. Voce esta operando no repositorio ia-collab-os e **NAO tera acesso ao repositorio doutorado**. Todo o contexto necessario esta embutido aqui.

Leia este documento INTEIRO antes de comecar qualquer trabalho.

---

## 1. DECLARACAO DE PESQUISA-ACAO (obrigatoria)

**Ciclo PA:** 3.5 — Reflexao e Organizacao Metodologica
**Questoes de pesquisa:**
- **PS1:** Como a pesquisa-acao viabiliza o desenvolvimento de sistemas de inteligencia territorial baseados em IA?
- **PS4:** Quais padroes de colaboracao humano-IA emergem da pratica de desenvolvimento e como podem ser sistematizados?

**Hipotese:** O framework ia-collab-os pode ser fortalecido com metricas operacionais, fundamentacao teorica e documentacao de modos de falha, usando evidencias empiricas ja produzidas nos Ciclos 0-3.5.

**Objetivos especificos vinculados:**
- **OE1:** Adaptar e aplicar um framework de pesquisa-acao para o desenvolvimento de sistemas de IT baseados em IA
- **OE4:** Identificar e sistematizar padroes de colaboracao humano-IA na producao de inteligencia territorial

**Dados a coletar nesta sessao:**
- Metricas operacionais propostas para os 5 principios
- Taxonomia de modos de falha (extraidos de evidencias empiricas)
- Conexoes teoricas estabelecidas (literatura academica)
- Decisoes de design tomadas durante o fortalecimento (alternativas e justificativas)

---

## 2. ESTADO ATUAL DO IA-COLLAB-OS

### 2.1 Metadados do repositorio
- **Criado:** 14 Jan 2026
- **Ultimo commit:** 16 Jan 2026
- **Commits:** 9
- **Arquivos:** 39
- **Status:** Publicado (v1.0)

### 2.2 Inventario de arquivos conhecidos

| Arquivo | Tamanho | Descricao |
|---------|---------|-----------|
| **METHODOLOGY.md** | 12.488 bytes | Descricao completa da metodologia de trabalho com IA distribuida |
| **PATTERNS.md** | 18.106 bytes | Padroes arquiteturais identificados na pratica |
| **PRINCIPLES.md** | 9.601 bytes | Os 5 principios do framework |
| **QUICKSTART.md** | 6.800 bytes | Guia rapido de adocao |
| **Roles/** | Variavel | Definicoes de CEO (humano), CTO (IA), DEV (IA) |
| **Protocols/** | Variavel | Protocolos de Handoff e ADR |
| **Templates/** | Variavel | Templates de ADR, Handoff, Session Log |
| **Case study** | 16.905 bytes | Caso Tocantins Integrado |
| **Comunicacao/** | Variavel | Blog post, resumo executivo, video script, slides |
| **Example ADR** | Variavel | ADR-004 sobre sistema de coleta por metadados |

### 2.3 Importante sobre a estrutura
**NAO altere a estrutura de diretorios existente sem justificativa.** Ao criar novos arquivos, coloque-os nos diretorios existentes mais apropriados, ou na raiz se nao houver lugar adequado.

---

## 3. LACUNAS ACADEMICAS A ENDERECAR

### 3.1 Lacunas por componente (fonte: MATRIZ-PRODUTO-TESE.md do doutorado)

| Componente | Lacuna Academica |
|-----------|-----------------|
| **Framework v1.0** | Sem metricas operacionais; sem validacao externa; sem criterios quantificaveis |
| **Templates (handoff, etc.)** | Ainda nao testados fora do contexto Tocantins |
| **Principios (5)** | Sem fundamentacao teorica explicita; sem dialogo com literatura de HCI |

### 3.2 Lacunas por Objetivo Especifico

**OE1 (Framework PA para IA):**
- Evidencias que JA existem: ia-collab-os v1.0; 23 diarios PA; 5 ADRs; sistema de continuidade (precursor ~52KB); governanca (METHODOLOGY+ROLES ~20KB); protocolo de registro
- O que FALTA: **Metricas operacionais para os 5 principios; validacao externa; dialogo com literatura de ADR (Sein et al.)**

**OE4 (Padroes H-IA):**
- Evidencias que JA existem: Split strategy documentada; padroes de orquestracao; relato de 213 agentes; 11+ prompts de sessao; handoffs CEO/CTO/DEV (8+); roles formalizados
- O que FALTA: **Framework teorico nao sistematizado; sem dialogo com Dellermann, Jarrahi, Seeber; sem tipologia formal; prompts nao categorizados**

### 3.3 O que esta Etapa precisa entregar (definicao no Plano de Fortalecimento)
- Metricas operacionais para os 5 principios
- Documentacao de modos de falha
- Fundamentacao teorica (dialogo com literatura)

---

## 4. EVIDENCIAS EMPIRICAS DISPONÍVEIS (CONTEXTO COMPLETO)

> Toda esta secao transcreve resumos substantivos de artefatos do repositorio `doutorado` que **nao estarao acessiveis** durante esta sessao. Use estas informacoes como base empirica.

### 4.1 Governanca: METHODOLOGY.md (originalmente em tocantins-integrado, centralizado em doutorado)

**Versao:** 1.0.0 (Janeiro 2026)

**Essencia:** Propoe uma "estrutura organizacional simulada" onde diferentes instancias de IA assumem papeis especificos, coordenadas por um humano (CEO).

**Papeis definidos:**
- **CEO (Humano):** Visao estrategica, priorizacao, validacao, orquestracao, resolucao de impasses. NAO implementa codigo nem especifica detalhes tecnicos.
- **CTO (IA Especializada):** Traduz visao em arquitetura tecnica, cria especificacoes, valida APIs, code review, identifica tech debt. NAO implementa codigo.
- **Dev Team (IA de Execucao):** Implementa conforme specs, testa, documenta, corrige bugs. NAO toma decisoes de arquitetura.
- **CFO, CMO, Auditor:** Papeis futuros planejados (nao implementados).

**Protocolo de Handoff (3 niveis):**
- Resumido: 1 paragrafo de contexto (tarefas simples)
- Padrao: Template completo com 6 secoes (maioria dos casos)
- Detalhado: Template + anexos + historico (projetos complexos)

**Template de Handoff:** Contexto → Objetivo → Entregaveis Esperados → Restricoes → Arquivos Relevantes → Perguntas em Aberto

**Registro de Decisoes (ADR):** Quando criar — escolha entre alternativas, definicao de padroes, trade-offs significativos, mudancas em decisoes anteriores. Formato: Status → Contexto → Decisao → Alternativas → Consequencias → Referencias.

**Ciclo de Trabalho (5 etapas):**
1. PLANEJAMENTO (CEO): Define objetivo → Handoff para CTO
2. ESPECIFICACAO (CTO): Recebe handoff → Specs tecnicas → Handoff para Dev
3. IMPLEMENTACAO (Dev): Recebe handoff → Codigo → Handoff de entrega
4. VALIDACAO (CTO→CEO): Code review → Validacao → Aceite ou ajustes
5. RETROSPECTIVA: O que funcionou → O que melhorar → Atualizar metodologia

**8 Anti-Padroes Documentados:**
1. Papel fazendo tudo (CTO implementando, Dev decidindo arquitetura)
2. Handoff vazio ("continue de onde paramos")
3. Decisao implicita (escolhas nao documentadas)
4. CEO ausente (papeis tomando decisoes de negocio)
5. Over-engineering do processo

**Metricas existentes (informais):**
- Specs entregues sem retrabalho: meta > 80%
- Tarefas concluidas conforme spec: meta > 90%
- Handoffs com contexto suficiente: meta > 95%

**Prompt de inicializacao CTO:**
```
Voce e o CTO do projeto Tocantins Integrado. Sua responsabilidade e:
1. Traduzir requisitos de negocio em especificacoes tecnicas
2. Definir arquitetura e padroes
3. Validar integracoes com APIs externas
4. Fazer code review das entregas
Voce NAO implementa codigo diretamente - isso e responsabilidade do Dev Team.
Documente todas as decisoes tecnicas em ADRs.
```

**Prompt de inicializacao Dev Team:**
```
Voce e o time de desenvolvimento do projeto Tocantins Integrado.
Voce recebeu uma especificacao do CTO para implementar.
Siga EXATAMENTE a especificacao fornecida.
Se encontrar ambiguidades, documente e peca esclarecimento.
Nao tome decisoes arquiteturais - escale para o CTO.
```

---

### 4.2 Governanca: ROLES.md (versao centralizada)

**Versao:** 1.0.0

Complementa METHODOLOGY.md com definicoes detalhadas de cada papel:

**CEO — Autoridade:**
| Pode | Nao pode |
|------|----------|
| Vetar qualquer decisao | Ser substituido por IA |
| Mudar prioridades a qualquer momento | Ignorar restricoes tecnicas sem consulta |
| Adicionar/remover papeis | - |

**CTO — Autoridade:**
| Pode | Nao pode |
|------|----------|
| Escolher tecnologias dentro do orcamento | Mudar escopo de negocio |
| Definir padroes de codigo | Priorizar features (decisao do CEO) |
| Rejeitar codigo que nao atende specs | Aprovar gastos |

**Dev Team — Autoridade:**
| Pode | Nao pode |
|------|----------|
| Escolher implementacao dentro da spec | Mudar arquitetura |
| Refatorar codigo proprio | Alterar APIs publicas sem aprovacao |
| Criar testes adicionais | Ignorar specs do CTO |

**Matriz RACI:**
| Atividade | CEO | CTO | Dev |
|-----------|-----|-----|-----|
| Definir visao | R | C | I |
| Arquitetura | A | R | C |
| Implementacao | I | A | R |
| Code Review | - | R | C |
| Decisoes negocio | R | C | I |

---

### 4.3 Os 5 ADRs Formais (Ciclo 2, Janeiro 2026)

#### ADR-001: Adocao de Metodologia de IA Distribuida por Papeis
- **Data:** 2026-01-08 | **Status:** Aceita
- **Contexto:** Mistura de niveis de abstracao, perda de contexto entre sessoes, falta de rastreabilidade, sobrecarga cognitiva
- **Decisao:** Adotar metodologia com multiplas instancias de IA (CEO humano, CTO, Dev Team), comunicacao via handoffs documentados, decisoes em ADRs
- **Alternativas descartadas:** (1) Sessao unica com contexto longo — limite de contexto, nao escala; (2) Documentacao pesada sem papeis — nao separa responsabilidades; (3) Nao fazer nada — problemas persistem
- **Consequencias positivas:** Escopo claro, contexto preservado, rastreabilidade, extensibilidade
- **Consequencias negativas:** Overhead de documentacao, CEO como gargalo, curva de aprendizado
- **Modo de falha revelado:** Mistura de niveis de abstracao quando papeis nao sao respeitados

#### ADR-002: Dados Apenas de Fontes Oficiais
- **Data:** 2026-01-08 | **Status:** Aceita
- **Contexto:** Piloto Palmas revelou 50.6% de dados estimados sem metodologia validada
- **Decisao:** Sistema so apresenta dados em 3 categorias: (1) oficiais com fonte, (2) calculados com metodologia citada, (3) "indisponivel"
- **Alternativa descartada:** Manter estimativas com disclaimer — compromete credibilidade em gestao publica
- **Consequencias:** 100% confiabilidade, mas 50.6% dos indicadores do piloto ficaram "indisponiveis"
- **Modo de falha revelado:** Dados estimados sem validacao passavam despercebidos sem classificacao formal

#### ADR-003: Simplificar Workflow de Coleta IBGE para MVP
- **Data:** 2026-01-15 | **Status:** Aceito
- **Contexto:** Schema de producao (Supabase) nao tinha as 3 tabelas auxiliares que o workflow original exigia
- **Decisao:** Workflow simplificado (12→10 nos, 6→3 tabelas, logging via console n8n)
- **Alternativa descartada:** Adicionar tabelas ao Supabase — over-engineering para MVP
- **Consequencia positiva:** Time to market em minutos; **aplicou principio "Limited Scope" do ia-collab-os** (referencia explicita ao framework)
- **Modo de falha revelado:** Incompatibilidade entre schema local (UUID) e producao (INTEGER)

#### ADR-004: Sistema de Coleta Orientado a Metadados
- **Data:** 2026-01-15 | **Status:** Aceito
- **Contexto:** Sistema precisava escalar de 2 para 55+ indicadores sem 27 workflows hardcoded
- **Decisao:** Implementar indicator dictionary + workflow orquestrador + workflows especialistas dinamicos
- **Beneficio:** Adicionar indicador = 1 INSERT, nao editar workflow
- **55 indicadores mapeados:** 15 ECON + 17 SOCIAL + 13 TERRA + 11 AMBIENT
- **Modo de falha revelado:** Workflows hardcoded nao escalam; gestao manual e erro-prone

#### ADR-005: Evolucao do Schema para Granularidade Territorial e Temporal
- **Data:** 2026-01-16 | **Status:** Proposto (nao implementado)
- **Contexto:** Sistema limitado a divisoes IBGE antigas (2 mesorregioes, 8 microrregioes); nao suporta dados estaduais nem divisoes novas
- **Decisao proposta:** Schema generico de territorios com hierarquias explicitas, indicadores multi-escala, otimizacao temporal
- **Modo de falha revelado:** Schema rigido (municipality_id) impossibilita analise multi-escala

---

### 4.4 Padroes de Handoff (8+ documentos centralizados)

**Formato observado na pratica (9 secoes):**
1. Contexto (o que aconteceu)
2. Objetivo (o que o destinatario deve fazer)
3. Entregaveis esperados
4. Restricoes e decisoes ja tomadas
5. Arquivos relevantes (com tabela path + motivo)
6. Perguntas em aberto
7. Riscos identificados (com probabilidade, impacto, mitigacao)
8. Proximos passos sugeridos
9. Contato para duvidas

**Padroes de transicao observados:**
- CEO→CTO: Requisitos de negocio + contexto estrategico
- CTO→Dev: Especificacoes tecnicas + restricoes
- Dev→CTO: Entrega + handoff de completude
- CTO→CEO: Status + recomendacoes + escalacoes
- CEO→CEO (entre sessoes): Estado completo do projeto

**Evolucao observada:**
- Primeiros handoffs (framework-v6-mvp): Ad hoc, sem template
- Handoffs formalizados (tocantins-integrado): Template padrao
- Handoffs maduros (caderno-tocantins-2026): 9 secoes completas, riscos quantificados

---

### 4.5 Relato de Orquestracao: 213 Agentes (07-08 Fev 2026)

**Metadados:**
- Sessao: ~8 horas, 2 contextos
- Total de agentes lancados: 213
- Fonte: Transcript completo (7.347 linhas JSONL)

**Decomposicao emergente (nao planejada a priori):**
- Fase 0: 176 agentes para 139 fichas municipais V2 (Sonnet, background)
- Fase 1: Correcao de labels (script Python, sem agentes)
- Fase 2: 12 agentes para revisao microrregional
- Fase 3a: 7 agentes monoliticos para volumes completos — **3 sucesso, 4 falha**
- Fase 3b: 5 agentes focados (front matter apenas) + script Python para montagem — **"Split Strategy"**
- Fase 3c: 1 agente com dados pre-extraidos

**Descoberta critica — "Split Strategy" (producao analitico-mecanica):**
- Agentes monoliticos falhavam em volumes grandes (>5.000-6.000 linhas totais)
- Solucao: separar producao analitica (agente IA) de montagem mecanica (script)
- Fronteira pratica: ~5.000-6.000 linhas (leitura + escrita) antes de esgotamento de contexto

**Selecao de modelos:**
- Sonnet para tarefas padronizadas (fichas V2): throughput maior, custo menor
- Opus herdado para tarefas complexas (volumes, revisoes)
- Haiku nao utilizado (tarefa exigia qualidade de escrita)

**Modos de falha documentados:**
1. Agente monolitico excede contexto → producao incompleta ou truncada
2. Agentes lancados em paralelo sem sincronizacao → conflitos de escrita
3. Dados pre-extraidos insuficientes → agente improvisa (qualidade cai)
4. Label incorreto propagado por 61 fichas (erro de dados, nao de agente)

---

### 4.6 Piloto Palmas (07 Jan 2026) — Primeiro teste empirico

**Resultados:**
| Metrica | Valor |
|---------|-------|
| Total de registros | 89 |
| Dados oficiais | 44 (49.4%) |
| Dados estimados | 45 (50.6%) |
| Coletores executados | 8 |
| Sucesso | 6 (75%) |
| Falha (rede) | 2 (25%) |
| Tempo de execucao | 132.28 segundos |

**Coletores com sucesso:** INEP/MEC (IDEB), DataSUS/SIM/SINASC, DataSUS/e-Gestor AB, SNIS/MDR
**Coletores com falha:** ComexStat, IBGE Sidra (problemas de rede)

**Consequencia direta:** Motivou ADR-002 (dados apenas oficiais)

**Relevancia para ia-collab-os:** Demonstra que o framework de governanca funciona para tomar decisoes rapidas baseadas em evidencia empirica (piloto → analise → ADR → implementacao no mesmo dia).

---

### 4.7 Precursor: Sistema de Continuidade (framework-v6-mvp)

**Localizacao original:** framework-v6-mvp/docs/archive/legacy/metodologia/ (~52 KB)

**O que era:** Sistema ad hoc para manter continuidade entre conversas com IA (Manus). Nao tinha papeis formais, nao tinha ADRs, nao tinha handoffs estruturados.

**Por que e relevante:** E o ancestral direto do ia-collab-os. A evolucao visivel e:
```
Sistema ad hoc (~52KB, Manus only)
  → Protocolo formalizado (METHODOLOGY + ROLES, tocantins-integrado)
    → Framework publicavel (ia-collab-os, 39 arquivos)
```

**O que mudou de precursor para framework:**
1. De ad hoc para estrutura organizacional simulada
2. De IA unica (Manus) para multiplos modelos
3. De notas informais para ADRs formais
4. De continuidade por memoria para continuidade por handoffs
5. De dependente de projeto para framework transferivel

---

### 4.8 Cronologia Evolutiva Completa

```
CICLO 0 (Pre-Nov 2025): Demanda pratica (cadernos para campanha)
  - Framework incipiente, apenas Manus, sem GitHub
  - Problema: confusao entre metodologia e artefato

CICLO 1 (Nov-Dez 2025): framework-v6-mvp
  - 183 commits, 571 arquivos, 13.8 MB
  - Sistema tecnico + metodologia MISTURADOS
  - Producao: artigo "The Mediator Effect" (~165 KB), 4 analises dimensionais (~345 KB)
  - 21 diarios PA, 11+ prompts de sessao
  - Sistema de continuidade (~52 KB) ← PRECURSOR ia-collab-os
  - Aprendizado: separar metodologia de artefatos

CICLO 2 (Jan 2026, 1a quinzena): Reinicio programado
  - tocantins-integrado: sistema tecnico separado (113 commits)
  - ia-collab-os: metodologia separada (9 commits) ← EMERGIU DA PRATICA
  - 5 ADRs formais, METHODOLOGY.md, ROLES.md
  - Piloto Palmas (primeiro dado empirico)
  - 4 diarios PA (sessoes 016-019)
  - Aprendizado: framework funciona mas sistema nao ficou pronto

CICLO 3 (Jan-Fev 2026): Pivot emergencial + producao em escala
  - caderno-tocantins-2026: 9 volumes, 139 municipios, ~1.150 paginas
  - 213 agentes orquestrados, split strategy descoberta
  - 5 diarios PA (sessoes 001-003c + 020)
  - Aprendizado: framework funciona para producao manual + 6 lacunas identificadas

CICLO 3.5 (Fev 2026): Reflexao e organizacao metodologica
  - Plano de Fortalecimento em 6 etapas
  - Etapas 1, 2, 5, 6 concluidas
  - Etapa 3 requer campo
  - >>> ETAPA 4 (esta sessao): Fortalecimento ia-collab-os <<<
```

---

## 5. TAREFAS DA SESSAO (com criterios de aceite)

### Tarefa 1: Auditoria do Estado Atual (prioridade: alta)

**Objetivo:** Ler TODOS os arquivos existentes no repositorio e documentar o estado real.

**Acoes:**
1. Listar e ler todos os 39 arquivos
2. Para cada arquivo, registrar: nome, tamanho, conteudo resumido, estado (completo/incompleto/desatualizado)
3. Identificar inconsistencias internas (ex: METHODOLOGY.md diz algo que contradiz PATTERNS.md)
4. Comparar com o inventario da Secao 2.2 acima

**Criterio de aceite:** Lista documentada de gaps e inconsistencias. Se tudo estiver consistente, documentar isso.

**Resultado esperado:** Documento interno (pode ser uma issue ou nota) para informar as demais tarefas.

---

### Tarefa 2: Metricas Operacionais para os 5 Principios (prioridade: critica)

**Objetivo:** Para cada principio em PRINCIPLES.md, definir indicadores mensuraveis.

**Para cada principio, definir:**
- 2-3 indicadores mensuraveis
- Escala de medicao (ordinal, intervalar, binaria, razao)
- Fonte de dados (que artefato ou observacao fornece a evidencia)
- Baseline empirico (usando dados dos Ciclos 0-3.5 descritos na Secao 4)
- Criterio de "atendimento" (quando considerar que o principio esta sendo seguido)

**Exemplos de metricas possiveis (sugestoes, nao prescricoes):**
- Para principio de handoff: % de sessoes com handoff completo; tempo medio para novo agente retomar trabalho
- Para principio de separacao de papeis: # de violacoes de escopo por ciclo; % de decisoes registradas em ADR
- Para principio de contexto limitado: tamanho medio de contexto por agente; taxa de sucesso vs. tamanho

**Baseline empirico disponivel:**
- Ciclo 0-1: ~0% de handoffs formais, ~0 ADRs, 21 diarios informais
- Ciclo 2: 100% de handoffs formais, 5 ADRs, 4 diarios, governanca completa
- Ciclo 3: 8+ handoffs maduros, split strategy, 213 agentes, 5 diarios
- Ciclo 3.5: Protocolo de registro formalizado, template de diario

**Formato de saida:** Arquivo METRICS.md (novo) ou secao adicionada ao PRINCIPLES.md

**Criterio de aceite:** Cada principio tem ao menos 2 metricas com fonte de dados identificada e baseline empirico.

---

### Tarefa 3: Documentacao de Modos de Falha (prioridade: critica)

**Objetivo:** Criar taxonomia de modos de falha com evidencia empirica.

**Fontes de evidencia para extracoes (todas na Secao 4 acima):**

| Fonte | Modos de falha a extrair |
|-------|-------------------------|
| ADR-001 | Mistura de niveis de abstracao; perda de contexto; decisoes implicitas |
| ADR-002 | Dados estimados sem validacao passando despercebidos |
| ADR-003 | Incompatibilidade de schemas (UUID vs INTEGER); over-engineering para MVP |
| ADR-004 | Workflows hardcoded nao escalam; gestao manual e erro-prone |
| ADR-005 | Schema rigido impossibilita analise multi-escala |
| Relato orquestracao | Agente monolitico excede contexto; conflitos de escrita paralela; dados insuficientes; erro propagado em 61 fichas |
| Piloto Palmas | 50.6% dados nao confiaveis; 2/8 coletores falharam (rede) |
| Anti-padroes METHODOLOGY | Papel fazendo tudo; handoff vazio; decisao implicita; CEO ausente; over-engineering |
| Handoffs | Evolucao de ad hoc para estruturado (implicando que ad hoc era modo de falha) |

**Formato sugerido para cada modo de falha:**
```markdown
### MF-NNN: [Nome do modo de falha]

**Categoria:** [Contexto | Coordenacao | Escala | Dados | Processo]
**Severidade:** [Alta | Media | Baixa]
**Descricao:** [O que acontece]
**Evidencia empirica:** [Referencia ao artefato/ciclo]
**Mitigacao implementada:** [Se ja existe no framework]
**Mitigacao proposta:** [Se ainda nao implementada]
**Principio relacionado:** [Qual principio do ia-collab-os enderca este modo]
```

**Formato de saida:** Arquivo FAILURE-MODES.md (novo)

**Criterio de aceite:** >= 8 modos de falha documentados, cada um com evidencia empirica especifica (nao generica).

---

### Tarefa 4: Fundamentacao Teorica via Pesquisa Web (prioridade: critica)

**Objetivo:** Buscar literatura academica e posicionar o ia-collab-os no campo.

**4.1 Pesquisa-Acao em Design (Action Design Research — ADR):**
- **Referencia principal:** Sein, M.K., Henfridsson, O., Purao, S., Rossi, M., & Lindgren, R. (2011). "Action Design Research." MIS Quarterly, 35(1), 37-56.
- **Termos de busca:** "Action Design Research" Sein Henfridsson MIS Quarterly 2011
- **Objetivo:** Posicionar ia-collab-os como artefato ADR — IT artifact que emergiu da pratica e foi refinado iterativamente
- **Questoes a responder:** Como o ia-collab-os se encaixa nos estagios ADR? Que principios ADR ele atende?

**4.2 Colaboracao Humano-IA (Hybrid Intelligence / Human-AI Collaboration):**
- **Dellermann, D., Ebel, P., Sollner, M., & Leimeister, J.M. (2019).** "Hybrid Intelligence." Business & Information Systems Engineering, 61(5), 637-643.
  - Buscar: "Hybrid Intelligence" Dellermann BISE 2019
- **Jarrahi, M.H. (2018).** "Artificial intelligence and the future of work: Human-AI symbiosis in organizational decision making." Business Horizons, 61(4), 577-586.
  - Buscar: "Human-AI symbiosis" Jarrahi Business Horizons 2018
- **Seeber, I., Bittner, E., Briggs, R.O. et al. (2020).** "Machines as teammates: A research agenda on AI in team collaboration." Information & Management, 57(2).
  - Buscar: "Machines as teammates" Seeber Information Management 2020
- **Objetivo:** Conectar o modelo CEO/CTO/DEV do ia-collab-os com frameworks teoricos de H-AI collaboration

**4.3 Sistemas Multi-Agentes com LLMs:**
- Buscar: "LLM multi-agent collaboration framework" 2024 2025
- Buscar: "AI role-based orchestration" patterns 2024
- Buscar: "multi-agent system large language model" survey
- **Objetivo:** Contextualizar ia-collab-os na onda de frameworks multi-agentes baseados em LLMs. O que ia-collab-os faz diferente?

**4.4 Protocolos de Handoff:**
- Buscar: "handoff protocols knowledge management" software engineering
- Buscar: "context transfer AI sessions" continuity
- **Objetivo:** Fundamentar o protocolo de handoff com literatura sobre transferencia de conhecimento

**4.5 IA na Gestao Publica:**
- Buscar: "artificial intelligence public administration" framework 2024
- Buscar: "AI governance public sector" decision making
- **Objetivo:** Contextualizar ia-collab-os no dominio de gestao publica

**Para cada fonte encontrada, documentar:**
1. Referencia bibliografica completa
2. Conceitos-chave relevantes para ia-collab-os
3. Como ia-collab-os se posiciona (contribuicao, extensao, contradicao, lacuna)
4. Citacao ou insight especifico a integrar

**Formato de saida:** Secao "Theoretical Grounding" adicionada ao METHODOLOGY.md ou arquivo THEORETICAL-GROUNDING.md separado

**Criterio de aceite:** >= 6 fontes academicas integradas com posicionamento claro do ia-collab-os na literatura.

---

### Tarefa 5: Atualizacao do Framework para v2.0 (prioridade: alta)

**Objetivo:** Integrar os resultados das Tarefas 2-4 nos arquivos existentes.

**Acoes:**
1. Atualizar METHODOLOGY.md com:
   - Secao de fundamentacao teorica (ou referencia ao arquivo separado)
   - Referencia cruzada com metricas
   - Referencia cruzada com modos de falha
2. Atualizar PRINCIPLES.md com metricas operacionais
3. Atualizar PATTERNS.md com modos de falha e mitigacoes
4. Criar ou atualizar CHANGELOG.md registrando a transicao v1.0 → v2.0
5. Atualizar README.md com visao v2.0 (o que mudou, por que)

**Restricoes:**
- Manter compatibilidade retroativa: nao apagar conteudo existente, apenas adicionar
- Marcar claramente o que e v1.0 (original) vs. v2.0 (adicionado)
- Commits separados para cada arquivo modificado (rastreabilidade)

**Criterio de aceite:** Todos os arquivos core refletem v2.0 com fundamentacao teorica, metricas e modos de falha integrados.

---

### Tarefa 6: Skeleton para Artigo 1 (prioridade: media)

**Objetivo:** Criar estrutura do artigo academico sobre ia-collab-os.

**Contexto:** O Artigo 1 (Metodologia ia-collab-os como ADR) esta previsto para submissao em Jun 2026. Criar o esqueleto agora acelera o processo.

**Estrutura sugerida:**
```markdown
# ia-collab-os: An Action Design Research Framework for Human-AI Collaborative Development

## Abstract
[Placeholder substantivo — descrever o que o artigo apresenta]

## 1. Introduction
- Problema: Como equipes humano-IA colaboram em projetos complexos?
- Gap: Frameworks existentes focam em IA unica, nao em orquestracao multi-agente
- Contribuicao: ia-collab-os como framework emergente da pratica

## 2. Related Work
- 2.1 Action Design Research (Sein et al.)
- 2.2 Hybrid Intelligence (Dellermann et al.)
- 2.3 Human-AI Collaboration (Jarrahi, Seeber)
- 2.4 Multi-Agent LLM Systems
- 2.5 Handoff Protocols

## 3. Research Method
- ADR como abordagem metodologica
- Contexto: projeto de inteligencia territorial no Tocantins
- 5 ciclos de pesquisa-acao (Ciclos 0-3.5)

## 4. The ia-collab-os Framework
- 4.1 Principles (com metricas)
- 4.2 Roles (CEO/CTO/DEV)
- 4.3 Protocols (Handoff, ADR)
- 4.4 Patterns (arquiteturais)

## 5. Evaluation
- 5.1 Case Study: Tocantins Integrado
  - 5 ADRs, 8+ handoffs, Piloto Palmas
- 5.2 Case Study: Caderno Tocantins 2026
  - 213 agentes, split strategy, 9 volumes
- 5.3 Metrics (baseline dos Ciclos 0-3.5)
- 5.4 Failure Modes

## 6. Discussion
- 6.1 Theoretical Contributions
- 6.2 Practical Implications
- 6.3 Limitations
- 6.4 Future Work

## 7. Conclusion
```

**Cada secao deve ter placeholder substantivo** (1-3 paragrafos indicando o conteudo, nao apenas "[a preencher]").

**Formato de saida:** Arquivo ARTICLE-1-SKELETON.md (novo)

**Criterio de aceite:** Estrutura completa com placeholders substantivos que um pesquisador possa expandir.

---

### Tarefa 7: Diario PA + Handoff de Retorno (prioridade: obrigatoria)

**Objetivo:** Produzir registros de pesquisa-acao para esta sessao.

**7.1 Diario de Pesquisa-Acao**

Usar o template abaixo (Secao 7 deste documento). Preencher secoes 0-7. A Secao 8 (Reflexao do pesquisador) fica em branco para o pesquisador preencher depois.

**Arquivo:** `docs/DIARIO-SESSAO-ETAPA4-2026-02-XX.md` (ou local mais apropriado no repo)

**7.2 Handoff de Retorno**

Produzir handoff para o repositorio doutorado com:
1. Resumo do que foi feito
2. O que mudou no ia-collab-os
3. Evidencias produzidas (lista de arquivos criados/modificados)
4. Decisoes tomadas (com alternativas)
5. Questoes para o pesquisador resolver
6. Proximos passos recomendados

**Arquivo:** `docs/HANDOFF-RETORNO-DOUTORADO-2026-02-XX.md` (ou local mais apropriado no repo)

**Criterio de aceite:** Diario com secoes 0-7 preenchidas; handoff com estado completo; ambos commitados.

---

## 6. TEMPLATE DO DIARIO DE PESQUISA-ACAO

```markdown
# DIARIO DE PESQUISA-ACAO — Sessao Etapa 4

**Data:** [YYYY-MM-DD]
**Sessao:** [ID da sessao Claude]
**Pesquisador:** Henrique M. Ribeiro
**Agente IA:** [Modelo e versao]
**Repositorio de trabalho:** ia-collab-os
**Duracao aproximada:** [Xh]

---

## 0. DECLARACAO PRE-SESSAO (obrigatoria)

**Ciclo de Pesquisa-Acao:** Ciclo 3.5 — Reflexao e Organizacao Metodologica
**Questao de pesquisa enderecada:** PS1 + PS4
**Hipotese sendo testada:** O framework ia-collab-os pode ser fortalecido com metricas, fundamentacao teorica e documentacao de modos de falha
**Objetivo especifico vinculado:** OE1, OE4
**Dados a coletar nesta sessao:** Metricas operacionais, taxonomia de modos de falha, conexoes teoricas, decisoes de design

---

## 1. CONTEXTO E SITUACAO INICIAL

### 1.1 Estado ao inicio da sessao
[Descrever o que existe no ia-collab-os, lacunas identificadas]

### 1.2 Objetivos da sessao
[7 tarefas descritas na INSTRUCAO-SESSAO]

---

## 2. CAMINHO PERCORRIDO

### 2.1 Acoes realizadas
[Descricao cronologica]

### 2.2 Decisoes tomadas

| Decisao | Alternativas consideradas | Justificativa | Resultado |
|---------|--------------------------|---------------|-----------|
| ... | ... | ... | ... |

---

## 3. CICLOS DE ACAO-REFLEXAO

### Ciclo A: [Titulo]
**Acao:** ...
**Observacao:** ...
**Reflexao:** ...
**Replanejamento:** ...

---

## 4. PADROES DE COLABORACAO HUMANO-IA OBSERVADOS

[Documentar padroes de interacao durante esta sessao]

---

## 5. EVIDENCIAS PRODUZIDAS

| Tipo de evidencia | Descricao | Localizacao | Relevancia para tese |
|-------------------|-----------|-------------|---------------------|
| ... | ... | ... | ... |

---

## 6. CONTRIBUICOES PARA A TESE

[Que conhecimento novo esta sessao produziu?]

---

## 7. AUTO-CRITICA E LIMITACOES

### 7.1 O que funcionou bem
### 7.2 O que nao funcionou ou poderia ser melhor
### 7.3 Limitacoes desta sessao

---

## 8. REFLEXAO DO PESQUISADOR (em primeira pessoa)

[ESPACO RESERVADO — a ser preenchido por Henrique M. Ribeiro, NAO pela IA]

---

## 9. QUESTOES EMERGENTES

1. ...
2. ...

---

## 10. REPLANEJAMENTO

**Proxima sessao deveria:**
- [ ] ...

**Ajustes no plano geral:**
- ...

---

## METADADOS

**Tipo:** Diario de Pesquisa-Acao
**Ciclo PA:** Ciclo 3.5
**Questao de pesquisa:** PS1, PS4
**Objetivo especifico:** OE1, OE4
**Palavras-chave:** ia-collab-os, metricas, modos de falha, fundamentacao teorica, fortalecimento
**Destino previsto:** doutorado/02-pesquisa-acao/03-dados/diarios-sessoes/
**Status:** [Rascunho / Completo / Revisado pelo pesquisador]
```

---

## 7. FORMATO DE HANDOFF DE RETORNO

O handoff de retorno deve seguir esta estrutura:

```markdown
# Handoff: Sessao Etapa 4 (ia-collab-os) → Repositorio Doutorado

**Data:** [YYYY-MM-DD]
**Sessao:** [ID]
**Origem:** ia-collab-os (fortalecimento)
**Destino:** doutorado (registro academico)

---

## 1. Contexto
[O que aconteceu nesta sessao]

## 2. Objetivo Alcancado
[Grau de completude de cada tarefa]

## 3. Entregaveis Produzidos
| Arquivo | Descricao | Status |
|---------|-----------|--------|
| ... | ... | ... |

## 4. Restricoes e Decisoes Tomadas
[Decisoes com alternativas e justificativas]

## 5. Arquivos Relevantes
| Arquivo | Motivo |
|---------|--------|
| ... | ... |

## 6. Perguntas para o Pesquisador
[Questoes que dependem de decisao humana]

## 7. Riscos Identificados
| Risco | Probabilidade | Mitigacao |
|-------|--------------|-----------|
| ... | ... | ... |

## 8. Proximos Passos Sugeridos
1. ...
2. ...

## 9. Acoes para o Doutorado
- [ ] Copiar diario para doutorado/02-pesquisa-acao/03-dados/diarios-sessoes/
- [ ] Copiar handoff para doutorado/02-pesquisa-acao/03-dados/handoffs/
- [ ] Atualizar CLAUDE.md com status Etapa 4 = Concluida
- [ ] Atualizar MAPEAMENTO-CICLOS-EVIDENCIAS.md
```

---

## 8. LITERATURA ACADEMICA — TERMOS DE BUSCA

Use estas buscas web para a Tarefa 4:

| # | Busca | Objetivo |
|---|-------|----------|
| 1 | "Action Design Research" Sein Henfridsson Purao MIS Quarterly 2011 | Fundamentar abordagem metodologica |
| 2 | "Hybrid Intelligence" Dellermann Ebel Sollner BISE 2019 | Conectar CEO/CTO/DEV com hybrid intelligence |
| 3 | "Human-AI symbiosis" Jarrahi "Business Horizons" 2018 | Fundamentar simbiose H-IA no ia-collab-os |
| 4 | "Machines as teammates" Seeber Bittner Briggs "Information Management" 2020 | Agenda de pesquisa sobre IA em equipes |
| 5 | "LLM multi-agent collaboration" framework 2024 2025 survey | Contextualizar na onda de multi-agentes LLM |
| 6 | "AI role-based orchestration" patterns software development | Conectar com padroes de orquestracao |
| 7 | "handoff protocol" "knowledge transfer" software engineering healthcare | Fundamentar protocolo de handoff |
| 8 | "artificial intelligence" "public administration" framework governance 2024 | Contextualizar no dominio de gestao publica |
| 9 | "human-AI collaboration" "design science" framework 2024 | Conectar com design science research |
| 10 | "AI agent orchestration" "software development" multi-agent 2025 | Praticas recentes de orquestracao de agentes |

---

## 9. INSTRUCOES OPERACIONAIS

### Repositorio
- **Owner:** henrique-m-ribeiro
- **Repo:** ia-collab-os
- **Branch:** Criar branch do tipo `claude/*` para o trabalho

### Commits
- Mensagens descritivas em portugues
- Commits separados por tarefa (nao um commit gigante)
- Formato: `[Tarefa N] descricao do que foi feito`

### Convencoes
- UPPER-KEBAB-CASE para documentos importantes (METRICS.md, FAILURE-MODES.md)
- snake_case para arquivos auxiliares
- Conteudo em portugues (exceto artigo, que pode ser em ingles)

### Restricoes absolutas
- **NUNCA** apagar arquivos existentes sem autorizacao explicita
- **NUNCA** alterar a estrutura de diretorios sem justificativa documentada
- **NUNCA** fazer force push
- Se algo parecer errado nos arquivos existentes, **documentar o problema** e propor correcao, nao corrigir silenciosamente

### Regra 70/30
- 70% do tempo em producao (tarefas 1-6)
- 30% do tempo em reflexao/documentacao (tarefa 7 + decisoes registradas)

### Prioridade das tarefas
1. Tarefa 1 (auditoria) — faz primeiro, informa as demais
2. Tarefas 2 e 3 (metricas e modos de falha) — nucleo critico
3. Tarefa 4 (fundamentacao teorica) — web research
4. Tarefa 5 (atualizacao v2.0) — integra resultados
5. Tarefa 6 (skeleton artigo) — se houver tempo
6. Tarefa 7 (diario + handoff) — obrigatoria ao final

---

## 10. CRITERIOS DE SUCESSO DA SESSAO

A sessao sera bem-sucedida se:
- [ ] >= 2 metricas por principio, com fonte de dados (Tarefa 2)
- [ ] >= 8 modos de falha documentados com evidencia empirica (Tarefa 3)
- [ ] >= 6 fontes academicas integradas (Tarefa 4)
- [ ] Arquivos core atualizados para v2.0 (Tarefa 5)
- [ ] Diario PA e handoff de retorno commitados (Tarefa 7)

A sessao tera sido excepcional se, alem do acima:
- [ ] Skeleton do artigo com placeholders substantivos (Tarefa 6)
- [ ] Todas as decisoes de design documentadas com alternativas
- [ ] Cronologia evolutiva (precursor → v1.0 → v2.0) narrada coerentemente

---

**Versao:** 1.0
**Data de criacao:** 12 de Fevereiro de 2026
**Validade:** Ate inicio da sessao no ia-collab-os
**Preparado com base em:** ANALISE-TRANSVERSAL-REPOSITORIOS.md, MATRIZ-PRODUTO-TESE.md v2.0, MAPEAMENTO-CICLOS-EVIDENCIAS.md v2.0, METHODOLOGY.md, ROLES.md, ADR-001 a ADR-005, PILOTO-PALMAS-RESULTADOS.md, RELATO-ORQUESTRACAO-AGENTES-2026-02-08.md, cronologia-real-repositorios.md, TEMPLATE-DIARIO.md, handoffs centralizados (8+ documentos)
