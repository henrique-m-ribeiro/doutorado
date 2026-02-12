# Matriz de Dupla Leitura: Produto Pratico x Dado de Pesquisa

**Data:** 12 de Fevereiro de 2026
**Objetivo:** Explicitar a relacao entre cada artefato produzido e sua dupla funcao — como produto pratico (para o senador/equipe) e como dado de pesquisa (para a tese de doutorado).
**Referencia:** Plano de Fortalecimento Metodologico, Etapa 5

---

## 1. Principio Orientador

> Todo artefato produzido deve ser lido em duas chaves: como **produto pratico** que resolve um problema real e como **dado de pesquisa** que gera evidencias para a tese. Nenhuma chave substitui a outra.

### O que a dupla leitura resolve:
- Evita que a producao pratica substitua o trabalho academico
- Evita que a reflexao academica paralise a producao pratica
- Cada sessao de trabalho gera valor em ambas as dimensoes
- Explicita lacunas academicas que o produto nao cobre

---

## 2. Matriz de Artefatos

### 2.1 Caderno Tocantins 2026 — 9 Volumes

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Volume 1 (Estadual)** | Panorama geral do Tocantins para equipe de campanha; subsidia discurso e estrategia | Demonstracao de capacidade de analise territorial com IA (OE3); artefato de referencia | Nao demonstra COMO a IA transformou o processo; nao tem feedback de usuarios |
| **Volumes 2-9 (Regionais)** | 8 cadernos por microrregiao para uso em campo; fichas municipais para visitas | Evidencia de producao em escala (213 agentes); base para teste de compreensibilidade com gestores | Producao "de gabinete"; sem validacao territorial; dados nao conferidos contra fontes primarias |
| **Fichas municipais V2** | Perfil de cada municipio (139) para consulta rapida | Padrao replicavel de analise territorial; base para comparacao manual vs. automatizado | Sem voz dos municipios; estrutura definida pelo pesquisador/IA, nao por usuarios |

### 2.2 Framework ia-collab-os

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Framework v1.0** | Guia para equipes que trabalham com IA; principios de handoff e orquestracao | Contribuicao metodologica central (OE1, OE4); framework de colaboracao H-IA extraido da pratica | Sem metricas operacionais; sem validacao externa; sem criterios quantificaveis |
| **Templates (handoff, etc.)** | Ferramentas reutilizaveis para qualquer projeto H-IA | Evidencia de como padronizar colaboracao H-IA (OE4) | Ainda nao testados fora do contexto Tocantins |
| **Principios (5)** | Diretrizes praticas para equipes | Categorias analiticas para estudar colaboracao H-IA | Sem fundamentacao teorica explicita; sem dialogo com literatura de HCI |

### 2.3 Sistema tocantins-integrado

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Camada 1 (Dashboard)** | Interface visual para equipe explorar dados | Demonstracao de como IT baseada em IA pode ser entregue (OE3) | 90% completo; nao usado por ninguem alem do pesquisador |
| **Camada 2 (Multiagentes)** | Analises sob demanda; atualizacao automatica | Dado central para comparacao manual vs. automatizado (OE3) | 0% implementado; placeholder no projeto |
| **Arquitetura tecnica** | Modelo replicavel para outros estados | Evidencia de design de sistema de IT (OE6) | Sem validacao tecnica por pares |

### 2.4 Documentacao de Processo

| Dimensao | Valor como Produto Pratico | Valor como Dado de Pesquisa | Lacuna Academica |
|----------|---------------------------|----------------------------|-----------------|
| **Diarios de PA (4)** | Memoria institucional; onboarding de novos agentes | Dados primarios sobre reflexividade e aprendizagem (OE1) | Escritos com IA (circularidade); falta voz do pesquisador em 1a pessoa |
| **Handoffs (7)** | Continuidade entre sessoes de trabalho | Registro contemporaneo de decisoes e estado (OE1, OE4) | Foco em "o que foi feito", pouco "por que" e "o que significa" |
| **Relato de orquestracao** | Tutorial para orquestracao de agentes | Dado unico sobre 213 lancamentos de agentes (OE4) | Baseado em um unico transcript; sem triangulacao |
| **Cronologia dos repos** | Referencia para entender relacoes entre artefatos | Narrativa historico-continuativa da pesquisa (validacao Heikkinen) | Falta distanciamento critico; muito descritivo |

---

## 3. Mapeamento: OEs x Evidencias Existentes x Lacunas

| OE | Evidencias que JA existem | O que FALTA para sustentar na tese |
|----|--------------------------|-----------------------------------|
| **OE1** (Framework PA para IA) | ia-collab-os v1.0; 4 diarios PA; protocolo de registro; mapeamento ciclos-evidencias | Metricas operacionais para os 5 principios; validacao externa; dialogo com literatura de ADR (Sein et al.) |
| **OE2** (Fundamentacao IT) | Revisao incipiente no projeto v2.0; secao 4.1 do projeto | Revisao sistematica (15-20 refs); fichar Girardot, Bertacchini, Masselot; adaptar ao Brasil |
| **OE3** (Transformacoes gestao) | 9 volumes produzidos; fichas V2; 139 municipios analisados | Nenhum ator territorial usou os cadernos; nenhuma observacao de transformacao; entrevistas pendentes |
| **OE4** (Padroes H-IA) | Split strategy documentada; padroes de orquestracao; relato de 213 agentes | Framework teorico nao sistematizado; sem dialogo com Dellermann, Jarrahi, Seeber; sem tipologia formal |
| **OE5** (Etica/governanca) | Reflexoes nos diarios sobre vieses, completude, validacao | Nenhuma audiencia publica realizada; nenhuma entrevista; nenhum grupo focal; CEP pendente |
| **OE6** (Escalabilidade) | Arquitetura modular do sistema; ia-collab-os como framework transferivel | Sem teste em outro contexto; sem analise de barreiras; sem entrevistas com gestores de outros estados |

---

## 4. Artefatos Academicos Faltantes (priorizados por dependencia)

### Prioridade 1: Pre-requisitos (Fev-Jun 2026)
| # | Artefato | OE | Depende de | Responsavel |
|---|---------|-----|-----------|-------------|
| A1 | Metricas operacionais para ia-collab-os | OE1 | Etapa 4 do Plano | Pesquisador + IA |
| A2 | Revisao sistematica de IT (15-20 refs) | OE2 | Nenhum | Pesquisador |
| A3 | Submissao ao CEP | OE3-OE6 | Nenhum | Pesquisador |
| A4 | Artigo 1: ia-collab-os (ADR) | OE1 | A1 | Pesquisador |

### Prioridade 2: Coleta de dados (Jul-Dez 2026)
| # | Artefato | OE | Depende de | Responsavel |
|---|---------|-----|-----------|-------------|
| B1 | Validacao territorial (3 municipios) | OE3 | A3 (CEP) | Pesquisador (campo) |
| B2 | Audiencia(s) publica(s) CDR | OE5 | Proposta formal | Pesquisador + equipe senador |
| B3 | 15+ entrevistas transcritas | OE3-OE6 | A3 (CEP), B1, B2 | Pesquisador |
| B4 | Upload dados para Camada 1 | OE3 | Nenhum | Pesquisador + IA |

### Prioridade 3: Analise e escrita (2027-2028)
| # | Artefato | OE | Depende de | Responsavel |
|---|---------|-----|-----------|-------------|
| C1 | Framework teorico H-IA para gestao publica | OE4 | A2, B3 | Pesquisador |
| C2 | Analise transversal dos 5 ciclos PA | OE1 | Todos os anteriores | Pesquisador |
| C3 | Capitulos 2-7 da tese | Todos | C1, C2 | Pesquisador |
| C4 | Artigos 2-3 | OE2-OE4 | C1, C2 | Pesquisador |

---

## 5. Regra de Ouro para Proximas Sessoes

### Proporcao 70/30
> Cada sessao de producao de artefatos deve ser acompanhada de registro reflexivo.
> **70% producao** (artefatos, codigo, documentos) + **30% reflexao/documentacao** (diario, observacoes, padroes)

### Dupla leitura obrigatoria
> Antes de iniciar a producao de qualquer novo artefato, responder:
> 1. **Que valor pratico este artefato tem?** (para quem, para que)
> 2. **Que valor academico este artefato tem?** (para qual OE, qual PS)
> 3. **Que dados de pesquisa posso coletar DURANTE a producao?** (padroes, decisoes, metricas)

### Teste do "e so isso?"
> Apos produzir um artefato pratico, perguntar: "Se eu so tivesse este artefato, seria suficiente para sustentar o OE correspondente na tese?"
> Se a resposta for NAO, identificar o que falta e planejar coleta.

---

## 6. Diagrama: Tensao Produto-Tese

```
PRODUTO PRATICO                          DADO DE PESQUISA
(valor para o senador/equipe)            (valor para a tese)

  Cadernos Tocantins  ←——→  Evidencia de capacidade IT-IA (OE3)
                             MAS: sem uso real, sem feedback

  ia-collab-os        ←——→  Framework metodologico (OE1, OE4)
                             MAS: sem metricas, sem validacao

  tocantins-integrado ←——→  Sistema demonstravel (OE3, OE6)
                             MAS: incompleto, sem usuarios

  Audiencias CDR      ←——→  Dados qualitativos (OE5)
                             MAS: nao realizadas ainda

       O PRODUTO NAO SUBSTITUI A PESQUISA.
       A PESQUISA NAO INVALIDA O PRODUTO.
       AMBOS SE COMPLEMENTAM QUANDO PLANEJADOS EM CONJUNTO.
```

---

**Versao:** 1.0
**Data:** 12 de Fevereiro de 2026
**Proxima revisao:** Apos inicio da coleta de dados no Ciclo 4
