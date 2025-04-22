# Convenções de Commit

## Estrutura Básica

```ascii
<tipo>(<escopo>): <descrição>

[corpo opcional]

[rodapé opcional]
```

## Tipos de Commit

### Principais Categorias
- `feat`: Nova funcionalidade
- `fix`: Correção de bug
- `docs`: Documentação
- `style`: Formatação
- `refactor`: Refatoração
- `test`: Testes
- `chore`: Tarefas gerais

## Boas Práticas

### Mensagens
- Use modo imperativo
- Mantenha até 50 caracteres no título
- Limite linhas do corpo em 72 caracteres
- Seja claro e conciso

### Exemplos
```bash
feat(auth): adiciona autenticação OAuth
fix(api): corrige timeout em requisições longas
docs(readme): atualiza instruções de instalação
```

## Ferramentas

### Commitlint
```json
{
  "extends": ["@commitlint/config-conventional"],
  "rules": {
    "type-enum": [2, "always", ["feat", "fix", "docs"]]
  }
}
```

### Commitizen
```bash
# Instalação
npm install -g commitizen
npm install -g cz-conventional-changelog

# Uso
git cz
```

## Automação

### Git Hooks
```bash
#!/bin/sh
# .git/hooks/commit-msg

commit_msg=$(cat "$1")
if ! echo "$commit_msg" | grep -qE "^(feat|fix|docs|style|refactor|test|chore):"; then
    echo "Erro: Mensagem não segue convenção"
    exit 1
fi
```

## Integração com CI

### Validação Automática
```yaml
name: Commit Check
on: [push, pull_request]
jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Commit Linter
        uses: wagoid/commitlint-github-action@v5
```