# Tabela Completa de Comandos

| Comando Git | Descrição | Categoria |
|------------|-----------|-----------|
| `git init` | Inicializa um novo repositório Git | 🆕 Básico |
| `git clone <url>` | Clona um repositório existente | 🆕 Básico |
| `git clone <url> <pasta>` | Clona para uma pasta específica | 🆕 Básico |
| `git clone --depth 1 <url>` | Clona apenas o último commit (shallow clone) | 🆕 Básico |
| `git clone --bare <url>` | Clona repositório sem working directory | 🆕 Básico |
| `git add <arquivo>` | Adiciona arquivo ao stage | 📝 Arquivos |
| `git add .` | Adiciona todos os arquivos ao stage | 📝 Arquivos |
| `git add -p` | Adiciona alterações interativamente | 📝 Arquivos |
| `git add -u` | Adiciona arquivos modificados e removidos | 📝 Arquivos |
| `git rm <arquivo>` | Remove arquivo do repositório | 📝 Arquivos |
| `git rm --cached <arquivo>` | Remove arquivo do stage mantendo local | 📝 Arquivos |
| `git mv <origem> <destino>` | Move ou renomeia arquivo | 📝 Arquivos |
| `git commit -m "<mensagem>"` | Cria um novo commit | 📝 Básico |
| `git commit -am "<mensagem>"` | Adiciona modificações e commita | 📝 Básico |
| `git commit --amend` | Modifica o último commit | 🎓 Avançado |
| `git commit --no-verify` | Commit ignorando hooks | 🎓 Avançado |
| `git status` | Mostra o estado atual do repositório | 🔍 Investigação |
| `git status -s` | Mostra status em formato curto | 🔍 Investigação |
| `git log` | Mostra histórico de commits | 🔍 Investigação |
| `git log --oneline` | Mostra histórico resumido | 🔍 Investigação |
| `git log --graph` | Mostra histórico com grafo | 🔍 Investigação |
| `git log --author="nome"` | Filtra commits por autor | 🔍 Investigação |
| `git log --since="1 week ago"` | Mostra commits da última semana | 🔍 Investigação |
| `git log -p` | Mostra diferenças em cada commit | 🔍 Investigação |
| `git log --stat` | Mostra estatísticas de alterações | 🔍 Investigação |
| `git blame <arquivo>` | Mostra quem alterou cada linha | 🔍 Investigação |
| `git blame -L 10,20 <arquivo>` | Blame de linhas específicas | 🔍 Investigação |
| `git diff` | Mostra alterações não staged | 🔍 Investigação |
| `git diff --staged` | Mostra alterações staged | 🔍 Investigação |
| `git diff HEAD` | Mostra todas as alterações | 🔍 Investigação |
| `git diff --word-diff` | Mostra diferenças por palavra | 🔍 Investigação |
| `git diff branch1..branch2` | Compara duas branches | 🔍 Investigação |
| `git branch` | Lista branches | 🌳 Branches |
| `git branch -r` | Lista branches remotas | 🌳 Branches |
| `git branch -a` | Lista todas as branches | 🌳 Branches |
| `git branch <nome>` | Cria nova branch | 🌳 Branches |
| `git branch -m <novo-nome>` | Renomeia branch atual | 🌳 Branches |
| `git branch --merged` | Lista branches mergeadas | 🌳 Branches |
| `git branch --no-merged` | Lista branches não mergeadas | 🌳 Branches |
| `git checkout <branch>` | Muda para outra branch | 🌳 Branches |
| `git checkout -` | Volta para branch anterior | 🌳 Branches |
| `git checkout -b <branch>` | Cria e muda para nova branch | 🌳 Branches |
| `git checkout -- <arquivo>` | Descarta alterações em arquivo | 🌳 Branches |
| `git checkout HEAD~1` | Vai para commit anterior | 🌳 Branches |
| `git switch <branch>` | Muda para branch (Git moderno) | 🌳 Branches |
| `git switch -c <branch>` | Cria e muda branch (Git moderno) | 🌳 Branches |
| `git branch -d <branch>` | Deleta branch (se mergeada) | 🌳 Branches |
| `git branch -D <branch>` | Força deleção de branch | 🌳 Branches |
| `git merge <branch>` | Faz merge de uma branch | 🤝 Merge/Rebase |
| `git merge --no-ff <branch>` | Merge criando commit mesmo se fast-forward | 🤝 Merge/Rebase |
| `git merge --squash <branch>` | Merge combinando commits | 🤝 Merge/Rebase |
| `git rebase <branch>` | Faz rebase em uma branch | 🤝 Merge/Rebase |
| `git rebase -i <commit>` | Rebase interativo desde commit | 🤝 Merge/Rebase |
| `git rebase --onto <base> <old> <new>` | Rebase específico | 🤝 Merge/Rebase |
| `git merge --abort` | Cancela merge em andamento | 🤝 Merge/Rebase |
| `git rebase --abort` | Cancela rebase em andamento | 🤝 Merge/Rebase |
| `git remote add <nome> <url>` | Adiciona repositório remoto | 🔄 Sincronização |
| `git remote -v` | Lista repositórios remotos | 🔄 Sincronização |
| `git remote show <nome>` | Mostra informações do remoto | 🔄 Sincronização |
| `git remote rename <old> <new>` | Renomeia remoto | 🔄 Sincronização |
| `git remote remove <nome>` | Remove remoto | 🔄 Sincronização |
| `git push` | Envia commits para remoto | 🔄 Sincronização |
| `git push -u origin <branch>` | Push configurando upstream | 🔄 Sincronização |
| `git push --force` | Força push (cuidado!) | 🔄 Sincronização |
| `git push --force-with-lease` | Force push mais seguro | 🔄 Sincronização |
| `git pull` | Atualiza do repositório remoto | 🔄 Sincronização |
| `git pull --rebase` | Pull usando rebase | 🔄 Sincronização |
| `git fetch` | Busca atualizações do remoto | 🔄 Sincronização |
| `git fetch --all` | Busca de todos os remotos | 🔄 Sincronização |
| `git fetch --prune` | Fetch removendo refs obsoletas | 🔄 Sincronização |
| `git tag <nome>` | Cria tag leve | 📌 Tags |
| `git tag -a <nome> -m "<msg>"` | Cria tag anotada | 📌 Tags |
| `git tag -l "v1.*"` | Lista tags com padrão | 📌 Tags |
| `git tag -d <nome>` | Remove tag local | 📌 Tags |
| `git push origin <tag>` | Envia tag específica | 📌 Tags |
| `git push origin --tags` | Envia todas as tags | 📌 Tags |
| `git push origin :refs/tags/<tag>` | Remove tag remota | 📌 Tags |
| `git stash` | Guarda alterações temporariamente | 📦 Stash |
| `git stash save "mensagem"` | Stash com descrição | 📦 Stash |
| `git stash push -m "mensagem"` | Stash moderno com mensagem | 📦 Stash |
| `git stash --keep-index` | Stash mantendo staging | 📦 Stash |
| `git stash --include-untracked` | Stash incluindo novos arquivos | 📦 Stash |
| `git stash pop` | Recupera e remove stash | 📦 Stash |
| `git stash apply` | Recupera mantendo stash | 📦 Stash |
| `git stash list` | Lista stashes salvos | 📦 Stash |
| `git stash show` | Mostra alterações do stash | 📦 Stash |
| `git stash drop` | Remove stash | 📦 Stash |
| `git stash clear` | Remove todos os stashes | 📦 Stash |
| `git stash branch <nome>` | Cria branch do stash | 📦 Stash |
| `git reset HEAD~1` | Desfaz último commit mantendo alterações | 💩 Correções |
| `git reset --soft HEAD~1` | Desfaz commit mantendo stage | 💩 Correções |
| `git reset --hard HEAD~1` | Desfaz commit e alterações | 💩 Correções |
| `git reset --mixed HEAD~1` | Reset padrão | 💩 Correções |
| `git reset <arquivo>` | Remove arquivo do stage | 💩 Correções |
| `git revert HEAD` | Cria commit que desfaz alterações | 💩 Correções |
| `git revert -m 1 <commit>` | Reverte merge commit | 💩 Correções |
| `git clean -n` | Lista arquivos a serem removidos | 🎓 Avançado |
| `git clean -df` | Remove arquivos não rastreados | 🎓 Avançado |
| `git clean -xdf` | Remove arquivos ignorados também | 🎓 Avançado |
| `git cherry-pick <commit>` | Copia commit específico | 🎓 Avançado |
| `git cherry-pick -x <commit>` | Cherry-pick com referência | 🎓 Avançado |
| `git rebase -i HEAD~n` | Rebase interativo | 🎓 Avançado |
| `git submodule add <url>` | Adiciona submódulo | 🎓 Avançado |
| `git submodule update --init` | Inicializa submódulos | 🎓 Avançado |
| `git submodule update --recursive` | Atualiza submódulos recursivamente | 🎓 Avançado |
| `git worktree add <path> <branch>` | Cria worktree | 🎓 Avançado |
| `git worktree list` | Lista worktrees | 🎓 Avançado |
| `git bisect start` | Inicia busca binária | 🎓 Avançado |
| `git bisect good/bad` | Marca commit como bom/ruim | 🎓 Avançado |
| `git bisect reset` | Finaliza bisect | 🎓 Avançado |
| `git gc` | Executa coleta de lixo | 📊 Performance |
| `git gc --aggressive` | Otimização mais agressiva | 📊 Performance |
| `git prune` | Remove objetos órfãos | 📊 Performance |
| `git fsck` | Verifica integridade do repositório | 📊 Performance |
| `git count-objects -v` | Conta objetos do repositório | 📊 Performance |
| `git config --global` | Define configurações globais | 🛠️ Configuração |
| `git config --local` | Define configurações do repo | 🛠️ Configuração |
| `git config --list` | Lista todas configurações | 🛠️ Configuração |
| `git config --edit` | Edita configurações no editor | 🛠️ Configuração |
| `git remote prune origin` | Remove branches remotas deletadas | 🧹 Limpeza |
| `git reflog` | Mostra histórico de referências | 🔍 Investigação |
| `git reflog expire --expire=now --all` | Limpa reflog | 🧹 Limpeza |
| `git maintenance start` | Inicia manutenção automática | 📊 Performance |
| `git verify-pack -v .git/objects/pack/pack-*.idx` | Analisa objetos empacotados | 📊 Performance |
| `git rev-parse HEAD` | Mostra hash do commit atual | 🔍 Investigação |
| `git rev-list --count HEAD` | Conta número de commits | 🔍 Investigação |
| `git shortlog` | Resumo de commits por autor | 🔍 Investigação |
| `git describe` | Descreve commit usando tags | 🔍 Investigação |
| `git archive` | Cria arquivo do repositório | 📦 Arquivamento |
| `git bundle create repo.bundle HEAD` | Cria bundle do repositório | 📦 Arquivamento |
| `git notes add -m "nota" <commit>` | Adiciona nota a commit | 📝 Notas |
| `git grep "termo"` | Busca termo no código | 🔍 Investigação |
| `git show <commit>` | Mostra informações do commit | 🔍 Investigação |
| `git show-branch` | Mostra branches e seus commits | 🔍 Investigação |
| `git whatchanged` | Mostra histórico de mudanças | 🔍 Investigação |
| `git log --graph --oneline` | Mostra log em formato de árvore | 🔍 Investigação |
| `git log --author="nome"` | Filtra commits por autor | 🔍 Investigação |
| `git log --since="1 week ago"` | Mostra commits da última semana | 🔍 Investigação |
| `git log --grep="feat"` | Busca commits por mensagem | 🔍 Investigação |
| `git log -p <arquivo>` | Mostra histórico de mudanças do arquivo | 🔍 Investigação |
| `git blame -L 10,20 <arquivo>` | Mostra autores das linhas 10-20 | 🔍 Investigação |
| `git diff --cached` | Mostra diferenças staged | 🔍 Investigação |
| `git diff branch1...branch2` | Compara branches desde ancestral comum | 🔍 Investigação |
| `git checkout -` | Volta para branch anterior | 🌳 Branches |
| `git branch --merged` | Lista branches já mergeadas | 🌳 Branches |
| `git branch --no-merged` | Lista branches não mergeadas | 🌳 Branches |
| `git push --delete origin <branch>` | Remove branch remota | 🌳 Branches |
| `git commit --amend --no-edit` | Adiciona alterações ao último commit | 💩 Correções |
| `git restore --staged <arquivo>` | Remove arquivo do stage (Git moderno) | 💩 Correções |
| `git restore <arquivo>` | Descarta alterações não staged (Git moderno) | 💩 Correções |
| `git rebase --onto main topic-1 topic-2` | Rebases encadeados | 🎓 Avançado |
| `git merge-base branch1 branch2` | Encontra commit ancestral comum | 🎓 Avançado |
| `git rev-parse --short HEAD` | Mostra hash curto do commit atual | 🔍 Investigação |
| `git update-index --skip-worktree <arquivo>` | Ignora mudanças locais | 🛠️ Configuração |
| `git update-index --no-skip-worktree <arquivo>` | Volta a rastrear mudanças | 🛠️ Configuração |

> **Dica Pro**: Use `git help <comando>` para ver a documentação completa de qualquer comando!