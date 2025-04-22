# Git e DevOps

## Integração Contínua

### Pipeline Básico
```mermaid
graph LR
    A[Git Push] -->|Trigger| B[Build]
    B -->|Success| C[Test]
    C -->|Pass| D[Deploy]
    D -->|Success| E[Monitor]
```

## Automação

### GitHub Actions
```yaml
name: CI/CD
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Build
        run: make build
      - name: Test
        run: make test
      - name: Deploy
        if: github.ref == 'refs/heads/main'
        run: make deploy
```

## Infrastructure as Code

### Git + IaC
```mermaid
mindmap
    root((IaC))
        Terraform
            State
            Modules
        Ansible
            Playbooks
            Roles
        Kubernetes
            Manifests
            Helm
```

## Monitoramento

### Métricas DevOps
```mermaid
graph TD
    A[Código] -->|Git| B[Métricas]
    B --> C[Lead Time]
    B --> D[Deploy Frequency]
    B --> E[MTTR]
    B --> F[Change Failure]
```

## Segurança

### DevSecOps
```ascii
+------------------------+
|     SEGURANÇA         |
|                       |
| • SAST              |
| • DAST              |
| • SCA               |
| • IAST              |
| • Secrets Scan      |
+------------------------+
```

## Deployment

### Estratégias
```mermaid
mindmap
    root((Deploy))
        Blue/Green
            Zero downtime
            Quick rollback
        Canary
            Gradual
            Monitored
        Rolling
            Continuous
            Resource efficient
```

## Ferramentas

### Stack DevOps
```mermaid
graph TD
    A[Git] -->|Source| B[Jenkins/GitLab CI]
    B -->|Build| C[Docker]
    C -->|Deploy| D[Kubernetes]
    D -->|Monitor| E[Prometheus]
```

## Boas Práticas

### Guidelines
1. Trunk-based development
2. Feature flags
3. Automated testing
4. Continuous feedback
5. Infrastructure as Code

### Workflow
```mermaid
sequenceDiagram
    participant D as Dev
    participant G as Git
    participant CI as CI/CD
    participant P as Prod
    D->>G: Push
    G->>CI: Trigger
    CI->>CI: Build & Test
    CI->>P: Deploy
```

## Observabilidade

### Componentes
```mermaid
mindmap
    root((Observability))
        Logs
            ELK
            Splunk
        Métricas
            Prometheus
            Grafana
        Traces
            Jaeger
            Zipkin
```

## Recuperação

### Disaster Recovery
```mermaid
graph TD
    A[Incident] -->|Detect| B[Alert]
    B -->|Analyze| C[Response]
    C -->|Fix| D[Recovery]
    D -->|Learn| E[Improve]
```

## Próximos Passos

### Tópicos Relacionados
- [CI/CD Integration](ci-cd-integration.md)
- [Git Security](git-security.md)
- [Workflow Automation](workflow-automation.md)

> **Dica Pro**: Use feature flags para separar deploy de release e permitir rollback rápido em caso de problemas.