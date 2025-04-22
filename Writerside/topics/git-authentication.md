# Autenticação no Git

## Métodos de Autenticação

### Visão Geral
```mermaid
mindmap
    root((Autenticação))
        SSH
            Chaves
            Config
            Agent
        HTTPS
            Tokens
            Credentials
            2FA
        Outros
            Kerberos
            LDAP
            OAuth
```

## SSH

### Configuração
```bash
# Gerar chave SSH
ssh-keygen -t ed25519 -C "email@example.com"

# Iniciar ssh-agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519

# Testar conexão
ssh -T git@github.com
```

### Estrutura
```ascii
~/.ssh/
├── config
├── id_ed25519
├── id_ed25519.pub
└── known_hosts
```

## HTTPS

### Token de Acesso
```mermaid
sequenceDiagram
    participant U as Usuário
    participant G as Git Host
    participant R as Repositório
    
    U->>G: Solicita token
    G->>U: Gera token
    U->>R: Clone/Push com token
    R->>G: Valida token
    G->>R: Autoriza acesso
```

### Credential Helper
```bash
# Windows
git config --global credential.helper manager

# macOS
git config --global credential.helper osxkeychain

# Linux
git config --global credential.helper cache
```

## Multi-Factor Authentication (MFA)

### Fluxo 2FA
```mermaid
graph TD
    A[Login] -->|Senha| B[1º Fator]
    B -->|Token| C[2º Fator]
    C -->|Sucesso| D[Acesso]
    C -->|Falha| E[Bloqueio]
```

### Configuração
1. Aplicativo autenticador
2. SMS/Email backup
3. Chaves de recuperação
4. Dispositivos confiáveis

## Gestão de Credenciais

### Boas Práticas
```ascii
+------------------------+
|    BOAS PRÁTICAS      |
|                       |
| • Rotação regular     |
| • Escopos mínimos    |
| • Auditoria de uso   |
| • Backup seguro      |
| • Revogação rápida   |
+------------------------+
```

### Automação
```yaml
name: Token Rotation
on:
  schedule:
    - cron: '0 0 1 * *'
jobs:
  rotate:
    runs-on: ubuntu-latest
    steps:
      - name: Rotate credentials
        run: ./rotate-credentials.sh
```

## Troubleshooting

### Problemas Comuns
```mermaid
mindmap
    root((Problemas))
        SSH
            Permissões
            Chave inválida
            Agent
        HTTPS
            Token expirado
            Cache
            Proxy
        2FA
            Sincronização
            Backup codes
            Device lost
```

### Soluções
```bash
# Verificar SSH
ssh -vT git@github.com

# Limpar cache
git credential-cache exit

# Testar conexão
git ls-remote
```

## Integração Enterprise

### LDAP/AD
```mermaid
graph LR
    A[Git Client] -->|Auth| B[LDAP]
    B -->|Validate| C[AD]
    C -->|Groups| D[Permissions]
```

### SSO
1. SAML 2.0
2. OAuth 2.0
3. OpenID Connect
4. Custom providers

## Monitoramento

### Auditoria
```mermaid
graph TD
    A[Login] -->|Log| B[Eventos]
    B -->|Análise| C[Alertas]
    C -->|Ação| D[Resposta]
```

### Métricas
1. Tentativas de login
2. Falhas de autenticação
3. Token usage
4. MFA compliance

## Próximos Passos

### Tópicos Relacionados
- Políticas de acesso
- Gestão de identidade
- Automação de segurança
- Compliance

> **Dica Pro**: Implemente uma estratégia de autenticação em camadas, combinando diferentes métodos para maior segurança.