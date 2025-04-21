# Trunk-Based Development

Imagine uma festa onde todo mundo dança na mesma pista. É assim que funciona o Trunk-Based Development (TBD)! 

## Anatomia do TBD

```mermaid
gitGraph
    commit
    commit
    branch feature1
    checkout feature1
    commit
    checkout main
    merge feature1
    commit
    branch feature2
    checkout feature2
    commit
    checkout main
    merge feature2
    commit
```

## Como Funciona?

Todo mundo trabalha direto na branch principal (trunk/main):

```mermaid
graph TD
    A[Main/Trunk] -->|Deploy| B[Produção]
    C[Dev 1] -->|Commit| A
    D[Dev 2] -->|Commit| A
    E[Dev 3] -->|Commit| A
```

## Regras do Jogo

### 1. Commits Pequenos e Frequentes

```mermaid
gitGraph
    commit
    branch feature
    checkout feature
    commit id: "pequeno-1"
    checkout main
    merge feature
    checkout feature
    commit id: "pequeno-2"
    checkout main
    merge feature
    checkout feature
    commit id: "pequeno-3"
    checkout main
    merge feature
```

### 2. Testes Antes de Tudo
```mermaid
sequenceDiagram
    participant D as Dev
    participant T as Testes
    participant M as Main
    D->>T: Roda Testes
    T->>M: Se Passar
    M->>D: Commit Aceito
```

### 3. Feature Flags
- Código novo entra escondido
- Ativa quando estiver pronto
- Como uma surpresa na festa!

## Ciclo de Vida do Código

```mermaid
gitGraph
    commit id: "inicio"
    branch desenvolvimento
    checkout desenvolvimento
    commit id: "codigo"
    commit id: "testes"
    checkout main
    merge desenvolvimento
    commit id: "review" type: HIGHLIGHT
    commit id: "deploy"
```

## Fluxo de Trabalho Típico

```mermaid
gitGraph
    commit
    branch feature-flag
    checkout feature-flag
    commit id: "add-flag"
    checkout main
    merge feature-flag
    commit id: "dev-1"
    commit id: "dev-2"
    branch hotfix
    checkout hotfix
    commit id: "fix"
    checkout main
    merge hotfix
    commit id: "release"
```

## Por Que Usar?

### Vantagens
- Integração contínua real
- Menos conflitos
- Deploy mais rápido
- Todo mundo no mesmo ritmo

### Desafios
- Precisa de muita disciplina
- Testes automatizados são obrigatórios
- Feature flags para código incompleto

## Na Prática

### Fluxo Básico
```ascii
1. Código novo
2. Testes locais
3. Code review
4. Merge na main
5. Deploy
```

### Dicas de Sobrevivência
- Commits pequenos
- Testes, testes e mais testes
- Feature flags são seus amigos
- Code review rápido

## Conclusão

TBD é rápido, moderno e eficiente. Como uma festa bem organizada, todo mundo se diverte junto, mas seguindo algumas regras básicas para manter tudo funcionando!