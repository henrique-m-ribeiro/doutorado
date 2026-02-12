# PROJETO DE DOUTORADO - VERSÃO 2.0

**Programa:** Pós-Graduação em Ciência Política
**Instituição:** [Nome da Instituição]
**Doutorando:** Henrique Marques Ribeiro
**Orientador:** Professor Fernando Filgueiras
**Versão:** 2.1 (Atualizada em 12 de Fevereiro de 2026)
**Versão Anterior:** 2.0 (31 de Janeiro de 2026), 1.0 (30 de Janeiro de 2026)

---

## TÍTULO

**Inteligência Territorial e IA na Gestão Pública: Pesquisa-Ação sobre o Sistema Tocantins Integrado para Desenvolvimento Regional**

---

## 1. INTRODUÇÃO

### 1.1 Contextualização

O Brasil enfrenta desafios históricos de desigualdades regionais e territoriais que impactam diretamente a efetividade de políticas públicas. Estados como o Tocantins, criado pela Constituição de 1988, apresentam realidades territoriais complexas: 139 municípios distribuídos em 8 microrregiões, com grandes variações em indicadores de saúde, educação, infraestrutura e desenvolvimento econômico.

A formulação de políticas públicas para essas realidades heterogêneas tradicionalmente se baseia em dados fragmentados, análises setoriais isoladas e conhecimento tácito de gestores. Embora existam fontes oficiais de dados (IBGE, DATASUS, INEP, etc.), a integração e análise multidimensional dessas informações para subsidiar decisões permanece um desafio técnico e metodológico.

Recentemente, sistemas de **inteligência territorial** (IT) baseados em inteligência artificial (IA) emergem como alternativa promissora para transformar dados dispersos em conhecimento acionável para gestão pública. Inteligência territorial, conforme Girardot (2009), refere-se a metodologias, ferramentas e conhecimentos multidisciplinares que integram dados ambientais, sociais, econômicos e de infraestrutura para análise holística de territórios, visando subsidiar tomada de decisão, desenvolvimento sustentável e planejamento territorial.

No entanto, a introdução de sistemas de IT baseados em IA na gestão pública brasileira enfrenta desafios teóricos e práticos significativos:

1. **Metodológicos:** Como desenvolver esses sistemas de forma participativa e contextualizada?
2. **Técnicos:** Como integrar dados heterogêneos e produzir análises multidimensionais confiáveis?
3. **Organizacionais:** Como transformar práticas estabelecidas de gestão pública?
4. **Éticos e de governança:** Como garantir transparência, accountability e uso responsável de IA?
5. **De escalabilidade:** Como transferir experiências bem-sucedidas para outros contextos?

Esta pesquisa aborda esses desafios através do desenvolvimento, implementação e avaliação, via pesquisa-ação, de um sistema de inteligência territorial baseado em IA para o Estado do Tocantins: o **Sistema Tocantins Integrado**. A pesquisa-ação, como metodologia que combina ação e reflexão, produção de conhecimento e transformação da prática, mostra-se particularmente adequada para investigar a introdução de tecnologias disruptivas como IA em contextos organizacionais complexos.

### 1.2 Trabalho Já Realizado e Contexto da Atualização

Esta é a versão 2.0 do projeto, atualizada para refletir **trabalho significativo já realizado** entre novembro de 2025 e janeiro de 2026, documentado em quatro repositórios GitHub que constituem os artefatos técnicos e metodológicos da pesquisa:

**0. framework-v6-mvp** (Ciclo 1 - Nov-Dez 2025) - 🟠 HISTÓRICO
Primeira tentativa de estruturação formal onde metodologia e código técnico estavam misturados. Identificou-se o problema fundamental: confundir processo (metodologia) com produto (sistema). Aprendizados: separar preocupações, usar GitHub para continuidade, empregar múltiplos modelos de IA.
- 183 commits documentando evolução e aprendizados
- Evoluiu para separação em 3 repositórios distintos

**1. tocantins-integrado** (Ciclo 2 - Jan 2026) - 🟡 PAUSADO
Sistema técnico principal com arquitetura de dupla camada (Dashboard + IA de exploração; Sistema multiagentes). Reinício programado após aprendizados do Ciclo 1.
- Camada 1: 90% implementada (falta upload de dados)
- Camada 2: 0% implementada (pausada por pivot emergencial)
- 113 commits em janeiro 2026

**2. ia-collab-os** (Ciclo 2-3 - Jan 2026) - 🟢 ATIVO E PUBLICADO
Framework metodológico para colaboração humano-IA-IA extraído DA PRÁTICA de desenvolver o sistema. Separa metodologia de artefatos técnicos (correção do problema do framework-v6-mvp).
- 9 commits (framework conciso e focado)
- Usado atualmente para produção dos cadernos

**3. caderno-tocantins-2026** (Ciclo 3 - Jan-Fev 2026) - 🟢 ATIVO
Análises territoriais dos 139 municípios do Tocantins. Demanda ORIGINAL que motivou o projeto (pré-GitHub). Retomado manualmente usando ia-collab-os após pivot emergencial.
- 9 volumes concluídos: Volume 1 estadual (v2.0, 579 KB, 12.572 linhas) + Volumes 2-9 regionais (~905 páginas)
- ~177 commits (20 janeiro - fevereiro 2026)
- 213 agentes IA orquestrados em sessão única (8 fev 2026)
- Descoberta da *split strategy* (separação produção analítica vs. mecânica)
- Demonstração prática em escala da metodologia ia-collab-os

**4. doutorado** (Ciclo 3.5 - Fev 2026) - 🟢 ATIVO
Repositório acadêmico central. Após a produção em escala do Ciclo 3, um ciclo de reflexão e organização metodológica (Ciclo 3.5) identificou 6 lacunas e produziu: análise transversal dos 5 repositórios, matriz de dupla leitura produto-tese, mapeamento retroativo ciclos-evidências v2.0, protocolos e templates para sessões futuras, e plano de fortalecimento metodológico em 6 etapas.

**Documentação completa:** `cronologia-real-repositorios.md`, `framework-v6-mvp.md`, `ANALISE-TRANSVERSAL-REPOSITORIOS.md` e `MATRIZ-PRODUTO-TESE.md` no repositório doutorado.

Esta versão também incorpora **nova oportunidade de pesquisa**: audiências públicas sobre inteligência territorial na Comissão de Desenvolvimento Regional (CDR) do Senado Federal, possibilitando ampliar escopo para desenvolvimento regional, coletar dados primários sobre percepções de IT no Brasil, e conectar pesquisa acadêmica com formulação de políticas nacionais.

**Nota de atualização (12 de Fevereiro de 2026):** Esta versão 2.1 incorpora atualizações decorrentes do Ciclo 3.5 (Reflexão e Organização Metodológica), incluindo: conclusão dos 9 volumes do caderno, análise transversal dos 5 repositórios, criação da MATRIZ-PRODUTO-TESE, mapeamento retroativo ciclos-evidências v2.0, e redescobrimento de evidências extensivas nos Ciclos 0-2 (21 diários PA, artigo rascunho, 5 ADRs, piloto Palmas).

### 1.3 Relevância e Justificativa

A relevância desta pesquisa desdobra-se em múltiplas dimensões:

**Relevância Teórica:**
- Contribui para literatura emergente sobre IA em governança e gestão pública
- Aprofunda conhecimento sobre inteligência territorial, conceito pouco explorado no Brasil
- Avança metodologias de pesquisa-ação em desenvolvimento de sistemas de IA
- Investiga padrões de colaboração humano-IA em contextos organizacionais complexos

**Relevância Prática:**
- Produz sistema utilizável para gestão pública do Tocantins
- Gera framework metodológico (ia-collab-os) transferível para outros contextos
- Fornece evidências empíricas sobre transformações organizacionais promovidas por IT
- Subsidia formulação de políticas públicas de desenvolvimento regional

**Relevância Social:**
- Aborda desigualdades territoriais, problema social persistente no Brasil
- Democratiza acesso a análises territoriais sofisticadas
- Promove uso responsável e transparente de IA no setor público
- Articula academia com demandas reais de gestores públicos

**Oportunidade Única:**
- Audiências públicas no Senado Federal possibilitam debate nacional sobre IT
- Momento propício para influenciar políticas públicas de desenvolvimento regional
- Experiência do Tocantins como case concreto para discussão de escalabilidade

---

## 2. PROBLEMA DE PESQUISA

### 2.1 Definição do Problema

O problema central desta pesquisa situa-se na **intersecção entre inteligência territorial, inteligência artificial e gestão pública**: como sistemas de inteligência territorial baseados em IA podem transformar processos de análise territorial, tomada de decisão e formulação de políticas públicas para desenvolvimento regional, e quais são as implicações teóricas e práticas dessa transformação?

Esse problema desdobra-se em três níveis complementares:

**Nível Teórico-Conceitual:**
A literatura sobre inteligência territorial desenvolveu-se primariamente na Europa (Girardot, Masselot, Bertacchini) com foco em participação comunitária e desenvolvimento local bottom-up. No Brasil, o conceito permanece pouco explorado academicamente, embora práticas de geoprocessamento e planejamento territorial sejam comuns. Com a emergência de IA, surgem questões sobre como IT e IA se relacionam, complementam ou conflitam.

**Nível Metodológico:**
Desenvolver sistemas de IA para gestão pública é tecnicamente complexo e politicamente sensível. Abordagens tradicionais de engenharia de software (requisitos → design → implementação → testes) mostram-se inadequadas quando: (a) requisitos emergem da prática; (b) usuários têm baixa literacia tecnológica; (c) contexto muda dinamicamente; (d) questões éticas e de governança são centrais. Pesquisa-ação oferece alternativa, mas sua aplicação ao desenvolvimento de sistemas de IA permanece pouco teorizada.

**Nível Empírico-Prático:**
Gestores públicos estaduais e municipais brasileiros frequentemente carecem de ferramentas e capacidades para análise territorial integrada. Dados existem mas estão dispersos, análises são setoriais, decisões baseiam-se em conhecimento tácito ou pressões políticas. Introduzir sistemas de IT baseados em IA promete transformar essas práticas, mas evidências empíricas sobre como, quando e sob quais condições essas transformações ocorrem são escassas.

### 2.2 Pergunta Central de Pesquisa

> **"Como um sistema de inteligência territorial baseado em IA, co-criado através de pesquisa-ação, pode transformar a formulação de políticas públicas e a governança para desenvolvimento regional no Brasil, e quais são as implicações desse processo para a colaboração humano-IA e para a gestão pública?"**

### 2.3 Perguntas Secundárias

**PS1. Metodologia de Desenvolvimento (Pesquisa-Ação e IA):**
Como a pesquisa-ação pode viabilizar o desenvolvimento colaborativo e contextualizado de sistemas de inteligência territorial baseados em IA? Quais princípios, processos e desafios caracterizam essa abordagem metodológica?

**PS2. Fundamentação Teórica (Inteligência Territorial):**
Como o conceito de inteligência territorial, desenvolvido na literatura europeia, pode ser adaptado e aplicado ao contexto brasileiro de desenvolvimento regional e gestão pública? Qual a relação entre IT tradicional e IT baseada em IA?

**PS3. Transformações na Gestão Pública:**
Quais transformações (em processos, práticas, capacidades e resultados) são produzidas pela introdução de sistema de inteligência territorial em processos de análise territorial, tomada de decisão e formulação de políticas públicas para desenvolvimento regional?

**PS4. Padrões de Colaboração Humano-IA:**
Que padrões de colaboração emergem entre gestores públicos, técnicos e sistemas de IA no processo de análise territorial e formulação de políticas? Como caracterizar e teorizar esses padrões em um framework transferível?

**PS5. Desafios Éticos, de Governança e Participação Democrática:**
Quais desafios éticos, de governança, accountability e participação democrática emergem da utilização de inteligência territorial baseada em IA na gestão pública? Como audiências públicas funcionam como espaço de debate e legitimação? Que princípios e salvaguardas são necessários para uso responsável?

**PS6. Escalabilidade e Transferibilidade:**
Sob quais condições a experiência de inteligência territorial do Tocantins pode ser transferida e escalada para outros contextos de gestão pública e desenvolvimento regional no Brasil? Quais são os facilitadores, barreiras e requisitos para escalabilidade nacional?

### 2.4 Delimitação do Problema

**Delimitação Geográfica:**
Estado do Tocantins (139 municípios, 8 microrregiões), com possibilidade de expansão conceitual via audiências públicas no Senado Federal.

**Delimitação Temporal:**
Novembro 2025 a Agosto 2028 (4 anos de doutorado), com foco nos ciclos de pesquisa-ação realizados nesse período.

**Delimitação Temática:**
Inteligência territorial para desenvolvimento regional; IA em gestão pública; pesquisa-ação em desenvolvimento de sistemas; colaboração humano-IA.

**O que NÃO é objeto desta pesquisa:**
- Desenvolvimento de algoritmos de IA inovadores (usamos modelos existentes)
- Avaliação de impacto eleitoral ou partidário dos cadernos territoriais
- Análise comparativa internacional de sistemas de IT
- Implementação em múltiplos estados simultaneamente

---

## 3. OBJETIVOS

### 3.1 Objetivo Geral

Desenvolver, implementar e avaliar, através de pesquisa-ação, um sistema de inteligência territorial baseado em IA para o Estado do Tocantins, analisando suas implicações para a transformação da gestão pública, da colaboração humano-IA e do desenvolvimento regional, contribuindo para a teoria e prática de inteligência territorial no Brasil.

### 3.2 Objetivos Específicos

**OE1. Pesquisa-Ação e Desenvolvimento de Sistemas de IA**
Adaptar e aplicar o framework de pesquisa-ação ao desenvolvimento colaborativo de sistemas de inteligência territorial baseados em IA, documentando princípios, processos e desafios dessa abordagem metodológica.

*Status: 🔄 AVANÇADO | Evidências: ia-collab-os v1.0; 23+ diários PA (Ciclos 0-3.5); 5 ADRs; sistema de continuidade (precursor); governança (METHODOLOGY+ROLES); mapeamento ciclos-evidências v2.0 | Lacuna: métricas operacionais; validação externa; diálogo com Sein et al. (ADR)*

**OE2. Fundamentação Teórica de Inteligência Territorial**
Revisar, sistematizar e aprofundar a literatura sobre inteligência territorial, conectando-a com IA em governança, colaboração humano-IA e desenvolvimento regional, estabelecendo framework teórico-conceitual para análise do sistema Tocantins Integrado.

*Status: 🔄 EM ANDAMENTO (Prioridade 2026.1) | Evidências parciais: 4 análises dimensionais (~345 KB); revisão incipiente neste projeto; artigo rascunho "The Mediator Effect" | Lacuna: revisão sistemática (15-20 refs); fichar Girardot, Bertacchini, Masselot*

**OE3. Transformações na Gestão Pública e Desenvolvimento Regional**
Identificar, descrever e analisar as transformações produzidas pela introdução do sistema de inteligência territorial nos processos de análise territorial, tomada de decisão e formulação de políticas públicas voltadas ao desenvolvimento regional do Tocantins.

*Status: 🟡 ARTEFATO SEM USO | Evidências: 9 volumes do Caderno Tocantins (~1.150 pág.); piloto Palmas (12 KB, primeiro dado empírico); sistema tocantins-integrado (Camada 1: 90%) | Lacuna: nenhum ator territorial usou os cadernos; piloto sem análise formal; entrevistas pendentes*

**OE4. Padrões de Colaboração Humano-IA**
Caracterizar os padrões de colaboração que emergem entre gestores públicos, técnicos e sistemas de IA no processo de análise territorial e formulação de políticas, propondo um framework de colaboração humano-IA para gestão pública.

*Status: 🔄 RICO MAS NÃO SISTEMATIZADO | Evidências: ia-collab-os (roles CEO/CTO/DEV); 11+ prompts de sessão (evolução H-IA); split strategy (213 agentes); relato de orquestração; 8+ handoffs CEO↔CTO↔DEV | Lacuna: framework teórico não sistematizado; sem diálogo com Dellermann, Jarrahi, Seeber; sem tipologia formal*

**OE5. Desafios Éticos, de Governança e Participação Democrática**
Identificar e analisar os desafios éticos, de governança, accountability e participação democrática que emergem da utilização de inteligência territorial baseada em IA na gestão pública, incluindo análise de audiências públicas como espaço de debate e legitimação, propondo princípios e salvaguardas para seu uso responsável.

*Status: 🟡 PLANEJADO (Audiências são oportunidade) | Justificativa: Audiências públicas trazem dimensão de participação democrática*

**OE6. Escalabilidade e Transferibilidade para Desenvolvimento Regional**
Analisar condições, facilitadores e barreiras para a transferência e escalabilidade da experiência de inteligência territorial para outros contextos de gestão pública e desenvolvimento regional no Brasil, propondo modelo de implementação adaptável e articulando com políticas públicas nacionais.

*Status: 🟡 PLANEJADO (Audiências são oportunidade) | Justificativa: Audiências no Senado possibilitam discussão de escalabilidade nacional*

### 3.3 Matriz de Alinhamento: Perguntas × Objetivos

| Pergunta de Pesquisa | Objetivo Específico | Trabalho Realizado | Próximas Ações |
|----------------------|---------------------|-------------------|----------------|
| **PC:** Como IT baseada em IA pode transformar gestão pública? | OG | Sistema (90%); 9 volumes; framework ia-collab-os | Análise integrada, audiências |
| **PS1:** Como PA viabiliza desenvolvimento? | OE1 | ia-collab-os v1.0; 23+ diários PA; 5 ADRs; mapeamento ciclos-evidências; governança formalizada | Métricas operacionais; validação externa; Artigo 1 |
| **PS2:** Fundamentos de IT | OE2 | 4 análises dimensionais (~345 KB); revisão incipiente; artigo rascunho "The Mediator Effect" | Revisão sistemática (15-20 refs) |
| **PS3:** Transformações na gestão | OE3 | 9 volumes (~1.150 pág.); piloto Palmas; fichas municipais | Validação territorial; entrevistas; observação |
| **PS4:** Padrões de colaboração H-IA | OE4 | Split strategy; 213 agentes; 11+ prompts; roles CEO/CTO/DEV; handoffs formalizados | Sistematizar framework teórico; diálogo com literatura |
| **PS5:** Desafios éticos e governança | OE5 | Reflexões em diários | Audiências, entrevistas, CEP |
| **PS6:** Escalabilidade | OE6 | Arquitetura modular; ia-collab-os transferível; produção em escala demonstrada | Teste em outro contexto; audiências |

---

## 4. REVISÃO DE LITERATURA

### 4.1 Inteligência Territorial: Conceitos e Fundamentos

**4.1.1 Origens e Desenvolvimento do Conceito**

O conceito de inteligência territorial (IT) emergiu na Europa, particularmente na França, nas décadas de 1990-2000, associado a práticas de desenvolvimento territorial participativo e sustentável (Girardot, 2000, 2009; Bertacchini, 2004; Masselot, 2008).

Girardot (2009, p. 23) define IT como:

> "Um meio, uma cultura, um processo de criação de conhecimento e de ação comunitária, que associa observação e pesquisa interdisciplinar, co-produção e apropriação participativa de conhecimento para o desenvolvimento sustentável dos territórios."

Elementos-chave do conceito:
- **Territorialidade:** Foco em territórios específicos (regiões, municípios, comunidades)
- **Multidimensionalidade:** Integração de dados ambientais, sociais, econômicos, culturais
- **Participação:** Envolvimento de atores locais na produção de conhecimento
- **Ação:** Conhecimento territorial visa subsidiar ação e transformação
- **Sustentabilidade:** Desenvolvimento equilibrado e de longo prazo

**4.1.2 IT vs. Conceitos Relacionados**

IT difere de conceitos próximos:
- **Geoprocessamento/SIG:** IT é mais abrangente, incluindo dimensão participativa e ação
- **Smart Cities:** IT foca territórios em geral, não apenas cidades; enfatiza participação vs. tecnologia
- **Business Intelligence:** IT aplica-se a territórios públicos, não apenas organizações privadas
- **Inteligência Competitiva:** IT visa desenvolvimento coletivo, não vantagem competitiva

**4.1.3 Inteligência Territorial no Brasil**

No Brasil, o conceito de IT permanece pouco explorado academicamente. Há práticas correlatas:
- Zoneamento ecológico-econômico (ZEE)
- Planos diretores municipais
- Sistemas estaduais de planejamento
- Análises territoriais setoriais (saúde, educação)

Lacuna: Falta framework integrado e participativo que caracteriza IT europeia. Esta pesquisa visa preencher essa lacuna adaptando IT ao contexto brasileiro.

### 4.2 Inteligência Artificial em Governança e Gestão Pública

**4.2.1 IA no Setor Público: Estado da Arte**

Uso de IA em gestão pública é fenômeno recente e em rápida expansão (Wirtz et al., 2019; Zuiderwijk et al., 2021). Aplicações incluem:
- Análise preditiva de demandas sociais
- Chatbots para atendimento ao cidadão
- Detecção de fraudes e irregularidades
- Otimização de recursos e rotas
- Suporte à tomada de decisão

No Brasil, iniciativas como ChatGPT no governo federal, uso de IA em tribunais, e sistemas de análise de dados sociais indicam tendência crescente.

**4.2.2 Desafios Específicos de IA em Gestão Pública**

Literatura identifica desafios únicos do setor público (Janssen & Kuk, 2016; Wirtz et al., 2019):
- **Transparência e explicabilidade:** Decisões públicas exigem justificação
- **Equidade e viés:** Algoritmos podem perpetuar discriminações
- **Accountability:** Quem responde por decisões algorítmicas?
- **Participação democrática:** IA pode excluir cidadãos de decisões
- **Capacidades organizacionais:** Setor público frequentemente carece de expertise técnica

**4.2.3 IA e Inteligência Territorial: Intersecção Emergente**

Esta pesquisa situa-se na intersecção emergente entre IT e IA. Questões teóricas:
- Como IA pode amplificar capacidades de IT?
- IA mantém ou prejudica dimensão participativa da IT?
- Que novos desafios éticos emergem de IT baseada em IA?

Poucos estudos abordam essa intersecção, constituindo lacuna que esta pesquisa visa preencher.

### 4.3 Pesquisa-Ação e Desenvolvimento de Sistemas de Informação

**4.3.1 Pesquisa-Ação: Princípios e Tradições**

Pesquisa-ação combina produção de conhecimento científico com transformação da prática (Lewin, 1946; Reason & Bradbury, 2001). Características centrais:
- Ciclos iterativos de ação-reflexão-aprendizagem
- Colaboração entre pesquisadores e praticantes
- Foco em problemas práticos relevantes
- Duplo objetivo: resolver problema E produzir conhecimento

Heikkinen et al. (2007) propõem cinco princípios para validação de pesquisa-ação:
1. **Princípio histórico-continuativo:** Pesquisa como narrativa temporal
2. **Princípio reflexivo:** Autorreflexão sobre processo
3. **Princípio dialético:** Tensões e contradições como motor de aprendizagem
4. **Princípio de trabalho:** Conhecimento emerge da prática
5. **Princípio evocativo:** Narrativas envolventes e autênticas

**4.3.2 Action Design Research (ADR)**

Sein et al. (2011) propõem Action Design Research (ADR) especificamente para desenvolvimento de sistemas de informação via pesquisa-ação. ADR enfatiza:
- Artefato tecnológico como resultado central
- Iteração entre construção e avaliação
- Intervenção guiada por teoria, produzindo teoria refinada
- Generalização de aprendizados para outros contextos

Esta pesquisa segue princípios de ADR, produzindo tanto sistema de IT quanto conhecimento teórico-metodológico.

**4.3.3 Desafios de Pesquisa-Ação em Desenvolvimento de IA**

Desenvolver sistemas de IA via pesquisa-ação apresenta desafios específicos:
- IA como "caixa preta" dificulta reflexão dos praticantes
- Ritmo acelerado de desenvolvimento de IA vs. ritmo de reflexão acadêmica
- Questões éticas emergem continuamente durante desenvolvimento
- Colaboração humano-IA muda dinâmica tradicional de PA (pesquisador-praticante)

Esta pesquisa aborda esses desafios documentando-os sistematicamente.

### 4.4 Colaboração Humano-IA

**4.4.1 Teorias de Colaboração Humano-IA**

Literatura emergente sobre colaboração humano-IA (também chamada Human-AI Collaboration ou HAI) investiga como humanos e sistemas de IA trabalham juntos (Jarrahi, 2018; Dellermann et al., 2019; Seeber et al., 2020).

Tipos de colaboração:
- **Aumentação (Augmentation):** IA amplifica capacidades humanas
- **Automação (Automation):** IA substitui tarefas humanas
- **Colaboração híbrida:** Divisão dinâmica de trabalho entre humano e IA

Framework de Dellermann et al. (2019) propõe quatro papéis de IA em colaboração:
1. **Fornecedor de informação:** IA como fonte de dados
2. **Conselheiro:** IA sugere, humano decide
3. **Tutor:** IA ensina humanos
4. **Colega:** IA e humano co-criam

Esta pesquisa investiga colaboração tipo "colega" no desenvolvimento e uso de sistema de IT.

**4.4.2 Colaboração Humano-IA em Contextos Organizacionais**

Pesquisas sobre IA em organizações focam frequentemente em adoção e resistência (Lebovitz et al., 2021). Menos estudos investigam como colaboração efetiva emerge na prática cotidiana.

Esta pesquisa, via pesquisa-ação, documenta processo emergente de colaboração, não apenas resultado final.

### 4.5 Desenvolvimento Regional no Brasil

**4.5.1 Histórico de Políticas Regionais**

Brasil tem longa tradição de políticas de desenvolvimento regional, desde SUDENE (1959) e SUDAM (1966). Celso Furtado (1967) argumentava que desigualdades regionais resultam de estrutura econômica concentradora.

Tocantins, criado em 1988, representa experiência recente de criação de estado para promover desenvolvimento regional. Desafios persistem: economia baseada em agropecuária, baixa industrialização, dependência de transferências federais.

**4.5.2 Planejamento Territorial e Capacidades Estatais**

Capacidade de estados e municípios para planejamento territorial é desigual. Enquanto grandes capitais têm equipes técnicas, municípios pequenos carecem de recursos humanos e tecnológicos para análises territoriais sofisticadas (Grin, 2019).

Inteligência territorial baseada em IA pode democratizar acesso a análises, mas requer alfabetização digital e capacidade de interpretação crítica.

### 4.6 Lacunas da Literatura e Contribuições Esperadas

Esta pesquisa visa preencher lacunas identificadas:

1. **Lacuna teórica em IT no Brasil:** Adaptar conceito europeu de inteligência territorial para contexto brasileiro de desenvolvimento regional e gestão pública.

2. **Lacuna metodológica em PA com IA:** Desenvolver e documentar abordagem de pesquisa-ação para desenvolvimento de sistemas de IA, especialmente sistemas de IT.

3. **Lacuna empírica em transformações:** Produzir evidências sobre como IT baseada em IA transforma práticas de gestão pública, análise territorial e formulação de políticas.

4. **Lacuna em padrões de colaboração H-IA:** Caracterizar padrões emergentes de colaboração humano-IA em contexto de gestão pública territorial.

5. **Lacuna em ética e governança de IT-IA:** Identificar desafios éticos específicos de IT baseada em IA e propor salvaguardas.

6. **Lacuna em escalabilidade:** Analisar condições para transferência e escalabilidade de experiências de IT para outros contextos brasileiros.

---

## 5. METODOLOGIA

### 5.1 Abordagem Geral: Pesquisa-Ação

Esta pesquisa adota **pesquisa-ação** (Action Research - AR) como metodologia principal, combinada com métodos complementares (entrevistas, análise documental, observação participante, grupos focais).

**Justificativa para escolha de pesquisa-ação:**

1. **Natureza do problema:** Desenvolvimento e implementação de sistema de IT requer intervenção prática, não apenas observação.

2. **Contexto dinâmico:** Gestão pública é contexto em constante mudança; PA permite adaptação contínua.

3. **Colaboração essencial:** Sistema deve ser co-criado com gestores, não imposto externamente; PA institucionaliza colaboração.

4. **Duplo objetivo:** Pesquisa visa tanto resolver problema prático (melhorar gestão territorial) quanto produzir conhecimento científico (sobre IT, IA, colaboração H-IA).

5. **Reflexividade:** PA enfatiza aprendizagem através de ciclos de ação-reflexão, fundamental para lidar com tecnologia emergente como IA.

### 5.2 Desenho da Pesquisa-Ação

**Baseado em:** Heikkinen et al. (2007), Sein et al. (2011 - ADR), Baskerville & Wood-Harper (1996)

**Estrutura:** Seis ciclos iterativos de pesquisa-ação (incluindo o Ciclo 3.5 de reflexão intermediária), cada ciclo contendo:
1. **Diagnóstico/Planejamento:** Identificar problema, planejar intervenção
2. **Ação:** Implementar intervenção (desenvolvimento de sistema, análises, audiências)
3. **Avaliação:** Coletar dados, avaliar resultados
4. **Reflexão:** Interpretar resultados, extrair aprendizados
5. **Aprendizagem:** Documentar conhecimento, ajustar teoria

### 5.3 Os Ciclos de Pesquisa-Ação (0 a 5, incluindo 3.5)

**IMPORTANTE:** A cronologia real dos ciclos difere da sequência de commits no GitHub. Ver documentação completa em `cronologia-real-repositorios.md`.

#### **Ciclo 0: Demanda Inicial e Framework Incipiente (Pré-Nov 2025)**

**Status:** ✅ CONCLUÍDO

**Contexto:**
Demanda de produção de cadernos territoriais do Tocantins para subsidiar estratégia eleitoral 2026 surgiu antes de qualquer estruturação formal do projeto de doutorado.

**Ações:**
- Produção manual inicial de análises territoriais
- Uso de IA (modelo Manus) sem framework estruturado
- Trabalho ad hoc, sem versionamento ou documentação sistemática

**Problema identificado:**
Framework incipiente, conhecimento tácito não sistematizado, dependência de único modelo de IA.

**Reflexão:**
Necessidade de framework mais robusto para sistematizar produção e permitir aprendizagem acumulativa.

**Aprendizados:**
- Viabilidade de usar IA para análises territoriais
- Importância de sistematização
- Valor de documentação para continuidade

**Evidências:**
- Trabalho realizado (não versionado no GitHub)
- Memórias e registros informais

---

#### **Ciclo 1: Framework V6 MVP - Sistema Monolítico (Nov-Dez 2025)**

**Status:** ✅ CONCLUÍDO

**Repositório:** github.com/henrique-m-ribeiro/framework-v6-mvp

**Diagnóstico/Planejamento:**
Após Ciclo 0, decidiu-se estruturar formalmente projeto, integrando metodologia de colaboração H-IA com sistema técnico Tocantins Integrado em repositório único.

**Ação:**
- Desenvolvimento do framework-v6-mvp (tudo junto: metodologia + código)
- 183 commits documentando evolução (571 arquivos)
- Tentativa de estruturação completa (React+TS, Node, PostgreSQL, pgvector, RAG, N8N, 19 agentes)

**Avaliação:**
Sistema ficou confuso: metodologia misturada com artefatos técnicos. Difícil manter, replicar e transferir conhecimento. Porém, a análise transversal dos repositórios (fev 2026) revelou que este ciclo é o **mais rico em evidências primárias** de todo o projeto.

**Problema identificado (CRÍTICO):**
Confundir PROCESSO (metodologia de colaboração) com PRODUTO (sistema técnico) em único repositório.

**Reflexão:**
Separação de preocupações é fundamental. Metodologia deve ser independente de artefatos específicos.

**Aprendizados (FUNDAMENTAIS):**
1. ✅ Separar metodologia de artefatos técnicos
2. ✅ Usar GitHub para continuidade entre sessões de trabalho
3. ✅ Benefício de múltiplos modelos de IA (não apenas Manus)
4. ✅ Valor de diários de pesquisa-ação para reflexão

**Evidências:**
- Repositório framework-v6-mvp (183 commits, 571 arquivos)
- **21 diários de pesquisa-ação** (~550 KB) cobrindo 15 sessões — registro reflexivo mais extenso do projeto
- **Artigo rascunho "The Mediator Effect"** (~165 KB, ~40 páginas) com cover letter para ACM TOCHI
- **4 análises dimensionais** do Tocantins (~345 KB): Ambiental, Econômica, Social, Territorial
- **11+ prompts de sessão** — evidência direta da evolução da capacidade de orquestração H-IA
- **Sistema de continuidade** (~52 KB) — precursor direto do ia-collab-os
- Conceitos teóricos emergentes (sessão 5) sobre colaboração H-IA
- Documento framework-v6-mvp.md (análise detalhada)
- Aprendizados documentados

**Transição para Ciclo 2:**
Decisão de REINICIAR separando em 3 repositórios distintos.

---

#### **Ciclo 2: Reinício Programado e Separação (Jan 2026 - 1ª quinzena)**

**Status:** 🟡 PARCIALMENTE CONCLUÍDO (pausado)

**Repositórios:** tocantins-integrado + ia-collab-os

**Diagnóstico/Planejamento:**
Usar aprendizados do Ciclo 1 para reiniciar com separação clara:
- Sistema técnico → tocantins-integrado
- Metodologia → ia-collab-os
- Produto final → cadernos (retomado depois)

**Ação:**
- Desenvolvimento do tocantins-integrado (113 commits, 278 arquivos, 24 PRs em jan/2026)
- Arquitetura de dupla camada definida
- Camada 1 (Dashboard): 90% implementada
- Extração da metodologia em ia-collab-os (9 commits, 39 arquivos)
- **5 Architecture Decision Records (ADRs)** formais documentando decisões-chave
- **Governança formalizada**: METHODOLOGY.md (11 KB) e ROLES.md (9 KB) com papéis CEO/CTO/DEV
- **Piloto Palmas realizado**: primeiro teste empírico com dados reais (89 registros, 49.4% oficiais)
- 4 diários de pesquisa-ação originais (sessões 16-19)

**Avaliação:**
- ✅ Separação metodologia/artefato funcionou
- ✅ ia-collab-os emergiu da prática como contribuição metodológica
- ✅ Disciplina de ADRs e governança formalizada como prática emergente
- ✅ Piloto Palmas forneceu primeiro dado empírico real (motivou ADR-002: dados apenas oficiais)
- ⚠️ Sistema não ficou pronto a tempo para gerar cadernos
- ⚠️ Complexidade técnica maior que previsto

**Problema identificado:**
Deadline de entrega dos cadernos se aproxima, sistema ainda incompleto.

**Reflexão:**
Necessidade de PIVOT: pausar sistema, retomar produção manual usando ia-collab-os. O piloto Palmas revelou que 50.6% dos dados eram estimados, motivando decisão de usar apenas dados oficiais.

**Aprendizados:**
1. ✅ Separação metodologia/artefato é eficaz
2. ✅ Framework ia-collab-os é aplicável independente do sistema
3. ⚠️ Equilíbrio entre inovação técnica e prazos práticos
4. ✅ Metodologia emergiu DA PRÁTICA (não planejada a priori)
5. ✅ ADRs como prática de registro de decisões arquiteturais
6. ✅ Governança formal (roles, handoffs) facilita continuidade entre sessões

**Evidências:**
- tocantins-integrado (113 commits, 278 arquivos, Camada 1: 90%)
- ia-collab-os (9 commits, 39 arquivos, framework publicado)
- **5 ADRs** (~46 KB): metodologia distribuída, dados oficiais, workflow IBGE, coleta por metadados, granularidade territorial
- **Governança** (~20 KB): METHODOLOGY.md + ROLES.md com RACI e limites de autoridade
- **Piloto Palmas** (12 KB): 89 registros, 6/8 coletores com sucesso
- **8+ handoffs** CEO↔CTO↔DEV documentando transições
- 4 diários de PA e meta-análise metodológica (9 KB)
- Issues documentando decisões e complicações

**Transição para Ciclo 3:**
Decisão de PIVOT EMERGENCIAL.

---

#### **Ciclo 3: Pivot Emergencial e Produção em Escala (Jan-Fev 2026)**

**Status:** ✅ CONCLUÍDO

**Repositório:** caderno-tocantins-2026

**Diagnóstico/Planejamento:**
Sistema não ficou pronto. Cadernos precisam ser entregues. Solução: produzir manualmente usando ia-collab-os.

**Ação:**
- PAUSOU implementação do tocantins-integrado
- RETOMOU produção dos cadernos manualmente
- APLICOU framework ia-collab-os sistematicamente
- Produção intensiva: ~177 commits (20 jan - fev 2026)
- **213 agentes IA orquestrados** em sessão única de 8 horas (8 fev 2026)
- **9 volumes produzidos**: Volume 1 estadual (v2.0, 579 KB, 12.572 linhas) + Volumes 2-9 regionais (~905 páginas)
- **Split strategy** descoberta: separação entre produção analítica (IA) e mecânica (scripts)

**Avaliação:**
- ✅ 9 volumes concluídos: 139 municípios, 8 microrregiões, ~1.150 páginas totais
- ✅ Demonstração prática em escala de que ia-collab-os funciona
- ✅ Produto entregue no prazo
- ✅ Split strategy como conhecimento transferível sobre orquestração H-IA
- ⚠️ Processo manual é trabalhoso (justifica retomada do sistema futuro)
- ⚠️ Produção "de gabinete" — sem validação territorial ou participação local

**Reflexão:**
Pivot foi necessário e bem-sucedido. Framework metodológico (ia-collab-os) mostrou-se robusto e independente do sistema técnico em escala industrial (213 agentes). A descoberta da split strategy — separar tarefas analíticas (melhor feitas por IA com contexto) de mecânicas (melhor feitas por scripts reproduzíveis) — é contribuição transferível. Cadernos gerados manualmente servirão como benchmark de qualidade para sistema automatizado futuro.

**Aprendizados:**
1. ✅ ia-collab-os é metodologia transferível e eficaz em escala
2. ✅ Flexibilidade e adaptação são essenciais em PA
3. ✅ Cadernos manuais têm valor como dados para pesquisa
4. ✅ Colaboração humano-IA-IA (múltiplos modelos) é produtiva
5. ✅ Split strategy: separar produção analítica de mecânica aumenta eficiência
6. ✅ Orquestração como competência-chave do pesquisador
7. ⚠️ Tensão entre produção e reflexão exige disciplina explícita

**Evidências:**
- caderno-tocantins-2026 (~177 commits, 9 volumes completos)
- 139 municípios analisados em 9 dimensões (~1.150 páginas)
- Relato de orquestração de 213 agentes (dado único sobre H-IA em escala)
- Split strategy formalizada (produção analítica vs. mecânica)
- 4 diários de PA + 7 handoffs centralizados no repositório doutorado
- Script assemble-volumes.py (reproduzível)
- Aplicação documentada do ia-collab-os

**Transição para Ciclo 3.5:**
A produção em escala revelou tensão entre quantidade de artefatos produzidos e qualidade da base de evidências acadêmicas. Uma autoavaliação crítica identificou 6 lacunas, motivando um ciclo intermediário de reflexão e organização antes de avançar.

---

#### **Ciclo 3.5: Reflexão e Organização Metodológica (Fev 2026)**

**Status:** ✅ CONCLUÍDO

**Repositório:** doutorado

**Diagnóstico/Planejamento:**
Após a produção em escala do Ciclo 3 (9 volumes, 213 agentes), uma autoavaliação crítica identificou **6 lacunas** na base de evidências acadêmicas: (1) ausência de reflexão em primeira pessoa do pesquisador nos diários; (2) diários escritos com assistência de IA (risco de circularidade); (3) produção orientada pela ferramenta, não pelas questões de pesquisa; (4) nenhum ator territorial consultado; (5) tensão entre produto prático e dado de pesquisa não explicitada; (6) evidências dos Ciclos 0-2 desconhecidas ou subestimadas.

**Ação:**
- Análise transversal dos 5 repositórios (inventário completo de todos os artefatos)
- Criação da Matriz de Dupla Leitura Produto-Tese (MATRIZ-PRODUTO-TESE.md)
- Mapeamento retroativo ciclos-evidências v2.0 (MAPEAMENTO-CICLOS-EVIDENCIAS.md)
- Centralização documental: diários, handoffs, ADRs, relatórios, governança
- Formalização dos ciclos PA: planos para Ciclos 4 e 5 com hipóteses testáveis
- Criação de protocolos e templates para sessões futuras
- Plano de Fortalecimento Metodológico em 6 etapas
- Instrução de sessão autocontida para Etapa 4 (ia-collab-os)

**Avaliação:**
- ✅ Redescobrimento de evidências extensivas nos Ciclos 0-2 (21 diários PA, artigo rascunho, 4 análises dimensionais, 5 ADRs, piloto Palmas)
- ✅ Explicitação da tensão produto-tese como princípio orientador (regra 70/30)
- ✅ Base de evidências mapeada: 23+ diários, 15+ handoffs, 5 ADRs, 4 análises dimensionais, relato de orquestração
- ✅ Lacunas acadêmicas identificadas por OE com clareza
- ✅ Plano de Fortalecimento com 4 de 6 etapas concluídas

**Reflexão:**
O Ciclo 3.5 validou o princípio "desacelerar para acelerar" — pausar a produção para organizar retroativamente fortaleceu significativamente a base de evidências. A análise transversal revelou que o projeto era muito mais rico em evidências do que se supunha, mas essas evidências estavam dispersas e desconectadas das questões de pesquisa. O princípio da PA (reflexão sobre a ação) operou aqui de forma exemplar.

**Aprendizados:**
1. ✅ Organização retroativa é tão valiosa quanto produção nova
2. ✅ A tensão produto-tese precisa ser gerida explicitamente (MATRIZ)
3. ✅ Evidências existentes subestimadas por falta de inventário sistemático
4. ✅ Protocolos e templates aumentam consistência entre sessões
5. ✅ Handoffs autocontidos permitem transferência de contexto entre repositórios

**Evidências:**
- ANALISE-TRANSVERSAL-REPOSITORIOS.md (inventário dos 5 repos)
- MATRIZ-PRODUTO-TESE.md (dupla leitura produto-tese)
- MAPEAMENTO-CICLOS-EVIDENCIAS.md v2.0 (mapeamento retroativo completo)
- CICLO-04-PLANO.md e CICLO-05-PLANO.md (com hipóteses testáveis)
- PROTOCOLO-REGISTRO-SESSAO.md e TEMPLATE-DIARIO.md
- INSTRUCAO-SESSAO-ETAPA4-IA-COLLAB-OS.md (~800 linhas, autocontido)
- CLAUDE.md (instruções para agentes IA)
- 10+ diários de sessão centralizados (Ciclos 3 e 3.5)

**Transição para Ciclo 4:**
Com base de evidências organizada, lacunas mapeadas e plano de fortalecimento parcialmente executado, Ciclo 4 pode focar em coleta de dados novos (campo, audiências, entrevistas) com fundamentação mais sólida.

---

#### **Ciclo 4: Retomada, Audiências e Consolidação (2026.2 - 2027.2) PLANEJADO**

**Status:** ⏳ PLANEJADO

**Diagnóstico/Planejamento:**
Com cadernos concluídos, metodologia validada, e oportunidade de audiências públicas no Senado, Ciclo 4 visa:
1. Retomar tocantins-integrado alimentando com dados dos cadernos
2. Realizar audiências públicas sobre IT na CDR
3. Coletar dados primários sobre percepções de IT
4. Completar Camada 1 e iniciar Camada 2

**Ações Planejadas:**
- Completar Camada 1 do sistema (upload de dados dos cadernos)
- Implementar Camada 2 (sistema multiagentes)
- Preparar e realizar audiência(s) pública(s)
- Entrevistas com senadores, gestores, especialistas
- Análise documental de proposições sobre IT
- Observação participante nas audiências
- Grupos focais pós-audiências

**Coleta de Dados:**
- **Técnicos:** Commits, issues, documentação técnica
- **Qualitativos:** Transcrições de audiências, entrevistas, notas de campo
- **Documentais:** Atas, proposições, pareceres
- **Métricas:** Uso do sistema, qualidade de análises

**Reflexão (a realizar):**
- Como audiências influenciaram percepção sobre IT?
- Que novos requisitos emergiram do debate público?
- Como ajustar sistema com base em feedback?

**Aprendizados (a documentar):**
- Condições para legitimação social de IT baseada em IA
- Preocupações éticas e de governança levantadas
- Facilitadores e barreiras para escalabilidade nacional

**Evidências (a coletar):**
- Sistema completo funcionando (tocantins-integrado v2.0)
- Gravações e transcrições de audiências
- Entrevistas transcritas
- Proposições legislativas
- Análises comparativas (cadernos manual vs. sistema)

---

#### **Ciclo 5: Análise Integrada e Defesa (2027.2 - 2028.2) PLANEJADO**

**Status:** ⏳ PLANEJADO

**Diagnóstico/Planejamento:**
Ciclo final foca em consolidação de aprendizados, análise integrada dos ciclos anteriores (0, 1, 2, 3, 3.5, 4), qualificação e defesa da tese.

**Ações Planejadas:**
- Análise transversal dos 6 ciclos (0-5, incluindo 3.5)
- Sistematização de aprendizados cumulativos
- Validação de qualidade (comparar cadernos manual vs. sistema)
- Análise de escalabilidade (condições para transferência)
- Escrita completa da tese
- Qualificação (2027.2)
- Defesa final (2028.2)

**Reflexão (a realizar):**
- Que conhecimento científico foi produzido ao longo dos 5 ciclos?
- Como prática transformou teoria e teoria transformou prática?
- Quais contribuições para literatura de IT, IA em governança, PA, colaboração H-IA?

**Aprendizados (a documentar):**
- Modelo integrado de inteligência territorial baseada em IA
- Framework validado de colaboração humano-IA para gestão pública
- Princípios e salvaguardas para uso responsável de IT-IA
- Condições para escalabilidade nacional

**Evidências (a coletar):**
- Tese completa (250-300 páginas)
- 3-4 artigos publicados ou submetidos
- Apresentações em congressos
- Policy briefs para gestores públicos
- Relatório para Senado Federal

---

### 5.4 Métodos Complementares

Além dos ciclos de PA, métodos complementares serão empregados:

**5.4.1 Entrevistas Semiestruturadas**

**Público-alvo:**
- Gestores públicos estaduais e municipais do Tocantins
- Senadores e assessores da CDR
- Especialistas em inteligência territorial
- Desenvolvedores de sistemas similares

**Objetivos:**
- Compreender percepções sobre IT e IA
- Identificar necessidades e expectativas
- Coletar feedback sobre sistema e metodologia
- Mapear facilitadores e barreiras para adoção

**Quantidade estimada:** 15-20 entrevistas

**5.4.2 Análise Documental**

**Documentos a analisar:**
- Commits e issues dos repositórios (análise de conteúdo)
- Proposições legislativas sobre IT e desenvolvimento regional
- Atas de audiências públicas
- Planos estaduais e municipais de desenvolvimento
- Relatórios de organismos internacionais sobre IT

**5.4.3 Observação Participante**

**Contextos de observação:**
- Audiências públicas no Senado
- Reuniões com gestores públicos
- Sessões de uso do sistema Tocantins Integrado
- Workshops e apresentações

**Registro:** Diário de campo, notas etnográficas

**5.4.4 Grupos Focais**

**Participantes:** Gestores públicos usuários do sistema

**Objetivos:**
- Discutir coletivamente experiências com IT-IA
- Identificar padrões de colaboração humano-IA
- Debater desafios éticos e de governança

**Quantidade estimada:** 2-3 grupos focais (6-8 participantes cada)

### 5.5 Análise de Dados

**5.5.1 Dados Qualitativos**

**Método:** Análise de conteúdo temática (Braun & Clarke, 2006)

**Processo:**
1. Familiarização com dados (leitura repetida)
2. Codificação inicial (códigos descritivos)
3. Identificação de temas (agrupamento de códigos)
4. Revisão de temas (refinamento)
5. Definição e nomeação de temas
6. Redação final

**Software:** NVivo ou ATLAS.ti

**5.5.2 Dados Quantitativos (Métricas de Repositórios)**

**Análises:**
- Estatísticas descritivas de commits, issues, contribuições
- Análise temporal (evolução ao longo dos ciclos)
- Análise de colaboração (razão humano/IA, tipos de contribuição)
- Métricas de sistema (performance, uso)

**Software:** Python (pandas, matplotlib), R

**5.5.3 Triangulação**

Dados de múltiplas fontes serão triangulados para aumentar validade:
- Entrevistas ↔ Observação ↔ Documentos
- Dados qualitativos ↔ Dados quantitativos
- Perspectivas de diferentes stakeholders

### 5.6 Considerações Éticas

**Comitê de Ética:** Projeto será submetido a Comitê de Ética em Pesquisa (CEP) via Plataforma Brasil.

**Consentimento Informado:** Todos participantes (entrevistados, grupos focais) assinarão Termo de Consentimento Livre e Esclarecido (TCLE).

**Anonimização:** Dados serão anonimizados quando necessário para proteger identidade de participantes.

**Dados Sensíveis:** Dados territoriais são públicos, mas cuidado será tomado para não expor informações que possam prejudicar indivíduos ou comunidades.

**Uso Responsável de IA:** Sistemas de IA serão desenvolvidos seguindo princípios de transparência, equidade, accountability (ver Objetivo Específico 5).

### 5.7 Validade e Confiabilidade

**Validação de Pesquisa-Ação (Heikkinen et al., 2007):**

1. **Validação Histórico-Continuativa:** Pesquisa narrada cronologicamente, mostrando evolução temporal dos 5 ciclos.

2. **Validação Reflexiva:** Autorreflexão sistemática documentada em diários de ciclo, análise crítica de decisões.

3. **Validação Dialética:** Tensões e contradições (ex: sistema vs. cadernos manual, inovação vs. prazo) são explicitadas e analisadas.

4. **Validação de Trabalho:** Conhecimento emerge da prática real (desenvolvimento de sistema, audiências públicas, colaboração com gestores).

5. **Validação Evocativa:** Narrativa envolvente e autêntica dos desafios e aprendizados.

**Adicionalmente:**
- **Triangulação:** Múltiplas fontes e métodos
- **Revisão por pares:** Artigos submetidos a periódicos
- **Feedback de stakeholders:** Gestores validam interpretações
- **Transparência:** Repositórios públicos, dados abertos quando possível

---

## 6. CRONOGRAMA

### 6.1 Cronograma Geral (2025-2028)

| Período | Fase Principal | Ciclo PA | Atividades-Chave | Entregas |
|---------|---------------|----------|------------------|----------|
| **2025.2** | Início | Ciclo 0-1 | Framework incipiente; framework-v6-mvp (21 diários, artigo rascunho) | Aprendizados documentados; evidências extensivas |
| **2026.1** | Consolidação | Ciclos 2-3-3.5 | Reinício; Pivot; 9 volumes; Reflexão e organização | Projeto v2.1; MATRIZ; MAPEAMENTO v2.0; Capítulo teórico |
| **2026.2** | Audiências | Ciclo 4 início | Audiências públicas; Retomada sistema | Artigo 1; Relatório Senado |
| **2027.1** | Análise | Ciclo 4 cont. | Análise integrada; Escrita | Artigo 2; Rascunho tese |
| **2027.2** | Qualificação | Ciclo 5 início | Qualificação; Ajustes | Defesa qualificação |
| **2028.1** | Finalização | Ciclo 5 cont. | Escrita final; Revisão | Tese completa; Artigo 3 |
| **2028.2** | Defesa | Ciclo 5 fim | Defesa final | Tese aprovada |

### 6.2 Detalhamento por Semestre

#### **2026.1 (JAN-JUN) - EM ANDAMENTO**

**Mês 1-2 (Jan-Fev):**
- ✅ Organizar repositório doutorado (CONCLUÍDO)
- ✅ Ciclos 2, 3 e 3.5 de PA (CONCLUÍDOS)
- ✅ Produção de 9 volumes do Caderno Tocantins (CONCLUÍDO)
- ✅ Análise transversal dos 5 repositórios (CONCLUÍDO)
- ✅ MATRIZ-PRODUTO-TESE e MAPEAMENTO-CICLOS-EVIDENCIAS v2.0 (CONCLUÍDOS)
- ✅ Plano de Fortalecimento Metodológico: 4/6 etapas concluídas
- ✅ Redigir e revisar projeto v2.0→v2.1 (CONCLUÍDO)
- 🔄 Revisar literatura sobre IT (15-20 refs)

**Mês 3-4 (Mar-Abr):**
- Aprofundar revisão teórica (fichar 10 textos IT)
- Escrever rascunho Cap. 2 (Fundamentação Teórica)
- Documentar trabalho dos repositórios
- Preparar proposta formal audiência pública

**Mês 5-6 (Mai-Jun):**
- Submeter projeto ao CEP
- Reunião com orientador (validar atualizações)
- Escrever artigo 1 (metodologia ia-collab-os)
- Submeter artigo 1 a periódico

**Entregas 2026.1:**
- Projeto v2.0 finalizado
- Capítulo 2 (Fundamentação) - rascunho
- Artigo 1 submetido
- Proposta formal de audiência

#### **2026.2 (JUL-DEZ)**

**Mês 7-8 (Jul-Ago):**
- Realizar audiência(s) pública(s) no Senado
- Transcrever e analisar audiências
- Iniciar entrevistas (5-8 entrevistas)
- Retomar tocantins-integrado (upload dados)

**Mês 9-10 (Set-Out):**
- Completar Camada 1 do sistema
- Continuar entrevistas (mais 5-8)
- Escrever Cap. 3 (Metodologia)
- Análise de dados das audiências

**Mês 11-12 (Nov-Dez):**
- Iniciar Camada 2 do sistema
- Grupos focais (2 grupos)
- Escrever artigo 2 (IT e desenvolvimento regional)
- Relatório para Senado Federal

**Entregas 2026.2:**
- Audiência(s) realizada(s)
- Entrevistas transcritas (15 entrevistas)
- Cap. 3 (Metodologia) - rascunho
- Artigo 2 submetido
- Relatório Senado

#### **2027.1 (JAN-JUN)**

**Mês 13-14 (Jan-Fev):**
- Completar Camada 2 do sistema
- Análise integrada dos Ciclos 1-4
- Escrever Cap. 4 (Ciclos de PA)

**Mês 15-16 (Mar-Abr):**
- Análise comparativa (cadernos vs. sistema)
- Escrever Cap. 5 (Análise Integrada)
- Apresentação em congresso 1

**Mês 17-18 (Mai-Jun):**
- Escrever rascunho Cap. 6 (Discussão)
- Análise de escalabilidade
- Preparar materiais de qualificação

**Entregas 2027.1:**
- Sistema completo (v2.0)
- Cap. 4 e 5 - rascunhos
- Apresentação congresso
- Materiais para qualificação

#### **2027.2 (JUL-DEZ)**

**Mês 19-20 (Jul-Ago):**
- Finalizar documento de qualificação
- Ensaios de apresentação
- **QUALIFICAÇÃO** (Agosto 2027)

**Mês 21-22 (Set-Out):**
- Incorporar feedback da banca
- Revisar capítulos 1-5
- Escrever artigo 3 (colaboração H-IA)

**Mês 23-24 (Nov-Dez):**
- Escrever Cap. 6 (Discussão) - versão final
- Escrever Cap. 7 (Conclusões) - rascunho
- Submeter artigo 3

**Entregas 2027.2:**
- Qualificação aprovada
- Feedback incorporado
- Artigo 3 submetido
- 80% da tese escrita

#### **2028.1 (JAN-JUN)**

**Mês 25-26 (Jan-Fev):**
- Finalizar Cap. 7 (Conclusões)
- Revisão completa Cap. 1-7
- Escrever Abstract/Resumo

**Mês 27-28 (Mar-Abr):**
- Normalização (ABNT, referências)
- Revisão final (português, clareza)
- Preparar apresentação defesa

**Mês 29-30 (Mai-Jun):**
- Depósito da tese (Maio 2028)
- Elaborar policy brief
- Ensaios de defesa

**Entregas 2028.1:**
- Tese depositada
- Apresentação pronta
- Policy brief

#### **2028.2 (JUL-AGO)**

**Mês 31-32 (Jul-Ago):**
- **DEFESA FINAL** (Agosto 2028)
- Incorporar correções da banca
- Versão final da tese

**Entregas 2028.2:**
- Tese aprovada e publicada
- Doutorado concluído

### 6.3 Marcos (Milestones)

| Data | Marco | Descrição |
|------|-------|-----------|
| Jan 2026 | ✅ Ciclos 2-3 concluídos | Repositórios criados; 9 volumes produzidos; 213 agentes orquestrados |
| Fev 2026 | ✅ Ciclo 3.5 concluído | Análise transversal; MATRIZ; MAPEAMENTO v2.0; Plano de Fortalecimento |
| Fev 2026 | ✅ Projeto v2.1 revisado | Incorpora descobertas do Ciclo 3.5 |
| Fev-Mar 2026 | Projeto aprovado pelo orientador | Orientador valida atualizações |
| Jun 2026 | Artigo 1 submetido | Metodologia ia-collab-os (depende de Etapa 4) |
| Ago 2026 | Audiência(s) realizada(s) | IT debatida no Senado |
| Dez 2026 | Sistema Camada 1 completa | Dashboard funcional |
| Jun 2027 | Sistema completo | Camadas 1 e 2 funcionando |
| Ago 2027 | **QUALIFICAÇÃO** | Defesa do projeto |
| Mai 2028 | Tese depositada | Documento completo entregue |
| Ago 2028 | **DEFESA FINAL** | Conclusão do doutorado |

---

## 7. PRODUTOS ESPERADOS

### 7.1 Produto Principal: Tese de Doutorado

**Título:** Inteligência Territorial e IA na Gestão Pública: Pesquisa-Ação sobre o Sistema Tocantins Integrado para Desenvolvimento Regional

**Estrutura (7 capítulos, 250-300 páginas):**

**1. Introdução** (30-40 páginas)
- Contextualização
- Problema de pesquisa
- Objetivos
- Justificativa e relevância
- Estrutura da tese

**2. Fundamentação Teórica** (50-60 páginas)
- Inteligência territorial
- IA em governança e gestão pública
- Pesquisa-ação e ADR
- Colaboração humano-IA
- Desenvolvimento regional no Brasil

**3. Metodologia** (40-50 páginas)
- Pesquisa-ação: justificativa e desenho
- Os 5 ciclos detalhados
- Métodos complementares
- Análise de dados
- Considerações éticas
- Validação

**4. Ciclos de Pesquisa-Ação** (50-60 páginas)
- Ciclo 0: Demanda inicial
- Ciclo 1: framework-v6-mvp (21 diários, artigo rascunho, 4 análises dimensionais)
- Ciclo 2: Reinício e separação (5 ADRs, governança, piloto Palmas)
- Ciclo 3: Pivot emergencial e produção em escala (9 volumes, 213 agentes, split strategy)
- Ciclo 3.5: Reflexão e organização metodológica (análise transversal, MATRIZ, MAPEAMENTO)
- Ciclo 4: Audiências e retomada
- Ciclo 5: Consolidação

**5. Análise Integrada** (40-50 páginas)
- Transformações na gestão pública
- Padrões de colaboração humano-IA
- Framework ia-collab-os
- Sistema Tocantins Integrado
- Cadernos territoriais

**6. Discussão** (30-40 páginas)
- Contribuições teóricas
- Implicações práticas
- Desafios éticos e de governança
- Escalabilidade e transferibilidade
- Limitações da pesquisa

**7. Conclusões** (20-30 páginas)
- Síntese dos achados
- Resposta à pergunta central
- Contribuições para IT, IA, PA
- Recomendações para políticas públicas
- Agenda de pesquisa futura

### 7.2 Artigos Acadêmicos (Meta: 3-4 artigos)

**Artigo 1: Metodologia de Pesquisa-Ação em Desenvolvimento de Sistemas de IA**

- **Título provisório:** "Action Design Research for AI-based Territorial Intelligence Systems: Lessons from a Brazilian Case"
- **Foco:** Framework ia-collab-os, abordagem metodológica, desafios de PA com IA
- **Periódico-alvo:** MIS Quarterly, Information Systems Journal, Information Systems Research
- **Status:** Submeter em Jun 2026
- **Base empírica:** Ciclos 1-3, repositórios

**Artigo 2: Inteligência Territorial e Desenvolvimento Regional**

- **Título provisório:** "Territorial Intelligence for Regional Development in Brazil: Adapting European Concepts to the Brazilian Context"
- **Foco:** Conceito de IT, aplicação no Tocantins, desenvolvimento regional
- **Periódico-alvo:** Revista Brasileira de Gestão e Desenvolvimento Regional, Revista de Administração Pública
- **Status:** Submeter em Dez 2026
- **Base empírica:** Sistema Tocantins Integrado, cadernos, literatura

**Artigo 3: Colaboração Humano-IA em Gestão Pública**

- **Título provisório:** "Patterns of Human-AI Collaboration in Public Sector Territorial Analysis"
- **Foco:** Padrões de colaboração, framework H-IA, transformações organizacionais
- **Periódico-alvo:** Government Information Quarterly, Public Administration Review
- **Status:** Submeter em Dez 2027
- **Base empírica:** Análise de colaboração nos repositórios, entrevistas, grupos focais

**Artigo 4 (Opcional): Participação Democrática e IT**

- **Título provisório:** "Public Hearings as Democratic Legitimation of AI-based Territorial Intelligence"
- **Foco:** Audiências públicas, participação, debate sobre IT
- **Periódico-alvo:** Revista Brasileira de Ciência Política, Opinião Pública
- **Status:** Submeter em Jun 2028
- **Base empírica:** Audiências no Senado, entrevistas, análise documental

### 7.3 Apresentações em Congressos (Meta: 4-6)

**Congressos Nacionais:**
- EnANPAD (2026, 2027, 2028)
- EnAPG (2026, 2027)
- Congresso de Ciência Política (2027)

**Congressos Internacionais:**
- ICIS (International Conference on Information Systems) - 2027
- AMCIS (Americas Conference on Information Systems) - 2027
- EGPA (European Group for Public Administration) - 2028

**Temas das apresentações:**
- Metodologia de PA em IA
- IT no contexto brasileiro
- Colaboração H-IA
- Audiências públicas e legitimação

### 7.4 Produtos Técnicos (Código Aberto)

**7.4.1 Sistema Tocantins Integrado**

- **Repositório:** github.com/henrique-m-ribeiro/tocantins-integrado
- **Versão final:** 2.0 (Camadas 1 e 2 completas)
- **Licença:** Código aberto (MIT ou GPL)
- **Documentação:**
  - README completo
  - Wiki técnica
  - Tutoriais de uso
  - Guia de instalação
  - API documentation

**Funcionalidades:**
- Dashboard interativo
- Análises multidimensionais (saúde, educação, infraestrutura, economia)
- IA assistente para exploração
- Sistema multiagentes para análises sob demanda
- Relatórios automatizados
- Visualizações geográficas

**7.4.2 Framework IA Collab OS**

- **Repositório:** github.com/henrique-m-ribeiro/ia-collab-os
- **Versão final:** 2.0 (validada e refinada)
- **Licença:** Código aberto
- **Documentação:**
  - Framework metodológico completo
  - Templates e workflows
  - Casos de uso
  - Guia de aplicação

**7.4.3 Caderno Tocantins 2026**

- **Repositório:** github.com/henrique-m-ribeiro/caderno-tocantins-2026
- **Versão atual:** 9 volumes concluídos (Volume 1 v2.0 + Volumes 2-9 regionais)
- **Formato:** Markdown
- **Conteúdo:**
  - 139 municípios analisados em 9 dimensões
  - 8 microrregiões documentadas
  - Volume 1 estadual: 579 KB, 12.572 linhas
  - Volumes 2-9 regionais: ~905 páginas
  - Fichas municipais V2
  - Insights territoriais

### 7.5 Produtos para Políticas Públicas

**7.5.1 Relatório para Senado Federal**

- **Título:** "Inteligência Territorial para Desenvolvimento Regional no Brasil: Estado da Arte e Recomendações"
- **Extensão:** 30-50 páginas
- **Público:** Senadores, assessores, gestores públicos
- **Conteúdo:**
  - Definição e fundamentos de IT
  - Experiências internacionais
  - Caso do Tocantins Integrado
  - Benefícios e desafios
  - Recomendações para políticas nacionais
- **Formato:** PDF executivo, linguagem acessível
- **Data:** Antes da audiência pública (Ago 2026)

**7.5.2 Policy Brief**

- **Título:** "Como Implementar Inteligência Territorial para Desenvolvimento Regional: Guia Prático para Gestores Públicos"
- **Extensão:** 4-6 páginas
- **Público:** Gestores estaduais e municipais
- **Conteúdo:**
  - O que é IT
  - Por que usar IT-IA
  - Passo a passo para implementação
  - Lições aprendidas do Tocantins
  - Recursos e contatos
- **Formato:** PDF, infográficos, checklists
- **Data:** Após audiência pública (Dez 2026)

**7.5.3 Apresentação em Audiência Pública**

- **Formato:** Slides + demonstração do sistema
- **Duração:** 20-30 minutos + debate
- **Conteúdo:**
  - Problema das desigualdades regionais
  - O que é IT baseada em IA
  - Case Tocantins Integrado (demonstração)
  - Benefícios comprovados
  - Recomendações para políticas
- **Materiais adicionais:**
  - Vídeo demonstrativo (3-5 min)
  - Folder explicativo
  - QR code para acesso ao sistema

### 7.6 Outros Produtos

**7.6.1 Workshops e Treinamentos**

- Workshop para gestores públicos do Tocantins (uso do sistema)
- Workshop para pesquisadores (metodologia ia-collab-os)
- Minicurso em congresso sobre PA em desenvolvimento de sistemas de IA

**7.6.2 Materiais Educacionais**

- Tutoriais em vídeo (YouTube)
- Postagens em blog acadêmico
- Threads explicativas em redes sociais acadêmicas

**7.6.3 Dados Abertos**

- Datasets territoriais processados (anonimizados quando necessário)
- Código-fonte de análises
- Transcrições de audiências públicas (se permitido)

---

## 8. COERÊNCIA ENTRE PROBLEMA, OBJETIVOS, LITERATURA E METODOLOGIA

### 8.1 Matriz de Coerência Geral

| Elemento | Problema Central | Literatura-Base | Método Principal | Produto Esperado |
|----------|-----------------|----------------|------------------|------------------|
| **IT baseada em IA** | Como transformar gestão pública? | Girardot, Bertacchini, Masselot | PA Ciclos 1-5 | Sistema Tocantins Integrado |
| **Metodologia de PA em IA** | Como desenvolver colaborativamente? | Heikkinen, Sein et al., Baskerville | ADR, 5 ciclos | Framework ia-collab-os |
| **Transformações organizacionais** | Que mudanças ocorrem? | Wirtz et al., Janssen & Kuk | Entrevistas, observação, métricas | Cap. 5 (Análise Integrada) |
| **Colaboração H-IA** | Que padrões emergem? | Dellermann, Jarrahi, Seeber | Análise de repositórios, grupos focais | Framework H-IA, Artigo 3 |
| **Ética e governança** | Que desafios éticos? | Literatura AI ethics | Audiências públicas, entrevistas | Princípios e salvaguardas |
| **Escalabilidade** | Como transferir? | Furtado, Tânia Bacelar | Audiências, análise comparativa | Modelo de implementação |

### 8.2 Alinhamento Detalhado

**CONSISTÊNCIA DA PROPOSTA (20% da nota):**

A proposta é **internamente consistente**: 
- Título, problema, objetivos, metodologia e produtos estão alinhados
- Foco claro em IT baseada em IA para desenvolvimento regional via PA
- Trabalho já realizado demonstra viabilidade
- Cronograma realista considerando 4 anos de doutorado

**IDENTIFICAÇÃO DO PROBLEMA (30% da nota):**

O problema está **claramente identificado** em 3 níveis:
1. **Teórico-conceitual:** Lacuna sobre IT no Brasil e IT-IA
2. **Metodológico:** Como fazer PA em desenvolvimento de sistemas de IA
3. **Empírico-prático:** Como IT-IA transforma gestão pública

Problema é **relevante** (desigualdades regionais) e **original** (poucos estudos sobre IT-IA no Brasil).

**COERÊNCIA ENTRE PROBLEMA, OBJETIVOS E LITERATURA (30% da nota):**

- **Problema** → **Literatura:** Lacunas identificadas na revisão (IT no Brasil, PA em IA, colaboração H-IA)
- **Problema** → **Objetivos:** Cada pergunta secundária tem objetivo específico correspondente
- **Objetivos** → **Literatura:** Cada OE dialoga com literatura específica (OE1→PA, OE2→IT, etc.)
- **Literatura** → **Metodologia:** Literatura de PA (Heikkinen, Sein) fundamenta escolha metodológica

**Exemplo de coerência:**
- **Lacuna na literatura:** IT pouco estudada no Brasil
- **Pergunta (PS2):** Como adaptar IT ao contexto brasileiro?
- **Objetivo (OE2):** Revisar e adaptar literatura de IT
- **Método:** Revisão teórica + aplicação empírica no Tocantins
- **Produto:** Cap. 2 (Fundamentação), Artigo 2

**COERÊNCIA ENTRE PROBLEMA E METODOLOGIA (20% da nota):**

**Por que Pesquisa-Ação é adequada?**

1. **Problema requer intervenção:** Não basta observar gestão pública; precisa transformá-la → PA permite intervenção
2. **Contexto dinâmico:** Gestão pública e IA mudam rapidamente → Ciclos iterativos de PA permitem adaptação
3. **Co-criação essencial:** Sistema deve ser feito COM gestores → PA institucionaliza colaboração
4. **Duplo objetivo:** Resolver problema prático E produzir conhecimento → PA permite ambos
5. **Reflexividade necessária:** Lidar com IA emergente requer aprendizagem contínua → Ciclos de reflexão da PA

**Por que métodos complementares?**

- **Entrevistas:** Captar percepções individuais de gestores e senadores
- **Observação:** Documentar uso real do sistema e dinâmicas de audiências
- **Análise documental:** Triangular com dados dos repositórios e proposições legislativas
- **Grupos focais:** Discussão coletiva de desafios éticos e de colaboração

**Alinhamento método-pergunta:**

| Pergunta | Método Principal | Justificativa |
|----------|-----------------|---------------|
| PS1 (PA viabiliza?) | 5 ciclos de PA | Resposta emerge DA PRÁTICA de fazer PA |
| PS2 (Fundamentos IT?) | Revisão teórica + aplicação | Adaptar teoria à prática brasileira |
| PS3 (Transformações?) | Entrevistas, observação, métricas | Captar mudanças organizacionais |
| PS4 (Padrões H-IA?) | Análise repositórios, grupos focais | Identificar padrões emergentes |
| PS5 (Ética?) | Audiências, entrevistas | Debate público sobre IT-IA |
| PS6 (Escalabilidade?) | Audiências, análise comparativa | Discutir replicação nacional |

---

## 9. REFERÊNCIAS BIBLIOGRÁFICAS PRINCIPAIS

### 9.1 Inteligência Territorial

Bertacchini, Y. (2004). *Territoire, Territorialité, Territorialisation: et après?* Université du Sud Toulon Var.

Girardot, J.-J. (2000). Principes, méthodes et outils d'intelligence territoriale. *Revista Netcom*, 14(1-2), 42-51.

Girardot, J.-J. (2009). Evolution of the concept of territorial intelligence within the coordination action of the European Network of Territorial Intelligence. *Res-Systemica*, 1.

Masselot, C. (2008). Intelligence territoriale et action régionale. In *Regards Croisés sur les Outils de Pilotage de Développement Régional* (pp. 35-52). L'Harmattan.

### 9.2 IA em Governança e Gestão Pública

Janssen, M., & Kuk, G. (2016). The challenges and limits of big data algorithms in technocratic governance. *Government Information Quarterly*, 33(3), 371-377.

Wirtz, B. W., Weyerer, J. C., & Geyer, C. (2019). Artificial Intelligence and the Public Sector—Applications and Challenges. *International Journal of Public Administration*, 42(7), 596-615.

Zuiderwijk, A., Chen, Y. C., & Salem, F. (2021). Implications of the use of artificial intelligence in public governance: A systematic literature review and a research agenda. *Government Information Quarterly*, 38(3), 101577.

### 9.3 Pesquisa-Ação e ADR

Baskerville, R. L., & Wood-Harper, A. T. (1996). A critical perspective on action research as a method for information systems research. *Journal of Information Technology*, 11(3), 235-246.

Heikkinen, H. L., Huttunen, R., & Syrjälä, L. (2007). Action research as narrative: five principles for validation. *Educational Action Research*, 15(1), 5-19.

Lewin, K. (1946). Action research and minority problems. *Journal of Social Issues*, 2(4), 34-46.

Reason, P., & Bradbury, H. (Eds.). (2001). *Handbook of Action Research: Participative Inquiry and Practice*. Sage.

Sein, M. K., Henfridsson, O., Purao, S., Rossi, M., & Lindgren, R. (2011). Action design research. *MIS Quarterly*, 35(1), 37-56.

### 9.4 Colaboração Humano-IA

Dellermann, D., Ebel, P., Söllner, M., & Leimeister, J. M. (2019). Hybrid intelligence. *Business & Information Systems Engineering*, 61(5), 637-643.

Jarrahi, M. H. (2018). Artificial intelligence and the future of work: Human-AI symbiosis in organizational decision making. *Business Horizons*, 61(4), 577-586.

Seeber, I., Bittner, E., Briggs, R. O., de Vreede, T., de Vreede, G. J., Elkins, A., ... & Söllner, M. (2020). Machines as teammates: A research agenda on AI in team collaboration. *Information & Management*, 57(2), 103174.

### 9.5 Desenvolvimento Regional no Brasil

Araújo, T. B. (2014). *Ensaios sobre o desenvolvimento brasileiro: heranças e urgências*. Revan.

Furtado, C. (1967). *Teoria e política do desenvolvimento econômico*. Companhia Editora Nacional.

Grin, E. J. (2019). Capacidades estatais municipais e desenvolvimento local no Brasil. *Revista de Administração Pública*, 53(5), 857-878.

### 9.6 Ética de IA e Governança

Floridi, L., Cowls, J., Beltrametti, M., Chatila, R., Chazerand, P., Dignum, V., ... & Vayena, E. (2018). AI4People—An ethical framework for a good AI society: Opportunities, risks, principles, and recommendations. *Minds and Machines*, 28(4), 689-707.

Jobin, A., Ienca, M., & Vayena, E. (2019). The global landscape of AI ethics guidelines. *Nature Machine Intelligence*, 1(9), 389-399.

### 9.7 Metodologia de Pesquisa

Braun, V., & Clarke, V. (2006). Using thematic analysis in psychology. *Qualitative Research in Psychology*, 3(2), 77-101.

Yin, R. K. (2015). *Estudo de Caso: Planejamento e Métodos* (5ª ed.). Bookman.

---

## 10. CONSIDERAÇÕES FINAIS

### 10.1 Contribuições Esperadas

Esta pesquisa visa contribuir em múltiplas dimensões:

**Contribuições Teóricas:**
1. Adaptação do conceito de inteligência territorial ao contexto brasileiro
2. Framework teórico-metodológico de pesquisa-ação para desenvolvimento de sistemas de IA
3. Tipologia de padrões de colaboração humano-IA em gestão pública
4. Princípios éticos e de governança para IT baseada em IA

**Contribuições Práticas:**
1. Sistema Tocantins Integrado utilizável para gestão pública
2. Framework ia-collab-os transferível para outros projetos
3. Modelo de implementação de IT adaptável a outros estados
4. Evidências empíricas para subsidiar políticas de desenvolvimento regional

**Contribuições Metodológicas:**
1. Demonstração de viabilidade de pesquisa-ação em desenvolvimento de IA
2. Documentação detalhada de 5 ciclos de PA
3. Uso de repositórios GitHub como dados para pesquisa
4. Integração de métodos qualitativos e quantitativos em PA

**Contribuições Sociais:**
1. Democratização de acesso a análises territoriais sofisticadas
2. Subsídio para formulação de políticas públicas de desenvolvimento regional
3. Debate público sobre IT via audiências no Senado
4. Formação de gestores públicos em uso de IT-IA

### 10.2 Originalidade da Pesquisa

A originalidade desta pesquisa reside em:

1. **Pioneirismo:** Primeira pesquisa brasileira sistemática sobre IT baseada em IA
2. **Abordagem metodológica:** Uso de PA em desenvolvimento de sistemas de IA é raro
3. **Contexto empírico:** Tocantins como laboratório de IT para desenvolvimento regional
4. **Integração:** Combina IT, IA, PA, colaboração H-IA, participação democrática
5. **Prática reflexiva:** Documentação detalhada de aprendizados ao longo de 5 ciclos
6. **Impacto real:** Audiências públicas conectam pesquisa acadêmica com formulação de políticas nacionais

### 10.3 Riscos e Mitigações

| Risco | Probabilidade | Impacto | Mitigação |
|-------|--------------|---------|-----------|
| Sistema não ficar completo | Média | Alto | Priorizar Camada 1; Camada 2 é adicional |
| Audiências não ocorrerem | Baixa | Médio | Pesquisa viável sem audiências; buscar alternativas |
| Dificuldade de acesso a gestores | Média | Médio | Networking contínuo; múltiplas tentativas |
| Problemas técnicos com IA | Baixa | Médio | Usar modelos robustos; ter plano B |
| Atraso no cronograma | Média | Alto | Buffer de tempo; priorizar essencial |
| Dificuldade de publicação | Média | Médio | Submeter a múltiplos periódicos; buscar feedback cedo |

### 10.4 Próximos Passos Imediatos

**Alta Prioridade (Fevereiro-Março 2026):**
1. ✅ Finalizar projeto v2.0 → v2.1 (este documento)
2. ✅ Análise transversal dos 5 repositórios (CONCLUÍDO — Ciclo 3.5)
3. ✅ Mapear ciclos-evidências retroativamente (CONCLUÍDO — MAPEAMENTO v2.0)
4. ✅ Criar MATRIZ-PRODUTO-TESE (CONCLUÍDO — Ciclo 3.5)
5. Executar Etapa 4 do Plano de Fortalecimento (ia-collab-os v2.0: métricas, modos de falha, fundamentação teórica)
6. Reunir com orientador para validar atualizações
7. Aprofundar revisão sobre IT (15-20 referências-chave)
8. Submeter projeto ao CEP

**Média Prioridade (Março-Maio 2026):**
1. Escrever rascunho Cap. 2 (Fundamentação Teórica)
2. Escrever artigo 1 sobre ia-collab-os (depende de Etapa 4)
3. Preparar proposta formal de audiência pública
4. Iniciar validação territorial (3 municípios) — Etapa 3

**Baixa Prioridade (Maio-Junho 2026):**
1. Apresentar em evento acadêmico local
2. Elaborar relatório preliminar para Senado
3. Iniciar contatos com gestores para entrevistas futuras

---

## ANEXOS

### Anexo A: Lista Completa de Repositórios

1. **framework-v6-mvp:** https://github.com/henrique-m-ribeiro/framework-v6-mvp
2. **tocantins-integrado:** https://github.com/henrique-m-ribeiro/tocantins-integrado
3. **ia-collab-os:** https://github.com/henrique-m-ribeiro/ia-collab-os
4. **caderno-tocantins-2026:** https://github.com/henrique-m-ribeiro/caderno-tocantins-2026
5. **doutorado:** https://github.com/henrique-m-ribeiro/doutorado

### Anexo B: Documentação Complementar no Repositório Doutorado

- `cronologia-real-repositorios.md` - Cronologia completa dos 5 repositórios e ciclos
- `framework-v6-mvp.md` - Análise detalhada do Ciclo 1
- `objetivos-questoes.md` - Detalhamento de objetivos e questões
- `bibliografia.bib` - Bibliografia em formato BibTeX
- `ANALISE-TRANSVERSAL-REPOSITORIOS.md` - Inventário completo dos 5 repositórios (Ciclo 3.5)
- `MATRIZ-PRODUTO-TESE.md` - Dupla leitura produto-tese por OE (Ciclo 3.5)
- `MAPEAMENTO-CICLOS-EVIDENCIAS.md` - Mapeamento retroativo ciclos-evidências v2.0 (Ciclo 3.5)
- `CICLO-04-PLANO.md` e `CICLO-05-PLANO.md` - Planos com hipóteses testáveis
- `PROTOCOLO-REGISTRO-SESSAO.md` - Checklist pré-sessão para agentes IA
- `TEMPLATE-DIARIO.md` - Template padronizado de diário de PA

### Anexo C: Estatísticas dos Repositórios (Atualizado Fev 2026)

**framework-v6-mvp:**
- Commits: 183 | Arquivos: 571
- Período: Nov-Dez 2025
- Evidências: 21 diários PA, artigo rascunho (~165 KB), 4 análises dimensionais (~345 KB), 11+ prompts, sistema de continuidade (~52 KB)
- Status: Histórico (superado, mas mais rico em evidências do que se supunha)

**tocantins-integrado:**
- Commits: 113 | Arquivos: 278 | PRs: 24
- Período: Jan 2026
- Evidências: 5 ADRs (~46 KB), governança (~20 KB), piloto Palmas (12 KB), 4 diários, 8+ handoffs
- Status: Pausado (Camada 1: 90%)

**ia-collab-os:**
- Commits: 9 | Arquivos: 39
- Período: Jan 2026
- Status: Ativo e publicado (fortalecimento Etapa 4 planejado)

**caderno-tocantins-2026:**
- Commits: ~177
- Período: 20 Jan - Fev 2026
- Volumes: 9 (Volume 1 estadual: 579 KB, 12.572 linhas + Volumes 2-9 regionais: ~905 páginas)
- Agentes orquestrados: 213
- Status: 9 volumes concluídos

**doutorado:**
- Período: Fev 2026 (Ciclo 3.5)
- Conteúdo: 23+ diários centralizados, ANALISE-TRANSVERSAL, MATRIZ-PRODUTO-TESE, MAPEAMENTO v2.0, planos Ciclos 4-5
- Status: Ativo (repositório acadêmico central)

---

**VERSÃO:** 2.1
**DATA:** 12 de Fevereiro de 2026
**STATUS:** ✅ COMPLETO - Incorpora descobertas do Ciclo 3.5. Aguardando validação do orientador.

**HISTÓRICO DE VERSÕES:**
- v1.0 (30 Jan 2026): Versão inicial
- v2.0 (31 Jan 2026): Incorporação de trabalho realizado e oportunidade de audiências
- v2.1 (12 Fev 2026): Atualização pós-Ciclo 3.5 — inclusão do Ciclo 3.5, atualização de Ciclos 1-3 com evidências redescobertas (21 diários, artigo, ADRs, piloto Palmas), incorporação da MATRIZ-PRODUTO-TESE e MAPEAMENTO v2.0

**REVISÕES FUTURAS:**
- Após reunião de orientação: Incorporar feedback
- Após qualificação: Ajustar conforme banca
- Contínuo: Atualizar conforme avanço da pesquisa

**CONTATO:**
Henrique Marques Ribeiro
[Email institucional]
GitHub: github.com/henrique-m-ribeiro

**ORIENTADOR:**
Professor Fernando Filgueiras
[Email]

---

*Este documento foi desenvolvido com assistência de IA (Claude) seguindo metodologia ia-collab-os, documentada em https://github.com/henrique-m-ribeiro/ia-collab-os*
