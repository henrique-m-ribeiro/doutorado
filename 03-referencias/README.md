# 03 - Referências

Biblioteca central de referências acadêmicas do doutorado, organizada por área temática.

---

## 📚 Sistema de Organização

### Estrutura de Pastas

```
03-referencias/
├── README.md (este arquivo)
├── bibliografia.bib (arquivo BibTeX central)
├── artigos/
│   ├── gestao-publica/
│   ├── ia-governanca/
│   └── pesquisa-acao/
├── livros/
└── relatorios-tecnicos/
```

### Convenções de Nomenclatura

**Artigos:**
```
autor-ano-primeiras-palavras-titulo.pdf

Exemplos:
heikkinen-2007-action-research-narrative.pdf
baskerville-1996-duality-information-systems.pdf
herr-anderson-2015-action-research-dissertation.pdf
```

**Livros:**
```
autor-ano-titulo-completo.pdf

Exemplos:
tripp-2005-pesquisa-acao-revisao.pdf
greenwood-levin-2007-introduction-action-research.pdf
```

**Capítulos de Livro:**
```
autor-ano-titulo-capitulo-in-livro.pdf

Exemplos:
checkland-2000-soft-systems-methodology-in-information-systems.pdf
```

---

## 🎯 Áreas Temáticas

### 1. Pesquisa-Ação

**Foco:** Fundamentação metodológica da tese

**Subtemas:**
- Pesquisa-ação clássica (Lewin, Carr & Kemmis)
- Pesquisa-ação em Sistemas de Informação
- Critérios de qualidade e validação
- Pesquisa-ação participativa
- Action Design Research

**Autores-chave:**
- Heikkinen, Huttunen & Syrjälä (2007) - Validação
- Baskerville (1996, 1999) - SI e pesquisa-ação
- Herr & Anderson (2015) - Teses em pesquisa-ação
- Tripp (2005) - Revisão conceitual
- Sein et al. (2011) - Action Design Research
- Greenwood & Levin (2007) - Introdução geral

**Artigos essenciais:**
- [ ] Heikkinen et al. (2007) - Action research as narrative
- [ ] Baskerville (1996) - Duality in information systems action research
- [ ] Herr & Anderson (2015) - The action research dissertation (livro)
- [ ] Tripp (2005) - Pesquisa-ação: uma introdução metodológica
- [ ] Sein et al. (2011) - Action Design Research

### 2. IA em Governança

**Foco:** Aplicação de IA no setor público

**Subtemas:**
- Governança algorítmica
- IA para políticas públicas
- Transformação digital do Estado
- E-government e smart cities
- Ética da IA no setor público

**Autores-chave:**
- [Adicionar conforme leituras]

**Artigos essenciais:**
- [ ] [Adicionar referências específicas]

### 3. Colaboração Humano-IA

**Foco:** Padrões de interação e colaboração

**Subtemas:**
- Human-AI interaction (HAI)
- Explainable AI (XAI)
- Confiança em sistemas de IA
- Competências para trabalhar com IA
- Design de sistemas colaborativos

**Autores-chave:**
- [Adicionar conforme leituras]

**Artigos essenciais:**
- [ ] [Adicionar referências específicas]

### 4. Gestão Pública

**Foco:** Contexto de aplicação da pesquisa

**Subtemas:**
- Políticas públicas baseadas em evidências
- Gestão territorial
- Federalismo brasileiro
- Capacidades estatais
- Inovação no setor público

**Autores-chave:**
- [Adicionar conforme leituras]

**Artigos essenciais:**
- [ ] [Adicionar referências específicas]

---

## 📥 Workflow de Adição de Referências

### Passo 1: Obtenção do Material

**Fontes Principais:**
- Portal de Periódicos CAPES
- Google Scholar
- Scielo
- ResearchGate
- Bibliotecas universitárias

**Critérios de Seleção:**
- Relevância para perguntas de pesquisa
- Qualidade (periódico, citações, autoria)
- Atualidade (preferencialmente últimos 10 anos, salvo clássicos)
- Acessibilidade (prefere acesso aberto)

### Passo 2: Nomenclatura do Arquivo

Renomear seguindo convenção:
```
autor-ano-palavras-chave.pdf
```

### Passo 3: Organização em Pasta

Colocar na pasta temática apropriada:
- `artigos/pesquisa-acao/`
- `artigos/ia-governanca/`
- `artigos/gestao-publica/`
- `livros/`
- `relatorios-tecnicos/`

### Passo 4: Registro no BibTeX

Adicionar entrada no arquivo `bibliografia.bib`:

```bibtex
@article{heikkinen2007action,
  title={Action research as narrative: five principles for validation},
  author={Heikkinen, Hannu LT and Huttunen, Rauno and Syrj{\"a}l{\"a}, Leena},
  journal={Educational Action Research},
  volume={15},
  number={1},
  pages={5--19},
  year={2007},
  publisher={Taylor \& Francis},
  keywords={pesquisa-acao, validacao, narrativa},
  file={artigos/pesquisa-acao/heikkinen-2007-action-research-narrative.pdf}
}
```

### Passo 5: Fichamento

Criar fichamento usando template:
```
01-disciplinas/templates/fichamento-template.md
```

Salvar fichamento em:
```
01-disciplinas/[disciplina-atual]/notas/fichamento-autor-ano.md
```

OU, se leitura independente:
```
02-pesquisa-acao/01-fundamentacao/fichamentos/autor-ano.md
```

### Passo 6: Integração com Outras Pastas

**Se a referência é usada em trabalho de disciplina:**
- Copiar/linkar PDF em `01-disciplinas/[disciplina]/referencias/`
- Mencionar no README da disciplina

**Se a referência fundamenta um capítulo específico:**
- Adicionar nota em `02-pesquisa-acao/06-escrita/capitulos/[capitulo]/referencias-chave.md`

---

## 🔍 Ferramentas Recomendadas

### Gerenciadores de Referências

**Zotero (Recomendado)**
- Gratuito e código aberto
- Integração com navegador para captura rápida
- Gera BibTeX automaticamente
- Sincronização em nuvem
- Plugins para Word e LibreOffice

**Mendeley**
- Gratuito
- Interface amigável
- Leitor de PDF integrado
- Rede social acadêmica

**JabRef**
- Gratuito e código aberto
- Editor nativo de BibTeX
- Integração com LaTeX

### Busca e Descoberta

**Google Scholar**
- Busca ampla
- Alertas de citação
- "Cited by" para encontrar trabalhos relacionados

**Connected Papers**
- Visualização de redes de citação
- Descoberta de literatura relacionada

**Semantic Scholar**
- Busca semântica
- Recomendações personalizadas

### Organização

**Obsidian / Notion**
- Para zettelkasten de fichamentos
- Links entre conceitos
- Visualização de conhecimento

---

## 📊 Estatísticas da Biblioteca

### Referências por Área (Atualizar regularmente)

| Área Temática | Artigos | Livros | Relatórios | Total |
|---------------|---------|--------|------------|-------|
| Pesquisa-ação | [X] | [Y] | [Z] | [Total] |
| IA em Governança | [X] | [Y] | [Z] | [Total] |
| Colaboração Humano-IA | [X] | [Y] | [Z] | [Total] |
| Gestão Pública | [X] | [Y] | [Z] | [Total] |
| **TOTAL** | **[X]** | **[Y]** | **[Z]** | **[Total]** |

### Referências por Ano

| Período | Quantidade | % do Total |
|---------|------------|------------|
| 2020-2025 | [X] | [%] |
| 2015-2019 | [X] | [%] |
| 2010-2014 | [X] | [%] |
| 2000-2009 | [X] | [%] |
| < 2000 (clássicos) | [X] | [%] |

### Status de Leitura

| Status | Quantidade | % do Total |
|--------|------------|------------|
| ✅ Lido e fichado | [X] | [%] |
| 📖 Em leitura | [X] | [%] |
| 📋 Fichamento pendente | [X] | [%] |
| 🔖 Na fila de leitura | [X] | [%] |
| ❓ Avaliar relevância | [X] | [%] |

---

## 🎯 Estratégia de Leitura

### Priorização

**Alta Prioridade (Ler primeiro):**
1. Referências metodológicas (pesquisa-ação)
2. Autores mais citados na área
3. Publicações recentes em periódicos top
4. Referências indicadas pelo orientador

**Média Prioridade:**
1. Revisões de literatura e meta-análises
2. Estudos de caso similares
3. Fundamentos teóricos complementares

**Baixa Prioridade:**
1. Literatura tangencial
2. Contextualizações gerais
3. Leituras exploratórias

### Cronograma de Leitura

**Fase de Fundamentação (2025.1 - 2025.2):**
- Meta: 50-60 referências lidas e fichadas
- Foco: Pesquisa-ação, IA em governança, colaboração humano-IA
- Ritmo: 2-3 artigos/semana + 1 livro/mês

**Fase de Execução (2026.1 - 2027.1):**
- Meta: 20-30 referências adicionais conforme necessidades
- Foco: Metodologia específica, casos similares
- Ritmo: 1 artigo/semana

**Fase de Escrita (2027.1 - 2028.1):**
- Meta: Leituras complementares conforme lacunas identificadas
- Foco: Complementação de argumentação
- Ritmo: Conforme demanda

---

## 🔗 Integração com Outras Pastas

### Com Disciplinas (`01-disciplinas/`)

**Disciplinas alimentam biblioteca:**
- Textos obrigatórios de disciplinas → `03-referencias/`
- Fichamentos de disciplina → Registro em `bibliografia.bib`

**Biblioteca alimenta disciplinas:**
- Referências da biblioteca → Trabalhos de disciplina
- Fichamentos podem ser reutilizados

### Com Fundamentação Teórica (`02-pesquisa-acao/01-fundamentacao/`)

**Referências estruturam fundamentação:**
- Cada subpasta tem fichamentos de referências-chave
- `bibliografia.bib` é fonte para citações na escrita

**Estrutura:**
```
01-fundamentacao/
├── pesquisa-acao/
│   ├── heikkinen-2007.md (fichamento)
│   ├── baskerville-1996.md
│   └── sintese-literatura.md
├── ia-governanca/
│   └── [fichamentos específicos]
└── colaboracao-humano-ia/
    └── [fichamentos específicos]
```

### Com Escrita (`02-pesquisa-acao/06-escrita/`)

**Durante a escrita:**
- Consultar `bibliografia.bib` para citações
- Verificar fichamentos para encontrar citações específicas
- Adicionar novas referências conforme necessário

---

## ✅ Checklist de Gestão da Biblioteca

### Semanal

- [ ] Adicionar novas referências encontradas
- [ ] Fichar ao menos 2 artigos
- [ ] Atualizar `bibliografia.bib`
- [ ] Organizar PDFs nas pastas corretas

### Mensal

- [ ] Revisar estatísticas da biblioteca
- [ ] Identificar lacunas temáticas
- [ ] Buscar novas referências em áreas deficitárias
- [ ] Fazer backup da pasta de referências
- [ ] Revisar fichamentos antigos e adicionar conexões

### Semestral

- [ ] Auditoria completa de referências
- [ ] Eliminar duplicatas
- [ ] Verificar links quebrados
- [ ] Atualizar buscas por trabalhos mais recentes
- [ ] Revisar estratégia de leitura

---

## 📖 Referências sobre Gestão de Referências

**Como fazer fichamentos:**
- SEVERINO, A. J. Metodologia do trabalho científico. São Paulo: Cortez, 2007.

**Como organizar bibliografia:**
- ECO, U. Como se faz uma tese. São Paulo: Perspectiva, 2007.

**Ferramentas digitais:**
- Documentação do Zotero: https://www.zotero.org/support/
- Guia BibTeX: https://www.bibtex.org/

---

## 🎯 Metas de Referências por Fase

### Qualificação

**Meta:** 60-80 referências sólidas
- Pesquisa-ação: 15-20 refs
- IA em governança: 15-20 refs
- Colaboração humano-IA: 15-20 refs
- Gestão pública: 10-15 refs
- Metodologia complementar: 5-10 refs

### Defesa Final

**Meta:** 100-120 referências
- Acrescentar: Literatura recente, casos comparativos, debates emergentes

---

## 💡 Dicas de Produtividade

1. **Leia com propósito:** Sempre pergunte "Como isso contribui para minha tese?"
2. **Fiche imediatamente:** Não acumule leituras sem fichamento
3. **Conecte conceitos:** Use fichamentos para identificar diálogos entre autores
4. **Organize fisicamente:** PDFs bem nomeados economizam tempo depois
5. **Backup religioso:** Bibliografia é ativo crítico do doutorado
6. **Compartilhe:** Discuta leituras com colegas e orientador
7. **Revise periodicamente:** Fichamentos antigos ganham novo sentido com o tempo

---

**Responsável:** Henrique M. Ribeiro
**Última auditoria:** 2026-01-31
**Próxima revisão:** [Data da próxima revisão semestral]
