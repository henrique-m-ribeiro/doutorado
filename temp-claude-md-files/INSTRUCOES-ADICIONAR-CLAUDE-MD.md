# Instrucoes para Adicionar CLAUDE.md aos 3 Repositorios

**Data:** 2026-02-13
**Criado por:** Claude Code Opus 4.6
**Contexto:** Implementacao de governanca de pesquisa-acao em todos os repositorios do projeto
**Atualizado:** Reflete ia-collab-os v2.2 com fundamentacao em delegacao inteligente (Tomasev et al., 2025)

---

## Visao Geral

Foram criados 3 arquivos CLAUDE.md personalizados para os repositorios:
1. `ia-collab-os`
2. `tocantins-integrado`
3. `caderno-tocantins-2026`

Estes arquivos estao salvos temporariamente em:
```
/home/user/doutorado/temp-claude-md-files/
├── CLAUDE.md-ia-collab-os
├── CLAUDE.md-tocantins-integrado
├── CLAUDE.md-caderno-tocantins-2026
└── INSTRUCOES-ADICIONAR-CLAUDE-MD.md (este arquivo)
```

---

## Opcao 1: Adicionar via GitHub Web Interface (Mais Simples)

### Para cada repositorio:

#### Passo 1: Abrir o repositorio no navegador
- `ia-collab-os`: https://github.com/henrique-m-ribeiro/ia-collab-os
- `tocantins-integrado`: https://github.com/henrique-m-ribeiro/tocantins-integrado
- `caderno-tocantins-2026`: https://github.com/henrique-m-ribeiro/caderno-tocantins-2026

#### Passo 2: Criar o arquivo CLAUDE.md
1. Clique em **"Add file"** (botao no topo da pagina) → **"Create new file"**
2. No campo "Name your file...", digite: `CLAUDE.md`
3. No editor de texto, copie e cole o conteudo do arquivo correspondente:
   - Para ia-collab-os: copiar conteudo de `temp-claude-md-files/CLAUDE.md-ia-collab-os`
   - Para tocantins-integrado: copiar conteudo de `temp-claude-md-files/CLAUDE.md-tocantins-integrado`
   - Para caderno-tocantins-2026: copiar conteudo de `temp-claude-md-files/CLAUDE.md-caderno-tocantins-2026`

#### Passo 3: Commit
1. Na secao "Commit new file" (abaixo do editor):
   - **Commit message:** `docs: Adicionar CLAUDE.md com governanca de pesquisa-acao`
   - **Extended description (opcional):**
     ```
     Implementa governanca metodologica para sessoes com agentes IA.

     - Declara ciclo PA, OE e PS endereçados
     - Instrui dupla leitura (produto pratico x dado de pesquisa)
     - Referencia repositorio hub (doutorado)
     - Define convencoes locais

     Parte da Etapa 6 do Plano de Fortalecimento Metodologico.
     ```
2. Selecione **"Commit directly to the main branch"**
3. Clique em **"Commit new file"**

---

## Opcao 2: Adicionar via Git Local (Mais Rapido para Multiplos Repos)

### Pre-requisitos:
- Repositorios ja clonados localmente
- Git configurado com suas credenciais

### Comandos:

#### Para ia-collab-os:
```bash
# Navegar ate o repositorio local
cd /caminho/para/ia-collab-os

# Copiar o arquivo
cp /home/user/doutorado/temp-claude-md-files/CLAUDE.md-ia-collab-os ./CLAUDE.md

# Adicionar e commitar
git add CLAUDE.md
git commit -m "docs: Adicionar CLAUDE.md com governanca de pesquisa-acao

Implementa governanca metodologica para sessoes com agentes IA.

- Declara Ciclos 2-3, OE1/OE3/OE5, PS1/PS3
- Instrui dupla leitura (framework metodologico x dado de pesquisa)
- Referencia repositorio hub (doutorado)
- Define convencoes: UPPER-CASE.md, commits em PT

Parte da Etapa 6 do Plano de Fortalecimento Metodologico."

# Push
git push origin main
```

#### Para tocantins-integrado:
```bash
cd /caminho/para/tocantins-integrado

cp /home/user/doutorado/temp-claude-md-files/CLAUDE.md-tocantins-integrado ./CLAUDE.md

git add CLAUDE.md
git commit -m "docs: Adicionar CLAUDE.md com governanca de pesquisa-acao

Implementa governanca metodologica para sessoes com agentes IA.

- Declara Ciclo 2 (pausado), OE1-OE5, PS1-PS4
- Instrui dupla leitura (sistema tecnico x dado de pesquisa)
- Referencia 5 ADRs e piloto Palmas
- Documenta status: Camada 1 90%, Camada 2 0%

Parte da Etapa 6 do Plano de Fortalecimento Metodologico."

git push origin main
```

#### Para caderno-tocantins-2026:
```bash
cd /caminho/para/caderno-tocantins-2026

cp /home/user/doutorado/temp-claude-md-files/CLAUDE.md-caderno-tocantins-2026 ./CLAUDE.md

git add CLAUDE.md
git commit -m "docs: Adicionar CLAUDE.md com governanca de pesquisa-acao

Implementa governanca metodologica para sessoes com agentes IA.

- Declara Ciclo 3, OE2-OE5, PS2/PS3/PS5
- Instrui dupla leitura (cadernos territoriais x dado de pesquisa)
- Documenta 9 volumes, 139 municipios, 213 agentes orquestrados
- Define etica: dados publicos apenas, transparencia de fontes

Parte da Etapa 6 do Plano de Fortalecimento Metodologico."

git push origin main
```

---

## Opcao 3: Script Automatizado (Se Repositorios Estao Clonados)

Se voce tem os 3 repositorios clonados localmente em um diretorio comum:

```bash
#!/bin/bash

# Configurar caminhos (ajuste conforme necessario)
REPOS_DIR="/caminho/para/seus/repositorios"
TEMP_DIR="/home/user/doutorado/temp-claude-md-files"

# Array de repositorios
repos=("ia-collab-os" "tocantins-integrado" "caderno-tocantins-2026")

# Iterar sobre repositorios
for repo in "${repos[@]}"; do
    echo "Processando $repo..."

    cd "$REPOS_DIR/$repo" || continue

    # Copiar arquivo correspondente
    cp "$TEMP_DIR/CLAUDE.md-$repo" ./CLAUDE.md

    # Adicionar e commitar
    git add CLAUDE.md
    git commit -m "docs: Adicionar CLAUDE.md com governanca de pesquisa-acao"

    # Push
    git push origin main

    echo "$repo concluido."
done

echo "Todos os repositorios atualizados!"
```

Salve como `adicionar-claude-md.sh`, torne executavel (`chmod +x adicionar-claude-md.sh`) e execute (`./adicionar-claude-md.sh`).

---

## Validacao Pos-Adicao

Apos adicionar os CLAUDE.md, valide que estao visiveis:

### Via Web:
- https://github.com/henrique-m-ribeiro/ia-collab-os/blob/main/CLAUDE.md
- https://github.com/henrique-m-ribeiro/tocantins-integrado/blob/main/CLAUDE.md
- https://github.com/henrique-m-ribeiro/caderno-tocantins-2026/blob/main/CLAUDE.md

### Via Raw (para agentes IA):
- https://raw.githubusercontent.com/henrique-m-ribeiro/ia-collab-os/main/CLAUDE.md
- https://raw.githubusercontent.com/henrique-m-ribeiro/tocantins-integrado/main/CLAUDE.md
- https://raw.githubusercontent.com/henrique-m-ribeiro/caderno-tocantins-2026/main/CLAUDE.md

---

## Proximo Passo: Atualizar README.md de cada Repositorio

Apos adicionar CLAUDE.md, recomendo adicionar uma secao no README.md de cada repositorio:

```markdown
## Para Agentes IA

Este repositorio faz parte de um projeto de pesquisa-acao em doutorado.
Leia [CLAUDE.md](./CLAUDE.md) para instrucoes completas sobre:
- Contexto da pesquisa e objetivos endereçados
- Dupla leitura: produto pratico x dado de pesquisa
- Governanca metodologica e convencoes
- Repositorio hub: [doutorado](https://github.com/henrique-m-ribeiro/doutorado)
```

---

## Registro no Repositorio Hub (doutorado)

Apos adicionar os 3 CLAUDE.md, registre este marco no repositorio `doutorado`:

1. Criar diario de sessao: `02-pesquisa-acao/03-dados/diarios-sessoes/2026-02-13-sessao-025.md`
2. Atualizar CHANGELOG (se existir)
3. Atualizar `CLAUDE.md` do hub com data de conclusao da Etapa 6:
   ```markdown
   | 6. Retomada de producao | ✅ Concluida (CLAUDE.md criado em 4/4 repos - 2026-02-13) |
   ```

---

## Troubleshooting

### Problema: "Permission denied" ao fazer push
**Solucao:** Verifique suas credenciais Git:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@example.com"
```

### Problema: Conflito ao fazer push
**Solucao:** Pull primeiro, depois push:
```bash
git pull origin main
git push origin main
```

### Problema: Arquivo ja existe (improvavel)
**Solucao:** Fazer backup do existente e substituir:
```bash
mv CLAUDE.md CLAUDE.md.backup
cp /home/user/doutorado/temp-claude-md-files/CLAUDE.md-[repo] ./CLAUDE.md
```

---

## Contato e Suporte

Se precisar de ajuda ou tiver duvidas sobre a implementacao, consulte:
- Repositorio hub: https://github.com/henrique-m-ribeiro/doutorado
- Instrucao sessao Etapa 6: `doutorado/02-pesquisa-acao/03-dados/handoffs/`
- Protocolo de sessao: `doutorado/02-pesquisa-acao/01-ciclos/PROTOCOLO-REGISTRO-SESSAO.md`

---

**Boa sorte com a implementacao!**
