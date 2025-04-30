# Comandos Essenciais do Git

## Comandos por Situação

### 💩 Socorro! Fiz Besteira!

```bash
# Ops, commitei na branch errada
git reset HEAD~1            # Desfaz o último commit mantendo as alterações
git checkout branch-correta # Muda para a branch correta
git add .                   # Adiciona as alterações
git commit -m "feat: ..."   # Commit na branch certa

# Ops, commitei algo errado
git reset --soft HEAD~1     # Desfaz o commit mantendo alterações em stage
git reset --hard HEAD~1     # Desfaz o commit E as alterações (cuidado!)

# Ops, modifiquei o arquivo errado
git checkout -- arquivo.txt # Desfaz alterações não commitadas

# Ops, dei push em algo errado
git revert HEAD            # Cria novo commit desfazendo alterações
git push origin main      # Envia a reversão para o remoto
```

### 🆕 Começando um Projeto

```bash
# Iniciando do zero
git init
git add .
git commit -m "feat: commit inicial"

# Clonando projeto existente
git clone https://github.com/user/repo.git
git clone https://github.com/user/repo.git minha-pasta
```

### 📝 Trabalhando com Arquivos

```bash
# Básico
git add arquivo.txt        # Adiciona arquivo específico
git add .                  # Adiciona tudo
git rm arquivo.txt        # Remove arquivo
git mv antigo.txt novo.txt # Renomeia arquivo

# Ignorando arquivos
echo "*.log" >> .gitignore # Adiciona padrão ao .gitignore
echo "node_modules/" >> .gitignore # Ignora pasta
```

### 🌳 Branches

```bash
# Operações básicas
git branch                  # Lista branches
git branch nova-feature    # Cria branch
git checkout nova-feature  # Muda para branch
git checkout -b feature    # Cria e muda de branch

# Limpeza
git branch -d feature      # Deleta branch (se mergeada)
git branch -D feature      # Deleta branch (força)
git remote prune origin    # Remove branches remotas deletadas
```

### 🔄 Sincronização

```bash
# Com remoto
git remote add origin https://github.com/user/repo.git
git push -u origin main   # Primeiro push
git push                  # Pushes subsequentes
git pull                  # Atualiza do remoto

# Branches específicas
git push origin feature   # Envia branch específica
git pull origin feature   # Puxa branch específica
```

### 🔍 Investigação

```bash
# Status e logs
git status                # Estado atual
git log                   # Histórico de commits
git log --oneline        # Histórico resumido
git blame arquivo.txt    # Quem alterou cada linha

# Diferenças
git diff                  # Alterações não staged
git diff --staged        # Alterações staged
git diff branch1..branch2 # Entre branches
```

### 🤝 Merge e Rebase

```bash
# Merge
git checkout main         # Vai para branch destino
git merge feature         # Merge da feature

# Rebase
git checkout feature      # Vai para branch origem
git rebase main          # Rebase na main

# Conflitos
git merge --abort        # Cancela merge
git rebase --abort       # Cancela rebase
```

### 📌 Tags

```bash
# Criação
git tag v1.0.0                    # Tag leve
git tag -a v1.0.0 -m "Release 1.0.0" # Tag anotada

# Publicação
git push origin v1.0.0           # Envia tag específica
git push origin --tags           # Envia todas as tags
```

### 📦 Stash

```bash
# Guardando alterações
git stash                 # Guarda alterações
git stash save "WIP:..." # Guarda com descrição
git stash pop            # Recupera e remove
git stash apply          # Recupera e mantém
git stash list           # Lista stashes
git stash drop           # Remove stash
```

## 🎓 Comandos Avançados

### Reescrevendo História

```bash
# Alterando commits
git commit --amend                # Altera último commit
git rebase -i HEAD~3             # Rebase interativo
git cherry-pick <commit-hash>    # Copia commit específico

# Limpeza
git clean -n                     # Lista arquivos a serem removidos
git clean -df                    # Remove arquivos não rastreados
```

### Submodules

```bash
# Adicionando
git submodule add https://github.com/user/repo
git submodule update --init --recursive

# Atualizando
git submodule update --remote
```

### Bisect

```bash
# Encontrando bugs
git bisect start
git bisect bad                   # Marca commit atual como ruim
git bisect good <commit-hash>    # Marca commit como bom
git bisect reset                # Finaliza busca
```

## 🛠️ Configurações Úteis

### Aliases Produtivos

```bash
# Configurando aliases
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.unstage 'reset HEAD --'
git config --global alias.last 'log -1 HEAD'
```

### Configurações Globais

```bash
# Identidade
git config --global user.name "Stifler"
git config --global user.email "stifler@milfsgo.com"

# Editor
git config --global core.editor "code --wait"

# Merge tool
git config --global merge.tool vscode
```

## 📊 Dicas de Performance

### Repositórios Grandes

```bash
# Clone parcial
git clone --depth 1 https://github.com/user/repo.git

# Fetch específico
git fetch origin branch --depth 1

# Limpeza
git gc                    # Coleta de lixo
git prune                # Remove objetos órfãos
```

### Otimizações

```bash
# Compressão
git gc --aggressive
git repack -ad

# Cache
git config --global core.preloadindex true
git config --global core.fscache true
```

## 🎯 Melhores Práticas

### Commits Semânticos

```bash
git commit -m "feat: adiciona busca por localização"
git commit -m "fix: corrige bug no filtro de idade"
git commit -m "docs: atualiza README"
git commit -m "style: formata código"
git commit -m "refactor: simplifica função de busca"
```

### Workflow Seguro

```bash
# Antes de começar
git pull origin main
git checkout -b feature

# Antes de commitar
git diff
git status
git add .
git commit -m "feat: ..."

# Antes de push
git pull --rebase origin main
git push origin feature
```

> **Dica Pro**: Mantenha esse cheat sheet sempre à mão. Com o tempo você vai decorar os comandos mais usados, mas é sempre bom ter onde consultar!

## 🔗 Links Úteis

- [Git Documentation](https://git-scm.com/doc)
- [Oh My Git!](https://ohmygit.org/)
- [Git Explorer](https://gitexplorer.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
