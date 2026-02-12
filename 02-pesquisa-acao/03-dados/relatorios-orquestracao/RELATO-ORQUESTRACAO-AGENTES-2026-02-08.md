# RELATO DE ORQUESTRACAO DE AGENTES IA
## A Producao dos Volumes 2-9 do Caderno Tocantins 2026

**Sessao:** session_01Hj1yX6KsVL4QbAqunMSRQv
**Data:** 07-08 de Fevereiro de 2026
**Agente Orquestrador:** Claude Code (Opus 4.6)
**Total de Agentes Lancados:** 213

---

## NOTA METODOLOGICA

Este relato foi reconstruido a partir do transcript completo da sessao (7.347 linhas JSONL), com extracao automatizada dos 213 lancamentos de agentes, seus prompts verbatim, modelos selecionados, e resultados. Nao e reconstrucao de memoria — e evidencia documental. As reflexoes interpretativas, contudo, sao posteriores ao trabalho e sujeitas a racionalizacao post-hoc.

---

## PARTE I — COMO A TAREFA FOI DECOMPOSTA

### 1.1 A Tarefa Original

O objetivo era produzir 8 volumes regionais (Vol 2-9), cada um contendo: capa, ficha tecnica, indice, apresentacao contextualizada, sumario executivo analitico, ficha microrregional revisada, e fichas municipais V2 em ordem alfabetica. Os volumes variam de 11 a 25 municipios.

### 1.2 Decomposicao em Fases

A decomposicao **nao foi planejada inteiramente a priori**. Emergiu iterativamente conforme restricoes se revelavam:

**Fase 0 — Producao das fichas V2 (Agentes #6-#181)**
176 agentes lancados para produzir 139 fichas municipais condensadas (alguns municipios exigiram relancamento). Cada agente recebia a mesma tarefa atomica: ler o prompt de condensacao, ler a ficha exemplo aprovada, ler a ficha completa do municipio, gerar a versao V2, escrever o arquivo.

**Fase 1 — Correcao de labels (sem agentes)**
Realizada pelo orquestrador diretamente via scripts Python. 61/139 fichas tinham labels de microrregiao incorretos.

**Fase 2 — Revisao microrregional (Agentes #189-#200)**
12 agentes no total (2 lancamentos para Miracema). 6 fichas microrregionais precisavam de municipios adicionados.

**Fase 3a — Producao monolitica de volumes (Agentes #201-#207)**
7 agentes tentaram produzir volumes completos. 3 tiveram sucesso (Porto Nacional/11 mun., Jalapao/15 mun., Rio Formoso/13 mun.). 4 falharam (Araguaina/17 mun., Bico/25 mun., Gurupi/14 mun., Dianopolis/20 mun.).

**Fase 3b — Split strategy (Agentes #209-#213)**
5 agentes focados geraram APENAS front matter. Script Python fez a montagem mecanica.

**Fase 3c — Miracema (Agente #208)**
1 agente focado com dados pre-extraidos para revisao da ficha microrregional mais complexa.

### 1.3 O Criterio de Decomposicao

A decomposicao seguiu um principio empirico, nao teorico: **cada agente deve conseguir manter em contexto simultaneamente todos os arquivos que precisa ler E o texto que precisa produzir**.

Na Fase 0, isso significava: 1 prompt + 1 exemplo + 1 ficha completa = ~1.500 linhas de leitura + ~300 linhas de escrita. Viavel.

Na Fase 2, significava: 1 ficha microrregional (~1.200 linhas) + 1-5 fichas V2 (~250-350 linhas cada) + revisao da ficha. Para 2 municipios ausentes (Araguaina), ~1.700 linhas de leitura. Para 5 ausentes (Miracema, primeira tentativa), pedi que lesse 24 fichas — ~7.200 linhas. Inviavel.

Na Fase 3a, significava: 1 ficha microrregional + 11-25 fichas V2 + producao de front matter + concatenacao. Para Porto Nacional (11 fichas), ~4.000 linhas de leitura + ~4.000 linhas de escrita. No limite. Para Bico (25 fichas), ~8.500 linhas de leitura + ~8.000 linhas de escrita. Impossivel.

**A fronteira pratica ficou em torno de 5.000-6.000 linhas totais** (leitura + escrita) antes de esgotamento de contexto. Este numero nao estava documentado em lugar algum — foi descoberto empiricamente pelas falhas.

---

## PARTE II — ESCOLHA E ATRIBUTOS DOS AGENTES

### 2.1 Tipos de Agente Disponiveis

O sistema oferece tres tipos de agente:
- **Explore**: Leitura rapida, busca de arquivos, responde perguntas. Nao escreve arquivos.
- **general-purpose**: Leitura + escrita + raciocinio complexo. O mais versatil.
- **Plan**: Planejamento sem execucao.

### 2.2 Modelos Disponiveis

- **Opus 4.6** (o orquestrador): Mais capaz, mais lento, mais caro. Herdado por default.
- **Sonnet 4.5**: Equilibrio entre capacidade e velocidade.
- **Haiku 4.5**: Rapido e barato, menos capaz para tarefas complexas.

### 2.3 Decisoes de Selecao

**Fase 0 — Fichas V2:**
- **Tipo:** `general-purpose` (precisa ler e escrever)
- **Modelo:** `sonnet` (escolha explicita)
- **Justificativa:** Tarefa padronizada, mesma estrutura para todos. Nao exige o raciocinio mais avancado do Opus. Sonnet tem throughput maior e custo menor — critico para 176 lancamentos.
- **Modo:** Background (nao bloqueia o orquestrador)

**Fase 2 — Revisao microrregional:**
- **Tipo:** `general-purpose` (precisa ler fichas V2 e reescrever ficha microrregional)
- **Modelo:** `inherited` (Opus 4.6, herdado do orquestrador)
- **Justificativa:** Tarefa analitica complexa — integrar dados de municipios ausentes em um documento existente, preservando coerencia. Exige julgamento sobre onde e como inserir informacoes. Opus era necessario.
- **Modo:** Background

**Fase 3a — Volumes monoliticos:**
- **Tipo:** `general-purpose`
- **Modelo:** `inherited` (Opus 4.6)
- **Justificativa:** A tarefa mais complexa — ler dezenas de fichas, analisar padroes transversais, escrever sumario executivo original, e concatenar tudo. Opus era indispensavel para a qualidade analitica.
- **Modo:** Background

**Fase 3b — Front matter:**
- **Tipo:** `general-purpose`
- **Modelo:** `sonnet` (escolha explicita)
- **Justificativa:** Apos o fracasso dos agentes monoliticos, a tarefa foi reduzida: ler 4-5 fichas amostrais e gerar ~200-300 linhas de front matter. Sonnet e suficiente para esta tarefa focada. Mais rapido e permite lancamento de 5 agentes simultaneos sem gargalo.
- **Modo:** Background

**A decisao de modelo reflete um trade-off consciente:**

| Cenario | Modelo | Razao |
|---------|--------|-------|
| Tarefa atomica, padronizada, em massa | Sonnet | Throughput e custo |
| Tarefa analitica complexa, integracao | Opus | Qualidade de raciocinio |
| Tarefa focada, escopo reduzido | Sonnet | Suficiente, mais rapido |

### 2.4 Como Identificar se o Agente e Capaz

Nao existiu avaliacao previa formal. A "avaliacao de capacidade" foi **empirica e iterativa**:

1. **Estimativa intuitiva de carga cognitiva**: Quantos arquivos precisa ler? Quao grande e a saida? Quao complexa e a analise?
2. **Lancamento**: Testar com a configuracao escolhida.
3. **Monitoramento**: Verificar se o agente progride ou trava.
4. **Resultado**: Aceitar ou rejeitar.
5. **Ajuste**: Se falhou, redesenhar a tarefa (nao trocar o agente).

**Insight critico**: Na maioria dos casos, a falha nao era do agente (modelo errado ou tipo errado), mas da **decomposicao da tarefa**. O mesmo Opus que falhou ao tentar produzir um volume de 25 municipios teve sucesso ao gerar front matter de 300 linhas. O problema nao era a "inteligencia" do agente — era o tamanho da tarefa em relacao a janela de contexto.

---

## PARTE III — COMO INSTRUIR AGENTES PARA TRABALHO PARALELO COERENTE

### 3.1 Elementos do Prompt

Cada prompt de agente continha:

1. **Papel**: "You are generating a condensed municipal ficha (V2)" ou "You are revising the microregional ficha for Araguaína"
2. **Contexto**: O que ja existe, o que esta faltando, qual e a situacao atual
3. **Tarefa explicita**: O que fazer, passo a passo
4. **Arquivos de entrada**: Caminhos absolutos de todos os arquivos a ler
5. **Arquivo de saida**: Caminho exato onde escrever o resultado
6. **Restricoes**: "Write in Brazilian Portuguese", "Preserve the existing document structure", "Keep it concise (~200-300 lines)"
7. **Contexto territorial**: Informacoes especificas da microrregiao (ex: "Araguaína is 2nd largest city", "Bico do Papagaio has the highest social vulnerability")

### 3.2 Estrategia de Coerencia

Para garantir coerencia entre agentes trabalhando em paralelo:

**a) Template implicito por exemplo:**
Na Fase 0, cada agente recebia o mesmo prompt de condensacao e a mesma ficha exemplo (Aguiarnopolis aprovada). Isso criou um "contrato" de formato sem precisar especifica-lo verbalmente — o exemplo era a especificacao.

**b) Metadados canonicos compartilhados:**
Todos os agentes recebiam a mesma lista de municipios por microrregiao, os mesmos caminhos de arquivo, e os mesmos metadados (responsavel tecnico, framework, data). Nao havia espaco para divergencia nestes elementos.

**c) Independencia por design:**
Os agentes da Fase 0 nao dependiam uns dos outros — cada um processava um municipio diferente. Os agentes da Fase 2 tambem eram independentes — cada um revisava uma microrregiao diferente. Nao havia necessidade de sincronizacao.

**d) Onde a coerencia falhou:**
Os agentes da Fase 3a (volumes monoliticos) produziam front matters com estilos ligeiramente diferentes. Quando os agentes da Fase 3b geraram front matters, cada um escreveu com voz propria. Os sumarios executivos tem profundidade e enfase variaveis — o de Araguaina e mais detalhado que o de Gurupi, por exemplo. **Esta variacao e um custo aceito da paralelizacao.**

### 3.3 Evolucao dos Prompts ao Longo da Sessao

Os prompts evoluiram visivelmente entre os ciclos:

**Fase 0, ciclo inicial (Agentes #6-#10):**
```
Você é um analista de inteligência territorial do Caderno Tocantins 2026.
Sua tarefa é condensar uma ficha municipal completa no formato V2 (5-7 páginas).

INSTRUÇÕES:
1. Leia o prompt de condensação em: [caminho]
2. Leia a ficha exemplo: [caminho]
3. Leia a ficha completa: [caminho]
4. Gere a versão V2 e escreva em: [caminho]
```

**Fase 0, ciclo tardio (Agentes #105+):**
```
You are generating a condensed municipal ficha (V2) for the Caderno Tocantins 2026 project.

TASK: Read the condensation prompt, the example V2 ficha, and the complete ficha
for [MUNICIPIO], then generate the condensed V2 version and write it to the output file.

STEPS:
1. Read the condensation prompt: [caminho]
2. Read the approved example V2: [caminho]
3. Read the complete ficha: [caminho]
4. Generate and write to: [caminho]
```

**Mudancas observaveis:**
- Idioma passou de portugues para ingles (prompts em ingles sao mais eficientes com modelos treinados majoritariamente em ingles)
- Estrutura passou de paragrafo para steps numerados
- Instrucoes ficaram mais diretas ("TASK" + "STEPS" em vez de "INSTRUÇÕES")
- O papel discursivo ("Você é um analista...") foi substituido por uma descricao tecnica ("You are generating...")

Estas mudancas nao foram planejadas. Emergiram da observacao de que agentes com prompts em ingles, estruturados por passos, tinham resultados mais consistentes.

**Fase 2, primeira tentativa (Agente #189 — Miracema):**
Prompt longo (2.382 chars) pedindo que o agente lesse TODAS as 24 fichas V2 da microrregiao.

**Fase 2, segunda tentativa (Agente #195 — Miracema, relancamento):**
Prompt mais longo (2.886 chars) mas com instrucao diferente: ler apenas as 5 fichas ausentes + 2-3 existentes para referencia.

**Fase 2, terceira tentativa (Agente #208 — Miracema, com dados pre-extraidos):**
Prompt ainda mais longo (4.584 chars) mas com DADOS DIRETAMENTE NO PROMPT — nao pede ao agente para ler as fichas, fornece os dados-chave de cada municipio ausente diretamente no texto do prompt.

**Esta progressao e a evidencia mais clara de aprendizagem durante a sessao**: de "leia tudo" para "leia apenas o necessario" para "aqui estao os dados, integre-os".

### 3.4 Evolucao dos Prompts — Fase 3

**Fase 3a, volumes monoliticos (Agentes #201-#207):**
Prompts longos (~4.000 chars) com instrucoes detalhadas para cada secao do volume. Pediam ao agente para ler TODOS os arquivos E produzir o volume completo.

Exemplo do prompt do Vol 2 (Porto Nacional, 11 mun.):
```
You need to produce Volume 2 of the Caderno Tocantins 2026: **Porto Nacional** microregion.

**Volume structure** (single markdown file):
1. CAPA
2. FICHA TÉCNICA
3. ÍNDICE
4. APRESENTAÇÃO
5. SUMÁRIO EXECUTIVO
6. FICHA DA MICRORREGIÃO
7. FICHAS MUNICIPAIS V2

**Steps:**
1. Read all source files [11 fichas + 1 ficha microrregional]
2. Generate the CAPA [template fornecido]
3. Generate FICHA TÉCNICA
4. Generate ÍNDICE
5. Generate APRESENTAÇÃO [contexto fornecido]
6. Generate SUMÁRIO EXECUTIVO [analitico, baseado em todas as fichas]
7. Append the microregion ficha
8. Append all 11 V2 fichas in alphabetical order
9. Write to output path
```

**Fase 3b, front matter focado (Agentes #209-#213):**
Prompts mais curtos (~700 chars) com escopo radicalmente reduzido:
```
Generate ONLY the front matter (capa, ficha técnica, índice, apresentação,
sumário executivo) for Volume 3 of Caderno Tocantins 2026.

Read a sample of 5-6 V2 fichas from this microregion to extract patterns:
- [5 fichas especificas escolhidas pelo orquestrador]

Write the front matter to: /home/.../front-matter-vol3.md

Write in Brazilian Portuguese. Keep it concise (~200-300 lines total).
```

**A diferenca critica**: Na Fase 3a, o agente devia ler 11-25 fichas. Na Fase 3b, lia apenas 4-5 fichas **escolhidas pelo orquestrador** como amostra representativa.

---

## PARTE IV — AVALIACAO DE QUALIDADE

### 4.1 Mecanismos de Avaliacao

**Avaliacao automatizada (Fase 0 — Fichas V2):**
- Script Python contava fichas produzidas: 139 necessarias, verificar quantas existiam
- Verificacao de estrutura: todas as fichas tinham secoes obrigatorias (Perfil do Eleitorado, 4 Prioridades)
- Verificacao de labels: microrregiao correta em cada ficha

**Avaliacao por tamanho (Fase 2 — Revisao microrregional):**
- Comparar numero de linhas antes e depois da revisao
- Se Araguaina era 1.211 linhas e precisava integrar 2 municipios, o resultado deveria ser > 1.300 linhas
- Araguaina ficou com 1.503 linhas (+292 linhas) — plausivel para 2 municipios adicionados

**Avaliacao por contagem (Fase 3 — Volumes):**
- Script Python extraia nomes de municipios de cada volume
- Comparava com lista canonica da microrregiao
- Se Vol 9 tinha 12/13 municipios, falhava na validacao

**Avaliacao por completude (Fase 3a — Volumes monoliticos):**
- Agentes que esgotaram contexto retornavam compaction summaries em vez de volumes
- Facilmente detectaveis: o arquivo de saida nao existia ou estava incompleto
- Agentes bem-sucedidos produziam arquivos > 200 KB

### 4.2 O Que NAO Foi Avaliado

- **Precisao factual**: Nenhum dado numerico nas fichas V2 foi verificado contra fontes primarias
- **Qualidade analitica dos sumarios**: Nao foi feita leitura humana dos 8 sumarios executivos
- **Consistencia de estilo entre volumes**: Cada agente escreveu com voz propria
- **Completude do front matter**: O front matter baseado em 4-5 amostras pode nao capturar padroes presentes nos outros 10-20 municipios

**Isso representa um trade-off consciente: amplitude (139 municipios, 8 volumes) versus profundidade (verificacao manual de cada elemento).**

### 4.3 Criterios de Sucesso vs. Fracasso

| Criterio | Sucesso | Fracasso |
|----------|---------|----------|
| Arquivo de saida existe | Agente concluiu | Agente esgotou contexto |
| Tamanho plausivel | > 200 KB para volumes | < 100 KB (incompleto) |
| Municipios presentes | N/N confirmados | < N (Araguacu ausente no Vol 9) |
| Estrutura preservada | Secoes obrigatorias presentes | Secoes faltantes |
| Labels corretos | Microrregiao canonica | Label legado do Vol 1 |

---

## PARTE V — COMO LIDAR COM TRABALHO INSATISFATORIO

### 5.1 Decisao: Aprimorar vs. Relançar vs. Redesenhar

A sessao apresentou tres situacoes distintas de trabalho insatisfatorio, com respostas diferentes:

**Situacao 1: Miracema — Agente #189 (primeiro lancamento)**
- **Problema**: Agente tentou ler 24 fichas V2 e esgotou contexto antes de produzir resultado
- **Diagnostico**: A tarefa era grande demais para a janela de contexto
- **Decisao**: Relançar com escopo reduzido (Agente #195 — ler apenas 5 fichas ausentes + 2-3 existentes)
- **Resultado do relancamento**: Tambem falhou (ainda muito material)
- **Decisao final**: Redesenhar completamente (Agente #208 — dados pre-extraidos no prompt)
- **Logica**: Nao adiantava "tentar de novo" com a mesma abordagem. O problema era estrutural, nao aleatorio.

**Situacao 2: Volumes monoliticos — Agentes #204-#207 (Araguaina, Bico, Gurupi, Dianopolis)**
- **Problema**: 4 de 4 agentes esgotaram contexto
- **Diagnostico**: Padrão — nao era falha individual, era falha sistematica. A abordagem estava errada.
- **Decisao**: NAO relançar. Redesenhar completamente a abordagem (split strategy).
- **Logica**: Quando 4/4 tentativas falham da mesma forma, o problema nao e do agente — e do design da tarefa. Relançar seria insistir em abordagem comprovadamente inviavel.

**Situacao 3: Vol 9 — Municipio Araguacu ausente**
- **Problema**: Volume produzido com 12/13 municipios
- **Diagnostico**: Agente "esqueceu" um municipio ao concatenar (provavelmente atingiu limite de contexto no final)
- **Decisao**: NAO relançar. Correcao cirurgica via script Python (inserir a ficha faltante na posicao correta).
- **Logica**: O volume estava 99% correto. Relançar destruiria o trabalho bom para corrigir um problema pontual. Correcao minimamente invasiva era preferivel.

### 5.2 Arvore de Decisao Implicita

```
Resultado insatisfatorio
|
|-- Agente nao produziu resultado (esgotou contexto)
|   |
|   |-- E caso isolado?
|   |   |-- Sim: Relançar com escopo reduzido
|   |   |-- Nao (padrao): Redesenhar a tarefa
|   |
|   |-- Mesmo agente ja falhou antes na mesma tarefa?
|       |-- Sim: Redesenhar RADICALMENTE (fornecer dados no prompt)
|       |-- Nao: Relançar com ajustes menores
|
|-- Agente produziu resultado, mas com problemas
    |
    |-- Problema e pontual/cirurgico?
    |   |-- Sim: Correcao manual (script/edit)
    |   |-- Nao: Relançar ou redesenhar
    |
    |-- Resultado esta > 80% correto?
        |-- Sim: Corrigir o que falta, manter o resto
        |-- Nao: Descartar e redesenhar
```

### 5.3 A Heuristica Central

**Se o agente falhou, o problema provavelmente esta nas instrucoes, nao no agente.**

Dos 213 lancamentos, nenhuma falha foi resolvida trocando o modelo (Opus por Sonnet ou vice-versa). Todas as falhas foram resolvidas por um dos seguintes:

1. **Reduzir o escopo da tarefa** (ler menos arquivos, produzir menos texto)
2. **Fornecer dados diretamente** (em vez de pedir ao agente para busca-los)
3. **Separar leitura de producao** (agentes diferentes para analisar e para montar)
4. **Correcao cirurgica** (manter 99% do resultado e corrigir 1%)

---

## PARTE VI — DIAGNOSTICANDO PROBLEMAS DE CONTEXTO VS. INSTRUCOES

### 6.1 Sinais de que o Problema e o Contexto

- **Compaction summaries**: O agente esgotou a janela de contexto. O sistema automaticamente compactou o historico e tentou continuar — mas o agente perdeu acesso aos dados que ja havia lido.
- **Arquivo de saida inexistente**: O agente nunca chegou a etapa de escrita.
- **Padrao consistente**: Multiplos agentes com a mesma configuracao falham de forma identica.
- **Correlacao com tamanho**: Agentes com mais arquivos para ler falham mais.

### 6.2 Sinais de que o Problema sao as Instrucoes

- **Resultado existe, mas incompleto**: O agente entendeu a tarefa mas a executou parcialmente.
- **Resultado existe, mas com formato errado**: O agente fez algo diferente do esperado.
- **Resultado inconsistente entre agentes similares**: Um agente produziu formato A, outro produziu formato B.

### 6.3 Evidencia Empirica desta Sessao

| Agente | Mun. | Leitura Est. | Resultado | Diagnostico |
|--------|------|-------------|-----------|-------------|
| #201 Vol 2 | 11 | ~4.000 lin | Sucesso (248 KB) | Dentro do limite |
| #202 Vol 8 | 15 | ~5.500 lin | Sucesso (319 KB) | No limite |
| #203 Vol 9 | 13 | ~4.800 lin | Sucesso com bug (12/13) | Quase no limite |
| #204 Vol 3 | 17 | ~6.200 lin | Falha (compaction) | Acima do limite |
| #205 Vol 4 | 25 | ~8.500 lin | Falha (compaction) | Muito acima |
| #206 Vol 6 | 14 | ~5.200 lin | Falha (compaction) | Acima do limite |
| #207 Vol 7 | 20 | ~7.000 lin | Falha (compaction) | Acima do limite |

A fronteira de viabilidade ficou entre 13-15 municipios (~5.000-5.500 linhas de leitura). Acima disso, falha sistematica. Abaixo, sucesso.

**O Vol 9 (13 municipios) e particularmente revelador**: funcionou, mas "quase falhou" — produzindo resultado com 1 municipio ausente. Sugere que 13 municipios estava no limite exato da janela.

### 6.4 Licao Nao-Obvia

**O agente nunca "reclama" que a tarefa e grande demais.** Ele tenta executar, come contexto lendo arquivos, chega no ponto de precisar escrever o resultado, e ja nao tem espaco. O fracasso e silencioso e tardio — nao ha warning antecipado.

Isso significa que o orquestrador precisa **antecipar** o problema antes de lancar o agente. A unica forma de fazer isso e ter experiencia empirica com os limites do sistema.

---

## PARTE VII — A SESSAO COMO SISTEMA ADAPTATIVO

### 7.1 Mapa Temporal das Adaptacoes

```
[T0] Tarefa definida: produzir 8 volumes

[T1] Fase 0 — Producao de fichas V2 (176 agentes, Sonnet)
     Estrategia: 1 agente = 1 municipio (atomico, paralelo)
     Resultado: 139/139 fichas produzidas (com relancamentos)
     Adaptacao: prompts evoluiram de PT para EN, de paragrafo para steps

[T2] Fase 1 — Correcao de labels (sem agentes, Python)
     Descoberta: 61/139 incorretos (3x mais que estimado)
     Adaptacao: shell grep/sed falhou → Python re.search

[T3] Fase 2 — Revisao microrregional (12 agentes, Opus)
     Estrategia: 1 agente = 1 microrregiao
     Resultado: 5/6 sucesso. Miracema falhou 2x.
     Adaptacao T3a: Miracema — reduzir escopo (ler menos fichas)
     Adaptacao T3b: Miracema — fornecer dados no prompt

[T4] Fase 3a — Volumes monoliticos (7 agentes, Opus)
     Estrategia: 1 agente = 1 volume completo
     Resultado: 3/7 sucesso (volumes pequenos). 4/7 falha.
     Descoberta: limite pratico ~13-15 municipios por agente

[T5] Fase 3b — Split strategy (5 agentes, Sonnet + script Python)
     Estrategia: agente gera front matter → script monta volume
     Resultado: 5/5 sucesso
     Descoberta: "producao analitico-mecanica" como padrao

[T6] Validacao — Script Python conta municipios
     Resultado: 138/139 (Araguacu ausente no Vol 9)
     Adaptacao: correcao cirurgica via script

[T7] 8 volumes publicados, 139/139 municipios confirmados
```

### 7.2 Metricas de Eficiencia

| Fase | Agentes | Sucesso | Falha | Taxa | Modelo |
|------|---------|---------|-------|------|--------|
| 0: Fichas V2 | ~176 | ~139 | ~37 | ~79% | Sonnet |
| 2: Revisao microrregional | 12 | 10 | 2 | 83% | Opus |
| 3a: Volumes monoliticos | 7 | 3 | 4 | 43% | Opus |
| 3b: Front matter focado | 5 | 5 | 0 | 100% | Sonnet |

**A taxa de sucesso cresce conforme a tarefa se torna mais focada**, nao conforme o modelo se torna mais capaz. Os agentes Sonnet na Fase 3b (100%) tiveram melhor taxa que os agentes Opus na Fase 3a (43%).

### 7.3 Custo das Adaptacoes

Cada adaptacao teve um custo:

- **Miracema (3 tentativas)**: ~45 minutos de latencia e contexto do orquestrador
- **Mudanca para split strategy**: ~30 minutos para criar o script Python e redesenhar os prompts
- **Relancamento de fichas V2 com erros**: ~37 agentes adicionais

O custo total de adaptacao foi significativo — talvez 30-40% do tempo total da sessao. Mas sem ele, 5 dos 8 volumes nao teriam sido produzidos.

---

## PARTE VIII — REFLEXOES PARA A PESQUISA

### 8.1 Sobre Orquestracao como Metacognicao

Orquestrar agentes IA e, na pratica, um exercicio de **metacognicao aplicada**: pensar sobre como outro "pensador" (o agente) vai pensar sobre a tarefa. Envolve:

- Antecipar quanta informacao o agente pode processar
- Prever onde a tarefa vai exigir mais raciocinio vs. mais memoria
- Decidir o que fornecer no prompt vs. o que pedir ao agente para buscar
- Reconhecer quando redesenhar a tarefa vs. quando insistir

Esta competencia nao tem nome estabelecido. Nao e programacao (nao envolve codigo). Nao e gestao de pessoas (agentes nao tem motivacao ou politica). E algo novo — **design de tarefas cognitivas para agentes nao-humanos**.

### 8.2 Sobre o Papel do Fracasso

As 4 falhas da Fase 3a foram mais valiosas que os 3 sucessos. Os sucessos confirmaram o que ja se esperava. As falhas revelaram um limite ate entao desconhecido (janela de contexto como gargalo de integracao) e motivaram a invencao de uma abordagem superior (split strategy).

Se todos os 7 agentes tivessem funcionado, o resultado seria identico em termos de produto final, mas o **conhecimento processual** seria pior — nao teriamos descoberto os limites praticos nem a solucao mais robusta.

### 8.3 Sobre Escala e Qualidade

A sessao produziu ~905 paginas em ~8 horas. Nenhum ser humano individual produz 905 paginas de analise territorial em 8 horas — nem em 8 semanas. Mas "paginas produzidas" nao e a metrica certa.

A metrica mais relevante e: **essas 905 paginas sao uteis para o publico-alvo?** Um assessor politico em visita a Carrasco Bonito encontrara dados relevantes na ficha do municipio? O sumario executivo do Bico do Papagaio captura os padroes reais da regiao?

Estas perguntas nao podem ser respondidas por validacao automatizada. Exigem leitura humana, uso em campo, e feedback do territorio. O que esta sessao produziu nao e "inteligencia territorial" — e **materia-prima estruturada** para inteligencia territorial.

### 8.4 Sobre Reprodutibilidade

Dos 213 agentes, os mais reprodutiveis sao os da Fase 0 (fichas V2): mesmo prompt, mesmo template, diferentes entradas, mesma saida. E praticamente uma funcao pura.

Os menos reprodutiveis sao os da Fase 3b (front matter): se lancados novamente com as mesmas fichas amostrais, produziriam sumarios executivos diferentes. A "criatividade" do agente e nao-deterministica.

O script `assemble-volumes.py` e 100% reprodutivel. Se executado novamente com os mesmos inputs, produz exatamente o mesmo output.

**Um sistema robusto maximiza a camada deterministica e minimiza a superficie de contato com a nao-determinismo.** A split strategy faz exatamente isso: reduz o nao-determinismo ao front matter (~200-300 linhas) e torna a montagem (~5.000-8.000 linhas) completamente deterministica.

---

## APENDICE A — INDICE DOS 213 AGENTES

| # | Fase | Descricao | Modelo | Tipo | Resultado |
|---|------|-----------|--------|------|-----------|
| 1-5 | Exploratoria | Exploracao do codebase | inherited | Explore | Sucesso |
| 6-181 | 0 | Producao de fichas V2 (139 mun.) | sonnet | general-purpose | ~79% sucesso |
| 182-188 | Exploratoria | Mapeamento microrregional | inherited | Explore/general | Sucesso |
| 189 | 2 | Revisao Miracema (1a tentativa) | inherited | general-purpose | Falha |
| 190-194 | 2 | Revisao Araguaina/Bico/Dianopolis/Gurupi | inherited | general-purpose | Sucesso |
| 195 | 2 | Revisao Miracema (2a tentativa) | inherited | general-purpose | Falha |
| 196-200 | 2 | Revisao Araguaina/Bico/Dianopolis/Gurupi/Verificacao (2o ciclo) | inherited | general-purpose | Sucesso |
| 201 | 3a | Vol 2 Porto Nacional (11 mun.) | inherited | general-purpose | Sucesso |
| 202 | 3a | Vol 8 Jalapao (15 mun.) | inherited | general-purpose | Sucesso |
| 203 | 3a | Vol 9 Rio Formoso (13 mun.) | inherited | general-purpose | Sucesso* |
| 204 | 3a | Vol 3 Araguaina (17 mun.) | inherited | general-purpose | Falha |
| 205 | 3a | Vol 4 Bico (25 mun.) | inherited | general-purpose | Falha |
| 206 | 3a | Vol 6 Gurupi (14 mun.) | inherited | general-purpose | Falha |
| 207 | 3a | Vol 7 Dianopolis (20 mun.) | inherited | general-purpose | Falha |
| 208 | 3c | Miracema (dados pre-extraidos) | inherited | general-purpose | Sucesso |
| 209 | 3b | Front matter Vol 3 Araguaina | sonnet | general-purpose | Sucesso |
| 210 | 3b | Front matter Vol 4 Bico | sonnet | general-purpose | Sucesso |
| 211 | 3b | Front matter Vol 6 Gurupi | sonnet | general-purpose | Sucesso |
| 212 | 3b | Front matter Vol 7 Dianopolis | sonnet | general-purpose | Sucesso |
| 213 | 3b | Front matter Vol 5 Miracema | sonnet | general-purpose | Sucesso |

*Vol 9 sucesso com bug: 12/13 municipios, corrigido por script.

---

## APENDICE B — PROMPTS REPRESENTATIVOS VERBATIM

### B.1 Prompt Padrao da Fase 0 (Sonnet, ficha V2)

```
You are generating a condensed municipal ficha (V2) for the Caderno
Tocantins 2026 project.

TASK: Read the condensation prompt, the example V2 ficha, and the
complete ficha for [MUNICIPIO], then generate the condensed V2 version
and write it to the output file.

STEPS:
1. Read the condensation prompt:
   /home/.../prompts/PROMPT-FICHA-MUNICIPAL-CONDENSADA.md
2. Read the approved example V2:
   /home/.../fichas-v2/FICHA-MUNICIPAL-AGUIARNOPOLIS-V2.md
3. Read the complete ficha:
   /home/.../fichas-completas/FICHA-MUNICIPAL-[MUNICIPIO]-COMPLETA.md
4. Generate and write the V2 to:
   /home/.../fichas-v2/FICHA-MUNICIPAL-[MUNICIPIO]-V2.md
```

### B.2 Prompt da Fase 2 — Revisao com Dados Pre-Extraidos (Miracema)

```
You need to revise the microregional ficha for Miracema do Tocantins
to integrate 5 missing municipalities. The current ficha lists 19
municipalities — the correct total is 24.

**5 municipalities to add (key data from their V2 fichas):**

### 1. Divinópolis do Tocantins
- Pop (2022): 7,024 hab (+10.4% since 2010)
- PIB (2021): R$ 249,235 mil | Per capita: R$ 35,676
- IDHM: 0.683 (Médio)
- Paradoxo: crescimento econômico sem desenvolvimento social inclusivo
- Agronegócio: soja 70,458t, milho 47,890t, bovinos 145,993 cabeças

### 2. Dois Irmãos do Tocantins
- Pop (2022): 6,327 hab (-11.6% since 2010, declínio grave)
- IDHM: 0.583 (BAIXO)
[... dados dos 5 municipios diretamente no prompt ...]

**Instructions**: Read the current ficha, integrate this data into
all sections, update all totals and rankings.
```

### B.3 Prompt da Fase 3b — Front Matter Focado (Sonnet)

```
Generate ONLY the front matter (capa, ficha técnica, índice,
apresentação, sumário executivo) for Volume 3 of Caderno Tocantins
2026: Microrregião de Araguaína (17 municipalities).

Read a sample of 5-6 V2 fichas from this microregion to extract
patterns for the sumário executivo:
- FICHA-MUNICIPAL-ARAGUAINA-V2.md
- FICHA-MUNICIPAL-COLINAS-DO-TOCANTINS-V2.md
- FICHA-MUNICIPAL-XAMBIOA-V2.md
- FICHA-MUNICIPAL-BABACULANDIA-V2.md
- FICHA-MUNICIPAL-WANDERLANDIA-V2.md

Write the front matter to: /home/.../front-matter-vol3.md
Write in Brazilian Portuguese. Keep it concise (~200-300 lines total).
```

---

## METADADOS

**Tipo de Documento:** Relato de Orquestracao de Agentes IA (pesquisa-acao)
**Sessao:** session_01Hj1yX6KsVL4QbAqunMSRQv
**Data:** 08 de Fevereiro de 2026
**Autor:** Claude Code (Opus 4.6) sob orientacao de Henrique M. Ribeiro
**Fonte:** Transcript JSONL (7.347 linhas) + extracao automatizada de 213 lancamentos
**Contexto Academico:** Doutorado em Politicas Publicas — Pesquisa-Acao sobre Colaboracao Humano-IA

**Palavras-Chave:** orquestracao de agentes, decomposicao de tarefas, janela de contexto, producao analitico-mecanica, split strategy, prompt engineering, metacognicao computacional, pesquisa-acao

---

*"A arte de programar nao e escrever codigo — e decompor problemas.
A arte de orquestrar agentes IA nao e escrever prompts — e decompor
tarefas na granularidade certa para cada agente."*
