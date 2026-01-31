# 04 - Repositórios Relacionados

Esta pasta documenta a integração entre o repositório de doutorado e os três repositórios técnicos que constituem os **artefatos práticos** da pesquisa-ação.

---

## 🔗 Os Três Repositórios Técnicos

### 1. [tocantins-integrado](https://github.com/henrique-m-ribeiro/tocantins-integrado)
**Sistema de Superinteligência Territorial para o Estado do Tocantins**

**Natureza:** Sistema técnico principal - objeto central da pesquisa-ação

**Descrição:**
Sistema de análise multidimensional dos 139 municípios e 8 microrregiões do Tocantins, integrando dados de saúde, educação, infraestrutura, economia e indicadores sociais para subsidiar formulação de políticas públicas baseadas em evidências.

**Papel na Pesquisa:**
- **Artefato** produzido pela pesquisa-ação
- **Campo** onde as transformações ocorrem
- **Evidência** das capacidades de IA em gestão pública

### 2. [ia-collab-os](https://github.com/henrique-m-ribeiro/ia-collab-os)
**Framework Metodológico para Coordenação de Equipes Humano-IA**

**Natureza:** Framework genérico - contribuição metodológica

**Descrição:**
Metodologia de orquestração de equipes mistas (humanos + agentes de IA) para desenvolvimento colaborativo de sistemas complexos, extraída e generalizada a partir da experiência do Tocantins Integrado.

**Papel na Pesquisa:**
- **Abstração** da metodologia de colaboração humano-IA
- **Contribuição teórica** para literatura de HCI e desenvolvimento de sistemas
- **Framework transferível** para outros contextos

### 3. [caderno-tocantins-2026](https://github.com/henrique-m-ribeiro/caderno-tocantins-2026)
**Compilação de Dados Territoriais do Tocantins**

**Natureza:** Notebook de análise de dados - contexto empírico

**Descrição:**
Análises territoriais detalhadas do Estado do Tocantins para subsidiar estratégias eleitorais 2026, servindo como caso de uso e validação do sistema Tocantins Integrado.

**Papel na Pesquisa:**
- **Contexto** empírico da pesquisa
- **Validação prática** do sistema em uso real
- **Fonte de dados** para análises territoriais

---

## 🔄 Fluxo de Dados e Integração

```
┌─────────────────────────────────────────────────────────────┐
│                    DOUTORADO (Este Repo)                    │
│  Documentação acadêmica, fundamentação teórica, análise     │
└────────────────────────┬────────────────────────────────────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
┌───────────────┐ ┌──────────────┐ ┌────────────────┐
│  TOCANTINS    │ │  IA-COLLAB   │ │   CADERNO      │
│  INTEGRADO    │ │  OS          │ │   TOCANTINS    │
│               │ │              │ │   2026         │
│ Sistema de IA │ │ Framework    │ │ Análises       │
│ em produção   │ │ metodológico │ │ territoriais   │
└───────┬───────┘ └──────┬───────┘ └───────┬────────┘
        │                │                 │
        │                │                 │
        └────────────────┼─────────────────┘
                         │
                         ▼
              TESE DE DOUTORADO
        (Análise integrada dos 3 artefatos)
```

### Fluxo de Trabalho

1. **Desenvolvimento** → `tocantins-integrado`
   - Implementação técnica do sistema
   - Commits documentam ciclos de pesquisa-ação
   - Issues registram decisões de design

2. **Uso Prático** → `caderno-tocantins-2026`
   - Aplicação do sistema em análises reais
   - Validação das capacidades analíticas
   - Feedback para refinamento

3. **Generalização** → `ia-collab-os`
   - Extração de padrões de colaboração
   - Abstração da metodologia
   - Framework transferível

4. **Análise Acadêmica** → `doutorado`
   - Interpretação teórica dos artefatos
   - Sistematização de aprendizados
   - Produção de conhecimento científico

---

## 📊 Mapeamento para Capítulos da Tese

### Capítulo 1: Introdução
**Repositórios utilizados:** Todos
- Contextualização a partir do `caderno-tocantins-2026`
- Problema identificado no desenvolvimento do `tocantins-integrado`
- Metodologia do `ia-collab-os`

### Capítulo 2: Fundamentação Teórica
**Repositórios utilizados:** Principalmente `ia-collab-os`
- Conceitos de colaboração humano-IA
- Frameworks teóricos para pesquisa-ação
- Literatura sobre IA em governança

### Capítulo 3: Metodologia
**Repositórios utilizados:** `ia-collab-os` e `tocantins-integrado`
- Framework do `ia-collab-os` aplicado
- Ciclos de desenvolvimento documentados no `tocantins-integrado`
- Contexto do `caderno-tocantins-2026`

### Capítulo 4: Ciclos de Pesquisa-Ação
**Repositórios utilizados:** Principalmente `tocantins-integrado`
- Análise de commits por ciclo
- Issues como evidência de desafios e decisões
- Releases como marcos dos ciclos

### Capítulo 5: Análise Integrada
**Repositórios utilizados:** Todos
- Capacidades analíticas demonstradas em `caderno-tocantins-2026`
- Padrões de colaboração extraídos em `ia-collab-os`
- Transformações evidenciadas em `tocantins-integrado`

### Capítulo 6: Discussão
**Repositórios utilizados:** Todos
- Implicações dos padrões identificados
- Contribuições teóricas e práticas
- Limitações dos artefatos

### Capítulo 7: Conclusões
**Repositórios utilizados:** Todos
- Síntese das contribuições dos 3 repositórios
- Modelo integrado de superinteligência territorial

---

## 🔍 Como Usar os Repositórios na Tese

### Para Coleta de Dados

**Dados de Desenvolvimento (tocantins-integrado):**
```bash
# Analisar commits por ciclo de pesquisa-ação
git log --since="2025-01-01" --until="2025-06-30" --oneline

# Extrair issues por categoria
gh issue list --label "ciclo-1" --state all

# Analisar contribuições por agente (humano vs IA)
git log --author="Claude" --oneline
git log --author="Henrique" --oneline
```

**Dados de Uso (caderno-tocantins-2026):**
- Notebooks Jupyter com análises completas
- Visualizações de dados territoriais
- Insights gerados pelo sistema

**Padrões Metodológicos (ia-collab-os):**
- Documentação de workflows
- Definição de papéis humano-IA
- Protocolos de colaboração

### Para Análise

**Análise Temporal:**
- Comparar versões do sistema ao longo dos 4 ciclos
- Identificar evolução das capacidades
- Mapear aprendizados acumulados

**Análise de Colaboração:**
- Razão commits humanos/IA
- Tipos de contribuição de cada agente
- Padrões de complementaridade

**Análise de Impacto:**
- Qualidade das análises antes/depois do sistema
- Tempo de execução de análises territoriais
- Profundidade de insights gerados

### Para Fundamentação

**Citação de Artefatos:**
```
RIBEIRO, H. M. Tocantins Integrado: Sistema de Superinteligência
Territorial para o Estado do Tocantins. Versão 2.0. GitHub, 2026.
Disponível em: https://github.com/henrique-m-ribeiro/tocantins-integrado.
Acesso em: 31 jan. 2026.
```

**Referência a Commits Específicos:**
```
No ciclo 2 da pesquisa-ação, a implementação da análise
multidimensional de saúde (commit 4a7f2c3) demonstrou...
```

**Citação de Issues:**
```
O desafio de integração de dados heterogêneos (Issue #23)
evidenciou a necessidade de...
```

---

## 📋 Documentos desta Pasta

### Documentos de Integração

- [ ] **tocantins-integrado.md** - Descrição detalhada do sistema principal
- [ ] **ia-collab-os.md** - Documentação do framework metodológico
- [ ] **caderno-tocantins.md** - Descrição das análises territoriais
- [ ] **mapeamento-commits-ciclos.md** - Mapeamento de commits para ciclos de pesquisa-ação
- [ ] **analise-colaboracao.md** - Análise quantitativa da colaboração humano-IA
- [ ] **metricas-sistema.md** - Métricas de evolução do sistema

### Diagramas e Visualizações

- [ ] **arquitetura-sistema.png** - Arquitetura técnica do Tocantins Integrado
- [ ] **fluxo-integracao.png** - Fluxo de dados entre repositórios
- [ ] **linha-tempo-desenvolvimento.png** - Linha do tempo do desenvolvimento
- [ ] **evolucao-capacidades.png** - Evolução das capacidades do sistema

---

## 🎯 Métricas de Integração

### Métricas Quantitativas

**Tocantins Integrado:**
- Total de commits: [X]
- Commits por ciclo: C1 [X], C2 [X], C3 [X], C4 [X]
- Issues abertas/fechadas: [X/Y]
- Contribuidores: Humanos [X], Agentes IA [Y]
- Linhas de código: [X]

**IA Collab OS:**
- Versões do framework: [X]
- Padrões de colaboração documentados: [X]
- Casos de uso: [X]

**Caderno Tocantins 2026:**
- Análises territoriais realizadas: [X]
- Municípios analisados: 139
- Microrregiões analisadas: 8
- Dimensões integradas: [X]

### Métricas Qualitativas

**Transformação da Prática:**
- Novos tipos de análise viabilizados
- Tempo economizado em processos
- Qualidade aumentada de decisões

**Aprendizados Metodológicos:**
- Padrões de colaboração identificados
- Desafios superados
- Boas práticas estabelecidas

---

## ✅ Checklist de Uso dos Repositórios

### Antes de Escrever Cada Capítulo

- [ ] Revisar commits relevantes do período
- [ ] Ler issues relacionadas ao tema
- [ ] Consultar documentação técnica atualizada
- [ ] Verificar análises no caderno-tocantins
- [ ] Revisar framework do ia-collab-os

### Durante a Escrita

- [ ] Citar versões específicas dos repositórios
- [ ] Referenciar commits e issues relevantes
- [ ] Incluir capturas de tela quando apropriado
- [ ] Documentar limitações técnicas encontradas
- [ ] Registrar insights emergentes

### Após Escrever

- [ ] Validar informações técnicas com os repositórios
- [ ] Verificar consistência de datas e versões
- [ ] Confirmar citações e referências
- [ ] Atualizar métricas se necessário

---

## 🔄 Sincronização e Versionamento

### Princípios de Sincronização

1. **Repositórios técnicos são fonte primária de verdade**
   - Dados e métricas devem vir dos repositórios
   - Análises acadêmicas interpretam, não alteram os artefatos

2. **Versionamento coordenado**
   - Tags nos repositórios correspondem a ciclos de pesquisa-ação
   - Releases marcam marcos importantes

3. **Documentação bidirecional**
   - Repositórios técnicos linkam para documentação acadêmica
   - Tese referencia commits e issues específicos

### Tags Importantes

**Tocantins Integrado:**
- `v1.0-ciclo1`: Final do primeiro ciclo de pesquisa-ação
- `v2.0-ciclo2`: Final do segundo ciclo
- `v3.0-ciclo3`: Final do terceiro ciclo
- `v4.0-ciclo4`: Final do quarto ciclo - versão para defesa

**IA Collab OS:**
- `v1.0-framework-inicial`: Framework extraído da experiência
- `v2.0-framework-refinado`: Versão refinada e validada

**Caderno Tocantins:**
- `v1.0-analise-inicial`: Primeira rodada de análises
- `v2.0-analise-completa`: Análise completa dos 139 municípios

---

## 📚 Referências sobre Integração

### Sobre Pesquisa com Artefatos Digitais

- Hevner, A. R., et al. (2004). Design Science in Information Systems Research
- Sein, M. K., et al. (2011). Action Design Research
- Gregor, S., & Hevner, A. R. (2013). Positioning and Presenting Design Science Research

### Sobre Análise de Repositórios

- Kalliamvakou, E., et al. (2014). The Promises and Perils of Mining GitHub
- Gousios, G., & Spinellis, D. (2012). GHTorrent: GitHub's Data from a Firehose

---

**Responsável pela integração:** Henrique M. Ribeiro
**Última sincronização:** 2026-01-31
**Próxima revisão:** [Data da próxima revisão dos repositórios]
