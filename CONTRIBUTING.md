# Guia de Contribuição

## Processo de Contribuição

1. Fork o repositório
2. Crie uma branch para sua feature (`git checkout -b feature/nome-da-feature`)
3. Faça suas alterações seguindo os padrões do projeto
4. Execute os testes localmente (`npm test`)
5. Commit suas mudanças seguindo as convenções de commit
6. Push para sua branch (`git push origin feature/nome-da-feature`)
7. Abra um Pull Request

## Convenções de Commit

Usamos convenções de commit padronizadas:

- `feat:` - Nova funcionalidade
- `fix:` - Correção de bug
- `docs:` - Alterações na documentação
- `style:` - Formatação, ponto e vírgula, etc; sem alteração de código
- `refactor:` - Refatoração de código
- `test:` - Adição ou correção de testes
- `chore:` - Atualizações de tarefas de build, configurações, etc

## CI/CD

Todas as contribuições passam por verificações automatizadas:
- Lint de código
- Testes unitários
- Validação de mensagens de commit
- Verificação de documentação

Seu PR só será mesclado após passar em todas as verificações.