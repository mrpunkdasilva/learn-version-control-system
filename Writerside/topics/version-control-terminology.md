# Terminologia do Controle de Versão

## Conceitos Básicos

### Repository (Repositório)
> ![](repo-illustration.png)
- Local onde o código é armazenado
- Contém todo o histórico do projeto
- Pode ser local ou remoto

### Branch (Ramo)
- Linha independente de desenvolvimento
- Permite trabalho paralelo
- Isola mudanças em desenvolvimento

### Commit (Confirmação)
- Snapshot do código em um momento
- Inclui mensagem descritiva
- Possui identificador único (hash)

## Operações Comuns

### Merge (Mesclagem)
- Combina mudanças de diferentes branches
- Pode gerar conflitos
- Mantém histórico de ambas as branches

### Rebase (Rebase)
- Reaplica commits sobre outra base
- Mantém histórico linear
- Útil para manter branches atualizadas

### Cherry-pick
- Aplica commits específicos
- Seletivo e preciso
- Útil para hotfixes

## Estados de Arquivos

### Tracked (Rastreado)
- Modified (Modificado)
- Staged (Preparado)
- Committed (Confirmado)

### Untracked (Não Rastreado)
- Arquivos novos
- Não incluídos no controle de versão
- Precisam ser adicionados explicitamente

## Glossário Expandido

| Termo | Definição |
|------|-----------|
| Clone | Cópia completa do repositório |
| Fork | Cópia independente do repositório |
| Pull Request | Solicitação para integrar mudanças |
| Tag | Marco específico no histórico |
| Hook | Script automatizado em eventos |