# Sistemas de Controle de Versão Distribuído

## A Rede Social das Milfs

Como uma rede social onde todo mundo tem sua própria cópia de tudo!

### Conceito

```mermaid
graph TD
    A((Repo Central)) --- B((Dev 1))
    A --- C((Dev 2))
    A --- D((Dev 3))
    B --- C
    C --- D
    D --- B
```

### Estrutura Distribuída
```ascii
    +----------------+
    |  Repositório   |
    |    Remoto      |
    +----------------+
     /      |       \
+-------+ +-----+ +-------+
| Clone | |Clone| | Clone |
|   1   | |  2  | |   3   |
+-------+ +-----+ +-------+
```

### Fluxo de Trabalho
```mermaid
sequenceDiagram
    participant L as Local
    participant R as Remote
    participant O as Other Dev
    L->>R: Push
    R->>O: Pull
    O->>R: Push
    R->>L: Pull
```

### Sistemas Populares
```mermaid
mindmap
    root((DVCS))
        Git
            GitHub
            GitLab
            Bitbucket
        Mercurial
            Facebook
            Mozilla
```