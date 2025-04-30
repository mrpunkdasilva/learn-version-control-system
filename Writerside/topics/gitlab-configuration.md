# Configuração do GitLab

```ascii
+------------------------+
| GitLab Configuration  |
|                       |
| Personalização        |
| Integração            |
| Segurança             |
| Performance           |
|                       |
| Adaptação Completa    |
+------------------------+
```

## Configuração Básica

### Arquivo de Configuração Principal
O arquivo principal de configuração do GitLab é o `/etc/gitlab/gitlab.rb` para instalações Omnibus. Todas as configurações são centralizadas neste arquivo.

```bash
# Editar configuração
sudo vim /etc/gitlab/gitlab.rb

# Aplicar alterações
sudo gitlab-ctl reconfigure
```

### URL Externa
```ruby
# /etc/gitlab/gitlab.rb
external_url 'https://gitlab.exemplo.com'
```

### Configurações de HTTPS
```ruby
# /etc/gitlab/gitlab.rb
# Habilitar HTTPS
external_url 'https://gitlab.exemplo.com'
nginx['redirect_http_to_https'] = true

# Certificados Let's Encrypt
letsencrypt['enable'] = true
letsencrypt['contact_emails'] = ['admin@exemplo.com']

# Certificados personalizados
nginx['ssl_certificate'] = "/etc/gitlab/ssl/gitlab.exemplo.com.crt"
nginx['ssl_certificate_key'] = "/etc/gitlab/ssl/gitlab.exemplo.com.key"
```

## Personalização da Interface

### Logo e Aparência
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['gitlab_logo'] = 'logo.png'
gitlab_rails['gitlab_favicon'] = 'favicon.ico'

# Cores e estilo
gitlab_rails['brand_primary_color'] = '#1d75b3'
gitlab_rails['brand_secondary_color'] = '#107a10'
```

### Página de Login
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['gitlab_signin_enabled'] = true
gitlab_rails['gitlab_signin_text'] = 'Bem-vindo ao GitLab da Empresa XYZ'
```

## Configuração de Email

### SMTP
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['smtp_enable'] = true
gitlab_rails['smtp_address'] = "smtp.office365.com"
gitlab_rails['smtp_port'] = 587
gitlab_rails['smtp_user_name'] = "gitlab@empresa.com"
gitlab_rails['smtp_password'] = "senha-segura"
gitlab_rails['smtp_domain'] = "empresa.com"
gitlab_rails['smtp_authentication'] = "login"
gitlab_rails['smtp_enable_starttls_auto'] = true
gitlab_rails['gitlab_email_from'] = 'gitlab@empresa.com'
gitlab_rails['gitlab_email_reply_to'] = 'noreply@empresa.com'
```

### Testando Configuração de Email
```bash
# Testar configuração de email
sudo gitlab-rails console

# No console Rails
Notify.test_email('seu-email@exemplo.com', 'Assunto', 'Corpo').deliver_now
```

## Autenticação e Autorização

### LDAP
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['ldap_enabled'] = true
gitlab_rails['ldap_servers'] = {
  'main' => {
    'label' => 'LDAP Corporativo',
    'host' =>  'ldap.empresa.com',
    'port' => 389,
    'uid' => 'sAMAccountName',
    'encryption' => 'plain',
    'bind_dn' => 'CN=GitLab,OU=Service Accounts,DC=empresa,DC=com',
    'password' => 'senha-ldap',
    'active_directory' => true,
    'base' => 'OU=Users,DC=empresa,DC=com',
    'user_filter' => ''
  }
}
```

### OAuth (Google, GitHub, etc)
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['omniauth_enabled'] = true
gitlab_rails['omniauth_allow_single_sign_on'] = ['google_oauth2', 'github']
gitlab_rails['omniauth_block_auto_created_users'] = false
gitlab_rails['omniauth_providers'] = [
  {
    "name" => "google_oauth2",
    "app_id" => "YOUR_APP_ID",
    "app_secret" => "YOUR_APP_SECRET",
    "args" => { "access_type" => "offline", "approval_prompt" => "" }
  },
  {
    "name" => "github",
    "app_id" => "YOUR_APP_ID",
    "app_secret" => "YOUR_APP_SECRET",
    "args" => { "scope" => "user:email" }
  }
]
```

## Configuração de Armazenamento

### Armazenamento de Objetos (S3)
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['object_store']['enabled'] = true
gitlab_rails['object_store']['connection'] = {
  'provider' => 'AWS',
  'region' => 'us-east-1',
  'aws_access_key_id' => 'SUA_ACCESS_KEY',
  'aws_secret_access_key' => 'SUA_SECRET_KEY',
  'endpoint' => 'https://s3.amazonaws.com'
}

# Configurar LFS, Artifacts, Uploads, etc
gitlab_rails['lfs_object_store_enabled'] = true
gitlab_rails['lfs_object_store_remote_directory'] = 'gitlab-lfs-objects'
```

### Configuração de Backup
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['backup_path'] = "/var/opt/gitlab/backups"
gitlab_rails['backup_archive_permissions'] = 0644
gitlab_rails['backup_keep_time'] = 604800  # 7 dias em segundos
```

## Configuração de Performance

### Recursos do Sistema
```ruby
# /etc/gitlab/gitlab.rb
puma['worker_processes'] = 4
puma['max_threads'] = 4
postgresql['shared_buffers'] = "2GB"
postgresql['work_mem'] = "128MB"
```

### Caching com Redis
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['redis_cache_instance'] = "redis://:password@redis-cache.example.com:6379/0"
gitlab_rails['redis_queues_instance'] = "redis://:password@redis-queues.example.com:6379/0"
gitlab_rails['redis_shared_state_instance'] = "redis://:password@redis-shared-state.example.com:6379/0"
```

## Configuração de Segurança

### Restrições de Registro
```ruby
# /etc/gitlab/gitlab.rb
gitlab_rails['gitlab_signup_enabled'] = false
gitlab_rails['gitlab_signin_enabled'] = true
gitlab_rails['gitlab_restricted_visibility_levels'] = ['public']
gitlab_rails['gitlab_default_projects_features_issues'] = true
```

### Configuração de Firewall
```bash
# Configurar firewall (Ubuntu/Debian)
sudo ufw allow http
sudo ufw allow https
sudo ufw allow OpenSSH

# Verificar regras
sudo ufw status
```

## Monitoramento e Logs

### Prometheus e Grafana
```ruby
# /etc/gitlab/gitlab.rb
prometheus['enable'] = true
grafana['enable'] = true
grafana['admin_password'] = 'senha-segura'
```

### Configuração de Logs
```ruby
# /etc/gitlab/gitlab.rb
logging['logrotate_frequency'] = "daily"
logging['logrotate_size'] = "10M"
logging['logrotate_rotate'] = 30
```

## Integração com Runners

### Registro de Runner
```bash
# Instalar GitLab Runner
curl -L https://packages.gitlab.com/install/repositories/runner/gitlab-runner/script.deb.sh | sudo bash
sudo apt-get install gitlab-runner

# Registrar Runner
sudo gitlab-runner register
```

### Configuração de Runner
```toml
# /etc/gitlab-runner/config.toml
[[runners]]
  name = "docker-runner"
  url = "https://gitlab.exemplo.com"
  token = "TOKEN"
  executor = "docker"
  [runners.docker]
    tls_verify = false
    image = "docker:latest"
    privileged = true
```

## Configurações Avançadas

### Alta Disponibilidade
```ruby
# /etc/gitlab/gitlab.rb no nó primário
roles ['redis_master', 'redis_sentinel', 'postgres_master', 'pgbouncer', 'consul_server']
postgresql['listen_address'] = '0.0.0.0'
redis['bind'] = '0.0.0.0'
```

### Geo Replication
```ruby
# /etc/gitlab/gitlab.rb no nó primário
gitlab_rails['geo_primary_role'] = true

# /etc/gitlab/gitlab.rb no nó secundário
gitlab_rails['geo_secondary_role'] = true
gitlab_rails['geo_secondary_name'] = 'secondary-site'
gitlab_rails['geo_node_name'] = 'secondary-site'
```

## Próximos Passos

### Tópicos Relacionados
- [Configuração SSH no GitLab](gitlab-ssh-setup.md)
- [Configuração CI/CD](gitlab-ci-setup.md)
- [Segurança no GitLab](gitlab-security-setup.md)
- [Backup e Restauração](gitlab-backup-setup.md)

> **Dica Pro**: Mantenha um ambiente de teste para validar alterações de configuração antes de aplicá-las em produção. Sempre faça backup antes de grandes mudanças.