# Ficha Descritiva: framework-v6-mvp

**Status:** Historico (superado)
**Repositorio:** github.com/henrique-m-ribeiro/framework-v6-mvp
**Periodo de atividade:** 10 Nov — 15 Dez 2025 (36 dias)
**Commits:** 183
**Tamanho:** 13,8 MB (571 arquivos)

---

## 1. O que e

O framework-v6-mvp foi o **primeiro repositorio do projeto de doutorado**, criado como um sistema monolitico que misturava:
- Sistema tecnico (dashboard, agentes IA, banco de dados)
- Metodologia de colaboracao humano-IA
- Dados territoriais
- Documentacao de pesquisa

Foi desenvolvido primariamente na plataforma **Replit**, usando **Replit Agent** e **Manus** como agentes IA.

## 2. Stack Tecnica

- **Frontend:** React + TypeScript + Vite
- **Backend:** Node.js + Express
- **Banco:** PostgreSQL + pgvector (para RAG)
- **Orquestracao:** N8N (workflows de agentes)
- **Agentes:** 19 agentes dimensionais (ambiental, economico, social, territorial)
- **RAG:** Retrieval-Augmented Generation para knowledge base

## 3. Por que foi Superado

O framework-v6-mvp foi abandonado por tres razoes:

1. **Mistura de preocupacoes:** Metodologia, sistema tecnico e dados de pesquisa estavam no mesmo repositorio, dificultando manutencao e reutilizacao.
2. **Plataforma limitante:** Replit impunha restricoes de ambiente que dificultavam deploys e testes.
3. **Complexidade excessiva:** 571 arquivos para um MVP era sinal de overengineering.

A decisao de refatorar gerou 3 novos repositorios:
- **tocantins-integrado** (sistema tecnico)
- **ia-collab-os** (metodologia extraida)
- **caderno-tocantins-2026** (artefatos praticos)

## 4. Valor como Evidencia de Pesquisa

Apesar de superado tecnicamente, o framework-v6-mvp contem **evidencias primarias insubstituiveis**:

### 4.1 Diarios de PA (21 documentos, ~550 KB)
Cobrem as sessoes 1-15, documentando a genese do projeto, as primeiras tentativas, os erros formativos e a evolucao da colaboracao humano-IA. Sao o registro dos **Ciclos 0 e 1** da pesquisa-acao.

**Versao canonica:** Os diarios foram copiados para tocantins-integrado com nomenclatura padronizada (2025-11-10_sessao-01.md, etc.). A versao em tocantins-integrado e a referencia.

### 4.2 Artigo Cientifico (rascunho, ~165 KB)
"The Mediator Effect" — artigo completo com introducao, metodos, resultados, discussao, conclusao e cover letter para TOCHI. Pode ser base para producoes futuras (Artigo 1 do plano Ciclo 5).

**Localizacao:** docs/archive/legacy/artigo/

### 4.3 Analises Dimensionais (4 documentos, ~345 KB)
Analises profundas das dimensoes ambiental, economica, social e territorial do Tocantins. Sao fundamentacao empirica para o framework de IT.

**Localizacao:** docs/archive/legacy/analises_dimensionais/

### 4.4 Prompts de Sessao (11+ documentos)
Registros de como o pesquisador instruia os agentes IA. Evidencia direta para PS4 (padroes de colaboracao H-IA).

**Localizacao:** docs/prompts/

### 4.5 Sistema de Continuidade
Documentacao do sistema de continuidade entre sessoes (~52 KB) — precursor do ia-collab-os.

**Localizacao:** docs/archive/legacy/metodologia/

## 5. Licoes Aprendidas

1. **Separar preocupacoes desde o inicio** — metodologia, sistema e dados devem ser repositorios distintos
2. **Nao depender de plataforma proprietaria** — Replit impunha limitacoes desnecessarias
3. **Documentar e desacelerar** — a producao intensa gera muitos artefatos, mas poucos sao reflexivos
4. **Os erros iniciais sao dados** — as 15 sessoes do framework-v6-mvp sao dados sobre como NAO organizar um projeto de pesquisa-acao com IA, e isso e valioso

---

**Versao:** 1.0
**Data:** 12 de Fevereiro de 2026
