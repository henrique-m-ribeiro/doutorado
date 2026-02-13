# ADR-002: Dados Apenas de Fontes Oficiais (Sem Estimativas)

**Data:** 2026-01-08
**Status:** Aceita
**Decisor:** CEO (Henrique M. Ribeiro)
**Participantes:** CEO, CTO (Manus), Dev Team (Claude Code)

---

## Contexto

O teste piloto de Palmas revelou que 50.6% dos dados coletados eram "estimados" - valores calculados pelo sistema sem metodologia validada ou citação acadêmica.

O CEO determinou que:
> "É crucial, mesmo no MVP, que todos os dados sejam obtidos de fontes oficiais, ou calculados de forma direta destes, a partir de uma metodologia validada ou acadêmica, com citação da referência."

Dados estimados sem fundamentação comprometem a credibilidade da plataforma junto a gestores públicos.

---

## Decisão

> **Decidimos que o sistema só apresentará dados de três categorias: (1) oficiais com fonte citada, (2) calculados com metodologia acadêmica citada, ou (3) marcados como "indisponível" quando não houver fonte confiável.**

### Classificação de dados

| Categoria | Critério | Apresentação |
|-----------|----------|--------------|
| `official` | Dado direto de fonte oficial (IBGE, INEP, etc) | Exibir com fonte |
| `calculated` | Calculado com metodologia citada | Exibir com metodologia |
| `unavailable` | Sem fonte confiável | "Dado indisponível" |

### O que foi eliminado

- Extrapolações temporais sem validação
- Estimativas baseadas em médias regionais
- Projeções sem metodologia citada

---

## Alternativas Consideradas

### Alternativa 1: Manter estimativas com disclaimer

**Descrição:** Exibir dados estimados com aviso de "valor aproximado"

| Prós | Contras |
|------|---------|
| + Mais dados disponíveis | - Compromete credibilidade |
| + Dashboards mais completos | - Gestores podem tomar decisões com dados ruins |
| | - Risco reputacional |

**Por que descartada:** Em contexto de gestão pública, dados imprecisos são piores que dados ausentes.

---

### Alternativa 2: Apenas dados 100% oficiais

**Descrição:** Remover qualquer dado que não seja direto da fonte

| Prós | Contras |
|------|---------|
| + Máxima confiabilidade | - Elimina cálculos úteis (PIB per capita, etc) |
| | - Muito restritivo |

**Por que descartada:** Cálculos derivados com metodologia clara são aceitáveis.

---

## Consequências

### Positivas
- 100% dos dados exibidos são confiáveis
- Credibilidade junto a gestores públicos
- Base sólida para decisões
- Transparência sobre limitações (dados indisponíveis)

### Negativas
- 50.6% dos indicadores do piloto ficaram "indisponíveis"
- Dashboards com lacunas visíveis
- Pressão para "preencher" dados que pode surgir

### Mitigação das negativas
- Priorizar integração com APIs faltantes (IBGE, SICONFI)
- Documentar plano para cada dado indisponível
- Comunicar claramente as limitações aos usuários

---

## Implementação

### Coletores modificados
| Coletor | Mudança |
|---------|---------|
| MapBiomasCollector | Estimativas → unavailable |
| AtlasBrasilCollector | Só retorna Censo 2010 |
| SNISCollector | Só 2020-2022 (oficial) |
| ComexStatCollector | API falha → unavailable |

### Código-chave
```typescript
// Padrão para todos os coletores
if (!fonteOficial) {
  return {
    data_quality: 'unavailable',
    notes: 'Fonte: [nome]. Dado requer [ação]. Ref: [citação]'
  };
}
```

---

## Reversibilidade

**Nível:** Média

Reativar estimativas requer modificar coletores e decisão do CEO. Não é trivial mas é possível se estratégia mudar.

---

## Referências

- Sessão 2026-01-08 com CEO
- docs/PILOTO_PALMAS_RESULTADOS.md
- docs/RELATORIO_CORRECOES_COLETORES.md

---

## Histórico

| Data | Mudança | Autor |
|------|---------|-------|
| 2026-01-08 | Criação | Dev Team |
| 2026-01-08 | Aprovação | CEO |

---

## Lente de Delegação Inteligente (adicionada v2.2)

> Anotação retroativa à luz de Tomašev, N., Franklin, M., & Osindero, S. (2025). "Intelligent AI Delegation." arXiv:2602.11865.

| Conceito de Delegação | Manifestação neste ADR |
|----------------------|------------------------|
| **Contract-First Decomposition** | Dados precisam de "contrato" (fonte oficial, metodologia citada) antes de serem aceitos — verificação antes da delegação |
| **Structural Transparency** | Classificação tripartite (official/calculated/unavailable) torna transparente o que o sistema sabe e não sabe |
| **Delegation Opacity** | O anti-padrão resolvido: dados estimados sem validação eram decisões opacas do agente |
| **Liability Firebreaks** | "Indisponível" é um firebreak: prefere-se lacuna visível a dado não confiável |

**Interpretação:** Esta ADR implementa Contract-First Decomposition para dados — o mesmo princípio que Tomašev et al. propõem para tarefas. A decisão de classificar dados em 3 categorias é um mecanismo processual de Structural Transparency.

