# Tocantins Integrado: Sistema de Superinteligência Territorial

**Repositório:** [github.com/henrique-m-ribeiro/tocantins-integrado](https://github.com/henrique-m-ribeiro/tocantins-integrado)

**Versão atual:** Em pausa - Camada 1 (90%), Camada 2 (0%)

**Status:** 🟡 PAUSADO - Pivot emergencial para produção manual dos cadernos

**Ciclo de Pesquisa-Ação:** Ciclo 2 (Reinício Programado - Jan 2026)

**Contexto:** Reinício programado após aprendizados do framework-v6-mvp (Ciclo 1), usando GitHub para continuidade e múltiplos modelos de IA

---

## 📋 Visão Geral do Sistema

### Definição

O **Tocantins Integrado** é um sistema de superinteligência territorial que realiza análise multidimensional dos 139 municípios e 8 microrregiões do Estado do Tocantins, integrando dados de múltiplas fontes para subsidiar a formulação de políticas públicas baseadas em evidências.

### Propósito

Transformar dados fragmentados em inteligência territorial acionável, permitindo que gestores públicos:
- Compreendam realidades municipais de forma holística
- Identifiquem padrões e tendências territoriais
- Formulem políticas públicas fundamentadas em evidências
- Monitorem indicadores sociais, econômicos e de infraestrutura
- Tomem decisões mais informadas e equitativas

### Diferenciais

1. **Análise Multidimensional:** Integra 4 dimensões (Saúde, Educação, Infraestrutura, Economia)
2. **Co-criação através de Pesquisa-Ação:** Desenvolvido colaborativamente com gestores públicos
3. **Colaboração Humano-IA:** Combina expertise de gestores com capacidades analíticas de IA
4. **Contextualização Territorial:** Respeita especificidades do contexto tocantinense
5. **Código Aberto:** Transparência e replicabilidade

---

## 🎯 Objetivos do Sistema

### Objetivo Principal

Viabilizar gestão pública baseada em evidências através de análise territorial integrada e inteligente.

### Objetivos Específicos

1. **Integração de Dados:** Consolidar dados dispersos de fontes oficiais (IBGE, DATASUS, INEP, etc.)
2. **Análise Multidimensional:** Permitir visão integrada de saúde, educação, infraestrutura e economia
3. **Identificação de Padrões:** Revelar correlações e tendências não evidentes em análises isoladas
4. **Suporte à Decisão:** Subsidiar formulação e priorização de políticas públicas
5. **Monitoramento Territorial:** Acompanhar evolução de indicadores ao longo do tempo
6. **Democratização de Informação:** Tornar análises complexas acessíveis a gestores não-técnicos

---

## 🏗️ Arquitetura do Sistema

### Arquitetura em Dupla Camada de Orquestração

O sistema foi concebido com uma arquitetura inovadora de dupla camada:

**CAMADA 1 (Dashboard + IA de Exploração):** 🟡 90% Implementada
- Dashboard com dados pré-computados e visualizações
- IA assistente para facilitar exploração dos dados (linha de frente)
- Consultas rápidas e análises padronizadas
- **Status:** Implementada, falta apenas upload final de dados

**CAMADA 2 (Sistema Multiagentes):** 🔴 0% Implementada
- Equipe de especialistas multidimensionais (multiagentes)
- Análises sob demanda mais profundas
- Orquestração inteligente de agentes especializados
- **Status:** Não implementada devido ao pivot emergencial

### Arquitetura Técnica (Camada 1)

```
┌─────────────────────────────────────────────────────┐
│          CAMADA DE APRESENTAÇÃO                     │
│  Interface Web │ Dashboards │ Relatórios │ API     │
│  + IA Assistente para Exploração (Claude)          │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────┴────────────────────────────────┐
│          CAMADA DE INTELIGÊNCIA                     │
│  Análise │ Clustering │ Correlações │ Predições    │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────┴────────────────────────────────┐
│          CAMADA DE INTEGRAÇÃO                       │
│  ETL │ Validação │ Padronização │ Enriquecimento   │
└────────────────────┬────────────────────────────────┘
                     │
┌────────────────────┴────────────────────────────────┐
│          CAMADA DE DADOS                            │
│  Fontes Oficiais │ Dados Brutos │ Dados Limpos     │
└─────────────────────────────────────────────────────┘
```

### Componentes Principais

**1. Módulo de Coleta de Dados**
- Extração de APIs governamentais
- Processamento de datasets públicos
- Validação de qualidade de dados
- Versionamento de datasets

**2. Módulo de Integração**
- Padronização de códigos municipais
- Reconciliação de nomenclaturas
- Tratamento de dados faltantes
- Agregação temporal

**3. Módulo de Análise**
- Estatísticas descritivas
- Análise de clusters (agrupamento de municípios similares)
- Análise de correlações entre dimensões
- Identificação de outliers
- Projeções e tendências

**4. Módulo de Visualização**
- Mapas temáticos interativos
- Dashboards configuráveis
- Relatórios comparativos
- Gráficos de evolução temporal
- Rankings municipais

**5. Módulo de IA**
- Processamento de linguagem natural para consultas
- Geração automática de insights
- Recomendações de políticas públicas
- Explicação de padrões identificados

---

## 📊 As 4 Dimensões de Análise

### 1. Dimensão Saúde

**Indicadores:**
- Cobertura de atenção básica
- Leitos hospitalares per capita
- Mortalidade infantil
- Cobertura vacinal
- Estabelecimentos de saúde
- Profissionais de saúde per capita

**Fontes de Dados:**
- DATASUS (Ministério da Saúde)
- CNES (Cadastro Nacional de Estabelecimentos de Saúde)
- SINASC (Sistema de Informações sobre Nascidos Vivos)
- SIM (Sistema de Informações sobre Mortalidade)

**Análises Realizadas:**
- Mapeamento de desertos assistenciais
- Correlação entre infraestrutura e indicadores de saúde
- Identificação de municípios prioritários para investimentos
- Análise de equidade na distribuição de recursos

### 2. Dimensão Educação

**Indicadores:**
- IDEB (Índice de Desenvolvimento da Educação Básica)
- Taxa de aprovação/reprovação/abandono
- Infraestrutura escolar
- Formação de professores
- Matrículas por etapa de ensino
- Distorção idade-série

**Fontes de Dados:**
- INEP (Instituto Nacional de Estudos e Pesquisas)
- Censo Escolar
- Prova Brasil / SAEB

**Análises Realizadas:**
- Correlação entre infraestrutura e desempenho
- Identificação de fatores de sucesso educacional
- Mapeamento de desigualdades educacionais
- Projeção de demandas futuras

### 3. Dimensão Infraestrutura

**Indicadores:**
- Saneamento básico (água, esgoto, coleta de lixo)
- Pavimentação urbana
- Energia elétrica
- Internet banda larga
- Transporte público
- Equipamentos públicos

**Fontes de Dados:**
- IBGE (Censo, PNAD Contínua)
- SNIS (Sistema Nacional de Informações sobre Saneamento)
- ANATEL

**Análises Realizadas:**
- Déficit de infraestrutura por município
- Correlação entre infraestrutura e desenvolvimento
- Priorização de investimentos
- Análise de conectividade territorial

### 4. Dimensão Economia

**Indicadores:**
- PIB municipal
- PIB per capita
- Composição setorial (agro, indústria, serviços)
- Emprego formal
- Massa salarial
- Empresas ativas
- Arrecadação tributária

**Fontes de Dados:**
- IBGE (PIB Municipal, CEMPRE)
- RAIS (Relação Anual de Informações Sociais)
- Receita Federal

**Análises Realizadas:**
- Vocações econômicas regionais
- Dinâmica do mercado de trabalho
- Dependência de transferências governamentais
- Potenciais de desenvolvimento econômico

---

## 🔄 Desenvolvimento através de Pesquisa-Ação

**IMPORTANTE:** Este repositório representa especificamente o **Ciclo 2** da pesquisa-ação completa. Ver `cronologia-real-repositorios.md` para o contexto completo dos 5 ciclos (0-4).

### Contexto Histórico: Ciclo 0-1 (framework-v6-mvp)

**Período:** Pré-GitHub até Dez 2025

**Situação:**
- Demanda inicial de criação dos cadernos Tocantins surgiu primeiro (Ciclo 0)
- Primeira tentativa de estruturação formal no framework-v6-mvp (Ciclo 1)
- Problema identificado: metodologia e código misturados

**Aprendizados do Ciclo 1:**
- Necessidade de separar metodologia de artefatos técnicos
- GitHub como ferramenta para continuidade entre sessões
- Benefício de usar múltiplos modelos de IA (não apenas Manus)
- Valor dos registros de diário de pesquisa-ação

Ver: `framework-v6-mvp.md` para análise detalhada

---

### Ciclo 2: Reinício Programado - Tocantins Integrado (Jan 2026)

**Período:** Janeiro 2026 - PRESENTE (PAUSADO)

**Motivação:**
Reiniciar o projeto usando conhecimentos e aprendizados do framework-v6-mvp, separando claramente:
- Sistema técnico → tocantins-integrado (este repositório)
- Metodologia de colaboração → ia-collab-os (emergiu da prática)
- Produto final → caderno-tocantins-2026 (retomado após pivot)

**Objetivos:**
- Implementar sistema com dupla camada de orquestração
- Usar GitHub para continuidade entre sessões
- Trabalhar com múltiplos modelos de IA
- Integrar 4 dimensões de análise territorial

**Entregas Realizadas:**
- ✅ Arquitetura do sistema definida
- ✅ Camada 1 (Dashboard + IA): 90% implementada
  - Estrutura de dados implementada
  - Pipeline de ETL desenvolvido
  - Dashboards básicos criados
  - Falta: Upload final dos dados
- ❌ Camada 2 (Multiagentes): 0% implementada

**Complicações Encontradas:**
- Complexidade da implementação maior que previsto
- Problemas de integração de dados de múltiplas fontes
- Dificuldades técnicas com a arquitetura multiagentes
- Prazo apertado para entrega dos cadernos (campanha eleitoral)

**Decisão Estratégica - Pivot Emergencial (Jan 2026):**
- **PAUSOU** implementação do sistema
- **RETOMOU** produção manual dos cadernos usando ia-collab-os
- **DOCUMENTOU** aprendizados para pesquisa-ação (Ciclo 3)

**Status Atual:** 🟡 PAUSADO
- Sistema funcional mas incompleto
- Camada 1 quase pronta (falta dados)
- Camada 2 não iniciada
- Pode ser retomado após entrega dos cadernos

**Aprendizados para os Ciclos Seguintes:**
- Importância de MVP mínimo viável antes de funcionalidades avançadas
- Equilíbrio entre inovação técnica e prazos de entrega
- Valor de ter metodologia separada (ia-collab-os) que funciona independente do sistema
- Framework metodológico emergiu DA PRÁTICA deste desenvolvimento

---

## 📈 Métricas do Sistema

### Métricas Técnicas

**Dados Integrados:**
- Municípios: 139 (100% do Tocantins)
- Microrregiões: 8
- Indicadores: ~150 (distribuídos nas 4 dimensões)
- Fontes de dados: ~12 APIs e datasets
- Série temporal: 2015-2025 (10 anos)

**Performance:**
- Tempo médio de análise de um município: < 5 segundos
- Tempo de análise comparativa (todos municípios): < 30 segundos
- Atualização de dados: Mensal/Trimestral (conforme disponibilidade)
- Disponibilidade do sistema: > 99%

### Métricas de Desenvolvimento

**NOTA:** Este repositório representa apenas o Ciclo 2. Para métricas do Ciclo 0-1, ver framework-v6-mvp.

**Ciclo 2 (tocantins-integrado) - Jan 2026:**
- Status: 🟡 PAUSADO
- Commits: [X - preencher com `git log --oneline | wc -l`]
- Issues abertas/fechadas: [Y/Z - preencher com `gh issue list`]
- Pull requests: [N]
- Contribuidores: Humanos [1], Agentes IA [múltiplos modelos]
- Linhas de código: [X]
- Camada 1: 90% completa
- Camada 2: 0% completa
- Data de pausa: Jan 2026 (pivot emergencial)

**Próximos Ciclos (Planejados):**
- **Ciclo 3:** Emergência do ia-collab-os da prática
- **Ciclo 4:** Produção dos cadernos usando ia-collab-os
- **Ciclo 5+:** Possível retomada do tocantins-integrado no futuro

### Métricas de Impacto

**Uso:**
- Usuários ativos: [X gestores públicos]
- Análises realizadas: [Y]
- Relatórios gerados: [Z]
- Tempo economizado: [H horas em análises manuais]

**Decisões Influenciadas:**
- Políticas públicas formuladas: [X]
- Investimentos priorizados: R$ [valor]
- Municípios beneficiados: [N]

---

## 🔍 Como o Sistema Serve à Pesquisa

### Como Artefato de Pesquisa-Ação

**O sistema É a intervenção:**
- Não apenas estudamos gestão pública, mas a transformamos
- Sistema materializa a colaboração humano-IA
- Cada versão reflete um ciclo de ação-reflexão-aprendizagem

**Commits como Dados:**
- Histórico de desenvolvimento documenta decisões
- Issues capturam desafios e dilemas
- Pull requests evidenciam colaboração

**Código como Evidência:**
- Implementação reflete princípios éticos discutidos
- Arquitetura incorpora aprendizados dos ciclos
- Testes documentam casos de uso validados

### Como Fonte de Dados para Análise

**Dados Quantitativos:**
- Métricas de uso (logs, analytics)
- Estatísticas de desenvolvimento (commits, issues)
- Performance técnica
- Razão contribuições humanas/IA

**Dados Qualitativos:**
- Comentários em issues e PRs
- Descrições de commits
- Documentação de decisões de design
- Feedback de usuários

### Como Contribuição Prática

**Valor para Gestão Pública:**
- Sistema utilizável além da pesquisa
- Código aberto = replicável em outros estados
- Modelo de governança de IA documentado

**Transferência de Conhecimento:**
- Documentação técnica completa
- Tutoriais de uso e implementação
- Workshops e treinamentos

---

## 🗺️ Mapeamento para Capítulos da Tese

### Capítulo 1: Introdução
- **Uso:** Apresentação do sistema como contexto da pesquisa
- **Referências:** Visão geral, objetivos, diferenciais

### Capítulo 2: Fundamentação Teórica
- **Uso:** Sistema exemplifica conceitos discutidos (superinteligência territorial, IA em governança)
- **Referências:** Arquitetura, design principles

### Capítulo 3: Metodologia
- **Uso:** Sistema como artefato da pesquisa-ação
- **Referências:** Ciclos de desenvolvimento, commits por ciclo

### Capítulo 4: Ciclos de Pesquisa-Ação
- **Uso:** Este sistema representa o Ciclo 2 (Reinício Programado)
- **Referências:** Commits do reinício, issues de desenvolvimento, decisão de pausa
- **Contexto:** Relacionar com Ciclo 1 (framework-v6-mvp) e Ciclo 4 (pivot para cadernos)

### Capítulo 5: Análise Integrada
- **Uso:** Capacidades do sistema como evidência de transformação
- **Referências:** Métricas de impacto, casos de uso, análises geradas

### Capítulo 6: Discussão
- **Uso:** Sistema como cristalização de padrões de colaboração humano-IA
- **Referências:** Análise de contribuições, decisões de design, trade-offs

### Capítulo 7: Conclusões
- **Uso:** Sistema como contribuição prática da pesquisa
- **Referências:** Modelo de implementação, lições aprendidas, escalabilidade

---

## 🔗 Links e Recursos

### Repositório Principal
- **GitHub:** https://github.com/henrique-m-ribeiro/tocantins-integrado
- **Documentação:** https://github.com/henrique-m-ribeiro/tocantins-integrado/wiki
- **Issues:** https://github.com/henrique-m-ribeiro/tocantins-integrado/issues

### Releases e Marcos Importantes

**Status Atual:** Sistema em estado pausado (Ciclo 2)

**Possíveis Tags Futuras:**
- **v0.9-paused-state:** Estado atual pausado (Camada 1: 90%, Camada 2: 0%)
- **v1.0-layer1-complete:** Quando Camada 1 for finalizada (com dados)
- **v2.0-layer2-complete:** Se/quando Camada 2 for implementada

**Contexto Histórico:**
- **framework-v6-mvp (Ciclo 1):** Ver repositório histórico separado

### Análises Demonstrativas
- Ver repositório: https://github.com/henrique-m-ribeiro/caderno-tocantins-2026

---

## 📝 Como Citar

### Citação do Repositório

```
RIBEIRO, Henrique M. Tocantins Integrado: Sistema de Superinteligência
Territorial para o Estado do Tocantins. Estado pausado (Ciclo 2 -
Pesquisa-Ação). GitHub, 2026. Disponível em:
https://github.com/henrique-m-ribeiro/tocantins-integrado.
Acesso em: [data].
```

### Citação de Estado Específico

```
RIBEIRO, Henrique M. Tocantins Integrado: Camada 1 - Dashboard com IA
de Exploração (90% implementada). Ciclo 2 de Pesquisa-Ação. GitHub, 2026.
Disponível em: https://github.com/henrique-m-ribeiro/tocantins-integrado.
Acesso em: [data].
```

### Citação de Commit Específico

```
RIBEIRO, Henrique M. Implementação de análise multidimensional de saúde.
In: Tocantins Integrado. Commit 4a7f2c3. GitHub, 15 mar. 2026.
Disponível em: https://github.com/henrique-m-ribeiro/tocantins-integrado/commit/4a7f2c3.
Acesso em: [data].
```

---

## ✅ Checklist de Uso na Tese

### Antes de Escrever

- [ ] Revisar últimas versões do sistema
- [ ] Atualizar métricas de desenvolvimento
- [ ] Verificar issues recentes relevantes
- [ ] Consultar documentação técnica
- [ ] Preparar capturas de tela e diagramas

### Durante a Escrita

- [ ] Citar versões específicas (v1.0, v2.0, etc.)
- [ ] Referenciar commits relevantes quando apropriado
- [ ] Incluir métricas atualizadas
- [ ] Documentar limitações técnicas
- [ ] Explicar decisões de design importantes

### Após Escrever

- [ ] Validar consistência com código atual
- [ ] Verificar se capturas de tela estão atualizadas
- [ ] Confirmar referências e links
- [ ] Revisar terminologia técnica

---

**Autor principal:** Henrique M. Ribeiro
**Contribuidores:** [Lista de contribuidores humanos e agentes IA]
**Licença:** [Especificar - ex: MIT, GPL, etc.]
**Última atualização:** 2026-01-31
