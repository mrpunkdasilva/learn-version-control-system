# Feature Branch Workflow

Imagine que cada nova funcionalidade é como uma nova cena do American Pie - precisa ser filmada separadamente antes de entrar no filme final!

## Como Funciona?

```mermaid
gitGraph
    commit
    branch feature/login
    commit
    commit
    checkout main
    branch feature/perfil
    commit
    commit
    checkout feature/login
    commit
    checkout main
    merge feature/login
    checkout feature/perfil
    commit
    checkout main
    merge feature/perfil
```

## Regras do Jogo

### 1. Uma Branch por Feature
```mermaid
graph TD
    A[Main] --> B[feature/login]
    A --> C[feature/perfil]
    A --> D[feature/chat]
    B --> E[Pull Request]
    C --> E
    D --> E
    E --> A
```

### 2. Processo de Review
```mermaid
sequenceDiagram
    participant D as Dev
    participant R as Reviewer
    participant M as Main
    D->>D: Cria Branch
    D->>D: Desenvolve
    D->>R: Pull Request
    R->>R: Code Review
    R->>D: Feedback
    D->>R: Ajustes
    R->>M: Aprova & Merge
```

## Anatomia de uma Feature Branch

```ascii
main
  │
  ├── feature/login
  │   ├── commit: "Adiciona form"
  │   ├── commit: "Valida campos"
  │   └── commit: "Integra API"
  │
  ├── feature/perfil
  │   ├── commit: "Layout base"
  │   └── commit: "Upload foto"
  │
  └── feature/chat
      └── commit: "MVP chat"
```

## Fluxo de Trabalho

### 1. Iniciando uma Feature
```bash
git checkout -b feature/nova-funcionalidade
```

### 2. Desenvolvimento
```mermaid
gitGraph
    commit
    branch feature/nova
    checkout feature/nova
    commit id: "inicial"
    commit id: "wip"
    commit id: "ajustes"
    commit id: "finaliza"
```

### 3. Mantendo Atualizado
```mermaid
sequenceDiagram
    participant F as Feature Branch
    participant M as Main
    F->>M: git pull origin main
    M->>F: Atualiza Branch
    F->>F: Resolve Conflitos
```

## Boas Práticas

### 1. Nomes de Branches
```ascii
✅ feature/adiciona-login
✅ feature/perfil-usuario
✅ feature/chat-tempo-real

❌ feature/f1
❌ nova-coisa
❌ mudancas-jim
```

### 2. Commits Organizados
```mermaid
gitGraph
    commit
    branch feature/login
    checkout feature/login
    commit id: "feat: form base"
    commit id: "feat: validação"
    commit id: "test: casos login"
    commit id: "fix: feedback erro"
```

## Pull Requests

### Estrutura Ideal
```ascii
📝 Pull Request: Adiciona Sistema de Login

✨ O que foi feito:
- Form de login responsivo
- Validação de campos
- Integração com API
- Testes unitários

🔍 Como testar:
1. Checkout na branch
2. npm install
3. npm run test
4. Teste manual do form

📸 Screenshots:
[imagens do antes/depois]
```

## Resolução de Conflitos

```mermaid
graph TD
    A[Conflito Detectado] --> B{Tipo?}
    B -->|Simples| C[Resolve Local]
    B -->|Complexo| D[Consulta Time]
    C --> E[Testa]
    D --> E
    E --> F[Commit Resolution]
```

## Dicas de Sobrevivência

### 1. Mantenha as Features Pequenas
```ascii
Grande Feature ❌
├── 2 semanas
├── 50 arquivos
└── Difícil review

Features Menores ✅
├── 2-3 dias
├── 5-10 arquivos
└── Review tranquilo
```

### 2. Review Checklist
```mermaid
mindmap
    root((Code Review))
        Funcionalidade
            Requisitos OK
            Casos de Uso
        Qualidade
            Clean Code
            Performance
        Testes
            Unitários
            Integração
        Documentação
            Comentários
            README
```

## Métricas de Sucesso

```ascii
📊 Indicadores Saudáveis

Tempo de Branch     ┌────────────┐
2-3 dias           |██████░░░░░░| ✅

Tamanho do PR      ┌────────────┐
200-400 linhas     |████░░░░░░░░| ✅

Taxa de Aprovação  ┌────────────┐
Primeira review    |████████░░░░| ✅
```

## Conclusão

Feature Branch Workflow é como dirigir na sua própria pista: você tem liberdade para desenvolver no seu ritmo, mas sempre seguindo as regras de trânsito para chegar seguro ao destino!

```mermaid
mindmap
    root((Feature Branch))
        Isolamento
            Desenvolvimento Seguro
            Experimentos
        Qualidade
            Code Review
            Testes
        Colaboração
            Feedback
            Conhecimento
```