# Git Internals: Como o Git Funciona por Dentro

```ascii
+------------------------+
|       Git Object       |
|        Storage        |
|                       |
|   +---------------+   |
|   |    Commit    |   |
|   |   +-Tree-+   |   |
|   |   |Blob  |   |   |
|   |   |Blob  |   |   |
|   |   +------+   |   |
|   +---------------+   |
|                       |
|   .git/              |
|   ├── objects/       |
|   ├── refs/         |
|   └── HEAD          |
+------------------------+
```

## Sistema de Objetos do Git

### Tipos de Objetos
```mermaid
mindmap
    root((Objetos Git))
        Blob
            Conteúdo
            SHA-1
        Tree
            Diretórios
            Permissões
        Commit
            Metadados
            Snapshot
        Tag
            Anotada
            Leve
```

### Como os Objetos se Relacionam
```mermaid
graph TD
    A[Commit] -->|Aponta para| B[Tree]
    B -->|Contém| C[Blob]
    B -->|Subdiretório| D[Tree]
    D -->|Arquivo| E[Blob]
    A -->|Parent| F[Commit Anterior]
```

## Anatomia de um Commit

### Estrutura Básica
```text
commit 1fc408bfdb92... 
tree a906cb2a4a904...
parent 83bc0145a898...
author Stifler <stifler@milfsgo.com> 1625097600 -0300
committer Stifler <stifler@milfsgo.com> 1625097600 -0300

feat: adiciona sistema de busca de milfs
```

### Composição do SHA-1
```mermaid
graph LR
    A[Metadata] -->|Hash| B[SHA-1]
    C[Content] -->|Hash| B
    D[Parent] -->|Hash| B
```

## Sistema de Referências

### Referencias Principais
```mermaid
mindmap
    root((Refs))
        HEAD
            Current
            Detached
        Branch
            Local
            Remote
        Tag
            Lightweight
            Annotated
        Remote
            Origin
            Upstream
```

### Como o HEAD Funciona
```mermaid
graph TD
    A[HEAD] -->|Aponta para| B[Branch]
    B -->|Aponta para| C[Commit]
    A -->|Detached| C
```

## Armazenamento de Objetos

### Estrutura do .git
```ascii
.git/
├── objects/
│   ├── pack/
│   ├── info/
│   ├── aa/
│   └── bb/
├── refs/
│   ├── heads/
│   ├── tags/
│   └── remotes/
├── HEAD
└── config
```

### Processo de Compressão
```mermaid
graph LR
    A[Objetos Soltos] -->|git gc| B[Packfile]
    B -->|Delta| C[Comprimido]
```

## Como o Git Armazena Mudanças

### Snapshot vs Delta
```mermaid
graph TD
    subgraph "Outros VCS"
        A1[V1] -->|Delta| B1[V2]
        B1 -->|Delta| C1[V3]
    end
    
    subgraph "Git"
        A2[Snapshot 1] 
        B2[Snapshot 2]
        C2[Snapshot 3]
    end
```

### Processo de Staging
```mermaid
sequenceDiagram
    participant WD as Working Dir
    participant Index as Staging
    participant Repo as Repository
    
    WD->>Index: git add
    Note over Index: Cria objetos
    Index->>Repo: git commit
    Note over Repo: Cria commit
```

## Garbage Collection

### O que é Coletado
- Objetos não referenciados
- Objetos soltos antigos
- Referências dangling
- Packfiles redundantes

### Quando Acontece
```mermaid
graph TD
    A[Manual] -->|git gc| D[GC]
    B[Auto] -->|Threshold| D
    C[Push] -->|Server| D
```

## Dicas de Performance

### Otimizações
1. Clones rasos
2. Sparse checkout
3. Partial clone
4. Prune regular

### Monitoramento
```mermaid
graph LR
    A[git count-objects] -->|Size| B[Disk Usage]
    C[git fsck] -->|Health| D[Repository]
    E[git gc --aggressive] -->|Optimize| F[Performance]
```

## Comandos para Exploração

### Comandos Úteis
```bash
# Ver objeto
git cat-file -p SHA1

# Listar referências
git show-ref

# Ver árvore
git ls-tree HEAD

# Contar objetos
git count-objects -v

# Verificar integridade
git fsck
```

## Considerações de Segurança

### Proteção de Dados
```mermaid
mindmap
    root((Segurança))
        Hash
            SHA-1
            Collision
        Refs
            Protected
            Signed
        Objects
            Immutable
            Verified
```

## Próximos Passos

### Tópicos Avançados
- [Objetos Git](git-objects.md)
- [Referências Git](git-refs.md)
- [Packfiles](git-packfiles.md)
- [Garbage Collection](git-garbage-collection.md)

> **Dica**: Entender os internals do Git ajuda muito na resolução de problemas e na otimização do uso da ferramenta.