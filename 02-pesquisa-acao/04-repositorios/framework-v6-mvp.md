# Framework V6 MVP: Contexto Histórico

**Repositório:** [github.com/henrique-m-ribeiro/framework-v6-mvp](https://github.com/henrique-m-ribeiro/framework-v6-mvp)

**Status:** 🟠 Versão superada - Valor histórico

**Período Ativo:** Novembro - Dezembro 2025

**Sucessores:** tocantins-integrado (sistema) + ia-collab-os (metodologia)

---

## 📋 Visão Geral

O **Framework V6 MVP** foi a primeira tentativa de sistematizar o trabalho de desenvolvimento de um sistema de inteligência territorial usando IA, surgindo após experiências iniciais de criação manual de cadernos de análise territorial.

### Contexto de Criação

**Origem:**
- Demanda prática: Criar cadernos de análise territorial do Tocantins
- Framework inicial incipiente (apenas Manus, sem GitHub)
- Necessidade de sistematizar o processo

**Por que "V6"?**
- Indica que já era a 6ª iteração de tentativas de framework
- Versões anteriores (v1-v5) não foram formalizadas ou versionadas
- V6 foi a primeira versão commitada no GitHub

**Por que "MVP"?**
- Produto Mínimo Viável (Minimum Viable Product)
- Objetivo: Sistema funcional básico, não completo
- Foco em validar a abordagem antes de expandir

---

## 🏗️ Arquitetura e Componentes

### O Que Continha (TUDO Misturado)

#### 1. **Sistema Técnico Completo**

**Banco de Dados:**
- PostgreSQL com 40+ tabelas
- Integração PostGIS para análise geoespacial
- Suporte pgvector para embeddings de IA

**Backend:**
- Sistema RAG (Retrieval-Augmented Generation)
- Workflows n8n para automação
- Integração com OpenAI embeddings
- API de acesso aos dados

**Frontend:**
- Dashboard com 6 abas analíticas
- Chat com IA integrada
- Visualizações interativas com Recharts
- Interface web responsiva

**Agentes Especializados:**
- **ECON** (Economia)
- **SOCIAL** (Indicadores Sociais)
- **TERRA** (Territorial/Geográfico)
- **ENVIRONMENT** (Meio Ambiente)

#### 2. **Metodologia de Colaboração** (Embutida no Código)

- Padrões de interação humano-IA
- Workflows de análise
- Protocolos de comunicação entre agentes
- Gestão de continuidade entre sessões

### Estrutura de Pastas (Antes da Reorganização Final)

Originalmente 34 pastas, depois reorganizado para 8:

```
framework-v6-mvp/
├── backend/
├── frontend/
├── database/
├── agents/
├── docs/
├── scripts/
├── tests/
└── config/
```

**Problema:** Misturava código técnico com documentação metodológica

---

## ⚠️ Problema Fundamental

### Confusão entre Metodologia e Artefatos

**O que acontecia:**
```
framework-v6-mvp/
├── codigo-do-sistema/          ← ARTEFATO (o que produzir)
│   ├── dashboard.tsx
│   ├── database.sql
│   └── agents.py
└── como-usar-IA/               ← METODOLOGIA (como trabalhar)
    ├── workflow-colaboracao.md
    ├── padroes-interacao.md
    └── continuidade-sessoes.md
```

**Dificuldade:**
- Para usar a **metodologia**, precisava entender o **sistema inteiro**
- Para replicar o **sistema**, vinha junto a metodologia específica
- Difícil de manter: mudança no sistema afetava documentação metodológica
- Difícil de transferir: metodologia estava acoplada ao código

### Analogia

É como se um livro de receitas (metodologia) estivesse escrito DENTRO da cozinha (sistema):
- Para ler a receita, você precisa ter a cozinha idêntica
- Para construir a cozinha, você precisa seguir a receita específica
- Impossível usar a receita em outra cozinha
- Impossível ter cozinha diferente com mesma receita

**O correto:**
- Livro de receitas separado (ia-collab-os) = METODOLOGIA
- Cozinha é um exemplo específico (tocantins-integrado) = ARTEFATO

---

## 📊 Desenvolvimento e Marcos

### Cronologia GitHub

**Criação:** 10 de novembro de 2025 (primeiro commit)

**Períodos de Atividade:**

**10-13 Nov:** Infraestrutura fundamental (Sprint inicial)
- PostgreSQL com schema completo
- Sistema RAG básico
- Workflows n8n
- Integração OpenAI

**13-15 Nov:** Features principais
- Dashboard com 6 abas
- Chat com IA
- Visualizações Recharts
- Análise geoespacial

**1-15 Dez:** Consolidação e validação
- Sessão #11 (1 dez): Validação dos 4 agentes especialistas
- Sessão #13 (8 dez): Arquitetura V4.0 com IDs semânticos
- Sessão #15 (12-14 dez): Análise multiterritorial
- **15 dez:** Reorganização profunda (34 → 8 pastas)

**Total de commits:** 183 em ~35 dias (5+ commits/dia)

**Última atividade:** 15 de dezembro de 2025

### Status Final

**O que funcionava:**
- ✅ Sistema técnico completo e funcional
- ✅ Dashboard com visualizações
- ✅ 4 agentes especializados operacionais
- ✅ Análise dos 139 municípios do Tocantins
- ✅ Integração de dados de múltiplas fontes

**O que faltava:**
- ❌ Separação clara entre metodologia e código
- ❌ Documentação metodológica independente
- ❌ Replicabilidade da metodologia sem replicar sistema
- ❌ Flexibilidade para diferentes artefatos usando mesma metodologia

---

## 🎓 Aprendizados e Lições

### 1. Separação Metodologia vs. Artefatos

**Aprendizado:**
- Metodologia (como trabalhar) deve ser independente de artefatos (o que produzir)
- Framework de colaboração deve poder ser aplicado a diferentes projetos
- Código técnico e documentação metodológica são coisas diferentes

**Aplicação:**
- **ia-collab-os:** Framework metodológico separado
- **tocantins-integrado:** Sistema técnico específico
- Metodologia pode ser usada em outros projetos além do Tocantins

### 2. Importância do GitHub para Continuidade

**Aprendizado:**
- Usar GitHub não apenas para versionamento, mas para **continuidade entre sessões**
- Issues, PRs, commits = "memória" do processo
- Documentação inline ajuda retomar contexto

**Aplicação:**
- Todos os repositórios subsequentes usam GitHub desde o início
- Issues documentam decisões e discussões
- README como ponto de entrada sempre atualizado

### 3. Múltiplos Modelos de IA

**Aprendizado:**
- Usar apenas um modelo (Manus) era limitante
- Diferentes modelos têm diferentes forças
- Colaboração entre múltiplos agentes de IA é mais rica

**Aplicação:**
- ia-collab-os formaliza colaboração humano-IA-IA
- tocantins-integrado e caderno-tocantins-2026 usam múltiplos modelos
- Framework permite orquestrar diferentes capacidades

### 4. Desenvolvimento Iterativo

**Aprendizado:**
- Framework evoluiu através de múltiplas versões (v1-v6)
- Cada iteração incorporou aprendizados da anterior
- MVP permite validar antes de investir demais

**Aplicação:**
- Ciclos de pesquisa-ação formalizados
- Cada ciclo = ação + reflexão + aprendizado
- Documentação sistemática de evolução

### 5. Valor de Arquitetura Flexível

**Aprendizado:**
- Reorganização de 34 para 8 pastas mostrou importância de simplicidade
- Arquitetura deve facilitar manutenção, não dificultar
- IDs semânticos (v4.0) melhoram rastreabilidade

**Aplicação:**
- tocantins-integrado tem arquitetura mais limpa desde o início
- Separação clara de responsabilidades
- Documentação de decisões arquiteturais

---

## 🔄 Evolução para Repositórios Separados

### Framework V6 MVP se dividiu em:

```
┌─────────────────────────────────┐
│      framework-v6-mvp           │
│                                 │
│  Sistema Técnico                │
│  +                              │
│  Metodologia                    │
│  (MISTURADOS)                   │
└────────┬────────────────────────┘
         │
         │ SEPARAÇÃO
         │
         ├──────────────────┬──────────────────┐
         │                  │                  │
         ▼                  ▼                  ▼
┌─────────────────┐  ┌──────────────┐  ┌──────────────┐
│ tocantins-      │  │ ia-collab-   │  │ caderno-     │
│ integrado       │  │ os           │  │ tocantins    │
│                 │  │              │  │ -2026        │
│ Sistema de IA   │  │ Metodologia  │  │              │
│ para análise    │  │ de           │  │ Artefato     │
│ territorial     │  │ colaboração  │  │ produzido    │
│                 │  │ H-IA-IA      │  │              │
│ (ARTEFATO)      │  │ (PROCESSO)   │  │ (PRODUTO)    │
└─────────────────┘  └──────────────┘  └──────────────┘
         │                  │                  │
         │                  │                  │
         └──────────────────┴──────────────────┘
                            │
                            ▼
                  ┌──────────────────┐
                  │   doutorado      │
                  │                  │
                  │ Integração       │
                  │ Acadêmica        │
                  │                  │
                  │ (ANÁLISE)        │
                  └──────────────────┘
```

### Por Que a Separação Foi Necessária

**1. tocantins-integrado** (Sistema Técnico):
- Foco em implementação técnica
- Código, arquitetura, funcionalidades
- Específico para Tocantins e análise territorial
- Pode evoluir independentemente

**2. ia-collab-os** (Metodologia):
- Foco em como trabalhar com IA
- Padrões, princípios, workflows
- Genérico, aplicável a outros projetos
- Pode ser usado por outras pessoas em outros contextos

**3. caderno-tocantins-2026** (Artefato):
- Produto concreto usando a metodologia
- Não é código, é análise
- Validação prática da metodologia
- Utilizável independentemente do sistema

**4. doutorado** (Documentação Acadêmica):
- Análise de todo o processo
- Reflexão sobre aprendizados
- Contribuição para conhecimento científico
- Integra todos os repositórios

---

## 📚 Valor do Framework V6 MVP para a Tese

### Como Ciclo 1 da Pesquisa-Ação

**Ação:** Desenvolver sistema técnico completo com metodologia embutida

**Reflexão:**
- Confusão entre metodologia e artefatos dificulta replicação
- Metodologia ficou acoplada ao código
- Difícil de transferir conhecimento

**Aprendizado:**
- Separar claramente metodologia de artefatos
- Metodologia deve ser documentada independentemente
- Framework deve ser genérico, não específico do sistema

**Nova Ação (Ciclo 2):**
- Criar tocantins-integrado (só sistema)
- Criar ia-collab-os (só metodologia)
- Aplicar metodologia em caderno-tocantins-2026

### Evidências para a Tese

**Diários de Pesquisa-Ação:**
- Issues documentam decisões e discussões
- Commits mostram evolução do pensamento
- Documentação técnica revela processo

**Artefatos Produzidos:**
- Código fonte (183 commits)
- Arquitetura evoluída (v1.0 → v4.0)
- Sistema funcional validado

**Reflexões Documentadas:**
- Sessões numeradas (#11, #13, #15)
- Reorganização de estrutura de pastas
- Decisões de design registradas

### Contribuição Teórica

**Demonstra:**
- Evolução iterativa de frameworks
- Importância de separação de conceitos
- Valor da reflexão em pesquisa-ação

**Serve de base para:**
- Discussão sobre design de frameworks colaborativos
- Análise de erros e correções
- Modelo de evolução de metodologias

---

## 🔗 Relação com Outros Repositórios

### → tocantins-integrado

**Herdou:**
- Arquitetura técnica base
- Conceito de agentes especializados
- Integração de dados de múltiplas fontes
- Uso de PostgreSQL + PostGIS

**Melhorou:**
- Separou sistema de metodologia
- Arquitetura mais limpa desde início
- Documentação técnica focada

**Diferenças:**
- Sem documentação metodológica embutida
- Foco apenas em funcionalidades do sistema
- Usa ia-collab-os como metodologia externa

### → ia-collab-os

**Extraiu:**
- Padrões de colaboração humano-IA observados
- Princípios de uso de GitHub para continuidade
- Workflows de orquestração de múltiplos agentes

**Generalizou:**
- Não é específico do Tocantins
- Aplicável a qualquer projeto de colaboração H-IA
- Framework independente de artefatos

**Adicionou:**
- Formalização de roles (humano, IA1, IA2)
- Documentação de padrões arquiteturais
- Templates e exemplos

### → caderno-tocantins-2026

**Usa:**
- Metodologia extraída (ia-collab-os)
- Não o código técnico (não precisa)

**Beneficiou:**
- Produção manual mais estruturada
- Colaboração multi-IA eficiente
- Continuidade entre sessões via GitHub

### → doutorado

**Documenta:**
- Framework v6-mvp como Ciclo 1 histórico
- Contexto de origem dos outros repositórios
- Aprendizados que levaram à separação

**Integra:**
- Diários de PA do período v6-mvp
- Reflexões sobre evolução
- Evidências de transformação da prática

---

## 📝 Status e Recomendações

### Status Atual

**Repositório:**
- 🟠 Arquivado (não recebe mais commits)
- 📚 Valor: Contexto histórico e referência
- 🔒 Não deve ser modificado (preservar histórico)

**Código:**
- ✅ Funcional mas não deve ser usado
- 🔄 Substituído por tocantins-integrado
- 📖 Útil para consulta de decisões passadas

### Recomendações de Uso

**✅ USAR para:**
- Consultar decisões de design passadas
- Entender evolução do pensamento
- Referência histórica em documentos
- Análise de aprendizados em pesquisa-ação

**❌ NÃO USAR para:**
- Desenvolvimento novo (usar tocantins-integrado)
- Metodologia (usar ia-collab-os)
- Produção de artefatos (usar ia-collab-os + manual)

### Como Citar na Tese

**Referência:**
```
RIBEIRO, Henrique M. Framework V6 MVP: Sistema de Inteligência
Territorial (Versão Superada). Versão histórica. GitHub, 2025.
Disponível em: https://github.com/henrique-m-ribeiro/framework-v6-mvp.
Acesso em: [data].
```

**No texto:**
```
O Ciclo 1 da pesquisa-ação resultou no Framework V6 MVP
(RIBEIRO, 2025a), que, embora funcional, apresentava confusão
entre metodologia e artefatos técnicos. Esta reflexão levou à
separação em repositórios distintos (tocantins-integrado para
sistema técnico e ia-collab-os para metodologia) no Ciclo 2.
```

---

## ✅ Checklist de Uso do Framework V6 MVP na Tese

### Na Fundamentação Teórica

- [ ] Mencionar como primeiro framework de colaboração H-IA tentado
- [ ] Discutir confusão entre metodologia e artefatos como problema teórico
- [ ] Conectar com literatura sobre design de frameworks

### Na Metodologia

- [ ] Descrever como Ciclo 1 da pesquisa-ação
- [ ] Explicar ação, reflexão e aprendizado
- [ ] Justificar decisão de separação em Ciclo 2

### Nos Resultados

- [ ] Apresentar evidências do Ciclo 1 (commits, issues, sistema funcional)
- [ ] Documentar reflexões que levaram à separação
- [ ] Mostrar evolução para repositórios separados

### Na Discussão

- [ ] Analisar importância de separar metodologia de artefatos
- [ ] Discutir valor de iteração e reflexão em design de frameworks
- [ ] Conectar com contribuições teóricas sobre pesquisa-ação

---

## 🎯 Principais Lições para o Campo

1. **Separação de Conceitos é Fundamental:**
   - Metodologia ≠ Artefato
   - Processo ≠ Produto
   - Framework ≠ Aplicação

2. **Reflexão Leva a Melhorias:**
   - Pesquisa-ação permite identificar problemas
   - Ciclos iterativos refinam abordagem
   - Não ter medo de refatorar completamente

3. **Documentação do Processo é Valiosa:**
   - GitHub como ferramenta de reflexão
   - Issues e commits como diários de PA
   - Histórico preservado tem valor acadêmico

4. **Frameworks Devem Ser Genéricos:**
   - Aplicáveis a múltiplos contextos
   - Independentes de implementações específicas
   - Transferíveis e replicáveis

---

**Status:** 🟠 Contexto Histórico
**Sucessores:** tocantins-integrado + ia-collab-os + caderno-tocantins-2026
**Valor:** Lições aprendidas e evidências de Ciclo 1 de pesquisa-ação
**Última atualização:** 31 de Janeiro de 2026
