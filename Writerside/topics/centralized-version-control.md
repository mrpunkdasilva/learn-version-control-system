# Sistemas de Controle de Versão Centralizado

## A Casa da Mãe do Stifler

Como uma festa na casa da mãe do Stifler, todos precisam ir ao mesmo lugar para participar!

### Arquitetura

```mermaid
graph TD
    S((Servidor Central)) --- C1[Cliente 1]
    S --- C2[Cliente 2]
    S --- C3[Cliente 3]
    S --- C4[Cliente N]
```

### Estrutura do Sistema
```ascii
      +----------------+
      |    Servidor    |
      |    Central     |
      +----------------+
            ||||
    +-------++-+-------+
    |        |         |
+-------+ +-------+ +-------+
|Cliente| |Cliente| |Cliente|
|   1   | |   2   | |   3   |
+-------+ +-------+ +-------+
```

### Fluxo de Operações
```mermaid
sequenceDiagram
    participant D as Dev
    participant L as Local
    participant S as Servidor
    D->>L: Checkout
    L->>S: Update
    D->>L: Modifica
    L->>S: Commit
    S->>L: Confirma
```

### Exemplos Famosos
```mermaid
mindmap
    root((VCS Centralizado))
        SVN
            Apache
            Multiplataforma
            Confiável
        CVS
            Legado
            Unix
            Histórico
```