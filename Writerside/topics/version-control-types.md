# Tipos de Sistemas de Controle de Versão

## Sistemas Locais
Esse tipo de sistema é mantido em uma maquina. Por exemplo, Jim vai fazer o versionamento da sua parte do *frontend*, onde ele possui um arquivo de *checkout* que vai servir para conferir/adicionar as versões e um banco de dados (poderia ser um outro arquivo) contento as versões que ele salvou.

> ![](Version-Control-System-sistema-local.png)
> - Diagrama de um sistema local

## Sistemas Centralizados
Estes sistemas nascem com a problemática que o Sistema Local trás que é justamente um não compartilhamento simultâneo, já que como no nosso exemplo esses dois teriam problemas de versões já que estarão em computadores diferentes.

> ![](Version-Control-System-sistema-compartilhado.png)
> -  Diagrama de um sistema compartilhado

## Sistemas Distribuídos
Com isso os DVCS (Sistemas de Controle de Versão Distribuídos) se tornam um protagonista, já que os clientes não somente clonam os estados atuais, mas também fazem uma cópia completa de todo o repositório localmente.

> ![](Version-Control-System-sistemasdistribuidos.png)
> - Diagrama de um sistema distribuído