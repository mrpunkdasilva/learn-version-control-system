# Melhores Práticas em Controle de Versão

## Organização de Repositório

### Estrutura de Diretórios
```
projeto/
├── src/
├── tests/
├── docs/
├── .gitignore
└── README.md
```

### Arquivos Essenciais
- README.md
- .gitignore
- CONTRIBUTING.md
- LICENSE

## Commits

### Anatomia de um Bom Commit
- Título claro e conciso
- Descrição detalhada quando necessário
- Referência a issues/tickets

### Convenções de Commit
```
feat: adiciona novo recurso
fix: corrige bug
docs: atualiza documentação
style: formatação de código
refactor: refatoração de código
test: adiciona/modifica testes
```

## Branches

### Nomenclatura
- feature/nome-da-feature
- bugfix/descricao-do-bug
- hotfix/correcao-urgente
- release/versao

### Estratégias de Merge
- Merge commit
- Squash and merge
- Rebase and merge

## Code Review

### Checklist
- [ ] Código segue padrões
- [ ] Testes adicionados/atualizados
- [ ] Documentação atualizada
- [ ] Performance considerada
- [ ] Segurança verificada

### Feedback Construtivo
- Foco no código, não no desenvolvedor
- Sugestões específicas
- Explicações claras
- Reconhecimento de boas práticas