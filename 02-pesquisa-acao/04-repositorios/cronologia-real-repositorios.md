# Cronologia Real e Relações entre os Repositórios

**Data:** 31 de Janeiro de 2026
**Status:** Cronologia corrigida e validada
**Versão:** 1.0

---

## 🎯 Propósito deste Documento

Este documento corrige e documenta a **cronologia REAL** de desenvolvimento dos repositórios relacionados à pesquisa-ação do doutorado, estabelecendo claramente as relações entre eles.

**IMPORTANTE:** A cronologia de commits do GitHub NÃO reflete a cronologia real de desenvolvimento, pois o projeto começou ANTES da adoção do GitHub como ferramenta de gestão.

---

## 📅 Linha do Tempo Real (Cronologia Correta)

### **Fase 1: Início com Demanda Prática** (Período: Pré-GitHub)

#### **Primeira Demanda: Criação dos Cadernos Tocantins**

**Contexto:**
- Surgiu a demanda de criar cadernos de análise territorial do Tocantins
- Objetivo: Subsidiar entrevistas e estratégias de campanha eleitoral 2026
- Trabalho iniciou SEM uso de GitHub

**Framework Inicial (Incipiente):**
- **Ferramenta:** Apenas modelo Manus (IA única)
- **Objetivo:** Garantir continuidade entre sessões de trabalho
- **Problema identificado:** Framework confundia metodologia de colaboração humano-IA com os artefatos produzidos (sistema informacional multiespecialistas)

**Artefato produzido:**
- Primeiros cadernos de análise (não versionados no GitHub inicialmente)

**Aprendizados:**
- Necessidade de framework mais estruturado
- Limitações de usar apenas um modelo de IA
- Confusão entre "como trabalhar" (metodologia) e "o que produzir" (sistema/artefato)

**Registros:**
- Diários de pesquisa-ação deste período existem mas estão esparsos

---

### **Fase 2: Primeira Tentativa de Sistematização** (Nov-Dez 2025)

#### **framework-v6-mvp**
**Repositório:** https://github.com/henrique-m-ribeiro/framework-v6-mvp

**Natureza:**
- Sistema técnico completo (código, banco de dados, dashboards)
- MAS misturado com documentação metodológica
- **TUDO junto e confuso** no mesmo repositório

**O que continha:**
- Código do sistema informacional multiespecialistas
- Banco de dados PostgreSQL com 40+ tabelas
- Dashboard com 6 abas analíticas
- Sistema RAG e workflows n8n
- Agentes especializados (ECON, SOCIAL, TERRA, ENVIRONMENT)
- Metodologia de colaboração humano-IA (misturada com o código)

**Primeiro commit no GitHub:** 10 de novembro de 2025
- Mas o desenvolvimento conceitual começou antes

**Problema Fundamental:**
- Confundia metodologia (como trabalhar com IA) com artefatos (sistema técnico)
- Dificultava manutenção e evolução
- Difícil de replicar a metodologia sem replicar todo o sistema

**Status Atual:**
- **Versão superada**, substituída pela separação em múltiplos repositórios
- Valor: **Contexto histórico** importante para entender a evolução

**Primeiro commit no GitHub:** 10 de novembro de 2025

---

### **Fase 3: Reinício Programado e Separação de Conceitos** (Jan 2026)

**Motivação do Reinício:**
- Usar conhecimentos adquiridos durante framework-v6-mvp
- Separar claramente metodologia de artefatos técnicos
- Adotar GitHub como ferramenta de continuidade entre sessões
- Usar múltiplos modelos de IA (não apenas Manus)

**Mudanças Fundamentais:**
1. ✅ GitHub para versionamento e continuidade
2. ✅ Múltiplos modelos de IA (não só Manus)
3. ✅ Separação metodologia vs. artefatos

#### **3.1. tocantins-integrado** (Sistema Técnico)
**Repositório:** https://github.com/henrique-m-ribeiro/tocantins-integrado

**Primeiro commit no GitHub:** 5 de janeiro de 2026

**Natureza:**
- **Parte técnica** separada do framework-v6-mvp
- Sistema de IA para diagnósticos territoriais multidimensionais
- Análise dos 139 municípios e 8 microrregiões do Tocantins

**Arquitetura Prevista (Dupla Camada):**

**Camada 1: Dashboard de Linha de Frente**
- Interface com dados e análises pré-realizadas
- IA para facilitar exploração dos dados
- Visualizações interativas
- **Status Atual:** 🟡 Quase funcional
- **Pendente:** Upload de dados e análises para alimentar o sistema

**Camada 2: Sistema Multiagentes**
- Equipe de especialistas em múltiplas dimensões de políticas públicas
- Análises sob demanda (não pré-computadas)
- 4 dimensões no MVP: Saúde, Educação, Infraestrutura, Economia
- **Status Atual:** 🔴 Não implementada ainda

**Objetivo Original:**
- Sistema completo geraria os cadernos Tocantins **automaticamente**
- Substituiria trabalho manual de análise territorial

**Objetivo Mantido:**
- ✅ Sistema deve gerar documentos com mesma qualidade dos cadernos manuais
- ✅ Sistema deve atualizar análises periodicamente (temporal)

**Complicações:**
- Implementação apresentou desafios técnicos
- Desenvolvimento mais complexo que previsto
- **Registrado em:** Issues e commits do repositório

**Papel dos Cadernos Manuais:**
- 📊 Cadernos finalizados vão **alimentar Camada 1** (dados e análises)
- 🧪 Cadernos vão servir de **benchmark de qualidade** para testar Camada 2 quando implementada

#### **3.2. ia-collab-os** (Framework Metodológico)
**Repositório:** https://github.com/henrique-m-ribeiro/ia-collab-os

**Primeiro commit no GitHub:** 14 de janeiro de 2026

**Origem:**
- Surgiu **DA PRÁTICA** de desenvolver tocantins-integrado
- Extração da metodologia de colaboração humano-IA observada no processo
- Separação clara entre "como trabalhar" e "o que produzir"

**Natureza:**
- **Parte metodológica** separada do framework-v6-mvp
- Framework de colaboração humano-IA-IA (múltiplos agentes de IA)
- Uso de GitHub para continuidade entre sessões
- Padrões de orquestração de equipes mistas

**Diferença Fundamental do V6 MVP:**
- ✅ Separa claramente metodologia de artefatos
- ✅ Pode ser aplicado a diferentes projetos (não só Tocantins Integrado)
- ✅ Documentação focada no "processo", não no "produto"

**Conteúdo:**
- Princípios de colaboração
- Roles (humano, agentes de IA)
- Padrões arquiteturais
- Templates e workflows
- Case study: Tocantins Integrado

---

### **Fase 4: Pivot Emergencial - Volta aos Cadernos** (Jan 2026)

#### **Contexto da Decisão:**

**Problema:**
- Implementação do tocantins-integrado apresentou complicações
- Sistema não estava pronto para gerar cadernos automaticamente

**Pressão Externa:**
- ⚠️ Cobrança pela entrega dos cadernos
- 📅 Início das entrevistas de campanha se aproximando
- ⏰ Prazo não poderia esperar conclusão do sistema

**Decisão Tomada:**
- ⏸️ **PAUSOU** implementação do sistema Tocantins Integrado
- 🔄 **VOLTOU** esforços para elaboração MANUAL dos cadernos
- 🆕 **Mas agora** usando framework ia-collab-os (não mais o incipiente)

#### **4.1. caderno-tocantins-2026** (Artefato Produzido)
**Repositório:** https://github.com/henrique-m-ribeiro/caderno-tocantins-2026

**Primeiro commit no GitHub:** 20 de janeiro de 2026
- **MAS:** Trabalho conceitual começou muito antes (Fase 1, pré-GitHub)

**Natureza:**
- **Artefato concreto** produzido aplicando ia-collab-os
- Análises territoriais dos 139 municípios do Tocantins
- Notebooks de pesquisa com dados e insights

**Modo de Produção ATUAL:**
- 👤 **Humano (você)** + 🤖 **IA usando ia-collab-os**
- Trabalho MANUAL, não automatizado
- Aplicação do framework de colaboração humano-IA-IA
- Múltiplos modelos de IA (não apenas Manus)

**Conteúdo Produzido:**
- Volume 1: Análises completas dos 139 municípios
- 9 dimensões de análise territorial
- 8 microrregiões documentadas
- ~6.965 linhas de conteúdo
- Dados de fontes governamentais oficiais (IBGE, DATASUS, INEP, etc.)

**Valor para o Sistema:**
- 📥 Vai **alimentar Camada 1** do tocantins-integrado quando retomar
- 🎯 Vai ser **referência de qualidade** para Camada 2 quando implementada
- 🧪 Teste: Sistema deve produzir análises de qualidade equivalente

**Última atividade GitHub:** 31 de janeiro de 2026 (consolidação Volume 1)

---

### **Fase 5: Consolidação Acadêmica** (31 Jan 2026 - Presente)

#### **5.1. doutorado** (Registro Acadêmico)
**Repositório:** https://github.com/henrique-m-ribeiro/doutorado

**Primeiro commit:** 31 de janeiro de 2026 (HOJE)

**Natureza:**
- **Repositório central acadêmico**
- Documentação de todo o processo de pesquisa-ação
- Integração dos 3 (+1 histórico) repositórios técnicos
- Organização do doutorado em Políticas Públicas

**Estrutura:**
- Disciplinas cursadas
- Projeto de pesquisa
- Fundamentação teórica
- Documentação dos ciclos de pesquisa-ação
- Referências bibliográficas
- Qualificação e defesa
- Administração do programa

**Relação com outros repositórios:**
- Documenta e integra tocantins-integrado, ia-collab-os, caderno-tocantins-2026
- Trata framework-v6-mvp como contexto histórico
- Centraliza diários de pesquisa-ação (quando organizados)

---

## 🔗 Mapa de Relações entre Repositórios

```
┌─────────────────────────────────────────────────────────────┐
│                    EVOLUÇÃO TEMPORAL                        │
└─────────────────────────────────────────────────────────────┘

FASE 1: Pré-GitHub
┌──────────────────────────┐
│ Cadernos Iniciais        │
│ (não versionados)        │
│ Framework incipiente     │
│ Apenas Manus             │
└────────────┬─────────────┘
             │
             │ Aprendizados
             ▼
FASE 2: Primeira Sistematização (Nov-Dez 2025)
┌──────────────────────────────────────────────┐
│         framework-v6-mvp                     │
│                                              │
│  ┌────────────────────────────────────┐    │
│  │ TUDO MISTURADO:                    │    │
│  │ • Sistema técnico                  │    │
│  │ • Código + Banco de dados          │    │
│  │ • Dashboard                        │    │
│  │ • Metodologia (confusa)            │    │
│  └────────────────────────────────────┘    │
│                                              │
│  PROBLEMA: Metodologia ≠ Artefato           │
└────────────┬─────────────────────────────────┘
             │
             │ Reinício Programado
             │ Separação de Conceitos
             ▼
FASE 3: Reinício e Separação (Jan 2026)
┌─────────────────────────────────────────────────┐
│                                                 │
│  ┌──────────────────────┐                      │
│  │  tocantins-integrado │ ◄────┐               │
│  │  (Sistema Técnico)   │      │               │
│  │                      │      │ Framework     │
│  │  Camada 1: 🟡 quase  │      │ emergiu da    │
│  │  Camada 2: 🔴 não    │      │ PRÁTICA       │
│  └──────────────────────┘      │               │
│                                 │               │
│  ┌──────────────────────┐      │               │
│  │    ia-collab-os      │ ◄────┘               │
│  │    (Metodologia)     │                      │
│  │                      │                      │
│  │  Colaboração H-IA-IA │                      │
│  │  GitHub + Multi-IA   │                      │
│  └──────────┬───────────┘                      │
│             │                                   │
└─────────────┼───────────────────────────────────┘
              │
              │ Usado para produzir
              ▼
FASE 4: Pivot Emergencial (Jan 2026)
┌─────────────────────────────────┐
│   caderno-tocantins-2026        │
│   (Artefato Produzido)          │
│                                 │
│   Produção: Manual              │
│   Humano + IA (ia-collab-os)    │
│   Volume 1: 139 municípios      │
│                                 │
│   Vai alimentar:                │
│   • Camada 1 do tocantins       │
│   • Benchmark Camada 2          │
└─────────────────────────────────┘

FASE 5: Consolidação Acadêmica (31 Jan 2026)
┌──────────────────────────────────────────┐
│           doutorado                      │
│     (Registro Acadêmico)                 │
│                                          │
│  Integra e documenta:                    │
│  • framework-v6-mvp (histórico)          │
│  • tocantins-integrado (sistema)         │
│  • ia-collab-os (metodologia)            │
│  • caderno-tocantins-2026 (artefato)     │
│                                          │
│  Centraliza:                             │
│  • Diários de pesquisa-ação              │
│  • Fundamentação teórica                 │
│  • Projeto de pesquisa                   │
│  • Qualificação e defesa                 │
└──────────────────────────────────────────┘

┌──────────────────────────────────────────┐
│         FUTUROS REPOSITÓRIOS?            │
│  Conforme necessidade de novos artefatos │
└──────────────────────────────────────────┘
```

---

## 📊 Matriz de Status dos Repositórios

| Repositório | Status | Papel | Commits GitHub | Início Real |
|-------------|--------|-------|----------------|-------------|
| **framework-v6-mvp** | 🟠 Histórico | Sistema+Metodologia misturados | 183 (nov-dez 2025) | Pré-nov 2025 |
| **tocantins-integrado** | 🟡 Em desenvolvimento | Sistema técnico (parte 1) | 113 (jan 2026) | Jan 2026 |
| **ia-collab-os** | 🟢 Publicado | Metodologia (parte 2) | 9 (jan 2026) | Jan 2026 |
| **caderno-tocantins-2026** | 🟢 Vol 1 concluído | Artefato produzido | 82 (jan 2026) | **Pré-GitHub** |
| **doutorado** | 🆕 Criado hoje | Registro acadêmico | 10 (31 jan 2026) | 31 jan 2026 |

### Legendas:
- 🟠 Histórico: Versão superada, valor como contexto
- 🟡 Em desenvolvimento: Ativo mas incompleto
- 🟢 Publicado/Concluído: Versão estável disponível
- 🆕 Novo: Recém criado

---

## 🎯 Como os Repositórios se Relacionam

### **framework-v6-mvp** → Contexto Histórico

**Foi:**
- Primeira tentativa de sistematizar tudo
- Sistema técnico + metodologia juntos (confuso)

**Ensinou:**
- Necessidade de separar metodologia de artefatos
- Valor de usar GitHub para continuidade
- Importância de múltiplos modelos de IA

**Evoluiu para:**
- **tocantins-integrado** (pegou a parte técnica/sistema)
- **ia-collab-os** (pegou a parte metodológica)

**Status:** Não usar mais, apenas referência histórica

---

### **tocantins-integrado** → Sistema em Construção

**É:**
- Sistema de IA para diagnósticos territoriais
- Dupla camada: Dashboard (quase pronto) + Multiagentes (não feito)
- Parte técnica separada do v6-mvp

**Objetivo:**
- Gerar cadernos automaticamente (futuramente)
- Atualizar análises periodicamente

**Status Atual:**
- ⏸️ PAUSADO por complicações técnicas + pressão de prazo
- 🟡 Camada 1: 90% completa (falta dados)
- 🔴 Camada 2: 0% implementada

**Vai ser alimentado por:**
- caderno-tocantins-2026 (dados e análises manuais)

**Quando retomar:**
- Usar dados dos cadernos para completar Camada 1
- Implementar Camada 2
- Validar qualidade comparando com cadernos manuais

---

### **ia-collab-os** → Metodologia Extraída

**É:**
- Framework de colaboração humano-IA-IA
- Metodologia de trabalho com múltiplos agentes de IA
- Uso de GitHub para continuidade entre sessões

**Origem:**
- Emergiu da PRÁTICA de desenvolver tocantins-integrado
- Não foi planejado, foi observado e extraído

**Pode ser aplicado a:**
- ✅ Desenvolvimento de tocantins-integrado
- ✅ Produção de caderno-tocantins-2026
- ✅ Qualquer projeto de colaboração humano-IA
- ✅ Outros projetos futuros (novos artefatos)

**Valor:**
- Replicável em outros contextos
- Independente de artefatos específicos
- Contribuição metodológica para o campo

---

### **caderno-tocantins-2026** → Artefato Produzido

**É:**
- Análises territoriais dos 139 municípios do Tocantins
- Produzido MANUALMENTE usando ia-collab-os
- Volume 1 concluído (31 jan 2026)

**Começou:**
- MUITO ANTES do GitHub (demanda original)
- Framework incipiente (só Manus)
- Não versionado inicialmente

**Depois do pivot:**
- Produzido com ia-collab-os (framework maduro)
- Múltiplos modelos de IA
- Versionado no GitHub

**Vai servir para:**
- 📥 Alimentar dados na Camada 1 do tocantins-integrado
- 🎯 Benchmark de qualidade para Camada 2
- 📊 Análises já utilizáveis (entrevistas de campanha)

---

### **doutorado** → Integração Acadêmica

**É:**
- Repositório central da pesquisa acadêmica
- Documenta TODA a jornada da pesquisa-ação
- Integra todos os repositórios técnicos

**Relaciona:**
- framework-v6-mvp: Como contexto histórico (Ciclo 1 inicial)
- tocantins-integrado: Como sistema sendo desenvolvido
- ia-collab-os: Como contribuição metodológica
- caderno-tocantins-2026: Como artefato e validação

**Centraliza:**
- Diários de pesquisa-ação (quando organizados)
- Fundamentação teórica
- Projeto de pesquisa
- Análises acadêmicas

---

## 🔄 Ciclos de Pesquisa-Ação (Corrigidos)

### **Ciclo 0 (Pré-Formal): Demanda Inicial** (Pré-Nov 2025)
- **Ação:** Criar cadernos para campanha
- **Problema:** Sem framework estruturado
- **Reflexão:** Framework incipiente é insuficiente
- **Aprendizado:** Necessidade de sistematizar

### **Ciclo 1: Framework V6 MVP** (Nov-Dez 2025)
- **Ação:** Desenvolver sistema técnico completo
- **Problema:** Metodologia misturada com código
- **Reflexão:** Confusão dificulta manutenção e replicação
- **Aprendizado:** Separar metodologia de artefatos

### **Ciclo 2: Reinício e Separação** (Jan 2026 - primeira quinzena)
- **Ação:** Refatorar em 2 repositórios (tocantins-integrado + ia-collab-os)
- **Problema:** Implementação mais complexa que previsto
- **Reflexão:** Sistema não ficou pronto a tempo
- **Aprendizado:** Necessidade de flexibilidade (pivot)

### **Ciclo 3: Pivot Emergencial** (Jan 2026 - segunda quinzena)
- **Ação:** Produzir cadernos manualmente com ia-collab-os
- **Problema:** Prazo não espera conclusão do sistema
- **Reflexão:** Framework funciona para produção manual
- **Aprendizado:** Cadernos manuais podem alimentar sistema futuro

### **Ciclo 4 (Futuro): Retomada do Sistema** (2026.2+ planejado)
- **Ação:** Retomar tocantins-integrado com dados dos cadernos
- **Problema:** [A descobrir]
- **Reflexão:** [A realizar]
- **Aprendizado:** [A documentar]

---

## 📋 Diários de Pesquisa-Ação

### **Situação Atual:**
- ✅ Existem registros ao longo do processo
- ⚠️ Estão **ESPARSOS** em diferentes repositórios
- 📁 Alguns salvos apenas **localmente**
- 🔄 Precisam ser **organizados** futuramente

### **Localização Atual (Parcial):**
- framework-v6-mvp: Issues, commits, alguns arquivos
- tocantins-integrado: Issues, PRs, documentação
- ia-collab-os: Case study, documentação
- caderno-tocantins-2026: Alguns registros inline
- **Local:** Arquivos não commitados

### **Plano Futuro:**
- 📦 Centralizar no repositório `doutorado`
- 📂 Pasta: `02-pesquisa-acao/03-dados/diarios-sessoes/`
- 🗂️ Organizar por ciclo e data
- 📝 Padronizar formato (template de diário)
- 🔗 Referenciar commits e issues relevantes

### **Importância:**
- Evidências do processo de pesquisa-ação
- Reflexões sobre decisões tomadas
- Aprendizados ao longo do tempo
- Material primário para análise na tese

---

## ✅ Correções Necessárias na Documentação

### **Documentos a Atualizar:**

1. **`plano-atualizacao-projeto-v2.md`**
   - ✏️ Corrigir cronologia dos ciclos de PA
   - ✏️ Adicionar framework-v6-mvp como Ciclo 1
   - ✏️ Atualizar status de cada repositório
   - ✏️ Documentar pivot emergencial corretamente

2. **`02-pesquisa-acao/04-repositorios/README.md`**
   - ✏️ Adicionar framework-v6-mvp como contexto histórico
   - ✏️ Explicar relação de evolução entre repos
   - ✏️ Atualizar status atual de cada repo

3. **`02-pesquisa-acao/04-repositorios/tocantins-integrado.md`**
   - ✏️ Atualizar status das camadas (1: quase pronto, 2: não feito)
   - ✏️ Documentar papel dos cadernos em alimentar o sistema
   - ✏️ Explicar pivot emergencial

4. **`02-pesquisa-acao/00-projeto/objetivos-questoes.md`**
   - ✏️ Ajustar cronologia dos ciclos
   - ✏️ Reconhecer que Ciclo 1 já foi parcialmente executado

5. **Novo documento necessário:**
   - 📄 `02-pesquisa-acao/04-repositorios/framework-v6-mvp.md`
   - Documentar como contexto histórico
   - Explicar por que foi superado
   - Lições aprendidas

---

## 🎯 Próximas Ações

### **Imediato (Esta semana):**
1. ✅ Este documento (cronologia corrigida)
2. ⏭️ Criar documento framework-v6-mvp.md (contexto histórico)
3. ⏭️ Atualizar README dos repositórios
4. ⏭️ Atualizar plano v2.0 com cronologia correta

### **Curto Prazo (Próximas semanas):**
1. Mapear todos os diários de PA existentes
2. Criar template de diário de PA
3. Começar migração de diários para doutorado/
4. Atualizar documentação dos ciclos de PA

### **Médio Prazo (Próximo mês):**
1. Consolidar diários de PA no repositório doutorado
2. Finalizar documentação de contexto histórico
3. Redigir versão 2.0 do projeto com cronologia correta
4. Reunir com orientador para validar entendimento

---

**Versão:** 1.0 (Cronologia Corrigida)
**Data:** 31 de Janeiro de 2026
**Status:** ✅ Validada com o pesquisador
**Próxima revisão:** Após criação dos documentos corretivos
