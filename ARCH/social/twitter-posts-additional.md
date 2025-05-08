# Posts Adicionais para Twitter (X)

## Dicas Rápidas

### Post 6: Bisect
```
💡 #GitTip

Encontre bugs com precisão cirúrgica:

git bisect start
git bisect bad  # versão atual com bug
git bisect good v1.0  # versão antiga sem bug
# Git fará busca binária automática!

Descubra exatamente qual commit introduziu o problema.

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 7: Reflog
```
💡 #GitTip

Perdeu um commit após reset --hard?

git reflog
# encontre o hash do commit perdido
git checkout -b recuperado [hash]

O reflog é sua rede de segurança no Git!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 8: Worktree
```
💡 #GitTip

Precisa trabalhar em múltiplas branches simultaneamente?

git worktree add ../feature-x feature/x
cd ../feature-x
# trabalhe na branch sem precisar de stash/checkout

Múltiplos workspaces do mesmo repo!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 9: Hooks
```
💡 #GitTip

Automatize verificações antes de commits:

echo '#!/bin/sh
npm test' > .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit

Evite commits que quebram testes!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 10: Sparse Checkout
```
💡 #GitTip

Repositório gigante mas só precisa de uma pasta?

git clone --no-checkout repo-url
cd repo
git sparse-checkout init
git sparse-checkout set path/que/preciso
git checkout

Economize espaço e tempo!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

## Threads Educativas

### Thread 3: Git para Iniciantes
```
🧵 THREAD: Git para iniciantes - do zero ao primeiro PR

1/8 Começando com Git? Esta thread vai te levar do zero ao seu primeiro Pull Request. Vamos lá!

#Git #GitPie 🥧
```

```
2/8 Instalação:

Windows: https://git-scm.com/download/win
Mac: brew install git
Linux: apt/yum install git

Configure seu nome e email:
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"

#Git #GitPie 🥧
```

```
3/8 Criando seu primeiro repositório:

mkdir meu-projeto
cd meu-projeto
git init
echo "# Meu Projeto" > README.md
git add README.md
git commit -m "Primeiro commit"

#Git #GitPie 🥧
```

```
4/8 Conectando ao GitHub:

1. Crie conta no GitHub
2. Crie novo repositório
3. Conecte seu repo local:

git remote add origin https://github.com/seu-usuario/seu-repo.git
git push -u origin main

#Git #GitPie 🥧
```

```
5/8 Fluxo básico de trabalho:

git pull  # atualiza seu repo
# faça alterações
git add .  # stage alterações
git commit -m "Descrição clara"
git push  # envia para o remoto

#Git #GitPie 🥧
```

```
6/8 Criando uma branch:

git checkout -b minha-feature
# trabalhe na sua feature
git add .
git commit -m "Implementa feature X"
git push -u origin minha-feature

#Git #GitPie 🥧
```

```
7/8 Criando seu Pull Request:

1. Vá ao GitHub
2. Navegue até seu repo
3. Clique em "Compare & pull request"
4. Descreva suas alterações
5. Clique em "Create pull request"

#Git #GitPie 🥧
```

```
8/8 Parabéns! Você completou o ciclo básico do Git!

Para aprofundar seus conhecimentos, acesse nosso guia completo em português:
https://mrpunkdasilva.github.io/learn-version-control-system/

#Git #GitPie 🥧
```

### Thread 4: Git Avançado
```
🧵 THREAD: Técnicas avançadas de Git que impressionarão seu tech lead

1/7 Pronto para elevar seu jogo no Git? Estas técnicas avançadas vão te destacar no time.

#Git #GitPie 🥧
```

```
2/7 Rebase interativo:

git rebase -i HEAD~3

Permite:
• Reordenar commits
• Combinar commits
• Editar mensagens
• Remover commits

Mantenha seu histórico limpo e profissional!

#Git #GitPie 🥧
```

```
3/7 Cherry-pick estratégico:

git cherry-pick abc123 def456

Aplique commits específicos de qualquer branch.
Perfeito para backports ou aplicar fixes em múltiplas branches.

#Git #GitPie 🥧
```

```
4/7 Bisect automatizado:

git bisect start
git bisect bad
git bisect good v1.0
git bisect run npm test

Encontre automaticamente qual commit quebrou os testes!

#Git #GitPie 🥧
```

```
5/7 Hooks customizados:

Crie em .git/hooks:
• pre-commit: validação de código
• pre-push: testes automatizados
• commit-msg: validação de mensagem

Automatize qualidade!

#Git #GitPie 🥧
```

```
6/7 Submódulos:

git submodule add https://github.com/user/repo
git submodule update --init --recursive

Gerencie dependências que também são repos Git.
Ideal para monorepos e libs compartilhadas.

#Git #GitPie 🥧
```

```
7/7 Estas técnicas avançadas impressionam qualquer tech lead!

Domine todas elas e muito mais em nosso guia completo em português:
https://mrpunkdasilva.github.io/learn-version-control-system/

#Git #GitPie 🥧
```

## Enquetes

### Enquete 4: Problemas
```
📊 ENQUETE: Qual problema com Git mais atrasa seu trabalho?

🔄 Conflitos de merge
🌿 Perder código não commitado
🔙 Desfazer alterações incorretas
🤝 Lidar com repositórios grandes

Soluções para todos no #GitPie: https://mrpunkdasilva.github.io/learn-version-control-system/ 🥧
```

### Enquete 5: Experiência
```
📊 ENQUETE: Qual seu nível de experiência com Git?

🔰 Iniciante (comandos básicos)
🏃‍♂️ Intermediário (branches, merges)
🧙‍♂️ Avançado (rebase, cherry-pick)
🦸‍♂️ Ninja (hooks, workflows customizados)

Evolua com #GitPie: https://mrpunkdasilva.github.io/learn-version-control-system/ 🥧
```

## Posts Problema-Solução

### Post 4: Histórico Confuso
```
😱 PROBLEMA: Histórico de commits confuso e difícil de entender?

✅ SOLUÇÃO:
git rebase -i HEAD~5
# marque commits para squash/fixup
# edite mensagens para clareza

Mantenha seu histórico limpo e significativo!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 5: Branches Desatualizadas
```
😱 PROBLEMA: Múltiplas branches desatualizadas em relação à main?

✅ SOLUÇÃO:
git checkout feature-x
git rebase main
# repita para cada branch

Mantenha suas branches atualizadas e evite conflitos futuros!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```