# Fluxo de Execução JES2

## 🔄 Ciclo Completo do Job no JES2

### 1. **Submissão do JCL**
```jcl
//MEUJOB JOB CLASS=A,MSGCLASS=H

    JCL é validado sintaticamente

    Entra na fila do JES2 para processamento

2. Processamento pelo JES2

    JES2 interpreta o JCL

    Aloca recursos necessários (datasets, memória)

    Agenda a execução baseado na CLASS do job

3. Spooling - Armazenamento Temporário

    Todo input/output do job vai para a SPOOL

    Permite acesso assíncrono às saídas

    Garante recuperação em caso de falhas

4. Execução dos Steps

    JES2 inicia os programas em cada STEP

    Monitora execução e captura return codes

    Gerencia datasets temporários (como &&TEMP)

5. Geração de Saída

    SYSOUT é direcionado para a classe definida (MSGCLASS=H)

    Datasets de saída são criados/atualizados

    Resultados ficam disponíveis para o usuário

6. Purga e Finalização

    Recursos temporários são liberados

    Job é marcado como completo

    Usuário é notificado (NOTIFY=&SYSUID)

📊 Componentes do JES2
Spool (SPOOL)

    Armazenamento em disco para jobs e saídas

    Permite múltiplos jobs rodarem simultaneamente

    Garante que saídas não sejam perdidas

Iniciadores (Initiators)

    Processos que executam os jobs

    Um iniciador processa um job por vez

    Múltiplos iniciadores permitem paralelismo

Filas de Trabalho

    Gerenciam prioridade entre jobs

    Controlam agendamento baseado em CLASS

    Permitem hold/release de jobs

🎯 JES2 vs JES3
JES2 (Mais Comum)

    Arquitetura independente por sistema

    Mais simples e robusto

    Padrão da indústria

JES3

    Controle centralizado multi-sistema

    Agenda jobs considerando dependências

    Menos comum hoje em dia

🔧 Comandos JES2 Úteis
jcl

// Ver status de jobs
STATUS *

// Cancelar um job
CANCEL JOB1234

// Hold em um job
HOLD JOB5678
