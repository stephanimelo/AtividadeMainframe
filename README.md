# Atividade Mainframe - JCL e PDS

## 👨‍💻 Sobre
Projeto demonstrando conceitos avançados de JCL, PDS e JES2 para ambiente mainframe z/OS. Desenvolvido como parte dos estudos em computação de alto desempenho.

## 🚀 Projetos

### [Combina PDS](JCL/combina-pds.jcl)
**Descrição**: JCL que combina múltiplos membros de um PDS em um único arquivo de saída, demonstrando fluxo completo de processamento batch.

**Tecnologias**: JCL, JES2, PDS, IEBGENER, Symbolics

**Como executar**:
```jcl
// Submeter JCL principal
submit 'STEPHANI.JCL(COMBINA)'

Cria Estrutura

Descrição: JCL para alocar a estrutura completa de datasets necessária para o projeto.

Tecnologias: JCL, IEFBR14, PDS Alocation

Como executar:
jcl

// Submeter JCL de criação de estrutura
submit 'STEPHANI.JCL(CRIESTR)'

🏗️ Tecnologias Utilizadas

    JCL - Job Control Language

    PDS/PDSE - Partitioned Data Sets

    JES2 - Job Entry Subsystem 2

    IEBGENER - Utilitário de cópia de datasets

    IEFBR14 - Utilitário para alocação de datasets

    Symbolics - Variáveis de sistema (&SYSUID, &&TEMP)

📋 Estrutura do Projeto
text

portfolio-mainframe/
├── 📄 README.md
├── 📁 JCL/
│   ├── combina-pds.jcl          # JCL principal
│   ├── cria-estrutura.jcl       # Criação de datasets
│   └── exemplo-dados.jcl        # Dados de teste
├── 📁 docs/
│   ├── explicacao-tecnica.md    # Conceitos técnicos
│   └── fluxo-jes2.md           # Fluxo do JES2
├── 📁 images/                   # Evidências e diagramas
└── 📁 exemplos/                 # Dados de exemplo

🔧 Como Executar
Pré-requisitos

    Ambiente z/OS (IBM z/OS, LinuxONE, MVS Tur(n)key)

    Acesso TSO/ISPF

    UserID autorizado

Passos para Execução

    Alocar estrutura:
    jcl

submit 'STEPHANI.JCL(CRIESTR)'

Criar dados de teste:
jcl

submit 'STEPHANI.JCL(EXEMPLO)'

Executar processamento principal:
jcl

submit 'STEPHANI.JCL(COMBINA)'

🎯 Conceitos Demonstrados
Organização de Dados

    Estruturação de PDS com múltiplos membros

    Alocação eficiente de datasets

    Gerenciamento de espaço em DASD

Processamento Batch

    Fluxo completo do JES2

    Uso de datasets temporários

    Controle de execução sequencial

Boas Práticas

    Uso de symbolics para portabilidade

    Comentários explicativos no JCL

    Organização modular de código

📊 Resultados Esperados

    Return Code: 0000 (sucesso)

    Saída: Membro RESULTADO criado no PDS de saída

    Log: Execução sequencial dos 3 steps com IEBGENER

    Performance: Processamento eficiente usando spooling JES2
