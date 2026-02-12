# HANDOFF - Sessão 27 de Janeiro 2026
## Projeto Caderno Tocantins 2026 - Planejamento da Refatoração V02

**Data da Sessão:** 27 de janeiro de 2026
**Duração:** ~2 horas (sessão de planejamento)
**Agente IA:** Claude (Sonnet 4.5)
**Branch:** `documentacao-plano-refatoracao-v02`
**Status:** Planejamento completo - Pronto para implementação

---

## 📋 CONTEXTO DA SESSÃO

Esta sessão focou exclusivamente no **planejamento detalhado da Refatoração V02**, identificando problemas estruturais da implementação anterior e propondo correções fundamentadas, além de integrar uma nova e rica fonte de dados.

### Problema Identificado

Durante a sessão anterior (23/01/2026), decisões de design foram tomadas automaticamente durante a execução sem aprovação prévia:
1. Remoção da coluna `territorio_tipo`
2. Remoção de sufixos `_ano_ref` de todos os indicadores
3. Mistura de linhas consolidadas com municípios
4. Uso exclusivo da classificação IBGE antiga (1989-2017)

### Nova Oportunidade Descoberta

O usuário identificou os **Perfis Socioeconômicos Municipais da SEPLAN-TO** (8ª edição, Dezembro 2024):
- 139 PDFs oficiais (um por município)
- ~40 MB cada, 10 capítulos estruturados
- Cobertura de ~85-95% dos indicadores necessários
- Dados oficiais e atualizados

---

## ✅ ENTREGAS DESTA SESSÃO

### 1. Plano Completo de Refatoração V02

**Documento:** `/docs/PLANO_REFATORACAO_V02_2026-01-27.md`

**Conteúdo:**
- 📋 Resumo executivo
- 🔍 Análise de problemas identificados
- 🎯 Estrutura alvo das planilhas (revisada)
- 📊 Estratégia de extração de PDFs SEPLAN-TO
- 🗂️ 7 fases de implementação detalhadas
- 📅 4 sprints de trabalho em paralelo
- ✅ Critérios de sucesso e validação
- ⚠️ Riscos e mitigações
- 📝 17 scripts Python planejados

**Estimativa:** 41-61 horas = 7-10 dias úteis (com 6h/dia)

### 2. Validação de Viabilidade

**Estrutura dos PDFs SEPLAN-TO confirmada:**
- ✅ 10 capítulos organizados
- ✅ Indicadores: Demografia, Economia, Educação, Saúde, Saneamento, Agropecuária
- ✅ Dados padronizados para todos os 139 municípios
- ✅ Compatibilidade: ~85-95% com estrutura planejada

**Acesso aos recursos:**
- ✅ Google Drive compartilhado com 139 PDFs
- ✅ Classificações regionais SEPLAN 2024 mapeadas
- ✅ Estratégia de trabalho em paralelo aprovada

### 3. Decisões Técnicas Aprovadas

**Correções de design:**
1. ✅ Restaurar coluna `territorio_tipo` (sempre "Município")
2. ✅ Restaurar sufixos `_ano_ref` para análise temporal
3. ✅ Criar 6 planilhas de consolidação separadas
4. ✅ Adicionar 11 colunas de classificação regional

**Nova estratégia:**
1. ✅ Extração automatizada de 139 PDFs (vs APIs manuais)
2. ✅ Geração automática da Parte III (139 fichas)
3. ✅ Revisão das Partes I e II integrada
4. ✅ Trabalho em paralelo em 4 sprints

### 4. Mapeamento de Recursos

**8 Regiões de Planejamento SEPLAN-TO 2024** (Portaria nº 91 - 22/10/2024):
1. Bico do Papagaio (25), Norte (15), Meio Norte (25)
2. Vale do Araguaia (15), Central (14), Jalapão (9)
3. Sul (17), Sudeste (19)

**3 Macrorregiões:**
- Norte: 65 municípios
- Central: 38 municípios
- Sul: 36 municípios

**Fonte:** https://www.to.gov.br/seplan/noticias/regioes-de-planejamento-sao-definidas-e-passam-a-ser-instrumento-das-acoes-de-governo/

### 5. Documentação Atualizada

**Arquivos modificados:**
- ✅ `/README.md` - Seção completa sobre Refatoração V02
- ✅ `/CHANGELOG.md` - Entrada detalhada v1.2.0-dev
- ✅ `/docs/PLANO_REFATORACAO_V02_2026-01-27.md` - Plano completo

**Branch criada:** `documentacao-plano-refatoracao-v02`

---

## 📊 ESTRUTURA ALVO DA REFATORAÇÃO V02

### Planilha Principal

**BASE_DADOS_TOCANTINS_V02.csv**
- 139 municípios (sem linhas consolidadas)
- ~65 colunas (vs 37 atuais)
- 11 colunas de classificação territorial:
  1. territorio_nome
  2. territorio_cod_ibge
  3. territorio_uf
  4. territorio_tipo (RESTAURADO)
  5. territorio_mesorregiao_ibge_1989
  6. territorio_microrregiao_ibge_1989
  7. territorio_regiao_intermediaria_ibge_2017 (NOVO)
  8. territorio_regiao_imediata_ibge_2017 (NOVO)
  9. territorio_regiao_planejamento_seplan_2024 (NOVO)
  10. territorio_macrorregiao_seplan_2024 (NOVO)
  11. territorio_observacoes (NOVO)

### Planilhas de Consolidação (6 arquivos)

1. **BASE_CONSOLIDACOES_MICRORREGIOES_IBGE_1989.csv** - 8 linhas
2. **BASE_CONSOLIDACOES_MESORREGIOES_IBGE_1989.csv** - 2 linhas
3. **BASE_CONSOLIDACOES_REGIOES_PLANEJAMENTO_SEPLAN_2024.csv** - 8 linhas
4. **BASE_CONSOLIDACOES_MACRORREGIOES_SEPLAN_2024.csv** - 3 linhas
5. **BASE_CONSOLIDACAO_ESTADUAL.csv** - 1 linha

**Benefícios:**
- ✅ Planilha principal limpa (apenas municípios)
- ✅ Flexibilidade para análises por diferentes classificações
- ✅ Facilita comparações entre classificações
- ✅ Atualizações independentes

### Metadados Expandidos

**METADADOS_BASE_DADOS_TOCANTINS_V02.csv**
- ~65-70 variáveis × 14 campos
- Colunas `_ano_ref` documentadas
- Fontes SEPLAN-TO adicionadas
- Métodos de agregação especificados

---

## 🗂️ FASES DE IMPLEMENTAÇÃO

### Fase 0: Preparação (30 min - 1h)
- Criar branch `refatoracao-planilhas-v02-revisada`
- Configurar estrutura de diretórios
- Download dos 139 PDFs do Google Drive
- Baixar PDF de Regiões de Planejamento 2024

### Fase 1: Análise de Viabilidade dos PDFs (2-3h)
- Baixar 3-5 PDFs de amostra
- Análise exploratória manual da estrutura
- Criar documento de mapeamento indicadores
- Mapear municípios para Regiões SEPLAN 2024
- Validar viabilidade da extração automatizada

### Fase 2: Refatoração da Estrutura (4-6h)
**Trabalho em paralelo:**
- Thread A: Nova especificação das planilhas
- Thread B: Mapear classificações IBGE 2017
- Thread C: Migrar dados V01 → V02

### Fase 3: Infraestrutura de Extração (10-15h)
- Script de download em lote (2h)
- Script de extração de tabelas (6-8h)
- Script de consolidação (2-3h)
- Testes e validação (2h)

### Fase 4: Execução da Extração (4-6h)
- Download/importação dos 139 PDFs
- Extração em lote com barra de progresso
- Revisão de erros e exceções
- Consolidação de todos os dados
- Validação de cobertura (meta: 85%+)

### Fase 5: Criação de Fichas Municipais (10-15h)
- Template de ficha municipal
- Script de geração automática
- Lote 1 (10 municípios prioritários)
- Lote 2 (30 municípios médios)
- Lote 3 (99 municípios pequenos)

### Fase 6: Revisão das Partes I e II (8-12h)
- Atualizar consolidado estadual (Parte I)
- Revisar 8 fichas regionais (Parte II)
- Recalcular médias e totais
- Atualizar análises SWOT

### Fase 7: Documentação e Encerramento (3-4h)
- Atualizar CHANGELOG.md
- Criar relatório de refatoração
- Atualizar README.md
- Lições aprendidas
- Commit e Push
- Criar Pull Request

---

## 📝 SCRIPTS PYTHON PLANEJADOS (17)

### Infraestrutura de Dados
1. `migrar_v01_para_v02.py` - Migração de dados existentes
2. `mapear_regioes_planejamento.py` - Mapeamento classificações regionais
3. `calcular_consolidacoes.py` - Gerar 6 planilhas de consolidação

### Extração de PDFs
4. `download_perfis_seplan_to.py` - Download/importação de PDFs
5. `extrair_tabelas_perfis_seplan.py` - Extração automatizada
6. `consolidar_extraidos_perfis.py` - Consolidação e validação

### Geração de Conteúdo
7. `gerar_fichas_municipais.py` - Geração automática Parte III

### Validação
8. `validar_dados.py` - Validações de integridade
9. `comparar_versoes.py` - Relatório V01 vs V02

### Utilitários
10-17. Scripts auxiliares conforme necessidade

---

## 🎯 CRITÉRIOS DE SUCESSO

### Refatoração de Estrutura
- ✅ BASE_DADOS_TOCANTINS_V02.csv: 139 × ~65 colunas
- ✅ Todas as colunas `_ano_ref` restauradas
- ✅ 11 colunas de classificação regional preenchidas
- ✅ 6 planilhas de consolidação criadas
- ✅ Metadados expandidos completos

### Extração de PDFs
- ✅ 139 PDFs processados com sucesso
- ✅ Taxa de extração ≥85%
- ✅ Menos de 10% de erros manuais
- ✅ Validações de integridade aprovadas

### Parte III
- ✅ Template de ficha municipal criado
- ✅ Lote 1 (10 municípios) gerado
- ✅ Script funcional para os demais 129

### Revisão Partes I e II
- ✅ Parte I atualizada com dados consolidados
- ✅ 8 fichas regionais revisadas
- ✅ Análises SWOT atualizadas se necessário

### Validações End-to-End
1. Todos os 139 municípios têm códigos IBGE válidos
2. Soma de municípios por região = 139 (sem duplicações)
3. Totais estaduais = soma de municípios (agregáveis)
4. PIB per capita = PIB total / População (margem <1%)
5. Todas as colunas documentadas nos metadados

---

## ⚠️ RISCOS IDENTIFICADOS E MITIGAÇÕES

### Risco 1: PDFs não contêm dados suficientes
**Probabilidade:** Baixa (estrutura validada via SEPLAN-TO)
**Impacto:** Alto
**Mitigação:** Fase 1 valida viabilidade ANTES de desenvolver scripts

### Risco 2: Estrutura heterogênea dos PDFs
**Probabilidade:** Média
**Impacto:** Alto
**Mitigação:**
- Script robusto com múltiplos padrões de parse
- Fallback para extração manual
- Relatório detalhado de erros

### Risco 3: Qualidade dos PDFs (OCR necessário)
**Probabilidade:** Baixa
**Impacto:** Médio
**Mitigação:** Testar OCR com pytesseract se necessário

### Risco 4: Tempo de processamento muito longo
**Probabilidade:** Média
**Impacto:** Baixo
**Mitigação:**
- Processamento paralelo (multiprocessing)
- Cache de resultados intermediários
- Processamento incremental

---

## 📅 ESTRATÉGIA DE TRABALHO EM PARALELO

### Sprint 1 (Dias 1-2)
- Refatoração de estrutura de planilhas
- Download e análise dos PDFs
- Mapeamento de classificações regionais

### Sprint 2 (Dias 3-5)
- Desenvolvimento de scripts de extração
- Migração de dados V01 → V02
- Início da extração em lote

### Sprint 3 (Dias 6-8)
- Conclusão da extração
- Geração de fichas municipais (Lote 1)
- Revisão de Partes I e II

### Sprint 4 (Dias 9-10)
- Validação e consolidações
- Documentação
- Preparação de Pull Request

---

## 📊 MÉTRICAS DE PROGRESSO

### Cobertura de Dados

| Status | V01 (Atual) | V02 (Meta) | Diferença |
|--------|-------------|------------|-----------|
| **Média Geral** | ~35% | ≥85% | +50% |
| População 2022 | 95.7% | 100% | +4.3% |
| IDEB 2023 | 0% | ≥90% | +90% |
| Saneamento | 0% | ≥85% | +85% |
| Agropecuária | 0% | ≥85% | +85% |

### Entregas

| Componente | V01 | V02 (Meta) |
|------------|-----|------------|
| **Parte I** | ✅ 100% | ✅ 100% (revisada) |
| **Parte II** | ✅ 100% | ✅ 100% (revisada) |
| **Parte III** | ❌ 0% | ✅ 100% |
| **Planilhas** | 1 (37 col) | 7 (~65 col) |
| **Scripts** | 1 | 17 |

---

## 🔗 RECURSOS E FONTES

### PDFs SEPLAN-TO
- **Google Drive:** https://drive.google.com/drive/folders/1BOS0LW8GEiwAPdAA3UlW_m6KpzRaG7-F?usp=sharing
- **Portal SEPLAN:** https://www.to.gov.br/seplan/perfil-socioeconomico-municipal/
- **Edição:** 8ª edição (Dezembro 2024)
- **Quantidade:** 139 PDFs (~40 MB cada)

### Classificações Regionais
- **Regiões de Planejamento 2024:** https://www.to.gov.br/seplan/noticias/regioes-de-planejamento-sao-definidas-e-passam-a-ser-instrumento-das-acoes-de-governo/
- **PDF oficial (>10MB):** https://geoportal.to.gov.br/geonetwork/srv/api/records/f290af9b-d47d-44b7-aa98-506f2d376cbc/attachments/Regioes_Planejamento_2024.pdf
- **Portaria:** nº 91 (22/10/2024)

### APIs e Fontes Complementares
- **IBGE Cidades:** https://cidades.ibge.gov.br/
- **SIDRA:** https://sidra.ibge.gov.br/
- **INEP:** https://www.gov.br/inep/
- **SNIS:** http://www.snis.gov.br/
- **Atlas Brasil:** http://www.atlasbrasil.org.br/

---

## 📂 ARQUIVOS CRÍTICOS

### Criados Nesta Sessão
- `/docs/PLANO_REFATORACAO_V02_2026-01-27.md` - Plano completo
- `/docs/HANDOFF-SESSION-2026-01-27.md` - Este documento

### Modificados Nesta Sessão
- `/README.md` - Seção Refatoração V02 adicionada
- `/CHANGELOG.md` - Versão 1.2.0-dev documentada

### A Criar na Implementação
- `/docs/PLANEJAMENTO_PLANILHAS_V02_REVISADA.md`
- `/docs/MAPEAMENTO_INDICADORES_SEPLAN_TO.md`
- `/docs/MAPEAMENTO_REGIOES_PLANEJAMENTO_2024.md`
- `/dados/finais/BASE_DADOS_TOCANTINS_V02.csv`
- `/dados/finais/METADADOS_BASE_DADOS_TOCANTINS_V02.csv`
- `/dados/finais/consolidacoes/*.csv` (6 arquivos)
- `/scripts/*.py` (17 scripts)
- `/parte-iii-fichas-municipais/municipios/*.md` (139 fichas)

---

## 🎯 PRÓXIMOS PASSOS IMEDIATOS

### Para Iniciar a Implementação

1. **Revisar e aprovar este handoff**
2. **Fazer merge da branch de documentação**
   - Branch atual: `documentacao-plano-refatoracao-v02`
   - Commits: Documentação completa do planejamento V02
3. **Iniciar Fase 0 (Preparação)**
   - Criar branch: `refatoracao-planilhas-v02-revisada`
   - Configurar estrutura de diretórios
   - Download dos 139 PDFs
4. **Iniciar Fase 1 (Análise de Viabilidade)**
   - Baixar 3-5 PDFs de amostra
   - Análise exploratória da estrutura
   - Criar mapeamento de indicadores

### Checklist Pré-Implementação

- [ ] Documentação aprovada e merged
- [ ] PDFs SEPLAN-TO acessíveis
- [ ] Ambiente Python configurado
- [ ] Bibliotecas instaladas (pdfplumber, pandas, openpyxl)
- [ ] Branch de implementação criada
- [ ] Estrutura de diretórios configurada

---

## 💡 LIÇÕES APRENDIDAS

### Desta Sessão

1. **Importância da aprovação prévia de decisões de design**
   - Decisões automáticas podem causar retrabalho
   - Planejar antes de executar é mais eficiente

2. **Valor de fontes oficiais consolidadas**
   - Os PDFs SEPLAN-TO são muito mais ricos que APIs fragmentadas
   - Uma boa fonte pode mudar completamente a estratégia

3. **Benefícios do planejamento meticuloso**
   - 2 horas de planejamento economizam dezenas de horas de retrabalho
   - Validação de viabilidade ANTES de implementar é crucial

4. **Documentação incremental e detalhada**
   - Registrar tudo facilita retomada de contexto
   - Handoffs completos permitem continuidade entre sessões

---

## 🔍 ANÁLISE DA CAUSA RAIZ DAS DIVERGÊNCIAS DA V01

**Objetivo:** Entender *por que* decisões automáticas não aprovadas foram tomadas na sessão anterior (23/01/2026), para evitar repetição em futuras colaborações.

**Contexto:** Durante a implementação anterior, 4 decisões de design foram feitas automaticamente sem aprovação:
1. Remoção da coluna `territorio_tipo`
2. Remoção de sufixos `_ano_ref` de todos os indicadores
3. Inclusão de linhas consolidadas misturadas com municípios
4. Uso exclusivo da classificação IBGE antiga (1989-2017)

### Divergência 1: Remoção de `territorio_tipo`

**Por que aconteceu:**
- A coluna tinha valor fixo "Município" para todas as 139 linhas
- Do ponto de vista de normalização de dados, parecia redundante
- A IA interpretou isso como "dado invariante = pode ser omitido"
- Não havia contexto explícito de que essa coluna seria necessária para futuras expansões

**Consequência:**
- Perda de flexibilidade para adicionar consolidações posteriormente
- Dificuldade para diferenciar municípios de consolidações regionais
- Necessidade de retrabalho para restaurar

**Como evitar no futuro:**
- ✅ **Especificar explicitamente colunas obrigatórias** mesmo que pareçam redundantes
- ✅ **Documentar justificativa para cada coluna no plano** (ex: "territorio_tipo é obrigatório para permitir expansão futura com consolidações")
- ✅ **Solicitar aprovação para remoção de qualquer coluna planejada** independente do motivo técnico

### Divergência 2: Remoção de sufixos `_ano_ref`

**Por que aconteceu:**
- A especificação original mencionava sufixos `_ano_ref` mas não explicava o *porquê*
- Muitos indicadores têm ano fixo (ex: IDHM sempre 2010, Censo sempre 2010/2022)
- A IA interpretou como "se o ano é fixo, o sufixo é redundante"
- Otimização prematura: reduzir colunas para simplificar a planilha

**Consequência:**
- Perda de capacidade de análise temporal
- Impossibilidade de adicionar séries históricas posteriormente
- Dificuldade para rastrear ano de referência de cada dado
- Metadados incompletos (ano de referência disperso)

**Como evitar no futuro:**
- ✅ **Explicar explicitamente a justificativa de cada padrão de nomenclatura**
  - Exemplo: "Sufixos `_ano_ref` são obrigatórios para permitir análise temporal, mesmo que o ano atual seja fixo"
- ✅ **Incluir casos de uso futuros no planejamento**
  - Exemplo: "No futuro, poderemos adicionar dados de 2030, então precisamos do sufixo agora"
- ✅ **Proibir otimizações não solicitadas**
  - Regra: "Não remova colunas para 'simplificar' sem aprovação explícita"

### Divergência 3: Mistura de linhas consolidadas com municípios

**Por que aconteceu:**
- O exemplo inicial do usuário mostrava um formato similar (municípios + totais)
- Planilhas do Excel frequentemente incluem linhas de "Total" ao final
- A IA generalizou esse padrão sem questionar
- Não havia instrução explícita de separar consolidações

**Consequência:**
- Dificuldade para filtrar apenas municípios
- Risco de contar consolidações como municípios em análises
- Confusão na hora de calcular agregações (pode somar o total com os municípios)
- Estrutura de dados não normalizada

**Como evitar no futuro:**
- ✅ **Especificar princípios de design de dados no início**
  - Exemplo: "Princípio 1: Planilha principal contém apenas entidades atômicas (municípios)"
  - Exemplo: "Princípio 2: Consolidações são sempre separadas"
- ✅ **Fornecer exemplos de anti-padrões**
  - Exemplo: "❌ NÃO misture municípios com consolidações na mesma planilha"
- ✅ **Solicitar revisão da estrutura antes da implementação**
  - Perguntar: "Você deseja que eu crie planilhas separadas para consolidações?"

### Divergência 4: Uso exclusivo de classificação IBGE antiga

**Por que aconteceu:**
- A fonte de dados inicial (IBGE) usava a classificação 1989-2017
- Não havia conhecimento imediato da classificação IBGE 2017+ (Regiões Intermediárias/Imediatas)
- Não havia conhecimento das classificações SEPLAN-TO 2024
- A IA usou os dados disponíveis sem buscar classificações alternativas

**Consequência:**
- Planilha ficou presa a classificações descontinuadas
- Incompatibilidade com planejamento governamental atual
- Necessidade de adicionar múltiplas colunas posteriormente

**Como evitar no futuro:**
- ✅ **Incluir pesquisa de fontes alternativas na fase de planejamento**
  - Perguntar: "Existem classificações regionais mais recentes?"
  - Pesquisar: "Divisão regional IBGE 2017", "Regiões de planejamento [estado]"
- ✅ **Especificar requisito de múltiplas classificações se relevante**
  - Exemplo: "Incluir tanto classificações históricas (IBGE 1989) quanto atuais (IBGE 2017, SEPLAN 2024)"
- ✅ **Validar fontes de dados antes da implementação**
  - Perguntar: "Estas são as classificações mais atuais disponíveis?"

### Padrão Geral Identificado: Otimização Prematura

**Problema raiz:**
- A IA priorizou **simplicidade imediata** sobre **flexibilidade futura**
- Decisões de normalização foram tomadas sem considerar requisitos de longo prazo
- Falta de questionamento: "Por que o usuário especificou isso dessa forma?"

**Estratégias de Prevenção:**

1. **Regra de Ouro: Seguir o Plano Literalmente**
   - ✅ Se o plano especifica uma coluna, mantê-la mesmo que pareça redundante
   - ✅ Se o plano especifica um padrão de nomenclatura, seguir exatamente
   - ✅ Questionar antes de simplificar ou otimizar

2. **Checklist de Validação Pré-Implementação**
   - [ ] Todas as colunas do plano original estão presentes?
   - [ ] Todos os padrões de nomenclatura foram seguidos?
   - [ ] A estrutura de arquivos está conforme especificado?
   - [ ] Fiz alguma "melhoria" não solicitada? (Se sim, revisar)

3. **Comunicação Proativa**
   - ✅ Se algo parecer redundante, perguntar antes de remover
   - ✅ Se houver uma "simplificação óbvia", confirmar com o usuário
   - ✅ Apresentar alternativas e deixar o usuário decidir

4. **Documentação de Justificativas**
   - ✅ Cada coluna deve ter justificativa no plano
   - ✅ Cada padrão de nomenclatura deve ter explicação
   - ✅ Princípios de design devem ser explicitados no início

### Ações Corretivas para Esta Refatoração

Para garantir que os mesmos erros não se repitam na V02:

1. ✅ **Plano V02 documenta explicitamente todas as restaurações**
   - Marcações `RESTAURADO` e `NOVO` em cada coluna
   - Justificativas para sufixos `_ano_ref`
   - Especificação clara de 6 planilhas separadas

2. ✅ **Fase 1 expandida (3-5h) para validação de viabilidade**
   - Análise detalhada de 10-15 PDFs (vs 3-5 original)
   - Relatório de variabilidade estrutural
   - Mapeamento completo de indicadores

3. ✅ **Validação de dados em 4 tipos (Fase 3)**
   - Schema, Range, Cross-field, Consistência histórica
   - Critérios de aprovação objetivos
   - Relatórios detalhados de qualidade

4. ✅ **Revisão de checkpoints antes de cada fase crítica**
   - Fase 2: Revisar estrutura de colunas antes de preencher
   - Fase 3: Validar extração antes de processar 139 PDFs
   - Fase 4: Validar dados antes de consolidar

### Lições para Futuras Colaborações IA-Humano

**Para o Humano (Usuário):**
- Especificar explicitamente justificativas de design no plano
- Incluir anti-padrões ("NÃO faça X")
- Revisar estrutura de dados antes da implementação completa
- Usar framework IA-Collab-OS sistematicamente

**Para a IA (Claude):**
- Seguir o plano literalmente, questionar antes de otimizar
- Priorizar flexibilidade futura sobre simplicidade imediata
- Perguntar proativamente sobre decisões de design
- Documentar todas as decisões tomadas durante implementação

**Resultado Esperado:**
- Redução de retrabalho em futuras iterações
- Maior alinhamento entre expectativa e implementação
- Colaboração mais eficiente e previsível

---

## 📞 INFORMAÇÕES DE CONTATO

### Repositório
- **GitHub:** https://github.com/henrique-m-ribeiro/caderno-tocantins-2026
- **Branch Atual:** `documentacao-plano-refatoracao-v02`
- **Branch Futura:** `refatoracao-planilhas-v02-revisada`

### Metodologia
- **IA Collab OS:** https://github.com/henrique-m-ribeiro/ia-collab-os

---

**Elaborado em:** 27 de janeiro de 2026
**Por:** Claude (Sonnet 4.5)
**Sessão:** Planejamento da Refatoração V02
**Próxima revisão:** Início da implementação (Fase 0)

**Status:** ✅ Documentação completa - Pronto para implementação

---

## ANEXO: Resumo de Decisões Técnicas

### Decisões Aprovadas pelo Usuário

1. **Acesso aos PDFs:** Google Drive compartilhado ✅
2. **Priorização:** Trabalho em paralelo (4 sprints) ✅
3. **Consolidações:** 6 planilhas separadas por classificação ✅
4. **Classificações Regionais:** SEPLAN-TO 2024 confirmada ✅
5. **Escopo de Revisão:** Partes I e II incluídas ✅

### Decisões Técnicas Tomadas

1. **Estrutura de colunas:** ~65 colunas (vs 37 atuais)
2. **Restauração de `_ano_ref`:** Para todos os indicadores
3. **Biblioteca de extração:** pdfplumber (recomendada)
4. **Estratégia de download:** Google Drive manual ou gdown
5. **Processamento:** Paralelo com multiprocessing

### Métricas de Sucesso

- Cobertura de dados: ≥85% (vs 35% atual)
- Taxa de extração: ≥85% dos 139 PDFs
- Erros manuais: <10% dos municípios
- Tempo de implementação: 7-10 dias úteis (6h/dia)

---

**FIM DO HANDOFF**
