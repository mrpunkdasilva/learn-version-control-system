# Conceitos Básicos do Git

## Como o Git Funciona
O Git funciona de forma diferente de outros VCS. Em um outro VCS ele terá os arquivos e quando houver alteração eles criam uma lista somente das alterações.

Em um outro VCS ele terá os arquivos e quando houver alteração eles criam uma lista somente  das alterações: 

> ![](Version-Control-System-basico-outros-vcs.png)

Agora com o Git ele faz diferente, já que vai tirando *snapshots* que são como fotos quando ocorre uma mudança e caso tenha algum arquivo que não foi alterado será guardado uma referencia para ele, assim pode ser recuperado.

## Estrutura de Diretórios
Assim temos dois níveis principais:
- Diretório de trabalho
- Área de preparo
- Diretório `.git` que vai ser o repositório ou banco de dados local

> ![](Version-Control-System-fluxodetrabalho.png)
> Diretórios quando se trabalha com Git