# ADR-001: Adoção de Metodologia de IA Distribuída por Papéis

**Data:** 2026-01-08
**Status:** Aceita
**Decisor:** CEO (Henrique M. Ribeiro)
**Participantes:** CEO, Dev Team (Claude Code)

---

## Contexto

O desenvolvimento do projeto Tocantins Integrado enfrentava desafios com o uso de IA para assistência:

1. **Mistura de níveis de abstração**: Sessões anteriores misturavam decisões estratégicas com implementação técnica, gerando confusão
2. **Perda de contexto**: Informações importantes se perdiam entre sessões
3. **Falta de rastreabilidade**: Decisões eram tomadas sem documentação adequada
4. **Sobrecarga cognitiva**: Uma única sessão tentava fazer tudo

A experiência com o ambiente Manus como intermediário técnico mostrou benefícios em separar responsabilidades.

---

## Decisão

> **Decidimos adotar uma metodologia de trabalho com múltiplas instâncias de IA, cada uma assumindo um papel organizacional específico (CEO humano, CTO, Dev Team, etc.), com comunicação via handoffs documentados e decisões registradas em ADRs.**

### Estrutura adotada

```
CEO (Humano) ─────────────────────────────────
      │         Visão, prioridades, validação
      ▼
CTO (IA) ─────────────────────────────────────
      │         Arquitetura, specs, code review
      ▼
Dev Team (IA) ────────────────────────────────
                Implementação, testes
```

### Elementos do framework

1. **Papéis definidos**: Cada papel tem escopo, autoridade e prompt de inicialização
2. **Handoffs estruturados**: Template padronizado para transferência de contexto
3. **ADRs**: Registro formal de decisões importantes
4. **Logs de sessão**: Documentação do que aconteceu em cada sessão

---

## Alternativas Consideradas

### Alternativa 1: Sessão única com contexto longo

**Descrição:** Usar uma única sessão de IA com todo o contexto do projeto

| Prós | Contras |
|------|---------|
| + Simplicidade | - Limite de contexto da IA |
| + Sem overhead de handoff | - Mistura de níveis de abstração |
| | - Difícil escalar |

**Por que descartada:** Limitações técnicas de contexto e experiência negativa em sessões anteriores.

---

### Alternativa 2: Documentação pesada sem papéis

**Descrição:** Manter documentação detalhada mas sem separar papéis

| Prós | Contras |
|------|---------|
| + Mais simples que papéis | - Ainda mistura responsabilidades |
| + Documentação persistente | - Sem clareza de quem faz o quê |

**Por que descartada:** Não resolve o problema de separação de responsabilidades.

---

### Alternativa 3: Não fazer nada

**Descrição:** Continuar com o modelo ad-hoc anterior

| Prós | Contras |
|------|---------|
| + Nenhum esforço | - Problemas persistem |
| | - Qualidade inconsistente |

**Por que descartada:** Experiência mostrou que modelo anterior era ineficiente.

---

## Consequências

### Positivas
- Cada sessão tem escopo claro e limitado
- Contexto é preservado via handoffs documentados
- Decisões ficam rastreáveis
- Facilita adicionar novos papéis (CFO, CMO) no futuro
- CEO humano mantém controle estratégico

### Negativas
- Overhead de documentação
- Custo de tradução entre sessões
- CEO como gargalo de orquestração
- Curva de aprendizado inicial

### Neutras
- Mudança de mindset necessária
- Novos arquivos no repositório

---

## Implementação

### Ações necessárias
1. [x] Criar estrutura de diretórios `.governance/`
2. [x] Criar documento de metodologia (METHODOLOGY.md)
3. [x] Criar definição de papéis (ROLES.md)
4. [x] Criar templates (handoff, ADR, sessão)
5. [x] Criar este ADR inaugural
6. [ ] Testar em próximas sessões
7. [ ] Iterar baseado em feedback

### Critérios de sucesso
- Handoffs permitem continuidade sem perda significativa de contexto
- Decisões importantes têm ADR correspondente
- Papéis respeitam seus limites de autoridade
- CEO consegue orquestrar sem sobrecarga excessiva

### Prazo
- Framework inicial: Janeiro 2026 (concluído)
- Primeira revisão: Após 5 sprints de uso

---

## Reversibilidade

**Nível:** Alta

A metodologia pode ser abandonada a qualquer momento, voltando ao modelo ad-hoc. Os artefatos documentados (handoffs, ADRs) permanecem úteis independentemente da metodologia.

---

## Referências

- Sessão de desenvolvimento 2026-01-08 (esta sessão)
- Experiência com Manus como CTO intermediário
- Conceito de ADR: https://adr.github.io/

---

## Histórico

| Data | Mudança | Autor |
|------|---------|-------|
| 2026-01-08 | Criação | Dev Team (Claude Code) |
| 2026-01-08 | Aprovação | CEO |

---

*Primeira decisão documentada do projeto*

---

## Lente de Delegação Inteligente (adicionada v2.2)

> Anotação retroativa à luz de Tomašev, N., Franklin, M., & Osindero, S. (2025). "Intelligent AI Delegation." arXiv:2602.11865.

| Conceito de Delegação | Manifestação neste ADR |
|----------------------|------------------------|
| **Cascading Delegation** | Estrutura CEO→CTO→Dev é delegação em cascata com atenuação de privilégio (bounded autonomy) |
| **Authority Gradient** | Hierarquia formal de autoridade definida entre os 3 papéis |
| **Privilege Attenuation** | Cada nível abaixo tem menos autoridade que o anterior (Dev não altera escopo, CTO não decide negócio) |
| **Delegation State Transfer** | Handoffs estruturados resolvem o problema de transferência de estado entre delegatários |
| **Delegation Accountability** | ADRs como mecanismo de rastreabilidade de decisões delegadas |
| **Stateless Delegatee Problem** | Motivação central: LLMs sem memória persistente entre sessões |
| **Meaningful Human Control** | CEO humano mantém controle estratégico significativo |

**Interpretação:** Esta ADR documenta a decisão que criou, empiricamente, uma estrutura de delegação em cascata que Tomašev et al. formalizariam teoricamente um mês depois. A convergência é independente — este ADR foi escrito em 08/01/2026, o artigo publicado em 17/02/2025 (arXiv), sem conhecimento mútuo.
