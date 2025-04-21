# Sistemas de Controle de Versão Centralizado

Um sistema de controle de versão centralizado (CVCS) é como uma festa na casa da mãe do Stifler - todos precisam ir ao mesmo lugar para participar! Este sistema utiliza um servidor central que armazena todos os arquivos versionados e permite que múltiplos desenvolvedores colaborem no mesmo projeto.

## Características Principais

### 1. Servidor Central
- Repositório único e autoritativo
- Controle de acesso centralizado
- Backup centralizado
- Administração simplificada

### 2. Clientes
- Checkout de arquivos específicos
- Histórico parcial
- Dependência de conectividade
- Workspace local limitado

## A Casa da Mãe do Stifler

Como uma festa na casa da mãe do Stifler, todos precisam ir ao mesmo lugar para participar!

### Arquitetura

```mermaid
graph TD
    S((Servidor Central)) --- C1[Cliente 1]
    S --- C2[Cliente 2]
    S --- C3[Cliente 3]
    S --- C4[Cliente N]
```

### Estrutura do Sistema
```ascii
      +----------------+
      |    Servidor    |
      |    Central     |
      +----------------+
            ||||
    +-------++-+-------+
    |        |         |
+-------+ +-------+ +-------+
|Cliente| |Cliente| |Cliente|
|   1   | |   2   | |   3   |
+-------+ +-------+ +-------+
```

### Fluxo de Operações
```mermaid
sequenceDiagram
    participant D as Dev
    participant L as Local
    participant S as Servidor
    D->>L: Checkout
    L->>S: Update
    D->>L: Modifica
    L->>S: Commit
    S->>L: Confirma
```

## Vantagens e Desvantagens

### Vantagens
1. **Controle Centralizado**
   - Governança simplificada
   - Políticas uniformes
   - Backup único
   - Auditoria facilitada

2. **Administração Simples**
   - Gerenciamento de usuários
   - Controle de permissões
   - Monitoramento de uso
   - Manutenção única

3. **Visibilidade do Projeto**
   - Visão única do projeto
   - Status em tempo real
   - Progresso transparente
   - Colaboração sincronizada

### Desvantagens
1. **Ponto Único de Falha**
```mermaid
graph TD
    A[Servidor Down] -->|Impacto| B[Sem Acesso]
    B -->|Resultado| C[Time Parado]
    C -->|Consequência| D[Perda de Produtividade]
```

2. **Dependência de Rede**
```ascii
Servidor
    ^
    |
    X (Conexão Perdida)
    |
Cliente
```

3. **Performance Limitada**
```mermaid
graph LR
    A[Operação] -->|Rede| B[Servidor]
    B -->|Latência| C[Resposta]
```

## Exemplos Famosos
```mermaid
mindmap
    root((VCS Centralizado))
        SVN
            Apache
            Multiplataforma
            Confiável
        CVS
            Legado
            Unix
            Histórico
        Perforce
            Empresarial
            Escalável
            Proprietário
```

## Casos de Uso Ideais

### 1. Equipes Localizadas
```ascii
+----------------+
|   Escritório   |
|  +----------+  |
|  | Time Dev |  |
|  +----------+  |
+----------------+
        |
   Servidor VCS
```

### 2. Projetos com Ativos Grandes
```mermaid
graph TD
    A[Arquivos Grandes] -->|Centralizado| B[Servidor]
    B -->|Checkout Parcial| C[Cliente 1]
    B -->|Checkout Parcial| D[Cliente 2]
```

### 3. Controle Rigoroso
```mermaid
sequenceDiagram
    participant D as Dev
    participant S as Servidor
    participant A as Admin
    D->>S: Solicita Acesso
    S->>A: Notifica
    A->>S: Aprova
    S->>D: Concede Acesso
```

## Melhores Práticas

### 1. Backup Regular
```ascii
Servidor Principal
      |
      v
Backup Diário
      |
      v
Backup Offsite
```

### 2. Monitoramento
```mermaid
graph LR
    A[Sistema] -->|Monitora| B[Performance]
    A -->|Monitora| C[Disponibilidade]
    A -->|Monitora| D[Segurança]
```

### 3. Políticas de Acesso
```mermaid
graph TD
    A[Usuário] -->|Autenticação| B[Permissões]
    B -->|Leitura| C[Código]
    B -->|Escrita| D[Commits]
    B -->|Admin| E[Configurações]
```

## Ferramentas de Suporte

### 1. Integração Contínua
```ascii
+----------------+
| Build Server   |
|  +----------+  |
|  | CI/CD    |  |
|  +----------+  |
+----------------+
```

### 2. Code Review
```mermaid
sequenceDiagram
    participant D as Dev
    participant R as Reviewer
    participant S as Servidor
    D->>S: Commit
    S->>R: Notifica
    R->>S: Aprova/Rejeita
```

### 3. Rastreamento de Issues
```ascii
+----------------+
| Issue Tracker  |
|  #123 Bug     |
|  #124 Feature |
|  #125 Task    |
+----------------+
```