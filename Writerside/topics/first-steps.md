# Primeiros Passos

## Iniciando um Repositório

### Novo Repositório
```bash
mkdir meu-projeto
cd meu-projeto
git init
```

### Clonar Repositório Existente
```bash
git clone https://github.com/usuario/repositorio.git
git clone git@github.com:usuario/repositorio.git  # Via SSH
```

## Ciclo Básico do Git

### Status do Repositório
```bash
git status  # Ver estado atual
git log     # Ver histórico
```

### Adicionando Arquivos
```bash
git add arquivo.txt          # Arquivo específico
git add .                    # Todos os arquivos
git add diretorio/*         # Todo conteúdo do diretório
```

### Criando Commits
```bash
git commit -m "Mensagem descritiva do commit"
git commit -am "Commit com add automático"
```

## Trabalhando com Branches

### Gerenciamento Básico
```bash
git branch                   # Listar branches
git branch nova-feature     # Criar branch
git checkout nova-feature   # Mudar de branch
git checkout -b outra-feature # Criar e mudar
```

### Merge de Branches
```bash
git checkout main           # Volta para main
git merge nova-feature     # Merge da feature
```

## Sincronização com Remoto

### Configurar Remoto
```bash
git remote add origin https://github.com/usuario/repo.git
git remote -v              # Listar remotos
```

### Push e Pull
```bash
git push origin main      # Enviar alterações
git pull origin main      # Receber alterações
```

## Boas Práticas

### Commits
1. Mensagens claras e descritivas
2. Um commit por alteração lógica
3. Prefixos comuns:
   - feat: nova funcionalidade
   - fix: correção de bug
   - docs: documentação
   - style: formatação
   - refactor: refatoração
   - test: testes

### Branches
1. Nomes descritivos
2. Use prefixos:
   - feature/
   - bugfix/
   - hotfix/
   - release/

## Fluxo de Trabalho Básico

1. Atualizar branch principal
```bash
git checkout main
git pull origin main
```

2. Criar branch de feature
```bash
git checkout -b feature/nova-funcionalidade
```

3. Fazer alterações
```bash
git add .
git commit -m "feat: adiciona nova funcionalidade"
```

4. Enviar alterações
```bash
git push origin feature/nova-funcionalidade
```

## Resolução de Problemas

### Reverter Alterações
```bash
git checkout -- arquivo.txt  # Descarta alterações
git reset --hard HEAD       # Reseta para último commit
git revert commit-hash      # Reverte commit específico
```

### Correções Comuns
```bash
git commit --amend          # Corrigir último commit
git reset HEAD arquivo.txt  # Remover do stage
```

## Próximos Passos

1. Pratique os comandos básicos
2. Crie alguns repositórios de teste
3. Experimente trabalhar com branches
4. Faça push/pull com repositório remoto
5. Avance para [Workflows](workflow-automation.md)

## Exercícios Práticos

1. Crie um novo repositório
2. Adicione alguns arquivos
3. Faça commits
4. Crie uma branch
5. Faça merge
6. Sincronize com GitHub

Lembre-se: a prática leva à perfeição. Quanto mais você usar estes comandos, mais natural o fluxo se tornará.