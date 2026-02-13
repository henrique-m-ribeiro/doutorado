# CLAUDE.md — Repositorio Doutorado

## Sobre este Repositorio

Repositorio central academico do doutorado em Ciencia Politica de Henrique Marques Ribeiro.
Orientador: Professor Fernando Filgueiras.
Tema: Inteligencia Territorial e IA na Gestao Publica.

## Sessao Ativa

**Ciclo PA:** Ciclo 3.5 — Reflexao e Organizacao Metodologica
**Questao de pesquisa:** PS1 (Como a PA viabiliza o desenvolvimento de sistemas de IT-IA?)
**Hipotese em teste:** A organizacao metodologica retroativa fortalece a base de evidencias da pesquisa
**Objetivo especifico:** OE1 (Adaptar e aplicar framework de pesquisa-acao)

## Estrutura do Repositorio

```
doutorado/
├── 01-disciplinas/          # Disciplinas cursadas (2025-1, 2025-2, 2026-1)
├── 02-pesquisa-acao/        # Nucleo da pesquisa
│   ├── 00-projeto/          # Projeto v2.1, objetivos, MATRIZ-PRODUTO-TESE
│   ├── 01-ciclos/           # Planos ciclos PA, mapeamento, protocolo
│   ├── 01-fundamentacao/    # Fichamentos e revisao teorica (em construcao)
│   ├── 02-metodologia/      # Documentacao metodologica
│   ├── 03-dados/            # Diarios PA, handoffs, ADRs, governanca, relatorios
│   ├── 04-repositorios/     # Analise transversal dos 5 repositorios
│   ├── 05-analise/          # Analise por ciclo (em construcao)
│   ├── 06-escrita/          # Capitulos da tese (em construcao)
│   └── 07-publicacoes/      # Artigos e conferencias (em construcao)
├── 03-referencias/          # Bibliografia central
├── 04-qualificacao/         # Exame de qualificacao (planejado Ago 2027)
├── 05-defesa/               # Defesa final (planejado Ago 2028)
└── 99-admin/                # Documentacao administrativa
```

## Instrucoes para Agentes IA

### Obrigatorio em TODA sessao:
1. **Declarar ciclo PA e questao de pesquisa** antes de iniciar trabalho substantivo
2. **Registrar decisoes explicitas** com alternativas consideradas e justificativa
3. **Produzir diario de PA ao final** usando template em `02-pesquisa-acao/03-dados/diarios-sessoes/TEMPLATE-DIARIO.md`
4. **Manter proporcao 70/30** producao/reflexao
5. **Consultar checklist pre-sessao** em `02-pesquisa-acao/01-ciclos/PROTOCOLO-REGISTRO-SESSAO.md`

### Antes de produzir novo artefato:
1. Consultar a **Matriz Produto-Tese** em `02-pesquisa-acao/00-projeto/MATRIZ-PRODUTO-TESE.md`
2. Verificar qual OE e PS o artefato endereca
3. Identificar que dados de pesquisa podem ser coletados durante a producao

### Documentos de referencia:

**Projeto e governanca:**
- Projeto de doutorado (v2.1): `02-pesquisa-acao/00-projeto/projeto-doutorado-v2.0.md`
- Objetivos e questoes (PS1-PS5, OE1-OE5): `02-pesquisa-acao/00-projeto/objetivos-questoes.md`
- Matriz produto-tese: `02-pesquisa-acao/00-projeto/MATRIZ-PRODUTO-TESE.md`

**Ciclos de pesquisa-acao:**
- Mapeamento ciclos-evidencias: `02-pesquisa-acao/01-ciclos/MAPEAMENTO-CICLOS-EVIDENCIAS.md`
- Protocolo de registro de sessao: `02-pesquisa-acao/01-ciclos/PROTOCOLO-REGISTRO-SESSAO.md`
- Ciclo 4 (planejado): `02-pesquisa-acao/01-ciclos/CICLO-04-PLANO.md`
- Ciclo 5 (planejado): `02-pesquisa-acao/01-ciclos/CICLO-05-PLANO.md`

**Dados e registros:**
- Template de diario PA: `02-pesquisa-acao/03-dados/diarios-sessoes/TEMPLATE-DIARIO.md`
- ADRs (001-005): `02-pesquisa-acao/03-dados/adrs/`
- Governanca Tocantins (METHODOLOGY, ROLES, Piloto Palmas): `02-pesquisa-acao/03-dados/governanca-tocantins/`
- Relatorio de revisao de decisoes: `02-pesquisa-acao/03-dados/relatorios-orquestracao/RELATORIO-REVISAO-DECISOES-PLANEJAMENTO.md`
- Instrucao sessao Etapa 4: `02-pesquisa-acao/03-dados/handoffs/INSTRUCAO-SESSAO-ETAPA4-IA-COLLAB-OS.md`

**Repositorios e analise transversal:**
- Analise transversal dos repositorios: `02-pesquisa-acao/04-repositorios/ANALISE-TRANSVERSAL-REPOSITORIOS.md`
- Cronologia dos repositorios: `02-pesquisa-acao/04-repositorios/cronologia-real-repositorios.md`

### Repositorios relacionados:

| Repositorio | Ciclo PA | Status | Descricao |
|------------|----------|--------|-----------|
| **caderno-tocantins-2026** | Ciclo 3 | Ativo | 9 volumes, 139 municipios, 213 agentes |
| **ia-collab-os** | Ciclos 2-3 | Ativo | Framework metodologico H-IA (CEO/CTO/DEV) |
| **tocantins-integrado** | Ciclo 2 | Pausado | Sistema tecnico; Camada 1: 90%, 5 ADRs |
| **framework-v6-mvp** | Ciclo 1 | Historico | Framework monolitico; 183 commits, 21 diarios |

## Plano de Fortalecimento Metodologico

Status das 6 etapas (atualizado 2026-02-13):

| Etapa | Status |
|-------|--------|
| 1. Centralizacao documental | ✅ Concluida |
| 2. Formalizacao ciclos PA | ✅ Concluida |
| 3. Vozes territoriais | ⏳ Requer trabalho de campo do pesquisador |
| 4. Fortalecimento IA-Collab-OS | 📋 Sessao planejada (ver `02-pesquisa-acao/03-dados/handoffs/INSTRUCAO-SESSAO-ETAPA4-IA-COLLAB-OS.md`) |
| 5. Tensao produto-tese | ✅ Concluida (matriz criada) |
| 6. Retomada de producao | ✅ CLAUDE.md e checklist criados |

## Convencoes

- Nomes de arquivo: snake_case ou UPPER-KEBAB-CASE para documentos importantes
- Diarios: `YYYY-MM-DD-sessao-NNN.md`
- Idioma: Portugues (sem acentos em nomes de arquivo; acentos permitidos em conteudo)
- Commits: mensagens descritivas em portugues
