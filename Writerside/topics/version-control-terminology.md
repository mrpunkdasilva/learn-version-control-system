# Terminologia do Controle de Versão

## Conceitos Fundamentais

### Repository (Repositório)
```mermaid
mindmap
    root((Repositório))
        Local
            Working Directory
            Staging Area
            Local Repository
        Remoto
            Origin
            Upstream
            Mirror
```

- Local onde o código é armazenado
- Contém todo o histórico do projeto
- Pode ser local ou remoto
- Inclui metadados e configurações

### Branch (Ramo)
```mermaid
graph TD
    A[main] --> B[develop]
    B --> C[feature/1]
    B --> D[feature/2]
    A --> E[hotfix]
```

- Linha independente de desenvolvimento
- Permite trabalho paralelo
- Isola mudanças em desenvolvimento
- Facilita experimentações

### Commit (Confirmação)
```mermaid
gitGraph
    commit id: "A"
    commit id: "B"
    branch feature
    commit id: "C"
    commit id: "D"
    checkout main
    merge feature
```

- Snapshot do código em um momento
- Inclui mensagem descritiva
- Possui identificador único (hash)
- Mantém autor e timestamp

## Operações Básicas

### Clone
```mermaid
sequenceDiagram
    participant R as Repositório Remoto
    participant L as Local
    R->>L: git clone
    Note over L: Cópia completa
    L->>L: Configuração local
```

- Cria cópia local do repositório
- Inclui todo histórico
- Configura remote origin
- Estabelece tracking branches

### Pull
```mermaid
sequenceDiagram
    participant R as Remoto
    participant L as Local
    L->>R: git fetch
    R->>L: Novos commits
    L->>L: git merge
```

- Atualiza repositório local
- Combina fetch + merge
- Sincroniza com remoto
- Resolve conflitos se necessário

### Push
```mermaid
sequenceDiagram
    participant L as Local
    participant R as Remoto
    L->>L: Commits locais
    L->>R: git push
    Note over R: Atualiza remoto
```

- Envia commits locais
- Atualiza repositório remoto
- Requer permissões
- Pode exigir resolução de conflitos

## Operações Avançadas

### Merge (Mesclagem)
```mermaid
gitGraph
    commit
    branch feature
    commit
    commit
    checkout main
    commit
    merge feature
```

- Combina mudanças de diferentes branches
- Pode gerar conflitos
- Mantém histórico de ambas as branches
- Cria commit de merge

### Rebase (Rebase)
```mermaid
gitGraph
    commit
    branch feature
    commit
    commit
    checkout main
    commit
    checkout feature
    rebase main
```

- Reaplica commits sobre outra base
- Mantém histórico linear
- Útil para manter branches atualizadas
- Altera histórico de commits

### Cherry-pick
```mermaid
gitGraph
    commit id: "A"
    commit id: "B"
    branch feature
    commit id: "C"
    checkout main
    cherry-pick id: "C"
```

- Aplica commits específicos
- Seletivo e preciso
- Útil para hotfixes
- Cria novos commits

## Estados de Arquivos

### Tracked (Rastreado)
```mermaid
stateDiagram-v2
    [*] --> Modified
    Modified --> Staged: git add
    Staged --> Committed: git commit
    Committed --> Modified: modificação
```

#### Modified (Modificado)
- Arquivo alterado
- Não preparado para commit
- Detectado pelo git status

#### Staged (Preparado)
- Marcado para commit
- Na área de staging
- Pronto para confirmação

#### Committed (Confirmado)
- Salvo no repositório
- Parte do histórico
- Possui hash único

### Untracked (Não Rastreado)
```mermaid
graph TD
    A[Arquivo Novo] --> B{git add?}
    B -->|Sim| C[Tracked]
    B -->|Não| D[Untracked]
```

- Arquivos novos
- Não incluídos no controle de versão
- Precisam ser adicionados explicitamente
- Ignorados via .gitignore

## Glossário Expandido

| Termo | Definição | Uso Comum |
|------|-----------|-----------|
| Clone | Cópia completa do repositório | Início do trabalho |
| Fork | Cópia independente do repositório | Contribuição externa |
| Pull Request | Solicitação para integrar mudanças | Colaboração |
| Tag | Marco específico no histórico | Releases |
| Hook | Script automatizado em eventos | Automação |
| Remote | Repositório em servidor | Colaboração |
| Head | Ponteiro para commit atual | Referência |
| Index | Área de staging | Preparação |
| Stash | Armazenamento temporário | Mudança de contexto |
| Fetch | Download de mudanças | Atualização |

## Configurações e Metadados

### Arquivos de Configuração
```ascii
.git/
├── config
├── HEAD
├── index
├── objects/
└── refs/
```

### Arquivos Especiais
```ascii
projeto/
├── .gitignore
├── .gitattributes
├── .gitmodules
└── .git/
```

## Fluxos de Trabalho

### Básico
```mermaid
graph LR
    A[Modificar] --> B[Stage]
    B --> C[Commit]
    C --> D[Push]
```

### Colaborativo
```mermaid
graph LR
    A[Pull] --> B[Modificar]
    B --> C[Commit]
    C --> D[Push]
    D --> E[Pull Request]
```

## Resolução de Problemas

### Conflitos
```mermaid
graph TD
    A[Conflito] --> B{Resolver}
    B -->|Manual| C[Editar Arquivo]
    B -->|Ferramenta| D[Merge Tool]
    C & D --> E[git add]
    E --> F[git commit]
```

### Recuperação
```mermaid
graph TD
    A[Problema] --> B{Tipo}
    B -->|Commit Errado| C[git reset]
    B -->|Perda de Arquivo| D[git checkout]
    B -->|Branch Errada| E[git branch]
```