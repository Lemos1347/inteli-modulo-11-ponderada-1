# CPU de 8 Bits - Simulação com ALU

<img width="1197" alt="image" src="https://github.com/user-attachments/assets/1e0ac645-a12e-49bb-8e9b-b233b4b4cd4b">

## Demonstração

### Geral

https://github.com/user-attachments/assets/0c52390a-21fa-4f19-92cc-9b169d4dce63

### Soma

https://github.com/user-attachments/assets/4d530ccb-a0fd-42ab-ad5b-d1b45ff8cdc1

### Subtração

https://github.com/user-attachments/assets/a18f4775-a494-49b3-883e-eec526e39aa9

### Comparação

https://github.com/user-attachments/assets/73747507-5460-41c3-a218-71d4651bc4c5

### Bit shift

https://github.com/user-attachments/assets/a932739f-ed3a-4d52-aae5-598d0ded4934

### Multiplicação

https://github.com/user-attachments/assets/0b4883ec-9c57-4aba-acdb-435753f937d4

## Descrição da Atividade

Esta atividade consiste na criação de uma CPU simplificada de 8 bits utilizando um simulador de lógica digital. A CPU foi projetada para executar um conjunto básico de operações aritméticas e lógicas, conforme os requisitos especificados.

### Objetivo

O objetivo da atividade é desenvolver uma CPU que simula apenas o ciclo de execução, sem a necessidade de temporização ou divisão de ciclos para busca e execução. A CPU implementa uma Unidade Lógica e Aritmética (ALU) capaz de realizar operações como adição, subtração, comparação, deslocamento de bits (bit shift) e multiplicação restrita a valores de 4 bits.

### Especificações das Operações da ALU

1. **Adição (Opcode: 0)**
   - Realiza a soma dos valores das entradas A e B (8 bits, signed).
   
2. **Subtração (Opcode: 1)**
   - A subtração é realizada utilizando a representação por complemento de dois.

3. **Comparação (Opcode: 2)**
   - Realiza a comparação entre A e B com três saídas: A == B, A < B, e A > B.

4. **Bit Shift (Opcode: 3)**
   - Realiza um deslocamento para a esquerda em A. Não há necessidade de selecionar a direção ou fazer wrap around.

5. **Multiplicação (Opcode: 4)**
   - Multiplicação restrita a valores de 4 bits.

### Funcionamento

- **Entradas**:
  - Duas entradas de dados de 8 bits (`A` e `B`) em complemento de dois.
  - Uma entrada de dados para o opcode de 3 bits que seleciona a operação desejada.
  
- **Saídas**:
  - Uma saída de 8 bits (`S`) representando o resultado das operações numéricas.
  - Indicadores de comparação (`A == B`, `A < B`, `A > B`).
  - Sinal de overflow (`Ov`) de 1 bit que é acionado em caso de overflow.

- **Displays de Sete Segmentos**:
  - Os resultados das operações que produzem um número são exibidos em dois displays de sete segmentos que mostram valores hexadecimais, com um terceiro display indicando o sinal.

## Como Testar a CPU

Para testar a CPU, siga as instruções abaixo:

>[!IMPORTANT]
> Essa ativiade foi contruída utilizando o simulador Digital. Para testar a CPU, é necessário ter o [Digital](https://github.com/hneemann/Digital) instalado. Após instalar o Digital, abra o arquivo `Using 8 bit ALU.dig` para visualizar o circuito e realizar a simulação.

1. **Configurar Entradas:**
   - Insira valores inteiros (em complemento de dois) nas entradas A e B, que possuem 8 bits cada.
   - Defina o `Opcode` (3 bits) para selecionar a operação desejada:
     - `0`: Adição
     - `1`: Subtração
     - `2`: Comparação
     - `3`: Bit Shift (esquerda)
     - `4`: Multiplicação (valores restritos a 4 bits)

2. **Executar a Simulação:**
   - Utilize o simulador de lógica digital, como o Digital, para rodar o circuito. Após definir as entradas, ative a simulação para observar os resultados.

3. **Verificar Resultados:**
   - O resultado da operação será exibido nos displays de sete segmentos. 
   - Para operações de comparação, verifique as saídas específicas para A == B, A > B, e A < B.
   - Caso ocorra overflow durante as operações, o indicador `Ov` será ativado.

4. **Exemplo de Teste:**
   - Para testar uma soma, defina A como `21` e B como `-15`, com o opcode `0` (adição). A saída será mostrada nos displays.
   - Para uma subtração com A = `10` e B = `5`, ajuste o opcode para `1` e observe o display.
   - Teste bit shifts, comparações e multiplicações conforme necessário, alterando os valores de A, B e opcode.

## Arquivos

Dentro desse projeto você encontrará uma sequência de arquivos que foram importante para a implementação da CPU de 8 bits, porém nem todos foram utilizados diretamente no simulador principal. Recomendo que você consulte o arquivo `Using 8 bit ALU.dig` para visualizar o circuito principal e a partir dele, navegue pelos demais circuitos conforme necessário.
