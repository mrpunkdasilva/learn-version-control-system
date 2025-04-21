# Gitflow Workflow

Se o Feature Branch é uma festa na casa do Stifler, o Gitflow é o baile de formatura - tem regras, tem estrutura, mas ainda é divertido!

## Estrutura Principal

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
    branch release/1.0
    checkout release/1.0
    commit
    checkout main
    merge release/1.0
    checkout develop
    merge release/1.0
```

## Branches Principais

### 1. Main e Develop
```mermaid
graph TD
    A[main] -->|"Sempre estável"| B[Produção]
    C[develop] -->|"Próxima versão"| D[Desenvolvimento]
    C -->|"Release pronta"| A
```

### 2. Branches de Suporte
```mermaid
mindmap
    root((Gitflow))
        Feature
            Nova funcionalidade
            Sai de develop
            Merge em develop
        Release
            Preparação
            Bugfix
            Merge em main/develop
        Hotfix
            Correção urgente
            Sai de main
            Merge em main/develop
```

## Ciclo de Vida

### 1. Feature Development
```mermaid
sequenceDiagram
    participant D as Develop
    participant F as Feature
    D->>F: branch feature/nova
    F->>F: Desenvolvimento
    F->>F: Testes
    F->>D: Merge quando pronto
```

### 2. Preparação de Release
```mermaid
gitGraph
    commit
    branch develop
    checkout develop
    commit
    branch release/1.0
    checkout release/1.0
    commit id: "bump version"
    commit id: "fix bugs"
    checkout main
    merge release/1.0
    checkout develop
    merge release/1.0
```

### 3. Hotfix em Produção
```mermaid
gitGraph
    commit
    branch hotfix/bug
    checkout hotfix/bug
    commit id: "fix critical"
    checkout main
    merge hotfix/bug
    checkout develop
    merge hotfix/bug
```

## Comandos Essenciais

### 1. Iniciando Gitflow
```bash
git flow init
```

### 2. Features
```bash
# Iniciar feature
git flow feature start login

# Finalizar feature
git flow feature finish login
```

### 3. Releases
```bash
# Criar release
git flow release start 1.0.0

# Finalizar release
git flow release finish 1.0.0
```

### 4. Hotfixes
```bash
# Criar hotfix
git flow hotfix start bug-critical

# Finalizar hotfix
git flow hotfix finish bug-critical
```

## Fluxo de Trabalho Completo

```mermaid
graph TD
    A[develop] -->|feature start| B[feature/nova]
    B -->|feature finish| A
    A -->|release start| C[release/1.0]
    C -->|release finish| D[main]
    C -->|release finish| A
    D -->|hotfix start| E[hotfix/bug]
    E -->|hotfix finish| D
    E -->|hotfix finish| A
```

## Boas Práticas

### 1. Nomenclatura
```ascii
Features:
  feature/login
  feature/user-profile

Releases:
  release/1.0.0
  release/2.1.0

Hotfixes:
  hotfix/security-fix
  hotfix/crash-bug
```

### 2. Versionamento
```mermaid
mindmap
    root((Versão))
        Major
            Breaking Changes
            1.0.0 -> 2.0.0
        Minor
            Novas Features
            1.0.0 -> 1.1.0
        Patch
            Bugfixes
            1.0.0 -> 1.0.1
```

## Quando Usar Gitflow?

```mermaid
mindmap
    root((Ideal Para))
        Releases Planejadas
            Ciclos definidos
            Versões numeradas
        Múltiplos Ambientes
            Dev
            QA
            Prod
        Equipes Grandes
            Processos claros
            Responsabilidades definidas
```

## Prós e Contras

### Vantagens
```ascii
✅ Estrutura clara e definida
✅ Ideal para releases planejadas
✅ Suporte a hotfixes
✅ Processos bem documentados
```

### Desvantagens
```ascii
❌ Mais complexo que feature branch
❌ Overhead para projetos pequenos
❌ Curva de aprendizado maior
❌ Pode ser "pesado" demais
```

## Dicas de Implementação

### 1. Ferramentas de Suporte
```mermaid
mindmap
    root((Tools))
        Git Flow CLI
            Comandos automatizados
            Menos erros
        IDE Plugins
            Visual feedback
            Integração
        CI/CD
            Automação
            Qualidade
```

### 2. Checklist de Release
```ascii
📋 Release Checklist

1. [ ] Feature freeze
2. [ ] Criar branch release
3. [ ] Bump version
4. [ ] Testes de regressão
5. [ ] Documentação
6. [ ] Code freeze
7. [ ] Deploy staging
8. [ ] Merge em main
9. [ ] Tag version
10.[ ] Deploy prod
```

## Conclusão

Gitflow é como um roteiro de filme bem planejado - tem pré-produção (develop), filmagem (features), edição (release) e até correções de última hora (hotfix). Quando bem executado, o resultado é um blockbuster!

```mermaid
mindmap
    root((Sucesso))
        Planejamento
            Branches corretas
            Momento certo
        Execução
            Seguir workflow
            Manter padrões
        Manutenção
            Releases limpas
            Hotfixes rápidos
```