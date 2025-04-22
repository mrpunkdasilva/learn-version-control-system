# Git Cheat Sheet

## Configuração Inicial

```bash
# Configurar nome e email
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"

# Configurar editor padrão
git config --global core.editor "code --wait"
```

## Comandos Básicos

### Iniciar e Clonar
```bash
# Iniciar novo repositório
git init

# Clonar repositório existente
git clone <url>
```

### Mudanças Básicas
```bash
# Ver status
git status

# Adicionar arquivos
git add <arquivo>
git add .

# Commit
git commit -m "mensagem"

# Ver histórico
git log
git log --oneline
```

### Branches
```bash
# Listar branches
git branch

# Criar branch
git branch <nome>

# Mudar branch
git checkout <nome>
git switch <nome>

# Criar e mudar
git checkout -b <nome>
```

### Sincronização
```bash
# Atualizar remoto
git fetch

# Baixar e mesclar
git pull

# Enviar mudanças
git push origin <branch>
```

## Operações Intermediárias

### Stash
```bash
# Guardar mudanças
git stash

# Listar stashes
git stash list

# Aplicar stash
git stash apply
git stash pop
```

### Merge
```bash
# Mesclar branch
git merge <branch>

# Abortar merge
git merge --abort
```

### Rebase
```bash
# Rebase interativo
git rebase -i HEAD~3

# Continuar rebase
git rebase --continue

# Abortar rebase
git rebase --abort
```

## Operações Avançadas

### Reset e Revert
```bash
# Reset soft
git reset --soft HEAD~1

# Reset hard
git reset --hard HEAD~1

# Reverter commit
git revert <commit>
```

### Cherry-pick
```bash
# Aplicar commit específico
git cherry-pick <commit>
```

### Submodules
```bash
# Adicionar submodule
git submodule add <url>

# Inicializar submodules
git submodule init
git submodule update
```

## Dicas e Truques

### Aliases Úteis
```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
```

### Busca Avançada
```bash
# Buscar em commits
git log --grep="termo"

# Buscar em arquivos
git grep "termo"
```

### Manutenção
```bash
# Limpar arquivos não rastreados
git clean -df

# Compactar repositório
git gc

# Verificar integridade
git fsck
```

## Resolução de Problemas

### Conflitos
```bash
# Ver arquivos em conflito
git diff --name-only --diff-filter=U

# Abortar merge com conflito
git merge --abort
```

### Recuperação
```bash
# Recuperar commit deletado
git reflog
git checkout -b recovery-branch <commit>
```

### Debug
```bash
# Encontrar bug
git bisect start
git bisect bad
git bisect good <commit>
```