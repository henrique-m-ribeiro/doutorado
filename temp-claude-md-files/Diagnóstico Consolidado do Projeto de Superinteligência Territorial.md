# Diagnóstico Consolidado do Projeto de Superinteligência Territorial

**Data da Análise:** 14 de fevereiro de 2026
**Foco:** Avaliação das alterações recentes, com ênfase no *pivot* para MVP do dashboard `tocantins-integrado`.

## Sumário Executivo

A análise dos quatro repositórios do projeto confirma a execução bem-sucedida do *pivot* estratégico para a entrega de um MVP (Minimum Viable Product) do dashboard `tocantins-integrado`. A decisão, documentada no **ADR-006**, foi implementada de forma robusta no *branch* `claude/deploy-mvp-dashboard-2XTLh` e integrada à `main`. O dashboard agora opera com uma camada de dados estática, alimentada por um *parser* que consome as fichas municipais do `caderno-tocantins-2026`, tornando-o funcional e independente do *backend* e banco de dados legados para fins de demonstração e uso inicial.

Contudo, a análise revelou **inconsistências documentais** significativas entre os repositórios. A documentação do `tocantins-integrado` e do `doutorado` não reflete o estado atual pós-*pivot*, ainda descrevendo o sistema como "pausado" e o plano do Ciclo 4 como futuro. Essa defasagem representa um risco para a continuidade do projeto e a correta interpretação da pesquisa-ação.

A recomendação central é **sincronizar a documentação** em todos os repositórios para refletir o *pivot* e o novo status ativo do dashboard, além de formalizar o novo plano de trabalho no repositório `doutorado`.

## 1. Análise Técnica do Repositório `tocantins-integrado`

O repositório central da aplicação passou por uma transformação significativa e bem-sucedida. A implementação do MVP foi eficaz e demonstrou alta qualidade técnica.

### 1.1 Implementação do MVP (Commit `05b5673`)

O *commit* que implementou o MVP é extenso e de alta qualidade, alinhado com a descrição fornecida.

- **Parser de Dados (`scripts/parse-caderno.cjs`):** Um *script* Node.js de mais de 1.000 linhas foi criado para extrair dados estruturados das 139 fichas municipais em formato Markdown. O *script* gera um arquivo JSON (`municipalities.json`) de 1.9 MB, que serve como a nova fonte de dados estática.
- **Camada de Dados Estática:** A implementação da camada de dados (`src/dashboard/lib/caderno-data.ts` e `hooks/useCadernoData.ts`) é limpa e eficiente. Ela abstrai o carregamento do JSON e fornece dados tipados aos componentes React, desacoplando a interface da fonte de dados.
- **Reescrita dos Componentes:** As seis *tabs* principais do dashboard foram refatoradas para consumir dados do *hook* `useCadernoData`, substituindo os dados *mock* anteriores. O código dos componentes (`OverviewTab.tsx`, `EconomicTab.tsx`, etc.) está bem estruturado e utiliza os dados reais de forma consistente.
- **Validação da Hipótese H4.4:** A implementação serve como uma validação prática da hipótese de que os dados dos cadernos poderiam alimentar a Camada 1 do sistema com perda mínima. O ADR-006 documenta a alta fidelidade do *parse*.

### 1.2 Estado do Projeto

- **Funcionalidade:** O dashboard é, agora, uma aplicação Next.js funcional que pode ser construída (`npm run build`) e iniciada (`npm run start`) de forma independente. A dependência do Supabase, n8n e do *backend* Express foi removida para o MVP, simplificando drasticamente o *deploy*.
- **Código Legado:** O código original do *backend* (coletores, agentes, API Express, migrações de banco) permanece intacto, mas não é utilizado na configuração atual do MVP. Isso está alinhado com a estratégia do ADR-006, que preserva a arquitetura completa para desenvolvimento futuro.

| Componente | Status Pós-Pivot (MVP) | Observações |
| :--- | :--- | :--- |
| **Frontend (Dashboard)** | **Ativo e Funcional** | Next.js, dados via JSON estático. | 
| **Parser de Cadernos** | **Novo e Crítico** | `scripts/parse-caderno.cjs` é a nova peça central da ingestão de dados. |
| **Backend (API/Agents)** | **Inativo** | Código preservado em `src/api`, `src/agents`, etc. Não é chamado pelo MVP. |
| **Banco de Dados (Supabase)** | **Inativo** | Migrações e cliente SQL preservados, mas não utilizados. |
| **Orquestração (n8n)** | **Inativo** | Workflows preservados, mas não utilizados. |

## 2. Análise de Consistência Documental (Cross-Repositório)

Esta é a área que exige **atenção imediata**. A velocidade da implementação técnica superou a atualização da documentação, criando uma defasagem entre o estado real do projeto e como ele é descrito.

### 2.1 Inconsistências Identificadas

1.  **Status do `tocantins-integrado`:** Tanto o `README.md` quanto o `CLAUDE.md` do repositório ainda o descrevem como **"Pausado (Camada 1: 90% completa)"**. Isso é factualmente incorreto. O sistema está **ativo** e a Camada 1 (MVP) está **100% funcional** com dados reais.
2.  **Plano do Ciclo 4:** O arquivo `CICLO-04-PLANO.md` no repositório `doutorado` **não foi atualizado** para refletir o *pivot*. Ele ainda descreve a retomada do sistema como uma fase futura (4D, Out-Dez 2026), quando na verdade essa fase foi antecipada e executada agora.
3.  **Registro do ADR-006:** O `ADR-006` foi criado corretamente no `tocantins-integrado`, mas **não há referência a ele no repositório `doutorado`**. Documentos centrais como `MAPEAMENTO-CICLOS-EVIDENCIAS.md` e os diários de pesquisa não mencionam esta decisão arquitetural crucial.
4.  **Diário de Pesquisa-Ação:** O diário da sessão que implementou o *pivot* (`2026-02-14-sessao-025.md`) está no repositório `doutorado`, mas foca na criação dos `CLAUDE.md` e na integração do `ia-collab-os`, sem detalhar a implementação técnica do MVP que ocorreu em paralelo. O *commit* no `tocantins-integrado` é a principal fonte de documentação da implementação.

### 2.2 Impacto das Inconsistências

- **Risco à Pesquisa-Ação:** A metodologia de pesquisa-ação depende de um registro fiel e tempestivo das decisões e suas justificativas. A defasagem documental enfraquece a rastreabilidade e a validade das conclusões da pesquisa.
- **Confusão para Colaboradores (Humanos e IA):** Qualquer agente (ou pessoa) que consulte a documentação será levado a acreditar que o sistema está pausado, o que levaria a planos de ação e análises incorretas.
- **Perda de Contexto:** A razão estratégica para o *pivot* (urgência da campanha) e suas implicações acadêmicas, embora mencionadas no texto inicial, não estão formalizadas nos documentos de governança do projeto (`doutorado`).

## 3. Análise dos Repositórios Satélite

Os demais repositórios estão bem estruturados e alinhados com seus propósitos, servindo como bases sólidas para o projeto.

- **`doutorado`:** Funciona bem como o *hub* acadêmico central, com uma estrutura de pastas lógica para a pesquisa. A principal lacuna é a falta de atualização para refletir o *pivot* do `tocantins-integrado`.
- **`ia-collab-os`:** Está maduro e bem documentado (versão 2.2), servindo como a espinha dorsal metodológica. A recente integração do artigo "Intelligent AI Delegation" (Tomasev et al., 2025) fortalece sua fundamentação teórica.
- **`caderno-tocantins-2026`:** Concluído e servindo como a fonte de dados validada para o MVP. A sua finalização foi o facilitador chave que permitiu o *pivot* para uma camada de dados estática.

## 4. Recomendações e Próximos Passos

Para garantir a integridade, consistência e continuidade do projeto, as seguintes ações são recomendadas, em ordem de prioridade:

1.  **Atualizar Documentação do `tocantins-integrado` (Prioridade Alta):**
    -   **Ação:** Editar `README.md` e `CLAUDE.md`.
    -   **Detalhes:** Mudar o status para **"Ativo (MVP com dados estáticos)"**. Descrever claramente a nova arquitetura do MVP, explicando que o *backend* legado está temporariamente inativo. Atualizar a seção "Quick Start" para refletir os passos de *deploy* simplificados (`npm run build` e `npm run start` dentro de `src/dashboard`).

2.  **Formalizar o Pivot no Repositório `doutorado` (Prioridade Alta):**
    -   **Ação:** Criar um novo diário de pesquisa-ação ou editar o `2026-02-14-sessao-025.md`.
    -   **Detalhes:** Documentar explicitamente a decisão e implementação do *pivot* (ADR-006). Explicar como a urgência da campanha motivou a reordenação do Ciclo 4, transformando a necessidade prática em um evento da pesquisa-ação.
    -   **Ação:** Editar `02-pesquisa-acao/01-ciclos/CICLO-04-PLANO.md`.
    -   **Detalhes:** Rebatizar o documento para `CICLO-04-PLANO-REVISADO.md`. Inserir uma seção no início explicando o *pivot* e reordenar as fases, movendo a "Fase 4D: Retomada do Sistema" para o início como "Fase 4A': Conclusão do MVP".

3.  **Centralizar o ADR-006 (Prioridade Média):**
    -   **Ação:** Copiar `006-mvp-dados-caderno-estatico.md` de `tocantins-integrado/docs/adr/` para `doutorado/02-pesquisa-acao/03-dados/adrs/`.
    -   **Detalhes:** Garantir que todas as decisões arquiteturais importantes estejam centralizadas no repositório acadêmico para fins de análise e escrita da tese.

4.  **Verificar o Deploy (Prioridade Média):**
    -   **Ação:** Executar os comandos de *build* e *start* do dashboard em um ambiente limpo para garantir que todas as dependências estão corretamente declaradas no `package.json` e que o MVP é de fato autocontido.
    -   **Comandos:** `cd /home/ubuntu/tocantins-integrado/src/dashboard && npm install && npm run build && npm run start`.

Ao concluir estes passos, o projeto estará em um estado consistente, com a documentação refletindo a realidade técnica e o registro da pesquisa-ação devidamente atualizado para capturar os eventos recentes. Isso fornecerá uma base sólida para os próximos passos, seja a utilização do dashboard na campanha ou a futura retomada do desenvolvimento do *backend* dinâmico.
