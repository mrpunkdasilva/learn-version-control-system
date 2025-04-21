# Melhores Práticas em Controle de Versão

O controle de versão é fundamental para o desenvolvimento de software moderno. Aqui estão as práticas essenciais para manter seu código organizado e sua equipe produtiva.

## Por que Seguir Boas Práticas?
```mermaid
mindmap
    root((Benefícios))
        Qualidade
            Código Limpo
            Rastreabilidade
        Produtividade
            Menos Conflitos
            Colaboração Eficiente
        Segurança
            Backup
            Auditoria
```

## Princípios Fundamentais

### 1. Consistência
- Mantenha padrões de código
- Siga convenções de commit
- Use nomenclatura uniforme

### 2. Atomicidade
- Commits pequenos e focados
- Uma feature por branch
- Mudanças relacionadas juntas

### 3. Rastreabilidade
- Commits descritivos
- Referência a issues
- Documentação atualizada

## Organização de Repositório

### Estrutura de Diretórios
```
projeto/
├── src/
├── tests/
├── docs/
├── .gitignore
└── README.md
```

### Arquivos Essenciais
- README.md
- .gitignore
- CONTRIBUTING.md
- LICENSE

## Commits

### Anatomia de um Bom Commit
```mermaid
mindmap
    root((Commit))
        Título
            Curto
            Descritivo
            Imperativo
        Corpo
            Contexto
            Motivação
            Impacto
        Metadados
            Issue ID
            Breaking Changes
            Co-authors
```

### Padrão de Mensagens
```mermaid
graph TD
    A[Tipo] -->|Ex: feat, fix| B[Escopo]
    B -->|Ex: auth, api| C[Descrição]
    C -->|Imperativo| D[Corpo]
    D -->|Opcional| E[Footer]
```

### Convenção de Commits
```ascii
<tipo>(<escopo>): <descrição>

[corpo]

[footer]

Exemplos:
✅ feat(auth): adiciona autenticação via Google
✅ fix(api): corrige timeout em requisições longas
✅ docs(readme): atualiza instruções de instalação
✅ style(login): ajusta layout responsivo
✅ refactor(core): migra para TypeScript
✅ test(unit): adiciona testes para módulo de pagamento
```

### Tipos de Commit
```mermaid
mindmap
    root((Tipos))
        Funcionalidades
            feat
            fix
        Código
            refactor
            style
        Documentação
            docs
            comments
        Infraestrutura
            build
            ci
        Testes
            test
            perf
```

### Fluxo de Trabalho
```mermaid
sequenceDiagram
    participant D as Developer
    participant G as Git
    participant R as Review
    D->>D: Codifica mudanças
    D->>D: Testa localmente
    D->>G: git add [files]
    D->>G: git commit -m "mensagem"
    G->>R: Push para review
    R->>D: Feedback
    D->>G: Ajustes se necessário
```

### Commits Atômicos
```mermaid
graph TD
    A[Uma mudança lógica] --> B[Commit único]
    B --> C{É atômico?}
    C -->|Sim| D[Perfect!]
    C -->|Não| E[Dividir em<br>múltiplos commits]
    E --> A
```

### O que Evitar
```ascii
❌ Commits Ruins:
└── "correções"
└── "wip"
└── "updates"
└── "fix bugs"
└── "commit final"
└── "alterações diversas"

✅ Commits Bons:
└── "feat(user): adiciona validação de email"
└── "fix(auth): corrige refresh token expirado"
└── "refactor(api): simplifica tratamento de erros"
└── "docs(swagger): atualiza documentação da API"
```

### Dicas para Commits Efetivos
```mermaid
mindmap
    root((Commits))
        Quando Commitar
            Mudança completa
            Testes passando
            Código revisado
        Como Commitar
            Mensagem clara
            Mudanças relacionadas
            Tamanho adequado
        Por que Commitar
            Histórico claro
            Rastreabilidade
            Colaboração
```

### Ferramentas Úteis
```mermaid
mindmap
    root((Tools))
        Conventional Commits
            commitlint
            commitizen
        Git Hooks
            husky
            pre-commit
        Automação
            semantic-release
            standard-version
```

### Revisão de Commits
```mermaid
graph TD
    A[Novo Commit] --> B{Checklist}
    B --> C[Mensagem clara?]
    B --> D[Mudança atômica?]
    B --> E[Testes incluídos?]
    B --> F[Documentação atualizada?]
    C & D & E & F --> G[Commit aprovado]
```

### Boas Práticas de Reescrita
```ascii
🔄 Reescrita de Commits

Local (antes do push):
├── git commit --amend
├── git rebase -i
└── git reset

Remoto (com cuidado):
├── Squash merges
├── Rebase time
└── Force push (-f)
```

## Gerenciamento de Branches

### Fluxo de Desenvolvimento
```mermaid
gitGraph
    commit
    branch develop
    checkout develop
    commit
    branch feature/login
    checkout feature/login
    commit
    commit
    checkout develop
    merge feature/login
    branch feature/profile
    checkout feature/profile
    commit
    commit
    checkout develop
    merge feature/profile
    checkout main
    merge develop
```

### Estrutura de Branches
```mermaid
graph TD
    A[main] --> B[develop]
    B --> C[feature/*]
    B --> D[bugfix/*]
    A --> E[hotfix/*]
    B --> F[release/*]
```

### Ciclo de Vida de uma Branch
```mermaid
sequenceDiagram
    participant M as Main
    participant D as Develop
    participant F as Feature
    participant R as Review
    D->>F: Criar branch
    F->>F: Desenvolvimento
    F->>F: Testes locais
    F->>R: Pull Request
    R->>F: Code Review
    F->>F: Ajustes
    F->>D: Merge
    D->>M: Release
```

### Convenções de Nomenclatura
```mermaid
mindmap
    root((Branches))
        Feature
            feature/login
            feature/user-profile
        Bugfix
            bugfix/login-error
            bugfix/profile-crash
        Hotfix
            hotfix/security-fix
            hotfix/critical-bug
        Release
            release/1.0.0
            release/2.0.0
```

## Code Review

### Checklist
- [ ] Código segue padrões
- [ ] Testes adicionados/atualizados
- [ ] Documentação atualizada
- [ ] Performance considerada
- [ ] Segurança verificada

### Feedback Construtivo
- Foco no código, não no desenvolvedor
- Sugestões específicas
- Explicações claras
- Reconhecimento de boas práticas