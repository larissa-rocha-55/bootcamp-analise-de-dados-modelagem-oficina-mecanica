# bootcamp-analise-de-dados-modelagem-oficina-mecanica

### **Objetivo:**

Cria o esquema conceitual para o contexto de oficina com base na narrativa fornecida

### **Narrativa:**

- Sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica
- Clientes levam veículos à oficina mecânica para serem consertados ou para passarem por revisões periódicas
- Cada veículo é designado a uma equipe de mecânicos que identifica os serviços a serem executados e preenche uma OS com data de entrega.
- A partir da OS, calcula-se o valor de cada serviço, consultando-se uma tabela de referência de mão-de-obra
- O valor de cada peça também irá compor a OS. O cliente autoriza a execução dos serviços.
- A mesma equipe avalia e executa os serviços.
- Os mecânicos possuem código, nome, endereço e especialidade.
- Cada OS possui: número, data de emissão, um valor, status e uma data para conclusão dos trabalhos.

**RESPOSTA:**

**Entidades:**

- **Cliente** - Armazena dados dos clientes.
- **Veículo** - Armazena os veículos dos clientes.
- **Mecânico** - Contém dados dos mecânicos, como nome, especialidade e endereço.
- **Ordem de Serviço (OS)** - Registra cada ordem de serviço, com número, tipo de serviço, data (emissão e entrega), status e valor total. Está associada a um veículo e a uma equipe de mecânicos.
- **Peça** - Registra as peças utilizadas, com descrição e preço.
- **Serviço** - Registra os tipos de serviços prestados (conserto/ revisão) e preço.
- **Equipe de Mecânicos** - Agrupa os mecânicos responsáveis de cada OS.

**Relacionamentos:**

- **Cliente - Veículo (1:N)**: Um cliente pode ter vários veículos, mas cada veículo pertence a um único cliente.
- **Veículo - Ordem de Serviço (1:N)**: Um veículo pode ter várias OS, mas cada OS pertence a um único veículo.
- **Ordem de Serviço - Equipe de Mecânicos (1:N)**: Cada OS é atribuída a uma equipe de mecânicos, mas uma equipe pode trabalhar em várias ordens de serviço.
- **Mecânico - Equipe de Mecânicos (N:M)**: Um mecânico pode fazer parte de várias equipes, e cada equipe é formada por vários mecânicos.
- **Ordem de Serviço - Peça (N:M)** e **Ordem de Serviço - Serviço (N:M)**: Uma OS pode envolver várias peças e serviços, e uma peça ou serviço pode estar em várias OS.
