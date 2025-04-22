# Integração com Gestão de Projetos

A integração entre controle de versão e ferramentas de gestão de projetos melhora a rastreabilidade e o gerenciamento do trabalho.

## Ferramentas Populares

### 1. Jira + Git
```mermaid
sequenceDiagram
    participant Dev
    participant Git
    participant Jira
    
    Dev->>Git: Commit com ID da Issue
    Git->>Jira: Atualiza Status
    Jira->>Dev: Notifica Mudança
```

### 2. Azure DevOps
- Work Items
- Boards
- Repos
- Pipelines

### 3. Trello + GitHub
- Card Links
- Automações
- Power-Ups

## Funcionalidades Principais

### 1. Rastreabilidade
```mermaid
graph LR
    A[Issue] -->|Link| B[Branch]
    B -->|Referência| C[Commit]
    C -->|Trigger| D[Pipeline]
    D -->|Update| A
```

### 2. Automações
- Status automático
- Assignees
- Labels
- Milestones

## Melhores Práticas

### 1. Nomenclatura
- Branches com ID da issue
- Commits com referências
- PRs linkados

### 2. Workflows
```mermaid
graph TD
    A[Todo] -->|Start| B[In Progress]
    B -->|Commit| C[Review]
    C -->|Merge| D[Done]
```