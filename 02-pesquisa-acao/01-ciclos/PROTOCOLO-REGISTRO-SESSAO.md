# Protocolo de Registro por Sessao de Trabalho

**Data de criacao:** 12 de Fevereiro de 2026
**Objetivo:** Garantir que cada sessao de trabalho com Claude (ou outro agente IA) seja simultaneamente produtiva e geradora de dados de pesquisa.
**Referencia:** Plano de Fortalecimento Metodologico, Etapa 2.4

---

## 1. ANTES de Iniciar a Sessao (Checklist Pre-Sessao)

Antes de iniciar qualquer sessao de producao, o pesquisador deve:

- [ ] **Qual ciclo PA estou enderecando?** (Ciclo 0-5)
- [ ] **Qual questao de pesquisa (PS1-PS6) esta em foco?**
- [ ] **Qual hipotese estou testando?** (se aplicavel)
- [ ] **Quais dados vou coletar durante a sessao?**
- [ ] **O handoff da sessao anterior foi revisado?**
- [ ] **O CLAUDE.md do repo de trabalho esta atualizado com estas informacoes?**

### Onde registrar:
- No CLAUDE.md do repositorio de trabalho (secao "Sessao Ativa")
- Na declaracao pre-sessao do diario (Secao 0 do template)

---

## 2. DURANTE a Sessao

### Regra 70/30
- **70% producao:** Trabalho substantivo (codigo, documentos, analises)
- **30% reflexao/documentacao:** Registro de decisoes, observacoes, padroes

### Registro minimo obrigatorio durante a sessao:
1. **Decisoes explicitas:** Quando uma escolha for feita, registrar alternativas consideradas e justificativa
2. **Falhas e contornos:** Quando algo falhar, registrar o que falhou, por que, e como foi contornado
3. **Padroes observados:** Quando um padrao de colaboracao H-IA for percebido, anotar brevemente

### Nao e obrigatorio durante a sessao:
- Reflexao profunda (reservar para o diario pos-sessao)
- Formalizacao de contribuicoes teoricas (reservar para analise posterior)

---

## 3. AO FINAL da Sessao

### 3.1 Handoff (obrigatorio)
Produzir handoff seguindo o formato IA-Collab-OS:
- Resumo executivo
- Caminho percorrido
- Decisoes arquiteturais
- Estado do projeto
- Proximos passos
- Questoes abertas

### 3.2 Diario de Pesquisa-Acao (obrigatorio)
Produzir diario usando o template padronizado (`TEMPLATE-DIARIO.md`):
- Secao 0 (Declaracao pre-sessao) pode ser preenchida retroativamente se nao foi feita antes
- **Secao 8 (Reflexao do pesquisador) DEVE ser escrita pelo pesquisador, nao pela IA**
- Demais secoes podem ser assistidas pela IA

### 3.3 Commit e versionamento
- Commitar diario e handoff no repositorio `doutorado`
- Referenciar commits da sessao produtiva

---

## 4. Frequencia e Excecoes

### Quando aplicar o protocolo completo:
- Sessoes de producao (codigo, documentos, analises) com duracao > 1 hora
- Sessoes que produzam artefatos commitados

### Quando aplicar versao simplificada:
- Sessoes curtas (< 1 hora) de consulta ou bug fix
- Neste caso: apenas commit com mensagem descritiva, sem diario completo

### Quando NAO aplicar:
- Conversas informais ou consultas rapidas sem producao de artefatos
- Sessoes puramente de leitura/estudo

---

## 5. Modelo de CLAUDE.md (para repos de trabalho)

Cada repositorio ativo deve ter no CLAUDE.md uma secao como esta:

```markdown
## Sessao Ativa

**Ciclo PA:** [Ciclo N]
**Questao de pesquisa:** [PSn — enunciado]
**Hipotese em teste:** [se aplicavel]
**Objetivo especifico:** [OEn]

### Instrucoes para agente IA:
- Cada sessao deve comecar declarando qual ciclo PA e qual questao de pesquisa endereca
- Registrar decisoes explicitas com alternativas e justificativa
- Produzir diario ao final usando template em `doutorado/02-pesquisa-acao/03-dados/diarios-sessoes/TEMPLATE-DIARIO.md`
- Manter proporcao 70/30 producao/reflexao
```

---

## 6. Fluxo Visual

```
PRE-SESSAO                DURANTE                 POS-SESSAO
-----------               --------                ----------
[Checklist]   --------→   [Producao 70%]  -----→  [Handoff]
[CLAUDE.md]               [Registro 30%]          [Diario PA]
[Handoff ant.]            [Decisoes]              [Commit]
                          [Falhas]
                          [Padroes]
```

---

## 7. Anti-padroes a Evitar

| Anti-padrao | Por que e problema | Alternativa |
|-------------|-------------------|-------------|
| Comecar sessao sem declarar ciclo PA | Producao desvinculada da pesquisa | Preencher checklist antes |
| Escrever diario apenas com IA | Circularidade; ausencia de voz do pesquisador | Secao 8 obrigatoriamente humana |
| Pular diario por "falta de tempo" | Reflexao e dado de pesquisa, nao overhead | Usar versao simplificada no minimo |
| Focar 100% em producao | Pesquisa-acao exige reflexao | Regra 70/30 |
| Copiar template sem reflexao genuina | Burocracia, nao rigor | Se o template nao ajuda, simplifica-lo |

---

**Versao:** 1.0
**Data:** 12 de Fevereiro de 2026
**Revisao prevista:** Apos 3 sessoes de uso (teste de utilidade do protocolo)
