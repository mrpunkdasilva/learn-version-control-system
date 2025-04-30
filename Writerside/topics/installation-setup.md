# Instalação e Setup

## Instalação do Git

### Windows
1. Baixe o instalador em https://git-scm.com/download/windows
2. Execute o arquivo .exe baixado
3. Siga o assistente de instalação mantendo as opções padrão
4. Verifique a instalação abrindo o terminal:
```bash
git --version
```

### Linux (Debian/Ubuntu)
```bash
sudo apt-get update
sudo apt-get install git
```

### macOS
1. Via Homebrew:
```bash
brew install git
```
2. Ou baixe o instalador em https://git-scm.com/download/mac

## Configuração Inicial

### Identidade
Configure seu nome e email que serão usados nos commits:
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu.email@exemplo.com"
```

### Editor Padrão
Configure seu editor de texto preferido:
```bash
git config --global core.editor "code --wait"  # VS Code
git config --global core.editor "vim"          # Vim
git config --global core.editor "nano"         # Nano
```

### Verificar Configurações
Liste todas as configurações atuais:
```bash
git config --list
```

## Configurações Recomendadas

### Aliases Úteis
```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
```

### Merge e Diff
```bash
git config --global merge.tool vimdiff
git config --global diff.tool vimdiff
```

### Final de Linha
Windows:
```bash
git config --global core.autocrlf true
```

Linux/macOS:
```bash
git config --global core.autocrlf input
```

## Integrações

### Configurar SSH
1. Gerar chave SSH:
```bash
ssh-keygen -t ed25519 -C "seu.email@exemplo.com"
```

2. Adicionar ao ssh-agent:
```bash
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
```

3. Copiar chave pública:
```bash
cat ~/.ssh/id_ed25519.pub
```

4. Adicionar a chave no GitHub/GitLab

### Autenticação HTTPS
Para evitar digitar senha constantemente:
```bash
git config --global credential.helper store  # Permanente
git config --global credential.helper cache  # Temporário
```

## Troubleshooting

### Problemas Comuns

1. Git não reconhecido no terminal
   - Verifique a variável PATH
   - Reinstale o Git

2. Erro de autenticação
   - Verifique suas credenciais
   - Regenere suas chaves SSH
   - Use token de acesso pessoal

3. Problemas de configuração
   - Reset configurações: `git config --global --reset`
   - Reconfigurar do zero

## Próximos Passos

1. Verifique a instalação
2. Configure sua identidade
3. Configure seu editor
4. Configure suas chaves SSH
5. Teste um clone de repositório

Agora você está pronto para começar a usar o Git. Continue para [Primeiros Passos](first-steps.md).