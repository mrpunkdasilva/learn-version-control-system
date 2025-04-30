# Git Debug

```ascii
+------------------------+
|      Git Debug        |
|                       |
| Diagnóstico           |
| Troubleshooting       |
| Resolução             |
|                       |
| Debugging Avançado    |
+------------------------+
```

## Ferramentas de Debug

### Variáveis de Ambiente
```bash
# Debug geral
GIT_TRACE=1

# Debug específico
GIT_TRACE_PACKET=1     # Protocolo
GIT_TRACE_PACK_ACCESS=1 # Acesso packfile
GIT_TRACE_PERFORMANCE=1 # Performance
GIT_TRACE_SETUP=1      # Setup
GIT_CURL_VERBOSE=1     # HTTP
```

### Comandos Essenciais
```mermaid
mindmap
    root((Debug))
        Verificação
            fsck
            verify-pack
        Logs
            reflog
            log
        Estado
            status
            remote -v
```

## Técnicas de Diagnóstico

### Verificação de Integridade
```bash
# Verificar repositório
git fsck --full

# Verificar objetos
git verify-pack -v .git/objects/pack/*.idx

# Verificar refs
git for-each-ref --verify
```

### Análise de Logs
```ascii
+------------------------+
|    NÍVEIS DE LOG      |
|                       |
| • Trace              |
| • Debug              |
| • Info               |
| • Warning            |
| • Error              |
+------------------------+
```

## Problemas Comuns

### Network Issues
```mermaid
sequenceDiagram
    participant C as Client
    participant S as Server
    C->>S: git fetch
    S-->>C: timeout
    Note over C,S: Debug com GIT_CURL_VERBOSE
    C->>S: retry com trace
```

### Resolução
```bash
# Problemas de rede
GIT_CURL_VERBOSE=1 git clone <url>

# Problemas de autenticação
ssh -vT git@github.com

# Problemas de objeto
git prune && git gc
```

## Debug Avançado

### Análise de Performance
```bash
# Trace detalhado
GIT_TRACE_PERFORMANCE=1 git status

# Estatísticas de objetos
git count-objects -v

# Profiling
git maintenance run --task=gc --verbose
```

### Ferramentas Externas
```mermaid
mindmap
    root((Tools))
        Git
            git-bisect
            git-blame
        IDE
            debugger
            profiler
        Sistema
            strace
            dtrace
```

## Boas Práticas

### Prevenção
```ascii
+------------------------+
|    CHECKLIST          |
|                       |
| • Backup regular     |
| • Verificações       |
| • Manutenção        |
| • Monitoramento     |
| • Documentação      |
+------------------------+
```

### Workflow de Debug
1. Identificar sintomas
2. Coletar informações
3. Reproduzir problema
4. Analisar logs
5. Aplicar solução
6. Verificar resolução

## Automação

### Scripts Úteis
```bash
#!/bin/bash
# Debug completo
debug_git() {
    export GIT_TRACE=1
    export GIT_TRACE_PERFORMANCE=1
    export GIT_TRACE_PACKET=1
    git "$@"
    unset GIT_TRACE GIT_TRACE_PERFORMANCE GIT_TRACE_PACKET
}
```

### Monitoramento
```mermaid
graph TD
    A[Coleta] -->|Logs| B[Análise]
    B -->|Alertas| C[Ação]
    C -->|Resolução| D[Verificação]
```

## Recuperação

### Dados Perdidos
```bash
# Recuperar commits deletados
git reflog

# Recuperar arquivos deletados
git fsck --lost-found

# Restaurar estado anterior
git reset --hard HEAD@{1}
```

### Corrupção
```bash
# Verificar e reparar
git fsck --full
git prune
git gc --aggressive

# Clonar novamente se necessário
git clone --mirror <url>
```

## Próximos Passos

### Tópicos Relacionados
- [Git Bisect](git-bisect.md)
- [Git Performance](git-performance.md)
- [Git Maintenance](git-maintenance.md)

> **Dica Pro**: Mantenha um registro de problemas encontrados e suas soluções para referência futura.