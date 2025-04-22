# Migrando para Git

## Visão Geral

```mermaid
mindmap
    root((Migração))
        Planejamento
            Análise
            Timeline
            Equipe
        Execução
            Ferramentas
            Scripts
            Testes
        Validação
            Integridade
            Histórico
            Permissões
```

## Estratégias de Migração

### Abordagens Comuns
```mermaid
graph TD
    A[Big Bang] -->|Migração total| B[Git]
    C[Gradual] -->|Por equipe| B
    D[Paralelo] -->|Coexistência| B
```

## Checklist de Migração

### Pré-Migração
- Inventário de repositórios
- Backup dos dados
- Documentação do processo
- Treinamento da equipe

### Durante Migração
- Congelamento de commits
- Execução dos scripts
- Validação dos dados
- Testes de integridade

### Pós-Migração
- Verificação de acessos
- Atualização de CI/CD
- Documentação atualizada
- Suporte à equipe

## Ferramentas Recomendadas

### Por Sistema de Origem
```mermaid
mindmap
    root((Tools))
        SVN
            git-svn
            svn2git
            SubGit
        Mercurial
            fast-export
            hg-fast-export
            hg-git
        Outros
            git-p4
            bzr-git
            cvs2git
```

## Próximos Passos

### Tópicos Relacionados
- [SVN para Git](svn-to-git.md)
- [Mercurial para Git](mercurial-to-git.md)
- [Divisão de Repositórios](repository-splitting.md)
- [Mesclagem de Repositórios](repository-merging.md)