# Fluxo de Trabalho do Git

## Iniciando um Repositório
Devemos usar o comando abaixo para iniciar o repositório para que o Git consiga ver os arquivos.

```bash
md MilfsGo # Cria a pasta
cd MilfsGo # acessa a pasta
git init
```

## Ciclo de Vida dos Arquivos

### Estados dos Arquivos
```mermaid
stateDiagram-v2
    [*] --> Untracked: Novo arquivo
    Untracked --> Staged: git add
    Staged --> Committed: git commit
    Committed --> Modified: Edição
    Modified --> Staged: git add
```

### Áreas do Git
```mermaid
graph LR
    A[Working Directory] -->|git add| B[Staging Area]
    B -->|git commit| C[Repository]
    C -->|git checkout| A
```

## Fazendo Alterações
Agora vamos fazer alterações básicas como adicionar um *README* para o projeto.

> README são arquivos geralmente em markdown (.md) para registrar a documentação do repositório com informações importantes como:
> - Nome
> - Descrição
> - Como usar
> - Etc

### Criando README
```bash
# Criar e editar README
echo "# MilfsGo" > README.md
echo "Projeto para encontrar milfs na sua região" >> README.md
```

### Adicionando ao Stage
```bash
# Adicionar arquivo específico
git add README.md

# Adicionar todos os arquivos
git add .
```

## Verificando Status
```bash
git status
```

> ![](Version-Control-System-gitstatus.png)
> Resultado da execução do comando...

## Commits

### Anatomia de um Bom Commit
```mermaid
mindmap
    root((Commit))
        Tipo
            feat
            fix
            docs
        Escopo
            login
            perfil
            busca
        Mensagem
            Clara
            Concisa
            Descritiva
```

### Padrões de Commit
```bash
# Commits semânticos
git commit -m "feat: adiciona sistema de busca"
git commit -m "fix: corrige bug no filtro de idade"
git commit -m "docs: atualiza documentação de instalação"
```

## Branches

### Fluxo de Branches
```mermaid
gitGraph
    commit
    branch feature/busca
    checkout feature/busca
    commit
    commit
    checkout main
    merge feature/busca
    branch feature/chat
    checkout feature/chat
    commit
    commit
```

### Comandos de Branch
```bash
# Criar e mudar de branch
git checkout -b feature/nova-busca

# Listar branches
git branch

# Mudar de branch
git checkout main

# Deletar branch
git branch -d feature/antiga
```

## Sincronização com Remoto

### Configurando Remoto
```bash
# Adicionar remoto
git remote add origin https://github.com/user/MilfsGo.git

# Verificar remotos
git remote -v
```

### Push e Pull
```mermaid
sequenceDiagram
    participant L as Local
    participant R as Remote
    L->>R: git push
    R->>L: git pull
    Note over L,R: Mantendo sincronizado
```

```bash
# Enviar alterações
git push origin main

# Buscar alterações
git pull origin main
```

## Resolução de Conflitos

### Tipos de Conflitos
```ascii
<<<<<<< HEAD
Sua versão
=======
Versão remota
>>>>>>> branch-name
```

### Resolvendo Conflitos
```mermaid
graph TD
    A[Conflito Detectado] -->|Abrir Arquivo| B[Editar Conflito]
    B -->|Escolher Versão| C[Salvar]
    C -->|Marcar Resolvido| D[git add]
    D -->|Finalizar| E[git commit]
```

## Stash

### Salvando Trabalho Temporário
```bash
# Guardar alterações
git stash

# Listar stashes
git stash list

# Recuperar alterações
git stash pop
```

### Fluxo com Stash
```mermaid
sequenceDiagram
    participant W as Working Dir
    participant S as Stash
    participant B as Branch
    W->>S: git stash
    W->>B: git checkout other
    B->>W: trabalho
    W->>S: git stash pop
```

## Tags

### Versionamento
```bash
# Criar tag
git tag -a v1.0.0 -m "Primeira versão estável"

# Listar tags
git tag

# Publicar tags
git push origin --tags
```

### Estrutura de Tags
```mermaid
mindmap
    root((Tags))
        Release
            v1.0.0
            v1.1.0
        Beta
            v0.9.0-beta
        RC
            v1.0.0-rc1
```

## Logs e Histórico

### Visualizando Histórico
```bash
# Log básico
git log

# Log formatado
git log --oneline --graph --decorate

# Log específico
git log --author="Stifler"
```

### Buscando no Histórico
```bash
# Buscar por mensagem
git log --grep="feat"

# Buscar por conteúdo
git log -S "milf"
```

## Melhores Práticas

### Commits
```mermaid
mindmap
    root((Boas Práticas))
        Commits
            Pequenos
            Focados
            Frequentes
        Mensagens
            Claras
            Padronizadas
            Descritivas
        Branches
            Organizadas
            Temporárias
            Descritivas
```

### Workflow Diário
```ascii
📋 Daily Git Workflow

1. [ ] git pull origin main
2. [ ] git checkout -b feature/nova
3. [ ] Desenvolvimento
4. [ ] git add .
5. [ ] git commit -m "feat: nova função"
6. [ ] git push origin feature/nova
7. [ ] Criar Pull Request
```

## Ferramentas Úteis

### GUI Clients
```mermaid
mindmap
    root((Git GUI))
        GitKraken
            Visual
            Intuitivo
        SourceTree
            Gratuito
            Completo
        GitHub Desktop
            Simples
            Integrado
```

### IDE Integration
- VS Code
- IntelliJ
- Eclipse
- Sublime

## Dicas Avançadas

### Aliases Úteis
```bash
# Configurar aliases
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
```

### Scripts de Produtividade
```bash
# Atualizar e limpar
git pull origin main && git remote prune origin

# Deletar branches mergeadas
git branch --merged | grep -v "\*" | xargs -n 1 git branch -d
```

## Troubleshooting

### Problemas Comuns
```mermaid
mindmap
    root((Problemas))
        Conflitos
            Merge
            Rebase
        Commits
            Reset
            Revert
        Remote
            Push
            Pull
```

### Soluções
```ascii
🔧 Git Fixes

Commit errado:
└── git reset --soft HEAD^

Branch errada:
└── git checkout -b correct-branch

Conflito:
└── Resolver + git add + git commit
```

## Próximos Passos

### Avançando no Git
1. Git Flow
2. Rebase interativo
3. Git Hooks
4. CI/CD

### Recursos Adicionais
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

> **Dica Pro**: Mantenha um cheat sheet personalizado com seus comandos mais usados!