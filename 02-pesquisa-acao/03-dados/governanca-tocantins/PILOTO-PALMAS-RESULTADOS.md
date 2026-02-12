# Relatório do Teste Piloto - Palmas (TO)

**Data:** 07/01/2026
**Município:** Palmas (IBGE: 1721000)
**Período de Análise:** 2019-2023

---

## 1. Resumo Executivo

| Métrica | Valor |
|---------|-------|
| Total de registros coletados | 89 |
| Dados oficiais | 44 (49.4%) |
| Dados estimados | 45 (50.6%) |
| Coletores executados | 8 |
| Coletores com sucesso | 6 (75%) |
| Coletores com falha (rede) | 2 (25%) |
| Tempo de execução | 132.28 segundos |

---

## 2. Análise Crítica: Qualidade dos Dados

### 2.1 Problema Identificado

**O MVP exige que 100% dos dados sejam:**
- Obtidos diretamente de fontes oficiais, OU
- Calculados a partir de dados oficiais usando metodologia validada (acadêmica ou institucional) com citação da referência

**Situação Atual:** 50.6% dos dados são classificados como "estimados", o que não atende ao requisito de qualidade do MVP.

### 2.2 Classificação dos Dados por Origem

#### DADOS OFICIAIS (49.4% - 44 registros)

| Indicador | Fonte Oficial | Status |
|-----------|---------------|--------|
| IDEB_ANOS_INICIAIS | INEP/MEC | Oficial |
| IDEB_ANOS_FINAIS | INEP/MEC | Oficial |
| IDEB_FUNDAMENTAL | INEP/MEC | Oficial |
| MORTALIDADE_INFANTIL | DataSUS/SIM/SINASC | Oficial |
| COBERTURA_ESF | DataSUS/e-Gestor AB | Oficial |
| COBERTURA_AGUA (2020-2022) | SNIS/MDR | Oficial |
| COBERTURA_ESGOTO (2020-2022) | SNIS/MDR | Oficial |

#### DADOS ESTIMADOS (50.6% - 45 registros) - REQUER AÇÃO

| Indicador | Fonte Atual | Problema | Ação Necessária |
|-----------|-------------|----------|-----------------|
| VEGETACAO_NATIVA_PCT | MapBiomas | Estimativa regional | Acessar API oficial MapBiomas |
| AGRICULTURA_HA | MapBiomas | Estimativa regional | Acessar API oficial MapBiomas |
| PASTAGEM_HA | MapBiomas | Estimativa regional | Acessar API oficial MapBiomas |
| IDH | Atlas Brasil | Projeção pós-2010 | Usar IDHM 2010 + metodologia PNUD |
| EXPORTACOES_FOB_USD | Comex Stat | Estimativa regional | Acessar API Comex Stat oficial |
| IMPORTACOES_FOB_USD | Comex Stat | Estimativa regional | Acessar API Comex Stat oficial |
| BALANCA_COMERCIAL_USD | Comex Stat | Cálculo de estimativas | Derivar de dados oficiais |
| COBERTURA_AGUA (2019, 2023) | SNIS | Projeção linear | Usar interpolação/extrapolação documentada |
| COBERTURA_ESGOTO (2019, 2023) | SNIS | Projeção linear | Usar interpolação/extrapolação documentada |

#### DADOS NÃO COLETADOS (APIs com falha de rede)

| Indicador | Fonte | Problema | Impacto |
|-----------|-------|----------|---------|
| PIB_PERCAPITA | IBGE Sidra | Falha de conectividade | Dado crítico ECON |
| POPULACAO | IBGE Sidra | Falha de conectividade | Dado crítico base |
| RECEITA_CORRENTE_LIQUIDA | SICONFI/Tesouro | Falha de conectividade | Dado crítico ECON |
| RECEITA_TRIBUTARIA | SICONFI/Tesouro | Falha de conectividade | Dado crítico ECON |
| DESPESA_EDUCACAO | SICONFI/Tesouro | Falha de conectividade | Dado crítico SOCIAL |
| DESPESA_SAUDE | SICONFI/Tesouro | Falha de conectividade | Dado crítico SOCIAL |

---

## 3. Plano de Ação para 100% Dados Oficiais

### 3.1 Fontes Oficiais Disponíveis

| Indicador | Fonte Oficial | API/Acesso | Granularidade |
|-----------|---------------|------------|---------------|
| Uso do Solo | MapBiomas | https://brasil.mapbiomas.org/estatisticas/ | Municipal |
| IDH | Atlas Brasil (PNUD/IPEA/FJP) | https://www.atlasbrasil.org.br/ranking | Municipal (Censo) |
| Comércio Exterior | Comex Stat/MDIC | http://comexstat.mdic.gov.br/pt/geral | Municipal |
| PIB | IBGE Sidra | https://sidra.ibge.gov.br/tabela/5938 | Municipal |
| População | IBGE | https://sidra.ibge.gov.br/tabela/6579 | Municipal |
| Finanças Públicas | SICONFI/STN | https://siconfi.tesouro.gov.br/siconfi/ | Municipal |

### 3.2 Metodologia para Dados Derivados

Quando não houver dado oficial disponível para um ano específico, usar **APENAS** as seguintes abordagens com citação obrigatória:

#### A) Interpolação Linear (para anos intermediários)

```
Valor(ano) = Valor(ano_anterior) + (Valor(ano_posterior) - Valor(ano_anterior)) × (ano - ano_anterior) / (ano_posterior - ano_anterior)
```

**Referência:** IBGE. Metodologia do Censo Demográfico 2022. Rio de Janeiro: IBGE, 2023.

#### B) Extrapolação (para anos recentes sem dados)

Não permitida no MVP. Usar apenas dados oficiais publicados.

#### C) Desagregação Proporcional (estadual → municipal)

```
Valor_municipal = Valor_estadual × (Participação_municipal_ano_base)
```

**Referência:** IBGE. Produto Interno Bruto dos Municípios - Metodologia. Série Relatórios Metodológicos, v. 29. Rio de Janeiro: IBGE, 2015.

**Condição:** Apenas quando a fonte oficial fornece dados estaduais e existe proporção municipal validada em ano-base oficial.

### 3.3 Ações Imediatas por Coletor

| Coletor | Ação | Prioridade |
|---------|------|------------|
| MapBiomasCollector | Implementar acesso direto à API/download oficial | ALTA |
| AtlasBrasilCollector | Usar apenas IDHM 2010 oficial, não projetar | ALTA |
| ComexStatCollector | Implementar API oficial do MDIC | ALTA |
| IBGESidraCollector | Corrigir conectividade (testar em prod) | CRÍTICA |
| SICONFICollector | Corrigir conectividade (testar em prod) | CRÍTICA |
| SNISCollector | Remover projeções, usar apenas anos oficiais | MÉDIA |

---

## 4. Resultados Detalhados por Dimensão

### 4.1 Dimensão ECON (Econômica)

| Indicador | 2019 | 2020 | 2021 | 2022 | 2023 | Qualidade | Fonte |
|-----------|------|------|------|------|------|-----------|-------|
| EXPORTACOES_FOB_USD | 155M | 170M | 210M | 240M | 225M | Estimado | Comex Stat |
| IMPORTACOES_FOB_USD | 4.65M | 4.5M | 5.25M | 6.3M | 6M | Estimado | Comex Stat |
| BALANCA_COMERCIAL_USD | 150.35M | 165.5M | 204.75M | 233.7M | 219M | Estimado | Comex Stat |

**Problema:** Valores calculados por distribuição proporcional regional sem metodologia oficial.

**Solução:** Acessar dados municipais diretamente via API Comex Stat:
- Endpoint: `http://comexstat.mdic.gov.br/pt/municipio`
- Filtro: Código IBGE do município

### 4.2 Dimensão SOCIAL

| Indicador | 2019 | 2020 | 2021 | 2022 | 2023 | Qualidade | Fonte |
|-----------|------|------|------|------|------|-----------|-------|
| IDH | 0.824 | 0.792 | 0.792 | 0.792 | 0.792 | Estimado | Atlas Brasil |
| IDEB_ANOS_INICIAIS | 5.9 | - | 6.0 | - | 6.1 | **Oficial** | INEP |
| IDEB_ANOS_FINAIS | 5.1 | - | 5.2 | - | 5.4 | **Oficial** | INEP |
| IDEB_FUNDAMENTAL | 5.5 | - | 5.6 | - | 5.8 | **Oficial** | INEP |
| MORTALIDADE_INFANTIL | 10.8 | 11.2 | 11.0 | 10.9 | 10.7 | **Oficial** | DataSUS |
| COBERTURA_ESF | - | - | - | 78.5 | 80.2 | **Oficial** | DataSUS |
| COBERTURA_AGUA | 94.8* | 98.5 | 98.8 | 99.1 | 100* | Misto | SNIS |
| COBERTURA_ESGOTO | 72.9* | 72.5 | 75.2 | 78.5 | 80.5* | Misto | SNIS |

*Valores projetados - não devem ser usados no MVP*

**Problema IDH:** O IDHM é calculado apenas nos anos de Censo (2000, 2010, 2022). Valores intermediários são projeções.

**Solução IDH:**
- Usar IDHM 2010 = 0.788 (oficial) para análises até 2021
- Aguardar publicação do IDHM 2022 pelo Atlas Brasil (previsão: 2024-2025)
- **Referência:** PNUD; IPEA; FJP. Atlas do Desenvolvimento Humano no Brasil. Metodologia. 2013.

### 4.3 Dimensão AMBIENT (Ambiental)

| Indicador | 2019 | 2020 | 2021 | 2022 | Qualidade | Fonte |
|-----------|------|------|------|------|-----------|-------|
| VEGETACAO_NATIVA_PCT | 66.4% | 66.0% | 65.0% | 65.0% | Estimado | MapBiomas |
| AGRICULTURA_HA | 18.801 | 19.024 | 19.584 | 19.584 | Estimado | MapBiomas |
| PASTAGEM_HA | 52.642 | 53.268 | 54.835 | 54.835 | Estimado | MapBiomas |

**Problema:** Dados calculados por estimativa regional, não extraídos diretamente da plataforma.

**Solução:**
- Download direto da estatística municipal: https://brasil.mapbiomas.org/estatisticas/
- Arquivo disponível: "Estatísticas da Coleção 8 por Município"
- **Referência:** MapBiomas. Coleção 8 da Série Anual de Mapas de Cobertura e Uso da Terra do Brasil. 2023.

### 4.4 Dimensão TERRA (Territorial)

**Status:** Não implementado no piloto.

**Indicadores Planejados:**
| Indicador | Fonte Oficial | Disponibilidade |
|-----------|---------------|-----------------|
| DESMATAMENTO_KM2 | PRODES/INPE | Anual, municipal |
| FOCOS_CALOR | BDQueimadas/INPE | Diário, municipal |
| AREA_PROTEGIDA_PCT | CNUC/MMA | Atualização contínua |

---

## 5. Critérios de Aceite para o MVP

Para que um indicador seja incluído no MVP, deve atender a **TODOS** os critérios:

| Critério | Requisito | Verificação |
|----------|-----------|-------------|
| **Origem** | Fonte oficial governamental ou institucional reconhecida | URL da fonte |
| **Metodologia** | Documentada publicamente | Citação bibliográfica |
| **Granularidade** | Disponível em nível municipal | Código IBGE 7 dígitos |
| **Atualidade** | Dados de 2019 ou posterior | Ano de referência |
| **Reprodutibilidade** | Coleta automatizável e verificável | Script de coleta |

### 5.1 Checklist de Qualidade por Indicador

```
[ ] Fonte oficial identificada e acessível
[ ] Metodologia de cálculo documentada
[ ] Citação bibliográfica incluída
[ ] Dado bruto armazenado para auditoria
[ ] Script de coleta versionado
[ ] Teste de validação implementado
```

---

## 6. Referências Bibliográficas

### Fontes de Dados Oficiais

1. **IBGE - Instituto Brasileiro de Geografia e Estatística**
   - Sistema IBGE de Recuperação Automática (SIDRA)
   - https://sidra.ibge.gov.br/
   - Acesso em: 07/01/2026

2. **INEP - Instituto Nacional de Estudos e Pesquisas Educacionais**
   - Índice de Desenvolvimento da Educação Básica (IDEB)
   - https://www.gov.br/inep/pt-br/areas-de-atuacao/pesquisas-estatisticas-e-indicadores/ideb
   - Acesso em: 07/01/2026

3. **DataSUS - Departamento de Informática do SUS**
   - Sistema de Informações sobre Mortalidade (SIM)
   - Sistema de Informações sobre Nascidos Vivos (SINASC)
   - http://tabnet.datasus.gov.br/
   - Acesso em: 07/01/2026

4. **SNIS - Sistema Nacional de Informações sobre Saneamento**
   - Série Histórica
   - http://app4.mdr.gov.br/serieHistorica/
   - Acesso em: 07/01/2026

5. **SICONFI - Sistema de Informações Contábeis e Fiscais**
   - Secretaria do Tesouro Nacional
   - https://siconfi.tesouro.gov.br/siconfi/
   - Acesso em: 07/01/2026

6. **MapBiomas**
   - Projeto de Mapeamento Anual do Uso e Cobertura da Terra no Brasil
   - Coleção 8 (1985-2022)
   - https://brasil.mapbiomas.org/
   - Acesso em: 07/01/2026

7. **Atlas do Desenvolvimento Humano no Brasil**
   - PNUD, IPEA, Fundação João Pinheiro
   - https://www.atlasbrasil.org.br/
   - Acesso em: 07/01/2026

8. **Comex Stat**
   - Ministério do Desenvolvimento, Indústria, Comércio e Serviços
   - http://comexstat.mdic.gov.br/
   - Acesso em: 07/01/2026

### Metodologias

9. **IBGE.** Produto Interno Bruto dos Municípios. Série Relatórios Metodológicos, v. 29. Rio de Janeiro: IBGE, 2015.

10. **PNUD; IPEA; FJP.** Atlas do Desenvolvimento Humano no Brasil: Metodologia. Brasília: PNUD, 2013.

11. **MapBiomas.** ATBD - Algorithm Theoretical Basis Document. Collection 8. São Paulo: MapBiomas, 2023.

12. **INEP.** Nota Técnica: Índice de Desenvolvimento da Educação Básica - IDEB. Brasília: INEP, 2021.

---

## 7. Próximos Passos

### Prioridade CRÍTICA (antes do MVP)
1. [ ] Corrigir IBGESidraCollector para obter PIB e População
2. [ ] Corrigir SICONFICollector para obter dados fiscais
3. [ ] Implementar download direto de estatísticas MapBiomas
4. [ ] Remover todas as estimativas sem metodologia oficial

### Prioridade ALTA
5. [ ] Implementar ComexStatCollector com API oficial municipal
6. [ ] Limitar IDH ao valor oficial de 2010 até publicação do IDHM 2022
7. [ ] Remover projeções de saneamento (SNIS) para anos sem dados

### Prioridade MÉDIA
8. [ ] Implementar coletores PRODES e BDQueimadas
9. [ ] Adicionar validação de qualidade em cada coletor
10. [ ] Criar relatório automático de auditoria de dados

---

## 8. Conclusão

O teste piloto identificou que **50.6% dos dados coletados são estimativas** que não atendem aos critérios de qualidade exigidos para o MVP.

**Ação imediata necessária:** Refatorar os coletores para:
1. Acessar apenas fontes oficiais
2. Usar metodologias documentadas para dados derivados
3. Citar referências bibliográficas para cada indicador
4. Não incluir anos sem dados oficiais disponíveis

O sistema está estruturalmente preparado, mas requer ajustes nos coletores antes da coleta completa dos 139 municípios.

---

*Documento gerado em: 07/01/2026*
*Versão: 1.0*
