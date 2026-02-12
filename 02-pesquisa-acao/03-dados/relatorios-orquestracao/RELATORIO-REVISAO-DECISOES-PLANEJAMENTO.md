# RELATÓRIO: REVISÃO DAS DECISÕES DE PLANEJAMENTO
## Análise Comparativa Planejado vs Executado
### Caderno Tocantins 2026

**Data:** 25 de janeiro de 2026
**Autor:** Sistema de Inteligência Territorial
**Tipo:** Análise Técnica e Estratégica
**Contexto:** Preparação para coleta manual de dados e automação posterior

---

## 📋 SUMÁRIO EXECUTIVO

Este relatório analisa profundamente as duas decisões críticas documentadas no Diário de Pesquisa-Ação:

1. **Decisão 1:** Criar documento de planejamento detalhado antes da implementação
2. **Decisão 2:** Aprovar simplificações da implementação (52 → 37 colunas)

### Principais Achados

- ✅ **15 indicadores foram excluídos** na simplificação
- ✅ **3 indicadores foram expandidos** (IDHM desdobrado em 4)
- ✅ **1 mudança conceitual importante** (VAB absoluto ao invés de percentual)
- ⚠️ **Turismo foi completamente removido** (4 colunas)
- ⚠️ **Metadados inline foram eliminados** (anos de referência, fontes)

### Cobertura Atual de Dados

| Status | Qtd Indicadores | % Total | Descrição |
|--------|----------------|---------|-----------|
| ✅ **Dados completos** | 3 | 8% | População 2010/2022, Crescimento |
| ⚠️ **Dados parciais** | 7 | 19% | 15-60% de cobertura |
| ❌ **Dados ausentes** | 27 | 73% | 0% de cobertura |
| **TOTAL** | **37** | **100%** | |

---

## 1. CONTEXTO DAS DECISÕES

### 1.1 Decisão 1: Planejamento Detalhado (1.5h investidas)

**Situação Original:**
- Necessidade de consolidar dados de 8 microrregiões em estrutura única
- Múltiplas dimensões de análise (demografia, economia, educação, saúde, etc.)
- Ausência de padrões estabelecidos

**Ação Tomada:**
Criação do documento `PLANEJAMENTO_PLANILHAS_CONSOLIDADAS.md` especificando:
- **52 colunas** organizadas em 9 dimensões
- **151 linhas** (139 municípios + consolidações)
- **Metadados com 14 campos** por variável
- Nomenclatura padronizada, fontes, fórmulas de agregação

**Resultado:**
- 13.000+ palavras de especificação técnica
- Estrutura hierárquica clara (município → microrregião → mesorregião → estado)
- Rastreabilidade completa documentada

---

### 1.2 Decisão 2: Aprovar Simplificações (52 → 37 colunas)

**Situação:**
Usuário criou planilhas com **37 colunas** ao invés das 52 planejadas.

**Ação Tomada:**
- Análise detalhada das simplificações
- Avaliação positiva (nota 9.8/10)
- Celebração das otimizações feitas

**Simplicações Aprovadas:**
1. Prefixo `[CONSOLIDADO]` no nome ao invés de coluna `tipo`
2. Anos de referência movidos para metadados (redução de 6 colunas)
3. Produtos agrícolas específicos (soja/milho/arroz) ao invés de genéricos
4. Eliminação da dimensão Turismo completa (4 colunas)
5. Ajustes em nomenclatura (mais concisa e clara)

---

## 2. ANÁLISE COMPARATIVA DETALHADA

### 2.1 Visão Geral das Mudanças

| Aspecto | Planejado | Executado | Diferença |
|---------|-----------|-----------|-----------|
| **Total de colunas** | 52 | 37 | -15 (-29%) |
| **Dimensões de análise** | 9 | 8 | -1 (Turismo removido) |
| **Colunas de identificação** | 6 | 5 | -1 (territorio_tipo) |
| **Colunas demográficas** | 7 | 6 | -1 |
| **Colunas econômicas** | 6 | 5 | -1 |
| **Colunas desenv. humano** | 2 | 4 | +2 (IDHM desdobrado) |
| **Colunas educação** | 6 | 4 | -2 |
| **Colunas saúde** | 5 | 2 | -3 |
| **Colunas saneamento** | 6 | 4 | -2 |
| **Colunas agropecuária** | 9 | 6 | -3 |
| **Colunas turismo** | 4 | 0 | -4 (removido) |
| **Coluna observações** | 1 | 0 | -1 |

---

### 2.2 Os 15 Indicadores Excluídos

#### GRUPO 1: Remoção de Coluna de Tipo (1 indicador)

| # | Código Planejado | Justificativa da Exclusão | Avaliação |
|---|------------------|---------------------------|-----------|
| 1 | `territorio_tipo` | **Substituído por prefixo `[CONSOLIDADO]` no nome**. Solução mais elegante que coluna separada. | ✅ Excelente decisão |

**Impacto:** Nenhum. A informação está preservada de forma mais limpa.

---

#### GRUPO 2: Anos de Referência e Fontes (6 indicadores)

| # | Código Planejado | Onde foi? | Avaliação |
|---|------------------|-----------|-----------|
| 2 | `econ_pib_ano_ref` | Movido para metadados | ✅ Correto - Evita redundância |
| 3 | `desenv_idhm_ano_ref` | Movido para metadados (fixo: 2010) | ✅ Correto - Valor único |
| 4 | `saude_mort_inf_ano_ref` | Movido para metadados | ✅ Correto |
| 5 | `agro_vbp_ano_ref` | Movido para metadados | ✅ Correto |
| 6 | `san_ano_ref` | Movido para metadados | ✅ Correto |
| 7 | `san_fonte` | Movido para metadados | ✅ Correto |

**Justificativa Unificada:**
- Anos de referência geralmente são os mesmos para todos os municípios de um indicador
- Fontes são padronizadas (IBGE, INEP, SNIS, etc.)
- Manter na planilha de dados criaria muita redundância
- Metadados são o local apropriado para documentação de contexto

**Impacto:** Positivo. Redução de ruído visual, metadados robustos.

---

#### GRUPO 3: IDEB 2021 (2 indicadores)

| # | Código Planejado | Por que foi excluído? | Avaliação |
|---|------------------|----------------------|-----------|
| 8 | `edu_ideb_ai_2021` | Foco em dados mais recentes (2023) | ⚠️ Questionável |
| 9 | `edu_ideb_af_2021` | Foco em dados mais recentes (2023) | ⚠️ Questionável |

**Justificativa Presumida:**
- IDEB é bienal (2019, 2021, 2023)
- Priorizar versão mais recente (2023)
- Evitar acúmulo de séries históricas completas

**Contra-Argumentos:**
- IDEB 2021 permite análise de tendência (crescimento ou queda)
- 2021 foi primeiro IDEB pós-pandemia (dado relevante)
- Comparação 2021 vs 2023 mostra recuperação educacional

**Recomendação:** ⚠️ **CONSIDERAR REINCLUSÃO**
- Séries temporais são valiosas para análise de tendências
- Adicionar apenas 2 colunas
- Custo-benefício favorável

---

#### GRUPO 4: Educação e Saúde (4 indicadores)

| # | Código Planejado | Por que foi excluído? | Avaliação |
|---|------------------|----------------------|-----------|
| 10 | `edu_analfab_15mais_perc` | Simplificação da dimensão educação | ⚠️ Perda significativa |
| 11 | `saude_cobert_esf_perc` | Simplificação da dimensão saúde | ⚠️ Perda significativa |
| 12 | `saude_leitos_1000hab` | Simplificação da dimensão saúde | ⚠️ Perda significativa |
| 13 | `saude_medicos_1000hab` | Simplificação da dimensão saúde | ⚠️ Perda significativa |

**Análise Crítica:**

**Taxa de Analfabetismo 15+ anos:**
- Indicador fundamental de desenvolvimento social
- Complementa taxa de escolarização
- Disponível no IBGE Cidades
- **Recomendação:** ⚠️ **CONSIDERAR REINCLUSÃO** - Relevância política alta

**Cobertura ESF (Estratégia Saúde da Família):**
- Indicador-chave de acesso à atenção primária
- Política prioritária do SUS
- Disponível no e-Gestor Atenção Básica
- **Recomendação:** ✅ **REINCLUIR** - Essencial para análise de saúde

**Leitos por 1000 habitantes:**
- Indicador de capacidade hospitalar
- Crítico para análise de infraestrutura de saúde
- Disponível no CNES (Cadastro Nacional de Estabelecimentos de Saúde)
- **Recomendação:** ⚠️ **CONSIDERAR REINCLUSÃO** - Especialmente relevante pós-pandemia

**Médicos por 1000 habitantes:**
- Indicador de recursos humanos em saúde
- Permite identificar "vazios assistenciais"
- Disponível no CNES
- **Recomendação:** ⚠️ **CONSIDERAR REINCLUSÃO** - Relevância política alta

---

#### GRUPO 5: Agropecuária - Culturas Genéricas (3 indicadores)

| # | Código Planejado | O que substituiu? | Avaliação |
|---|------------------|-------------------|-----------|
| 14 | `agro_cultura_princ_1` | `agro_prod_soja_ton` | ✅ Excelente mudança |
| 15 | `agro_cultura_princ_2` | `agro_prod_milho_ton` | ✅ Excelente mudança |
| 16 | `agro_cultura_princ_3` | `agro_prod_arroz_ton` | ✅ Excelente mudança |

**Justificativa:**
- Cultura principal 1/2/3 eram **campos de texto** genéricos (ex: "soja", "milho")
- Substituição por **colunas específicas com dados quantitativos** (toneladas)
- Soja, milho e arroz são as 3 principais culturas do Tocantins
- Dados quantitativos permitem análises econômicas mais robustas

**Impacto:** ✅ Muito positivo. Troca de dados qualitativos por quantitativos.

---

#### GRUPO 6: Dimensão Turismo COMPLETA (4 indicadores + 1 observação)

| # | Código Planejado | Status | Avaliação |
|---|------------------|--------|-----------|
| 17 | `tur_visitantes_ano` | ❌ Removido | ⚠️ Perda moderada |
| 18 | `tur_receita_milhoes` | ❌ Removido | ⚠️ Perda moderada |
| 19 | `tur_atrativos` | ❌ Removido | ⚠️ Perda moderada |
| 20 | `tur_ano_ref` | ❌ Removido | ⚠️ Perda moderada |
| 21 | `obs` | ❌ Removido | ⚠️ Perda baixa |

**Justificativa Presumida:**
- Turismo é relevante apenas para alguns municípios (Jalapão, principalmente)
- Dados de difícil obtenção (não há sistema nacional consolidado)
- Foco em indicadores universalmente aplicáveis
- Priorização de recursos de coleta

**Contra-Argumentos:**
- Jalapão é destino turístico nacional (Parque Estadual)
- Turismo é vetor de desenvolvimento para municípios pequenos
- Palmas tem turismo de negócios significativo
- Dados estão disponíveis (NATURATINS, Secretaria de Turismo TO)

**Análise de Custo-Benefício:**
- **Benefício:** Moderado (relevante para 15-20% dos municípios)
- **Custo de coleta:** Alto (fontes dispersas, não padronizadas)
- **Decisão original:** Compreensível no contexto de priorização

**Recomendação:**
1. **Curto prazo:** ❌ Manter exclusão (priorizar indicadores universais)
2. **Médio prazo:** ⚠️ Criar planilha complementar específica para municípios turísticos
3. **Longo prazo:** ✅ Integrar quando estrutura de coleta estiver madura

---

### 2.3 Mudanças Conceituais Importantes

#### MUDANÇA 1: VAB Absoluto ao invés de Percentual

**Planejado:**
- `econ_vab_agro_perc` (% do VAB)
- `econ_vab_ind_perc` (% do VAB)
- `econ_vab_serv_perc` (% do VAB)

**Executado:**
- `econ_vab_agro_mil_reais` (valor absoluto)
- `econ_vab_ind_mil_reais` (valor absoluto)
- `econ_vab_serv_mil_reais` (valor absoluto)

**Análise:**
- ✅ **Valores absolutos são mais informativos** (permitem calcular percentuais E valores totais)
- ✅ **Agregação mais simples** (soma direta para consolidações)
- ✅ **Permite análises de escala econômica** (não apenas composição)
- ⚠️ **Percentuais precisam ser calculados** (mas é trivial: VAB_agro / PIB_total)

**Avaliação:** ✅ **Mudança muito positiva.** Valores absolutos são mais versáteis.

---

#### MUDANÇA 2: IDHM Desdobrado em Subíndices

**Planejado:**
- `desenv_idhm` (índice geral)
- `desenv_idhm_ano_ref` (ano de referência)

**Executado:**
- `idh_idhm_2010` (índice geral)
- `idh_idhm_renda_2010` (subíndice renda)
- `idh_idhm_long_2010` (subíndice longevidade)
- `idh_idhm_educ_2010` (subíndice educação)

**Análise:**
- ✅ **Desdobramento permite análise dimensional** (qual dimensão puxa o IDHM pra cima/baixo?)
- ✅ **Identifica gargalos específicos** (município com renda alta mas educação baixa, etc.)
- ✅ **Dados estão disponíveis no Atlas Brasil** (mesmo esforço de coleta)
- ⚠️ **Adiciona 3 colunas**, mas compensa com eliminação de `ano_ref`

**Avaliação:** ✅ **Mudança excelente.** Enriquece capacidade analítica.

---

#### MUDANÇA 3: Adição de Taxa de Escolarização 15-17 anos

**Planejado:**
- `edu_escol_6_14_perc` (escolarização 6-14 anos)

**Executado:**
- `educ_tx_escolar_6_14_pct` (escolarização 6-14 anos)
- `educ_tx_escolar_15_17_pct` (escolarização 15-17 anos) ← **NOVO**

**Análise:**
- ✅ **Adição não planejada mas valiosa**
- ✅ **Captura acesso ao ensino médio** (evasão escolar na adolescência)
- ✅ **Disponível na mesma fonte** (IBGE Cidades)
- ✅ **Complementa dimensão educação**

**Avaliação:** ✅ **Adição excelente.** Melhora análise educacional.

---

#### MUDANÇA 4: Adição de Expectativa de Vida

**Planejado:**
- Não estava previsto na dimensão saúde

**Executado:**
- `saude_expect_vida_anos` ← **NOVO**

**Análise:**
- ✅ **Indicador síntese de condições de saúde**
- ✅ **Componente do IDHM Longevidade** (coerência com desdobramento do IDHM)
- ✅ **Disponível no Atlas Brasil** (mesma fonte do IDHM)
- ⚠️ **Compensa parcialmente remoção de leitos e médicos**

**Avaliação:** ✅ **Adição positiva.** Indicador síntese importante.

---

## 3. ANÁLISE DA SITUAÇÃO DOS DADOS FALTANTES

### 3.1 Panorama Geral de Cobertura

| Indicador | Cobertura Atual | Status | Dificuldade de Coleta | Prioridade |
|-----------|-----------------|--------|----------------------|------------|
| **DIMENSÃO TERRITORIAL** |
| terr_area_km2 | 38.8% | ⚠️ Parcial | 🟢 Baixa | Alta |
| **DIMENSÃO DEMOGRÁFICA** |
| demo_pop_2010 | 95.7% | ✅ Quase completo | 🟢 Baixa | Média |
| demo_pop_2022 | 95.7% | ✅ Quase completo | 🟢 Baixa | Alta |
| demo_pop_2025_est | ~20% | ❌ Baixo | 🟢 Baixa | Baixa |
| demo_cresc_2010_2022_pct | 95.7% | ✅ Calculado | - | - |
| demo_dens_dem_hab_km2 | 38.8% | ⚠️ Parcial (depende área) | - | Alta |
| demo_tx_urban_pct | 0% | ❌ Ausente | 🟢 Baixa | Média |
| **DIMENSÃO ECONÔMICA** |
| econ_pib_total_mil_reais | ~20% | ❌ Baixo | 🟢 Baixa | Alta |
| econ_pib_per_capita_reais | 29.5% | ⚠️ Parcial | 🟢 Baixa | Alta |
| econ_vab_agro_mil_reais | 0% | ❌ Ausente | 🟡 Média | Alta |
| econ_vab_ind_mil_reais | 0% | ❌ Ausente | 🟡 Média | Alta |
| econ_vab_serv_mil_reais | 0% | ❌ Ausente | 🟡 Média | Alta |
| **DIMENSÃO DESENVOLVIMENTO HUMANO** |
| idh_idhm_2010 | 27.3% | ⚠️ Parcial | 🟢 Baixa | Alta |
| idh_idhm_renda_2010 | 0% | ❌ Ausente | 🟢 Baixa | Média |
| idh_idhm_long_2010 | 0% | ❌ Ausente | 🟢 Baixa | Média |
| idh_idhm_educ_2010 | 0% | ❌ Ausente | 🟢 Baixa | Média |
| **DIMENSÃO EDUCAÇÃO** |
| educ_ideb_anos_iniciais_2023 | 0% | ❌ Ausente | 🟡 Média | Máxima |
| educ_ideb_anos_finais_2023 | 0% | ❌ Ausente | 🟡 Média | Máxima |
| educ_tx_escolar_6_14_pct | 25.9% | ⚠️ Parcial | 🟢 Baixa | Alta |
| educ_tx_escolar_15_17_pct | 0% | ❌ Ausente | 🟢 Baixa | Alta |
| **DIMENSÃO SAÚDE** |
| saude_mort_inf_por_mil | 16.5% | ❌ Baixo | 🟡 Média | Alta |
| saude_expect_vida_anos | 0% | ❌ Ausente | 🟢 Baixa | Média |
| **DIMENSÃO SANEAMENTO** |
| sanea_agua_adequada_pct | 0% | ❌ Ausente | 🟡 Média | Máxima |
| sanea_esgoto_adequado_pct | 0% | ❌ Ausente | 🟡 Média | Máxima |
| sanea_trat_esgoto_pct | 0% | ❌ Ausente | 🟡 Média | Alta |
| sanea_coleta_lixo_pct | 0% | ❌ Ausente | 🟢 Baixa | Alta |
| **DIMENSÃO AGROPECUÁRIA** |
| agro_vbp_total_mil_reais | 0% | ❌ Ausente | 🟡 Média | Máxima |
| agro_area_plantada_ha | 0% | ❌ Ausente | 🟡 Média | Alta |
| agro_rebanho_bovino_cabecas | 0% | ❌ Ausente | 🟡 Média | Máxima |
| agro_prod_soja_ton | 0% | ❌ Ausente | 🟡 Média | Máxima |
| agro_prod_milho_ton | 0% | ❌ Ausente | 🟡 Média | Alta |
| agro_prod_arroz_ton | 0% | ❌ Ausente | 🟡 Média | Alta |

---

### 3.2 Agrupamento por Facilidade de Coleta

#### GRUPO A: Coleta Muito Fácil (1 dia de trabalho)

**Fonte:** IBGE Cidades + Atlas Brasil (interfaces web amigáveis)

| Indicador | Município | Ação |
|-----------|-----------|------|
| terr_area_km2 | 139 | Download de tabela única do IBGE |
| demo_pop_2010 | 6 faltantes | Completar lacunas |
| demo_pop_2022 | 6 faltantes | Completar lacunas |
| demo_tx_urban_pct | 139 | IBGE Cidades - Dado do Censo 2010 |
| idh_idhm_2010 | 101 faltantes | Atlas Brasil - Planilha consolidada TO |
| idh_idhm_renda_2010 | 139 | Atlas Brasil - Mesma planilha |
| idh_idhm_long_2010 | 139 | Atlas Brasil - Mesma planilha |
| idh_idhm_educ_2010 | 139 | Atlas Brasil - Mesma planilha |
| saude_expect_vida_anos | 139 | Atlas Brasil - Mesma planilha |
| educ_tx_escolar_6_14_pct | 103 faltantes | IBGE Cidades |
| educ_tx_escolar_15_17_pct | 139 | IBGE Cidades |

**Total:** 11 indicadores | **Esforço estimado:** 6-8 horas

---

#### GRUPO B: Coleta Fácil com Download de Arquivos (2-3 dias)

**Fonte:** IBGE SIDRA (Sistema de Recuperação Automática)

| Indicador | Município | Fonte SIDRA | Tabela |
|-----------|-----------|-------------|--------|
| econ_pib_total_mil_reais | 111 faltantes | PIB Municipal | 5938 |
| econ_pib_per_capita_reais | 98 faltantes | PIB Municipal | 5938 |
| econ_vab_agro_mil_reais | 139 | Contas Regionais | 5938 |
| econ_vab_ind_mil_reais | 139 | Contas Regionais | 5938 |
| econ_vab_serv_mil_reais | 139 | Contas Regionais | 5938 |
| agro_area_plantada_ha | 139 | PAM | 5457 |
| agro_rebanho_bovino_cabecas | 139 | PPM | 3939 |
| agro_prod_soja_ton | 139 | PAM | 5457 |
| agro_prod_milho_ton | 139 | PAM | 5457 |
| agro_prod_arroz_ton | 139 | PAM | 5457 |
| sanea_coleta_lixo_pct | 139 | Censo 2010 | 1378 |

**Total:** 11 indicadores | **Esforço estimado:** 12-16 horas

**Estratégia:**
1. Acessar SIDRA Tabular
2. Filtrar: Tocantins, Todos os municípios, Ano mais recente
3. Download em CSV ou Excel
4. Script Python para transformar em formato da planilha consolidada

---

#### GRUPO C: Coleta Moderada com Múltiplas Fontes (3-5 dias)

**Fontes:** INEP, QEdu, SNIS, DATASUS (portais especializados)

| Indicador | Município | Fonte | Desafio |
|-----------|-----------|-------|---------|
| educ_ideb_anos_iniciais_2023 | 139 | INEP/QEdu | Nem todos municípios têm IDEB (escolas pequenas) |
| educ_ideb_anos_finais_2023 | 139 | INEP/QEdu | Idem |
| saude_mort_inf_por_mil | 116 faltantes | DATASUS TabNet | Interface complexa, requer múltiplas queries |
| sanea_agua_adequada_pct | 139 | SNIS | Nem todos municípios reportam ao SNIS |
| sanea_esgoto_adequado_pct | 139 | SNIS | Idem |
| sanea_trat_esgoto_pct | 139 | SNIS | Idem |
| agro_vbp_total_mil_reais | 139 | MAPA/IBGE | Cálculo a partir de PAM e PPM |

**Total:** 7 indicadores | **Esforço estimado:** 16-24 horas

**Desafios:**
- **IDEB:** Municípios muito pequenos podem não ter IDEB calculado (menos de 20 alunos)
- **SNIS:** Adesão voluntária, alguns municípios não reportam
- **DATASUS:** Interface TabNet complexa, requer conhecimento técnico
- **VBP:** Requer cálculo (soma de VBP de culturas individuais)

---

### 3.3 Estimativa Total de Esforço para Completar Dados

| Grupo | Indicadores | Municípios afetados | Horas Manuais | Horas Automação | Total |
|-------|-------------|--------------------|--------------|--------------------|-------|
| **Grupo A** | 11 | ~1.200 células | 6-8h | 2-3h (script de carga) | 8-11h |
| **Grupo B** | 11 | ~1.500 células | 12-16h | 4-6h (script de transformação) | 16-22h |
| **Grupo C** | 7 | ~970 células | 16-24h | 6-8h (múltiplos scripts) | 22-32h |
| **Validação** | - | - | - | 4-6h (checagem de integridade) | 4-6h |
| **TOTAL** | **29** | **~3.670 células** | **34-48h** | **16-23h** | **50-71h** |

**Com dedicação de 6h/dia:** 9-12 dias úteis

**Com dedicação de 4h/dia:** 13-18 dias úteis

---

## 4. RECOMENDAÇÕES E DECISÕES A TOMAR

### 4.1 Sobre os Indicadores Excluídos

#### ✅ MANTER EXCLUSÃO (6 indicadores)

1. `territorio_tipo` - Substituição por prefixo [CONSOLIDADO] é superior
2-7. Anos de referência e fontes - Metadados são local apropriado

**Justificativa:** Simplificações que melhoraram qualidade sem perda de informação.

---

#### ⚠️ REAVALIAR PARA REINCLUSÃO (8 indicadores)

**PRIORIDADE ALTA - Reincluir na V02:**

| Indicador | Justificativa | Esforço |
|-----------|---------------|---------|
| `edu_analfab_15mais_perc` | Relevância política alta, complementa educação | Baixo (IBGE Cidades) |
| `saude_cobert_esf_perc` | Essencial para análise de atenção primária | Baixo (e-Gestor AB) |
| `edu_ideb_ai_2021` | Permite análise de tendência 2021→2023 | Baixo (INEP) |
| `edu_ideb_af_2021` | Permite análise de tendência 2021→2023 | Baixo (INEP) |

**Impacto:** +4 colunas (37 → 41)

**PRIORIDADE MÉDIA - Reavaliar em V03:**

| Indicador | Justificativa | Esforço |
|-----------|---------------|---------|
| `saude_leitos_1000hab` | Infraestrutura hospitalar é relevante | Médio (CNES) |
| `saude_medicos_1000hab` | Recursos humanos em saúde | Médio (CNES) |

**Impacto adicional:** +2 colunas (41 → 43)

---

#### ❌ MANTER EXCLUSÃO DEFINITIVA (2 indicadores)

| Indicador | Justificativa |
|-----------|---------------|
| `obs` (Observações) | Informação qualitativa, melhor em documentação separada |
| Dimensão Turismo completa (4 indicadores) | Criar planilha complementar específica futuramente |

---

### 4.2 Proposta de Versionamento

#### V01 (ATUAL)
- **37 colunas**
- **35% de cobertura média**
- **Status:** Infraestrutura criada, dados parciais

#### V02 (PRÓXIMA - 2-3 semanas)
- **41 colunas** (+ 4 reinclusões prioritárias)
- **Meta: 85% de cobertura média**
- **Foco:**
  - Completar todos os indicadores dos Grupos A e B
  - IDEB 2023 (prioridade máxima)
  - Saneamento SNIS (prioridade máxima)
  - Agropecuária PAM/PPM (prioridade máxima)
  - **Reincluir:** Analfabetismo, ESF, IDEB 2021

#### V03 (FUTURA - 1-2 meses)
- **43-45 colunas** (+ saúde infraestrutura)
- **Meta: 95% de cobertura média**
- **Foco:**
  - Completar lacunas remanescentes
  - Adicionar leitos e médicos
  - Validação e refinamento

#### V04 (EXPANSÃO - 3-6 meses)
- **~50 colunas** (+ turismo para municípios relevantes)
- **Planilha complementar de turismo**
- **Dados históricos** (séries temporais quando relevante)

---

## 5. PASSO-A-PASSO PARA COLETA MANUAL E AUTOMAÇÃO

### 5.1 Filosofia do Processo

```
DOWNLOAD MANUAL → SCRIPT DE TRANSFORMAÇÃO → VALIDAÇÃO → INTEGRAÇÃO
```

**Princípio:** Você baixa os dados brutos manualmente (garante flexibilidade e conhecimento das fontes). Depois, scripts Python transformam e integram automaticamente (garante reprodutibilidade e eficiência).

---

### 5.2 FASE 1: Coleta de Dados Fáceis (Grupo A)

#### PASSO 1.1: Área Territorial (IBGE)

**Download Manual:**
1. Acessar: https://www.ibge.gov.br/geociencias/organizacao-do-territorio/estrutura-territorial/15761-areas-dos-municipios.html
2. Baixar planilha: "Área territorial - Brasil, Grandes Regiões e Unidades da Federação"
3. Filtrar Tocantins
4. Salvar como: `dados/brutos/ibge-area-territorial-to-2022.xlsx`

**Script de Automação:**
```python
# scripts/carregar_area_territorial.py
import pandas as pd

# Ler arquivo bruto
df_area = pd.read_excel('dados/brutos/ibge-area-territorial-to-2022.xlsx')

# Transformar
df_area_limpo = df_area[['cod_ibge', 'area_km2']].copy()

# Integrar com base consolidada
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V01.csv')
df_base = df_base.merge(df_area_limpo, left_on='terr_codigo_ibge', right_on='cod_ibge', how='left')
df_base['terr_area_km2'] = df_base['area_km2']

# Recalcular densidade demográfica
df_base['demo_dens_dem_hab_km2'] = df_base['demo_pop_2022'] / df_base['terr_area_km2']

# Salvar
df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 15 min manual + 30 min script = 45 min

---

#### PASSO 1.2: IDHM e Subíndices (Atlas Brasil)

**Download Manual:**
1. Acessar: http://www.atlasbrasil.org.br/consulta/planilha
2. Filtrar: Tocantins
3. Selecionar indicadores:
   - IDHM 2010
   - IDHM Renda 2010
   - IDHM Longevidade 2010
   - IDHM Educação 2010
   - Expectativa de vida ao nascer 2010
4. Download Excel
5. Salvar como: `dados/brutos/atlas-brasil-idhm-to-2010.xlsx`

**Script de Automação:**
```python
# scripts/carregar_idhm_atlas_brasil.py
import pandas as pd

# Ler arquivo bruto
df_idhm = pd.read_excel('dados/brutos/atlas-brasil-idhm-to-2010.xlsx')

# Mapear colunas
mapa_colunas = {
    'Codmun7': 'terr_codigo_ibge',
    'IDHM 2010': 'idh_idhm_2010',
    'IDHM Renda 2010': 'idh_idhm_renda_2010',
    'IDHM Longevidade 2010': 'idh_idhm_long_2010',
    'IDHM Educação 2010': 'idh_idhm_educ_2010',
    'Esperança de vida ao nascer': 'saude_expect_vida_anos'
}

df_idhm_limpo = df_idhm.rename(columns=mapa_colunas)

# Integrar
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
df_base = df_base.merge(df_idhm_limpo[list(mapa_colunas.values())],
                        on='terr_codigo_ibge', how='left', suffixes=('', '_novo'))

# Preencher apenas células vazias
for col in ['idh_idhm_2010', 'idh_idhm_renda_2010', 'idh_idhm_long_2010',
            'idh_idhm_educ_2010', 'saude_expect_vida_anos']:
    df_base[col] = df_base[col].fillna(df_base[f'{col}_novo'])

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 20 min manual + 45 min script = 65 min

---

#### PASSO 1.3: Taxas de Escolarização (IBGE Cidades)

**Download Manual:**
1. Acessar: https://cidades.ibge.gov.br/
2. Para cada município (139):
   - Buscar município
   - Copiar "Taxa de escolarização - 6 a 14 anos"
   - Copiar "Taxa de escolarização - 15 a 17 anos"
3. Colar em planilha auxiliar: `dados/brutos/ibge-escolarizacao-to.xlsx`

**Alternativa Mais Eficiente:**
1. IBGE SIDRA - Tabela 1378 (Censo 2010)
2. Filtrar Tocantins, todos os municípios
3. Variável: Taxa de escolarização
4. Download CSV

**Script de Automação:**
```python
# scripts/carregar_escolarizacao.py
import pandas as pd

# Ler CSV do SIDRA
df_escol = pd.read_csv('dados/brutos/sidra-tabela-1378-escolarizacao-to.csv', sep=';')

# Transformar formato SIDRA (pivotado) para wide
df_escol_6_14 = df_escol[df_escol['Grupo de idade'] == '6 a 14 anos']
df_escol_15_17 = df_escol[df_escol['Grupo de idade'] == '15 a 17 anos']

# Integrar
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
# ... merge logic

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 30 min manual + 60 min script = 90 min

---

### 5.3 FASE 2: Coleta de Dados Moderados (Grupo B)

#### PASSO 2.1: PIB Municipal e VAB Setorial (IBGE SIDRA)

**Download Manual:**
1. Acessar: https://sidra.ibge.gov.br/tabela/5938
2. Configurar:
   - **Variáveis:**
     - Produto Interno Bruto (Mil Reais)
     - PIB per capita (Reais)
     - Valor adicionado bruto da Agropecuária (Mil Reais)
     - Valor adicionado bruto da Indústria (Mil Reais)
     - Valor adicionado bruto dos Serviços (Mil Reais)
   - **Territorialidade:** Tocantins > Todos os municípios
   - **Período:** 2021 (mais recente disponível)
3. Download CSV
4. Salvar como: `dados/brutos/sidra-5938-pib-vab-to-2021.csv`

**Script de Automação:**
```python
# scripts/carregar_pib_vab_sidra.py
import pandas as pd

# Ler CSV SIDRA (formato específico do SIDRA tem cabeçalhos complexos)
df_pib = pd.read_csv('dados/brutos/sidra-5938-pib-vab-to-2021.csv',
                     sep=';', skiprows=1, encoding='latin-1')

# Transformar de formato long para wide
# (cada município terá uma linha, variáveis nas colunas)
df_pib_wide = df_pib.pivot_table(
    index='Município (Código)',
    columns='Variável',
    values='Valor',
    aggfunc='first'
).reset_index()

# Renomear colunas
df_pib_wide.columns = [
    'terr_codigo_ibge',
    'econ_pib_total_mil_reais',
    'econ_pib_per_capita_reais',
    'econ_vab_agro_mil_reais',
    'econ_vab_ind_mil_reais',
    'econ_vab_serv_mil_reais'
]

# Integrar com base consolidada
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
df_base = df_base.merge(df_pib_wide, on='terr_codigo_ibge', how='left', suffixes=('', '_novo'))

# Atualizar apenas células vazias
for col in ['econ_pib_total_mil_reais', 'econ_pib_per_capita_reais',
            'econ_vab_agro_mil_reais', 'econ_vab_ind_mil_reais', 'econ_vab_serv_mil_reais']:
    df_base[col] = df_base[col].fillna(df_base[f'{col}_novo'])

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 30 min manual + 90 min script = 120 min

---

#### PASSO 2.2: Produção Agrícola - PAM (IBGE SIDRA)

**Download Manual:**
1. Acessar: https://sidra.ibge.gov.br/tabela/5457
2. Configurar:
   - **Variáveis:**
     - Área plantada ou destinada à colheita (Hectares)
     - Quantidade produzida (Toneladas)
   - **Produto das lavouras:** Soja (em grão), Milho (em grão), Arroz (em casca)
   - **Territorialidade:** Tocantins > Todos os municípios
   - **Período:** 2023 (mais recente)
3. Download CSV
4. Salvar como: `dados/brutos/sidra-5457-pam-to-2023.csv`

**Script de Automação:**
```python
# scripts/carregar_pam_agricultura.py
import pandas as pd

# Ler CSV SIDRA
df_pam = pd.read_csv('dados/brutos/sidra-5457-pam-to-2023.csv',
                     sep=';', skiprows=1, encoding='latin-1')

# Filtrar e transformar
df_area = df_pam[df_pam['Variável'] == 'Área plantada ou destinada à colheita']
df_prod = df_pam[df_pam['Variável'] == 'Quantidade produzida']

# Pivot por cultura
df_soja = df_prod[df_prod['Produto'] == 'Soja (em grão)'][['Município (Código)', 'Valor']]
df_soja.columns = ['terr_codigo_ibge', 'agro_prod_soja_ton']

df_milho = df_prod[df_prod['Produto'] == 'Milho (em grão)'][['Município (Código)', 'Valor']]
df_milho.columns = ['terr_codigo_ibge', 'agro_prod_milho_ton']

df_arroz = df_prod[df_prod['Produto'] == 'Arroz (em casca)'][['Município (Código)', 'Valor']]
df_arroz.columns = ['terr_codigo_ibge', 'agro_prod_arroz_ton']

# Área total
df_area_total = df_area.groupby('Município (Código)')['Valor'].sum().reset_index()
df_area_total.columns = ['terr_codigo_ibge', 'agro_area_plantada_ha']

# Integrar tudo
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
for df in [df_soja, df_milho, df_arroz, df_area_total]:
    df_base = df_base.merge(df, on='terr_codigo_ibge', how='left', suffixes=('', '_novo'))
    # Preencher vazios
    col = [c for c in df.columns if c != 'terr_codigo_ibge'][0]
    df_base[col] = df_base[col].fillna(df_base[f'{col}_novo'])

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 30 min manual + 90 min script = 120 min

---

#### PASSO 2.3: Pecuária - PPM (IBGE SIDRA)

**Download Manual:**
1. Acessar: https://sidra.ibge.gov.br/tabela/3939
2. Configurar:
   - **Variável:** Efetivo dos rebanhos (Número de cabeças)
   - **Tipo de rebanho:** Bovino
   - **Territorialidade:** Tocantins > Todos os municípios
   - **Período:** 2023
3. Download CSV
4. Salvar como: `dados/brutos/sidra-3939-ppm-bovinos-to-2023.csv`

**Script de Automação:**
```python
# scripts/carregar_ppm_pecuaria.py
import pandas as pd

df_ppm = pd.read_csv('dados/brutos/sidra-3939-ppm-bovinos-to-2023.csv',
                     sep=';', skiprows=1, encoding='latin-1')

df_bovinos = df_ppm[['Município (Código)', 'Valor']].copy()
df_bovinos.columns = ['terr_codigo_ibge', 'agro_rebanho_bovino_cabecas']

# Integrar
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
df_base = df_base.merge(df_bovinos, on='terr_codigo_ibge', how='left', suffixes=('', '_novo'))
df_base['agro_rebanho_bovino_cabecas'] = df_base['agro_rebanho_bovino_cabecas'].fillna(
    df_base['agro_rebanho_bovino_cabecas_novo'])

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 15 min manual + 45 min script = 60 min

---

### 5.4 FASE 3: Coleta de Dados Complexos (Grupo C)

#### PASSO 3.1: IDEB 2023 e 2021 (INEP/QEdu)

**Opção 1: Download Oficial INEP**
1. Acessar: https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/ideb/resultados
2. Baixar planilha nacional do IDEB 2023
3. Filtrar Tocantins
4. Salvar: `dados/brutos/inep-ideb-2023-to.xlsx`

**Opção 2: QEdu (mais amigável)**
1. Acessar: https://www.qedu.org.br/estado/118-tocantins/ideb
2. Download da planilha municipal
3. Salvar: `dados/brutos/qedu-ideb-2023-to.xlsx`

**Script de Automação:**
```python
# scripts/carregar_ideb_inep.py
import pandas as pd

# Ler arquivo INEP ou QEdu
df_ideb = pd.read_excel('dados/brutos/qedu-ideb-2023-to.xlsx')

# Extrair Anos Iniciais e Finais 2023 e 2021
df_ideb_limpo = df_ideb[['cod_municipio',
                          'ideb_ai_2023', 'ideb_af_2023',
                          'ideb_ai_2021', 'ideb_af_2021']].copy()

df_ideb_limpo.columns = ['terr_codigo_ibge',
                          'educ_ideb_anos_iniciais_2023',
                          'educ_ideb_anos_finais_2023',
                          'educ_ideb_anos_iniciais_2021',
                          'educ_ideb_anos_finais_2021']

# Integrar
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
df_base = df_base.merge(df_ideb_limpo, on='terr_codigo_ibge', how='left')

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 45 min manual + 90 min script = 135 min

---

#### PASSO 3.2: Saneamento Básico (SNIS)

**Download Manual:**
1. Acessar: http://appsnis.mdr.gov.br/indicadores/web/agua_esgoto/mapa-esgotamento
2. Filtrar: Tocantins, Ano 2022
3. Baixar arquivo Excel ou CSV
4. Salvar: `dados/brutos/snis-agua-esgoto-to-2022.xlsx`

**Indicadores SNIS Relevantes:**
- IN055: Índice de atendimento total de água
- IN056: Índice de atendimento total de esgoto
- IN046: Índice de tratamento de esgoto
- IN014: Índice de coleta de resíduos

**Script de Automação:**
```python
# scripts/carregar_snis_saneamento.py
import pandas as pd

df_snis = pd.read_excel('dados/brutos/snis-agua-esgoto-to-2022.xlsx')

# Mapear indicadores SNIS para colunas
mapa = {
    'IN055': 'sanea_agua_adequada_pct',
    'IN056': 'sanea_esgoto_adequado_pct',
    'IN046': 'sanea_trat_esgoto_pct'
}

df_snis_limpo = df_snis[['cod_municipio'] + list(mapa.keys())].copy()
df_snis_limpo.columns = ['terr_codigo_ibge'] + list(mapa.values())

# Integrar
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
df_base = df_base.merge(df_snis_limpo, on='terr_codigo_ibge', how='left')

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**IMPORTANTE:** Nem todos os municípios reportam ao SNIS. Municípios faltantes podem ter dados no Censo 2022 (quando disponível).

**Tempo estimado:** 60 min manual + 120 min script = 180 min

---

#### PASSO 3.3: Mortalidade Infantil (DATASUS TabNet)

**Download Manual:**
1. Acessar: http://tabnet.datasus.gov.br/cgi/deftohtm.exe?sim/cnv/inf10uf.def
2. Configurar:
   - **Linha:** Município
   - **Coluna:** Não ativa
   - **Conteúdo:** Óbitos
   - **Períodos:** 2023
   - **Município:** Tocantins (todos)
3. Copiar tabela
4. Repetir para Nascidos Vivos: http://tabnet.datasus.gov.br/cgi/deftohtm.exe?sinasc/cnv/nvuf.def
5. Salvar ambas em: `dados/brutos/datasus-mortalidade-infantil-to-2023.xlsx`

**Script de Automação:**
```python
# scripts/carregar_mortalidade_infantil.py
import pandas as pd

# Carregar óbitos e nascidos vivos
df_obitos = pd.read_excel('dados/brutos/datasus-mortalidade-infantil-to-2023.xlsx',
                          sheet_name='obitos_menores_1ano')
df_nascidos = pd.read_excel('dados/brutos/datasus-mortalidade-infantil-to-2023.xlsx',
                            sheet_name='nascidos_vivos')

# Calcular taxa de mortalidade infantil (por mil nascidos vivos)
df_mort = df_obitos.merge(df_nascidos, on='cod_municipio')
df_mort['saude_mort_inf_por_mil'] = (df_mort['obitos'] / df_mort['nascidos_vivos']) * 1000

df_mort_limpo = df_mort[['cod_municipio', 'saude_mort_inf_por_mil']].copy()
df_mort_limpo.columns = ['terr_codigo_ibge', 'saude_mort_inf_por_mil']

# Integrar
df_base = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')
df_base = df_base.merge(df_mort_limpo, on='terr_codigo_ibge', how='left', suffixes=('', '_novo'))
df_base['saude_mort_inf_por_mil'] = df_base['saude_mort_inf_por_mil'].fillna(
    df_base['saude_mort_inf_por_mil_novo'])

df_base.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)
```

**Tempo estimado:** 90 min manual + 120 min script = 210 min

---

### 5.5 FASE 4: Validação e Cálculo de Consolidações

#### PASSO 4.1: Script de Validação

```python
# scripts/validar_dados.py
import pandas as pd
import numpy as np

df = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')

print("=== VALIDAÇÃO DE INTEGRIDADE ===\n")

# 1. Verificar códigos IBGE (7 dígitos, começam com 17)
codigos_invalidos = df[~df['terr_codigo_ibge'].astype(str).str.match(r'^17\d{5}$')]['terr_nome']
if len(codigos_invalidos) > 0:
    print(f"⚠️ Códigos IBGE inválidos: {list(codigos_invalidos)}")
else:
    print("✅ Todos os códigos IBGE válidos")

# 2. Verificar percentuais (0-100)
colunas_perc = [c for c in df.columns if '_pct' in c or '_perc' in c]
for col in colunas_perc:
    invalidos = df[(df[col] < 0) | (df[col] > 100)][col].dropna()
    if len(invalidos) > 0:
        print(f"⚠️ {col}: {len(invalidos)} valores fora de 0-100%")
    else:
        print(f"✅ {col}: percentuais válidos")

# 3. Verificar consistência de VAB
df['vab_total'] = df['econ_vab_agro_mil_reais'] + df['econ_vab_ind_mil_reais'] + df['econ_vab_serv_mil_reais']
df['diferenca_pib_vab'] = abs(df['econ_pib_total_mil_reais'] - df['vab_total'])
problemas = df[df['diferenca_pib_vab'] > df['econ_pib_total_mil_reais'] * 0.1]  # >10% diferença
if len(problemas) > 0:
    print(f"⚠️ Inconsistência PIB/VAB em {len(problemas)} municípios")
else:
    print("✅ PIB e VAB consistentes")

# 4. Verificar densidade demográfica
df['dens_calculada'] = df['demo_pop_2022'] / df['terr_area_km2']
df['diferenca_dens'] = abs(df['demo_dens_dem_hab_km2'] - df['dens_calculada'])
problemas_dens = df[df['diferenca_dens'] > 0.1]
if len(problemas_dens) > 0:
    print(f"⚠️ Densidade mal calculada em {len(problemas_dens)} municípios")
else:
    print("✅ Densidade demográfica correta")

# 5. Relatório de cobertura
print("\n=== RELATÓRIO DE COBERTURA ===\n")
for col in df.columns:
    if col.startswith(('demo_', 'econ_', 'idh_', 'educ_', 'saude_', 'sanea_', 'agro_')):
        total = len(df)
        preenchidos = df[col].notna().sum()
        pct = (preenchidos / total) * 100
        print(f"{col}: {preenchidos}/{total} ({pct:.1f}%)")
```

**Tempo estimado:** 90 min desenvolvimento + 30 min execução/correções = 120 min

---

#### PASSO 4.2: Cálculo de Consolidações

```python
# scripts/calcular_consolidacoes.py
import pandas as pd
import numpy as np

df = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')

# Identificar municípios (não consolidados)
df_municipios = df[~df['terr_nome'].str.contains('[CONSOLIDADO]', na=False)]

# Função para agregar por território
def consolidar(df_mun, nome_territorio, tipo):
    """
    tipo: 'microrregiao', 'mesorregiao', ou 'estado'
    """
    consolidado = {}
    consolidado['terr_nome'] = f'[CONSOLIDADO] {nome_territorio}'
    consolidado['terr_codigo_ibge'] = np.nan
    consolidado['terr_uf'] = 'TO'

    if tipo == 'microrregiao':
        consolidado['terr_mesorregiao'] = df_mun['terr_mesorregiao'].iloc[0]
        consolidado['terr_microrregiao'] = nome_territorio
    elif tipo == 'mesorregiao':
        consolidado['terr_mesorregiao'] = nome_territorio
        consolidado['terr_microrregiao'] = np.nan
    else:  # estado
        consolidado['terr_mesorregiao'] = np.nan
        consolidado['terr_microrregiao'] = np.nan

    # SOMAS DIRETAS
    colunas_soma = [
        'terr_area_km2',
        'demo_pop_2010', 'demo_pop_2022', 'demo_pop_2025_est',
        'econ_pib_total_mil_reais',
        'econ_vab_agro_mil_reais', 'econ_vab_ind_mil_reais', 'econ_vab_serv_mil_reais',
        'agro_area_plantada_ha', 'agro_rebanho_bovino_cabecas',
        'agro_prod_soja_ton', 'agro_prod_milho_ton', 'agro_prod_arroz_ton'
    ]
    for col in colunas_soma:
        consolidado[col] = df_mun[col].sum()

    # MÉDIAS PONDERADAS POR POPULAÇÃO
    consolidado['econ_pib_per_capita_reais'] = (
        consolidado['econ_pib_total_mil_reais'] * 1000 / consolidado['demo_pop_2022']
    )

    consolidado['demo_dens_dem_hab_km2'] = (
        consolidado['demo_pop_2022'] / consolidado['terr_area_km2']
    )

    consolidado['demo_cresc_2010_2022_pct'] = (
        (consolidado['demo_pop_2022'] - consolidado['demo_pop_2010']) /
        consolidado['demo_pop_2010'] * 100
    )

    # Indicadores NÃO AGREGÁVEIS (deixar vazio)
    nao_agregaveis = [
        'idh_idhm_2010', 'idh_idhm_renda_2010', 'idh_idhm_long_2010', 'idh_idhm_educ_2010',
        'educ_ideb_anos_iniciais_2023', 'educ_ideb_anos_finais_2023',
        'educ_ideb_anos_iniciais_2021', 'educ_ideb_anos_finais_2021'
    ]
    for col in nao_agregaveis:
        consolidado[col] = np.nan

    # MÉDIAS PONDERADAS para outros indicadores
    # (requer dados de ponderação específicos - implementar quando necessário)

    return consolidado

# Calcular consolidações
consolidacoes = []

# 1. Microrregiões
for microregiao in df_municipios['terr_microrregiao'].unique():
    df_micro = df_municipios[df_municipios['terr_microrregiao'] == microregiao]
    consolidacoes.append(consolidar(df_micro, microregiao, 'microrregiao'))

# 2. Mesorregiões
for mesorregiao in df_municipios['terr_mesorregiao'].unique():
    df_meso = df_municipios[df_municipios['terr_mesorregiao'] == mesorregiao]
    consolidacoes.append(consolidar(df_meso, mesorregiao, 'mesorregiao'))

# 3. Estado
consolidacoes.append(consolidar(df_municipios, 'Tocantins', 'estado'))

# Criar DataFrame de consolidações
df_consol = pd.DataFrame(consolidacoes)

# Concatenar municípios + consolidações
df_final = pd.concat([df_municipios, df_consol], ignore_index=True)

# Ordenar: mesorregião > microrregião > município (alfabético)
df_final = df_final.sort_values([
    'terr_mesorregiao',
    'terr_microrregiao',
    'terr_nome'
])

df_final.to_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv', index=False)

print("✅ Consolidações calculadas e adicionadas!")
print(f"Total de linhas: {len(df_final)} (139 municípios + {len(consolidacoes)} consolidações)")
```

**Tempo estimado:** 180 min desenvolvimento + 30 min validação = 210 min

---

### 5.6 Resumo de Esforço por Fase

| Fase | Atividade | Tempo Manual | Tempo Scripts | Total |
|------|-----------|--------------|---------------|-------|
| **1** | Área, IDHM, Escolarização | 65 min | 135 min | 200 min (~3.5h) |
| **2** | PIB/VAB, PAM, PPM | 75 min | 225 min | 300 min (~5h) |
| **3** | IDEB, SNIS, DATASUS | 195 min | 330 min | 525 min (~8.7h) |
| **4** | Validação + Consolidações | 30 min | 330 min | 360 min (~6h) |
| **TOTAL** | | **6h** | **17h** | **23h** |

**Com 4h/dia:** 6 dias úteis
**Com 6h/dia:** 4 dias úteis

---

## 6. RECOMENDAÇÕES FINAIS

### 6.1 Para a Coleta Imediata (V02)

1. ✅ **Priorizar GRUPO A (dados fáceis)**
   - 1 dia de trabalho concentrado
   - Alta taxa de sucesso
   - Preenche 11 indicadores

2. ✅ **Atacar IDEB logo em seguida (GRUPO C)**
   - Prioridade máxima definida
   - Interface QEdu é amigável
   - 1-2 dias de trabalho

3. ✅ **Paralelizar coletas do GRUPO B**
   - SIDRA permite múltiplas tabelas abertas
   - Downloads podem ser feitos em sequência rápida
   - Processamento pode ser em lote

4. ⚠️ **Deixar SNIS e DATASUS para o final do GRUPO C**
   - Interfaces mais complexas
   - Possíveis lacunas de dados
   - Exigem paciência

---

### 6.2 Para os Scripts de Automação

1. ✅ **Criar biblioteca de funções reutilizáveis**
```python
# scripts/lib/transformacoes.py

def ler_sidra_csv(caminho, mapa_colunas):
    """Lê CSV do SIDRA e renomeia colunas"""
    pass

def integrar_com_base(df_novo, coluna_chave='terr_codigo_ibge'):
    """Integra novos dados com base consolidada"""
    pass

def validar_percentuais(df, colunas_perc):
    """Valida se percentuais estão entre 0-100"""
    pass
```

2. ✅ **Manter logs de transformação**
   - Quantos municípios foram atualizados
   - Quais dados eram novos vs sobrescritos
   - Anomalias detectadas

3. ✅ **Criar notebook Jupyter para exploração**
   - Permite visualizar dados antes de integrar
   - Facilita debug
   - Documenta processo visualmente

---

### 6.3 Para Qualidade dos Dados

1. ✅ **Estabelecer regra de atualização**
   - Nunca sobrescrever dados existentes sem validação
   - Manter versões anteriores (V01, V02, etc.)
   - Documentar todas as mudanças no CHANGELOG

2. ✅ **Criar relatório de mudanças entre versões**
```python
# scripts/comparar_versoes.py
df_v01 = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V01.csv')
df_v02 = pd.read_csv('dados/finais/BASE_DADOS_TOCANTINS_V02.csv')

# Identificar células que mudaram
# Identificar cobertura nova
# Gerar relatório markdown
```

3. ✅ **Atualizar metadados automaticamente**
   - Quando novo dado é adicionado, atualizar data_coleta
   - Registrar método usado
   - Manter histórico de fontes

---

### 6.4 Decisão Estratégica: Adicionar 4 Colunas na V02?

#### Proposta: V02 com 41 Colunas

**Adicionar:**
1. `edu_analfab_15mais_pct` - Taxa de Analfabetismo 15+ anos
2. `saude_cobert_esf_perc` - Cobertura ESF
3. `edu_ideb_ai_2021` - IDEB Anos Iniciais 2021
4. `edu_ideb_af_2021` - IDEB Anos Finais 2021

**Justificativa:**
- Esforço adicional é baixo (2-3 horas totais)
- Relevância política e analítica alta
- Aproveitamento de dados já disponíveis
- Séries temporais enriquecem análise

**Contra:**
- Aumenta complexidade ligeiramente
- Pode atrasar entrega da V02

**RECOMENDAÇÃO:** ✅ **SIM, adicionar na V02**
- Dados estão facilmente disponíveis
- Benefício analítico supera custo marginal
- Estabelece precedente de séries temporais

---

## 7. CONCLUSÃO E PRÓXIMOS PASSOS

### 7.1 Reavaliação das Decisões Originais

#### Decisão 1: Planejamento Detalhado

**Veredicto Final:** ✅ **DECISÃO CORRETA E VALIDADA**

O documento de planejamento com 52 colunas foi essencial para:
- Estabelecer visão compreensiva do projeto
- Criar referência para decisões posteriores
- Documentar todas as possibilidades
- Permitir simplificações **informadas**

A simplificação para 37 colunas só foi possível porque havia um plano detalhado como base. **Planejamento não foi desperdiçado, foi filtro de qualidade.**

---

#### Decisão 2: Celebrar Simplificações

**Veredicto Final:** ✅ **DECISÃO CORRETA, MAS REVISÁVEL**

As simplificações foram majoritariamente excelentes:
- Eliminação de redundâncias (anos de referência)
- Melhorias conceituais (VAB absoluto, IDHM desdobrado)
- Foco em dados quantitativos (soja/milho/arroz específicos)

**PORÉM**, algumas exclusões merecem reconsideração:
- **IDEB 2021** - Reincluir para análise temporal
- **Analfabetismo e ESF** - Relevância política alta
- **Turismo** - Manter exclusão, criar planilha complementar futura

**Aprendizado:** Simplificação é iterativa. V01 estabeleceu base sólida. V02 pode refinar com adições cirúrgicas.

---

### 7.2 Plano de Ação Imediato

#### SEMANA 1: Grupo A (Dados Fáceis)
- [ ] Dia 1: Área territorial + População faltante
- [ ] Dia 2: IDHM completo (Atlas Brasil)
- [ ] Dia 3: Taxas de escolarização + Urbanização

#### SEMANA 2: IDEB e Grupo B
- [ ] Dia 4: IDEB 2023 e 2021 (QEdu/INEP)
- [ ] Dia 5: PIB e VAB (SIDRA 5938)
- [ ] Dia 6: PAM - Produção Agrícola (SIDRA 5457)
- [ ] Dia 7: PPM - Pecuária (SIDRA 3939)

#### SEMANA 3: Grupo C e Validação
- [ ] Dia 8: SNIS - Saneamento
- [ ] Dia 9: DATASUS - Mortalidade Infantil
- [ ] Dia 10: Validação completa + Correções
- [ ] Dia 11: Cálculo de consolidações
- [ ] Dia 12: Testes finais + Documentação

**Meta:** V02 com 85% de cobertura em 3 semanas (12 dias úteis)

---

### 7.3 Mensagem Final

Este projeto é um exemplo de **colaboração IA-Humano bem-sucedida**:

1. **IA trouxe:** Estrutura abrangente, sistematização, automação
2. **Humano trouxe:** Julgamento pragmático, simplificação elegante, priorização
3. **Resultado:** Sistema de inteligência territorial robusto e escalável

As decisões documentadas no Diário de Pesquisa-Ação não foram apenas corretas — foram **essenciais**. O planejamento detalhado criou a fundação. As simplificações criaram a elegância. Agora, a revisão informada criará a **completude**.

**A jornada continua. V02 será ainda melhor que V01 porque aprendemos com ambas as decisões: planejar profundamente E simplificar pragmaticamente.**

---

**Elaborado em:** 25 de janeiro de 2026
**Por:** Sistema de Inteligência Territorial - Caderno Tocantins 2026
**Status:** Relatório Completo - Pronto para Decisões Estratégicas

---

## ANEXO: Tabela Comparativa Completa

| # | Código Planejado (52) | Código Executado (37) | Status | Observação |
|---|-----------------------|------------------------|--------|------------|
| 1 | territorio_nome | terr_nome | ✅ Mantido | Prefixo simplificado |
| 2 | territorio_cod_ibge | terr_codigo_ibge | ✅ Mantido | Prefixo simplificado |
| 3 | territorio_uf | terr_uf | ✅ Mantido | Prefixo simplificado |
| 4 | territorio_mesorregiao | terr_mesorregiao | ✅ Mantido | Prefixo simplificado |
| 5 | territorio_microrregiao | terr_microrregiao | ✅ Mantido | Prefixo simplificado |
| 6 | territorio_tipo | - | ❌ Removido | Substituído por prefixo [CONSOLIDADO] |
| 7 | demo_area_km2 | terr_area_km2 | ✅ Mantido | Movido para dimensão territorial |
| 8 | demo_pop_2010 | demo_pop_2010 | ✅ Mantido | |
| 9 | demo_pop_2022 | demo_pop_2022 | ✅ Mantido | |
| 10 | demo_pop_2025_est | demo_pop_2025_est | ✅ Mantido | |
| 11 | demo_cresc_2010_2022_perc | demo_cresc_2010_2022_pct | ✅ Mantido | Sufixo _perc → _pct |
| 12 | demo_densidade | demo_dens_dem_hab_km2 | ✅ Mantido | Nome mais descritivo |
| 13 | demo_urbanizacao_perc | demo_tx_urban_pct | ✅ Mantido | Nome mais conciso |
| 14 | econ_pib_total_milhoes | econ_pib_total_mil_reais | ✅ Mantido | Unidade explícita |
| 15 | econ_pib_pc | econ_pib_per_capita_reais | ✅ Mantido | Nome mais explícito |
| 16 | econ_pib_ano_ref | - | ❌ Removido | Movido para metadados |
| 17 | econ_vab_agro_perc | econ_vab_agro_mil_reais | ✅ Modificado | Percentual → Absoluto |
| 18 | econ_vab_ind_perc | econ_vab_ind_mil_reais | ✅ Modificado | Percentual → Absoluto |
| 19 | econ_vab_serv_perc | econ_vab_serv_mil_reais | ✅ Modificado | Percentual → Absoluto |
| 20 | desenv_idhm | idh_idhm_2010 | ✅ Mantido | Ano explícito, prefixo idh_ |
| 21 | desenv_idhm_ano_ref | - | ❌ Removido | Ano no nome da coluna |
| 22 | - | idh_idhm_renda_2010 | ✅ Adicionado | Desdobramento IDHM |
| 23 | - | idh_idhm_long_2010 | ✅ Adicionado | Desdobramento IDHM |
| 24 | - | idh_idhm_educ_2010 | ✅ Adicionado | Desdobramento IDHM |
| 25 | edu_escol_6_14_perc | educ_tx_escolar_6_14_pct | ✅ Mantido | Prefixo educ_, sufixo _pct |
| 26 | - | educ_tx_escolar_15_17_pct | ✅ Adicionado | Ensino médio |
| 27 | edu_ideb_ai_2023 | educ_ideb_anos_iniciais_2023 | ✅ Mantido | Nome mais explícito |
| 28 | edu_ideb_af_2023 | educ_ideb_anos_finais_2023 | ✅ Mantido | Nome mais explícito |
| 29 | edu_ideb_ai_2021 | - | ❌ Removido | ⚠️ Reconsiderar reinclusão |
| 30 | edu_ideb_af_2021 | - | ❌ Removido | ⚠️ Reconsiderar reinclusão |
| 31 | edu_analfab_15mais_perc | - | ❌ Removido | ⚠️ Reconsiderar reinclusão |
| 32 | saude_mort_inf | saude_mort_inf_por_mil | ✅ Mantido | Unidade explícita |
| 33 | saude_mort_inf_ano_ref | - | ❌ Removido | Movido para metadados |
| 34 | - | saude_expect_vida_anos | ✅ Adicionado | Complementa IDHM Longevidade |
| 35 | saude_cobert_esf_perc | - | ❌ Removido | ⚠️ Reconsiderar reinclusão |
| 36 | saude_leitos_1000hab | - | ❌ Removido | ⚠️ Considerar reinclusão V03 |
| 37 | saude_medicos_1000hab | - | ❌ Removido | ⚠️ Considerar reinclusão V03 |
| 38 | san_agua_perc | sanea_agua_adequada_pct | ✅ Mantido | Nome mais descritivo |
| 39 | san_esgoto_coleta_perc | sanea_esgoto_adequado_pct | ✅ Mantido | Nome mais descritivo |
| 40 | san_esgoto_trat_perc | sanea_trat_esgoto_pct | ✅ Mantido | |
| 41 | san_residuos_coleta_perc | sanea_coleta_lixo_pct | ✅ Mantido | Nome mais comum |
| 42 | san_ano_ref | - | ❌ Removido | Movido para metadados |
| 43 | san_fonte | - | ❌ Removido | Movido para metadados |
| 44 | agro_vbp_milhoes | agro_vbp_total_mil_reais | ✅ Mantido | Unidade explícita |
| 45 | agro_vbp_ano_ref | - | ❌ Removido | Movido para metadados |
| 46 | agro_area_plantada_ha | agro_area_plantada_ha | ✅ Mantido | |
| 47 | agro_rebanho_bovino | agro_rebanho_bovino_cabecas | ✅ Mantido | Unidade explícita |
| 48 | agro_cultura_princ_1 | agro_prod_soja_ton | ✅ Modificado | Genérico → Específico |
| 49 | agro_cultura_princ_2 | agro_prod_milho_ton | ✅ Modificado | Genérico → Específico |
| 50 | agro_cultura_princ_3 | agro_prod_arroz_ton | ✅ Modificado | Genérico → Específico |
| 51 | agro_prod_1_ton | - | ❌ Removido | Substituído por soja/milho/arroz |
| 52 | agro_prod_2_ton | - | ❌ Removido | Substituído por soja/milho/arroz |
| 53 | tur_visitantes_ano | - | ❌ Removido | Dimensão completa removida |
| 54 | tur_receita_milhoes | - | ❌ Removido | Dimensão completa removida |
| 55 | tur_atrativos | - | ❌ Removido | Dimensão completa removida |
| 56 | tur_ano_ref | - | ❌ Removido | Dimensão completa removida |
| 57 | obs | - | ❌ Removido | Observações em documentação separada |

**TOTAIS:**
- Planejado: 52 colunas
- Executado: 37 colunas
- Mantidas com alteração mínima: 28
- Adicionadas: 4 (IDHM desdobrado + escolarização 15-17 + expectativa vida)
- Removidas: 19
- Modificadas conceitualmente: 6 (VAB, culturas, mortalidade)
