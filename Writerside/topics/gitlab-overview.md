# GitLab: Visão Geral

```ascii
+------------------------+
|        GitLab         |
|                       |
| DevOps Completo       |
| Ciclo de Vida         |
| Colaboração           |
|                       |
| Tudo em Um            |
+------------------------+
```

## O que é GitLab?

O GitLab é uma plataforma DevOps completa, entregue como uma única aplicação. Ele abrange todo o ciclo de vida DevOps, permitindo que equipes colaborem, desenvolvam, testem, implantem e monitorem aplicações em um único ambiente.

```mermaid
mindmap
    root((GitLab))
        SCM
            Git
            Branches
            MRs
        CI/CD
            Pipelines
            Runners
            Environments
        Planejamento
            Issues
            Boards
            Milestones
        Segurança
            SAST
            DAST
            Dependency Scanning
        Monitoramento
            Metrics
            Logs
            Alerts
```

## Edições do GitLab

### Comparação
```ascii
+------------------------+
|      EDIÇÕES          |
|                       |
| • Community Edition   |
|   - Open Source       |
|   - Gratuito          |
|                       |
| • Enterprise Edition  |
|   - Comercial         |
|   - Recursos extras   |
|                       |
| • SaaS (gitlab.com)   |
|   - Hospedado         |
|   - Planos variados   |
+------------------------+
```

### Recursos por Edição
```mermaid
graph TD
    A[GitLab] --> B[CE]
    A --> C[EE]
    B --> D[Recursos Básicos]
    C --> D
    C --> E[Recursos Enterprise]
    E --> F[Governança]
    E --> G[Segurança Avançada]
    E --> H[Gerenciamento]
```

## Arquitetura

### Componentes
```mermaid
graph TD
    A[Frontend] --> B[Rails]
    B --> C[PostgreSQL]
    B --> D[Redis]
    B --> E[Sidekiq]
    F[GitLab Runner] -.-> B
    G[GitLab Shell] --> B
    H[Gitaly] --> B
```

### Serviços
```ascii
+------------------------+
|     COMPONENTES       |
|                       |
| • Nginx               |
| • Unicorn/Puma        |
| • Sidekiq             |
| • Redis               |
| • PostgreSQL          |
| • Gitaly              |
| • GitLab Workhorse    |
| • GitLab Shell        |
+------------------------+
```

## Principais Recursos

### Gerenciamento de Código
- Repositórios Git
- Merge Requests
- Code Review
- Web IDE
- Snippets

### CI/CD
```mermaid
sequenceDiagram
    participant D as Dev
    participant P as Pipeline
    participant E as Env
    D->>P: Push code
    P->>P: Build
    P->>P: Test
    P->>P: Security Scan
    P->>E: Deploy
```

### Planejamento e Monitoramento
- Issues
- Boards
- Milestones
- Epics (EE)
- Roadmaps (EE)
- Métricas e Analytics

## Comparação com Outras Plataformas

### GitLab vs GitHub
```ascii
+------------------------+
|   GitLab vs GitHub    |
|                       |
| GitLab:               |
| • DevOps completo     |
| • CI/CD integrado     |
| • Self-hosted fácil   |
|                       |
| GitHub:               |
| • Maior comunidade    |
| • Actions             |
| • Melhor UX           |
+------------------------+
```

### GitLab vs Bitbucket
```mermaid
mindmap
    root((Comparação))
        GitLab
            DevOps completo
            CI/CD nativo
            Community Edition
        Bitbucket
            Integração Jira
            Pipelines
            Data Center
```

## Próximos Passos

### Tópicos Relacionados
- [Instalação do GitLab](gitlab-installation.md)
- [Configuração do GitLab](gitlab-configuration.md)
- [Configuração SSH no GitLab](gitlab-ssh-setup.md)
- [CI/CD no GitLab](gitlab-ci-cd.md)

> **Dica Pro**: O GitLab oferece uma experiência DevOps completa, mas comece com os recursos básicos e vá expandindo conforme sua equipe se familiariza com a plataforma.