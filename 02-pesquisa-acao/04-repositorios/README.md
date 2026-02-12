# 04 - Repositórios Relacionados

Esta pasta documenta a integração entre o repositório de doutorado e os 4 repositórios técnicos relacionados à pesquisa-ação. Para inventário completo, ver [ANALISE-TRANSVERSAL-REPOSITORIOS.md](./ANALISE-TRANSVERSAL-REPOSITORIOS.md).

---

## 🔗 Os Repositórios do Projeto

### 0. [framework-v6-mvp](https://github.com/henrique-m-ribeiro/framework-v6-mvp) 🟠 HISTÓRICO
**Framework V6 MVP - Versão Monolítica (Supersedida)**

**Natureza:** Contexto histórico - Ciclo 1 de pesquisa-ação

**Descrição:**
Primeira tentativa de estruturação formal do projeto (Nov-Dez 2025), onde metodologia de colaboração humano-IA e código do sistema Tocantins Integrado estavam misturados no mesmo repositório. Representou um aprendizado fundamental sobre a importância de separar metodologia de artefatos técnicos.

**Papel na Pesquisa:**
- **Ciclo 1** de pesquisa-ação (ação-reflexão-aprendizado)
- **Problema identificado:** Confusão entre metodologia e sistema técnico
- **Aprendizados:** Separação de preocupações, GitHub para continuidade entre sessões, uso de múltiplos modelos de IA
- **Legado:** Evoluiu para 3 repositórios separados (tocantins-integrado, ia-collab-os, caderno-tocantins-2026)

**Status:** ✅ CONCLUÍDO E SUPERSEDIDO (mantido apenas como contexto histórico)

**Documentação:** Ver `framework-v6-mvp.md` nesta pasta para análise detalhada

---

### 1. [tocantins-integrado](https://github.com/henrique-m-ribeiro/tocantins-integrado) 🟡 PAUSADO
**Sistema de Superinteligência Territorial para o Estado do Tocantins**

**Natureza:** Sistema técnico principal - objeto central da pesquisa-ação

**Descrição:**
Sistema de análise multidimensional dos 139 municípios e 8 microrregiões do Tocantins, integrando dados de saúde, educação, infraestrutura, economia e indicadores sociais para subsidiar formulação de políticas públicas baseadas em evidências.

**Arquitetura em Dupla Camada:**
- **Camada 1 (Dashboard):** 90% implementado - falta apenas upload de dados
- **Camada 2 (Multiagentes):** 0% implementado - análises sob demanda

**Papel na Pesquisa:**
- **Artefato** produzido pela pesquisa-ação
- **Campo** onde as transformações ocorrem
- **Evidência** das capacidades de IA em gestão pública

**Status:** 🟡 PAUSADO (pivot emergencial para produção manual dos cadernos devido a prazos eleitorais)

### 2. [ia-collab-os](https://github.com/henrique-m-ribeiro/ia-collab-os) 🟢 ATIVO E PUBLICADO
**Framework Metodológico para Coordenação de Equipes Humano-IA-IA**

**Natureza:** Framework genérico - contribuição metodológica

**Descrição:**
Metodologia de orquestração de equipes mistas (humanos + múltiplos agentes de IA) para desenvolvimento colaborativo de sistemas complexos, extraída e generalizada a partir da experiência do Tocantins Integrado. Separa claramente metodologia de colaboração dos artefatos técnicos produzidos.

**Papel na Pesquisa:**
- **Abstração** da metodologia de colaboração humano-IA-IA
- **Contribuição teórica** para literatura de HCI e desenvolvimento de sistemas
- **Framework transferível** para outros contextos
- **Metodologia emergente** da prática (surgiu DO desenvolvimento do tocantins-integrado)

**Status:** 🟢 ATIVO - usado atualmente para produção dos cadernos e continuidade entre sessões

### 3. [caderno-tocantins-2026](https://github.com/henrique-m-ribeiro/caderno-tocantins-2026) 🟢 ATIVO
**Compilação de Dados Territoriais do Tocantins**

**Natureza:** Notebook de análise de dados - contexto empírico

**Descrição:**
Análises territoriais detalhadas do Estado do Tocantins para subsidiar estratégias eleitorais 2026. Originalmente era a primeira demanda (pré-GitHub), foi pausado para desenvolvimento do sistema, e retomado manualmente após pivot emergencial. Agora é produzido usando a metodologia ia-collab-os.

**Evolução:**
- **Fase Inicial (Pré-Nov 2025):** Produção manual com framework incipiente, apenas modelo Manus
- **Fase Atual (Jan 2026):** Produção manual usando ia-collab-os com múltiplos modelos e GitHub

**Papel na Pesquisa:**
- **Demanda original** que motivou o projeto
- **Contexto** empírico da pesquisa
- **Validação prática** das metodologias de colaboração humano-IA
- **Produto final** para entrega ao cliente (campanha eleitoral)

**Status:** 🟢 ATIVO - 9 volumes concluídos (~1.150 páginas, 139 municípios, 213 agentes orquestrados)

---

## 🔄 Fluxo de Dados e Integração

**Nota:** O diagrama abaixo mostra apenas os 3 repositórios ativos. O framework-v6-mvp (histórico) é documentado separadamente como Ciclo 1 de pesquisa-ação.

```
┌─────────────────────────────────────────────────────────────┐
│                    DOUTORADO (Este Repo)                    │
│  Documentação acadêmica, fundamentação teórica, análise     │
│         + framework-v6-mvp (contexto histórico)             │
└────────────────────────┬────────────────────────────────────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
┌───────────────┐ ┌──────────────┐ ┌────────────────┐
│  TOCANTINS    │ │  IA-COLLAB   │ │   CADERNO      │
│  INTEGRADO    │ │  OS          │ │   TOCANTINS    │
│               │ │              │ │   2026         │
│ 🟡 PAUSADO    │ │ 🟢 ATIVO     │ │ 🟢 ATIVO       │
│ Sistema de IA │ │ Framework    │ │ Análises       │
│ (Camada 1:90%)│ │ metodológico │ │ territoriais   │
└───────┬───────┘ └──────┬───────┘ └───────┬────────┘
        │                │                 │
        │                │                 │
        └────────────────┼─────────────────┘
                         │
                         ▼
              TESE DE DOUTORADO
        (Análise integrada dos 4 repositórios)
```

### Fluxo de Trabalho (Cronológico)

**OBSERVAÇÃO IMPORTANTE:** A cronologia REAL do projeto difere da ordem dos commits no GitHub. Ver `cronologia-real-repositorios.md` para detalhes.

0. **Contexto Histórico** → `framework-v6-mvp` (Nov-Dez 2025)
   - Primeira estruturação formal (tudo misturado)
   - Identificação do problema: metodologia + código juntos
   - Aprendizado fundamental: separar preocupações

1. **Desenvolvimento do Sistema** → `tocantins-integrado` (Jan 2026)
   - Reinício programado usando aprendizados do Ciclo 1
   - Implementação técnica da Camada 1 (90%)
   - GitHub para continuidade entre sessões
   - Múltiplos modelos de IA

2. **Metodologia Emergente** → `ia-collab-os` (Jan 2026)
   - Surgiu DA PRÁTICA de desenvolver tocantins-integrado
   - Extração de padrões de colaboração humano-IA-IA
   - Abstração da metodologia em framework transferível

3. **Pivot Emergencial** → `caderno-tocantins-2026` (Jan 2026)
   - Demanda original retomada manualmente
   - Uso do ia-collab-os para produção
   - Validação prática da metodologia
   - Produto final para entrega

4. **Produção em Escala** → `caderno-tocantins-2026` continuação (Fev 2026)
   - 213 agentes orquestrados em sessão única (8 fev 2026)
   - 9 volumes produzidos (~1.150 páginas)
   - Descoberta da split strategy (analítica vs. mecânica)

5. **Reflexão e Organização (Ciclo 3.5)** → `doutorado` (Fev 2026)
   - Análise transversal dos 5 repositórios
   - MATRIZ-PRODUTO-TESE e MAPEAMENTO-CICLOS-EVIDENCIAS v2.0
   - Plano de Fortalecimento Metodológico (4/6 etapas concluídas)
   - Redescobrimento de evidências extensivas nos Ciclos 0-2

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
**Repositórios utilizados:** Todos os 4 (incluindo framework-v6-mvp)
- **Ciclo 0-1:** Contexto histórico do `framework-v6-mvp`
- **Ciclo 2:** Desenvolvimento do `tocantins-integrado` (commits, issues)
- **Ciclo 3:** Emergência do `ia-collab-os` da prática
- **Ciclo 4:** Pivot para `caderno-tocantins-2026`
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
**Repositórios utilizados:** Todos os 4
- Síntese das contribuições dos 4 repositórios
- Trajetória evolutiva desde framework-v6-mvp até consolidação atual
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

- [x] **ANALISE-TRANSVERSAL-REPOSITORIOS.md** - Inventário completo dos 5 repos (Ciclo 3.5)
- [x] **cronologia-real-repositorios.md** - Cronologia real vs. commits GitHub
- [x] **framework-v6-mvp.md** - Contexto histórico e análise do Ciclo 1
- [x] **tocantins-integrado.md** - Descrição detalhada do sistema principal
- [ ] **ia-collab-os.md** - Documentação do framework metodológico
- [ ] **caderno-tocantins.md** - Descrição das análises territoriais

### Diagramas e Visualizações

- [ ] **arquitetura-sistema.png** - Arquitetura técnica do Tocantins Integrado
- [ ] **fluxo-integracao.png** - Fluxo de dados entre repositórios
- [ ] **linha-tempo-desenvolvimento.png** - Linha do tempo do desenvolvimento
- [ ] **evolucao-capacidades.png** - Evolução das capacidades do sistema

---

## 🎯 Métricas de Integração

### Métricas Quantitativas

**Framework V6 MVP (Histórico):**
- Status: ✅ Concluído e supersedido
- Ciclo: Ciclo 1 (Nov-Dez 2025)
- Aprendizados documentados: [X]
- Problema identificado: Metodologia + código misturados

**Tocantins Integrado:**
- Status: 🟡 Pausado (Camada 1: 90%, Camada 2: 0%)
- Total de commits: [X]
- Commits por ciclo: C2 [X], C3 [X], C4 [X]
- Issues abertas/fechadas: [X/Y]
- Contribuidores: Humanos [X], Agentes IA [Y]
- Linhas de código: [X]

**IA Collab OS:**
- Status: 🟢 Ativo e publicado
- Versões do framework: [X]
- Padrões de colaboração documentados: [X]
- Casos de uso: [X]

**Caderno Tocantins 2026:**
- Status: 🟢 9 volumes concluídos
- Commits: ~177
- Análises territoriais: 139 municípios, 8 microrregiões
- Volume 1 estadual: 579 KB, 12.572 linhas
- Volumes 2-9 regionais: ~905 páginas
- Agentes orquestrados: 213 (sessão de 8 fev 2026)

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

**Framework V6 MVP (Histórico):**
- `final-state`: Estado final antes da separação em 3 repositórios
- Representa Ciclo 0-1 de pesquisa-ação

**Tocantins Integrado:**
- `v1.0-ciclo2`: Reinício programado - primeira versão separada
- `v2.0-ciclo3`: Emergência do ia-collab-os
- `v3.0-ciclo4`: Antes do pivot emergencial
- `v4.0-paused`: Estado atual pausado (Camada 1: 90%)

**IA Collab OS:**
- `v1.0-framework-inicial`: Framework extraído da experiência (Ciclo 3)
- `v2.0-framework-publicado`: Versão refinada e publicada

**Caderno Tocantins:**
- `v0.0-pre-github`: Versão inicial manual (Ciclo 0)
- `v1.0-volume-1`: Volume 1 completo usando ia-collab-os (Ciclo 4)
- `v2.0-volume-2`: [Planejado] Segundo volume

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
**Última atualização:** 2026-02-12
**Próxima revisão:** Início do Ciclo 4

---

**Nota sobre cronologia:** Este documento foi atualizado para refletir a cronologia REAL do desenvolvimento, que difere da sequência de commits no GitHub. Ver `cronologia-real-repositorios.md` para detalhes completos sobre as 5 fases do projeto.
