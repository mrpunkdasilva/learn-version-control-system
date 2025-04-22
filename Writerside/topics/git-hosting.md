# Hospedagem Git: Plataformas e Soluções

```ascii
+------------------------+
|    Git Hosting        |
|                       |
| Cloud Services       |
| Self-Hosted         |
| Features            |
|                       |
| Platform Choice     |
+------------------------+
```

## Plataformas Principais

### Comparativo
```mermaid
mindmap
    root((Hosting))
        GitHub
            Actions
            Packages
            Pages
            Codespaces
        GitLab
            CI/CD
            Registry
            Wiki
            Issues
        Bitbucket
            Pipelines
            Jira
            Confluence
            Bamboo
```

## Critérios de Escolha

### Fatores Decisivos
```ascii
+------------------------+
|    CONSIDERAR         |
|                       |
| • Custo              |
| • Integração         |
| • Escalabilidade     |
| • Segurança          |
| • Compliance         |
| • Suporte            |
+------------------------+
```

### Comparativo de Preços
```mermaid
graph TD
    A[Preços] --> B[GitHub]
    A --> C[GitLab]
    A --> D[Bitbucket]
    B --> E[Free/Team/Enterprise]
    C --> F[Free/Premium/Ultimate]
    D --> G[Free/Standard/Premium]
```

## Self-Hosted vs Cloud

### Análise
```mermaid
mindmap
    root((Hosting Type))
        Cloud
            Managed
            Scalable
            Pay-as-you-go
        Self-Hosted
            Control
            Compliance
            Customization
```

## Próximos Passos

### Tópicos Relacionados
- [GitHub Specific](github-specific.md)
- [GitLab Specific](gitlab-specific.md)
- [Bitbucket Specific](bitbucket-specific.md)
- [Self-Hosted Git](self-hosted-git.md)

> **Dica Pro**: Avalie cuidadosamente as necessidades específicas do seu projeto e equipe antes de escolher uma plataforma.