# Posts para Twitter (X)

## Dicas Rápidas

### Post 1: Alias
```
💡 #GitTip

Cansado de digitar comandos Git longos?

git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status

Aumente sua produtividade com aliases! #GitPie 🥧
https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 2: Stash
```
💡 #GitTip

Precisa mudar de branch mas não quer fazer commit?

git stash save "WIP: feature X"
git checkout outra-branch
# faça o que precisar
git checkout -
git stash pop

Salve seu trabalho temporariamente! #GitPie 🥧
https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 3: Amend
```
💡 #GitTip

Esqueceu algo no último commit?

git add arquivo-esquecido
git commit --amend --no-edit

Sem criar um novo commit! Simples assim.

Mais dicas em: https://mrpunkdasilva.github.io/learn-version-control-system/ #GitPie 🥧
```

### Post 4: Revert
```
💡 #GitTip

Fez um commit errado e já enviou pro remoto?

git revert HEAD

Cria um novo commit que desfaz as alterações sem reescrever o histórico!

Mais dicas em: https://mrpunkdasilva.github.io/learn-version-control-system/ #GitPie 🥧
```

### Post 5: Log
```
💡 #GitTip

Visualize seu histórico de forma elegante:

git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

Adicione como alias "git lg" para facilitar!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

## Threads Educativas

### Thread 1: Comandos Essenciais
```
🧵 THREAD: 5 comandos Git que resolverão 90% dos seus problemas

1/6 Já se sentiu perdido usando Git? Vou compartilhar os comandos que todo dev deveria dominar.

#Git #GitPie 🥧
```

```
2/6 git status

O primeiro comando que você deve executar quando estiver confuso.
Mostra arquivos modificados, staged e untracked.

Dica: use "git status -s" para uma versão compacta.

#Git #GitPie 🥧
```

```
3/6 git diff

Veja exatamente o que mudou nos seus arquivos:
- git diff: mudanças não staged
- git diff --staged: mudanças staged
- git diff HEAD: todas as mudanças

#Git #GitPie 🥧
```

```
4/6 git checkout

Navegue entre branches ou restaure arquivos:
- git checkout branch-name: muda de branch
- git checkout -: volta para branch anterior
- git checkout -- arquivo: descarta mudanças

#Git #GitPie 🥧
```

```
5/6 git reset

Desfaça commits ou unstage arquivos:
- git reset --soft HEAD~1: desfaz commit mantendo alterações
- git reset HEAD arquivo: unstage arquivo
- git reset --hard HEAD: descarta todas as mudanças (cuidado!)

#Git #GitPie 🥧
```

```
6/6 git pull --rebase

Atualiza seu branch local e evita commits de merge desnecessários.

Quer dominar Git de vez? Temos um guia completo em português:
https://mrpunkdasilva.github.io/learn-version-control-system/

#Git #GitPie 🥧
```

### Thread 2: Resolução de Conflitos
```
🧵 THREAD: Como resolver conflitos de merge no Git sem pânico

1/7 Conflitos de merge assustam muitos devs, mas são parte normal do trabalho em equipe. Vamos desmistificar!

#Git #GitPie 🥧
```

```
2/7 O que são conflitos?

Ocorrem quando duas pessoas editam a mesma linha de código.
Git não sabe qual versão manter e pede sua ajuda.

Não é um erro - é uma oportunidade de decisão!

#Git #GitPie 🥧
```

```
3/7 Prevenção:

- Pull frequente da branch principal
- Comunicação com o time
- Branches pequenas e focadas
- Commits frequentes

Evite o problema antes que aconteça!

#Git #GitPie 🥧
```

```
4/7 Quando o conflito aparece:

git status: veja quais arquivos têm conflitos

No arquivo, você verá:
<<<<<<< HEAD
sua versão
=======
versão deles
>>>>>>> branch-name

#Git #GitPie 🥧
```

```
5/7 Resolução manual:

1. Abra o arquivo no editor
2. Escolha qual código manter (ou combine ambos)
3. Remova os marcadores <<<, ===, >>>
4. git add arquivo
5. Continue o merge/rebase

#Git #GitPie 🥧
```

```
6/7 Ferramentas visuais:

- git mergetool: abre ferramenta visual
- VSCode: excelente visualização de conflitos
- GitKraken/Sourcetree: interfaces gráficas

Use a que for mais confortável!

#Git #GitPie 🥧
```

```
7/7 Lembre-se: conflitos são normais!

Com prática, você resolverá em segundos.

Quer um guia completo sobre resolução de conflitos?
https://mrpunkdasilva.github.io/learn-version-control-system/

#Git #GitPie 🥧
```

## Enquetes

### Enquete 1: Dificuldades
```
📊 ENQUETE: Qual parte do Git você acha mais confusa?

🔄 Resolução de conflitos
🌿 Gerenciamento de branches
🔙 Desfazer alterações
🤝 Trabalho em equipe

Respondemos a todas essas no #GitPie: https://mrpunkdasilva.github.io/learn-version-control-system/ 🥧
```

### Enquete 2: Workflows
```
📊 ENQUETE: Qual workflow Git sua equipe utiliza?

🔀 GitFlow
🛣️ Trunk-based
🍴 GitHub Flow
🔄 Feature Branch
🤔 Não seguimos um padrão

Comparamos todos no #GitPie: https://mrpunkdasilva.github.io/learn-version-control-system/ 🥧
```

### Enquete 3: Ferramentas
```
📊 ENQUETE: Qual ferramenta Git você prefere?

💻 Linha de comando
🖱️ GitHub Desktop
🐙 GitKraken
🌲 Sourcetree
🧰 Extensão da IDE

Dicas para todas no #GitPie: https://mrpunkdasilva.github.io/learn-version-control-system/ 🥧
```

## Posts Problema-Solução

### Post 1: Commit Errado
```
😱 PROBLEMA: Fez commit na branch errada?

✅ SOLUÇÃO:
git cherry-pick <commit-hash>
git checkout branch-correta
git cherry-pick <commit-hash>
git checkout branch-errada
git reset --hard HEAD~1

Transfira commits entre branches sem perder trabalho!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 2: Arquivo Grande
```
😱 PROBLEMA: Tentou fazer commit de arquivo grande por engano?

✅ SOLUÇÃO:
git reset HEAD <arquivo-grande>
echo "<arquivo-grande>" >> .gitignore
git add .gitignore
git commit -m "Ignorar arquivo grande"

Considere Git LFS para arquivos grandes!

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```

### Post 3: Rebase vs Merge
```
😱 PROBLEMA: Merge ou Rebase? Qual usar quando?

✅ SOLUÇÃO:
Merge: preserva histórico, cria commit de merge
Rebase: histórico linear, reescreve commits

Regra prática:
- Rebase em branches locais/pessoais
- Merge em branches compartilhadas

#GitPie 🥧 https://mrpunkdasilva.github.io/learn-version-control-system/
```