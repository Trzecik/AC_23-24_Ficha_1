# Arquitetura de Computadores - Ficha 1

## Informação do aluno

    Nome: Caio Trzecik dos Santos

Escreve as respostas dentro dos blocos correspondentes.
Substitui as reticências pelo que é pedido em cada pergunta.
Não desformates o documento.

### P1. Identifica e descreve os principais componentes de um processador. Fornece uma breve explicação da função de cada componente

- Lista os componentes principais de um processador.
- Para cada componente, descreve o seu papel e função no processador.
- Considera componentes como unidade lógica aritmética (ALU), unidade de controlo (UC), registos internos, memória e interfaces de entrada/saída (I/O).

P1 - Resposta:

    Unidade de controle: busca a instrução da memória e decodifica-a.
    
    ALU (ou unidade aritmética e lógica): realiza operações aritméticas e booleanas.
    
    Registradores: memória rápida para guardar informações de controle, resultados intermediários.
    
    Entrada: Rato, Teclado, microfone e etc... .
    Saida: Fones, colunas de som, monitor etc... .
    
    Unidade de gerenciamento de memória:
    Dependendo da arquitetura da CPU, pode haver uma unidade de interface de barramento separada ou uma unidade de gerenciamento de memória. Esses componentes lidam com tarefas     relacionadas à memória, como o gerenciamento da interação entre a CPU e a RAM. A unidade também lida com a memória do cache, uma unidade de memória pequena e rápida que está localizada dentro da CPU, e a memória virtual que a CPU requer para o processamento de dados.
    
    Cache: Cache do processador é uma memória de acesso rápido. É usada pela Unidade Central de Processamento com o objetivo de reduzir o tempo médio de acesso aos dados armazenados na memória.

### P2. Compara as arquiteturas de Von Neumann e Harvard em termos de características e principais diferenças

- Lista as principais características da arquitetura Von Neumann.
- Lista as principais características da arquitetura de Harvard.
- Explica as principais diferenças entre as duas arquiteturas, particularmente na organização da memória, busca de instruções e separação de dados.
- Fornece exemplos de sistemas de computação que usam cada arquitetura.

P2 - Resposta:

    A Arquitetura de von Neumann: A Arquitetura de computador de von Neumann se caracteriza pela possibilidade de uma
    máquina digital armazenar seus programas no mesmo espaço de memória que os dados,
    podendo assim manipular tais programas. Esta arquitetura é um projeto modelo de um
    computador digital de programa armazenado que utiliza uma unidade de processamento (CPU) e
    uma de armazenamento ("memória") para comportar, respectivamente, instruções e dados.

    Arquitetura de harvard: É uma arquitetura de computador que se distingue das outras por possuir duas memórias diferentes e independentes em termos de barramento e ligação ao processador.
    É utilizada nos microcontroladores PIC. Tem, como principal característica, o acesso à memória de dados de modo separado em relação à memória de programa.
     
    Principais diferenças: Existem duas arquiteturas clássicas para os microprocessadores em geral: a arquitetura Von-Neumann, onde existe apenas um barramento interno por onde circulam instruções e dados e a arquitetura Harvard, que é caracterizada por dois barramentos internos, sendo um de instruções e outro de dados.

    Exemplos: Os microcontroladores com arquitetura Havard são também conhecidos como "microcontroladores RISC" (Computador com Conjunto Reduzido de Instruções), e os microcontroladores com uma arquitetura Von-Neumann, de "microcontroladores CISC" (Computador com um Conjunto Complexo de Instruções).
    
    RISC é uma linha de arquitetura de processadores que favorece um conjunto simples e pequeno de instruções que levam aproximadamente a mesma quantidade de tempo para serem executadas. Em oposição, a arquitetura CISC possui um conjunto maior de instruções especializadas, algumas delas raramente usadas pelos programas.
    


### P3. Descreve o ciclo *fetch-decode-execute* num processador, detalhando cada etapa e explicando a sua importância na execução de programas de computador

- Fornece uma explicação detalhada da fase de busca de instrução, incluindo o que ela envolve e por que é importante na operação do processador.
- Explica a fase de descodificação e o seu papel na interpretação das instruções de execução.
- Descreve a fase de execução, destacando a execução propriamente dita das instruções e quaisquer interações com dados.
- Conclui explicando a ordem destas fases e como elas garantem a execução adequada dos programas de computador.
- Usa um diagrama para ilustrar o ciclo.

P3 - Resposta:

    Busca: 
    1 A primeira fase do ciclo de instrução é responsável por capturar as instruções no RAM memória atribuída ao processador por meio de uma série de unidades e registros que são os seguintes:
    2 Contador de programa ou contador de programa: O que aponta para a próxima linha de memória onde a próxima instrução do processador está localizada. Seu valor é incrementado em 1 cada vez que um ciclo de instrução completo é concluído ou quando uma instrução de salto altera o valor do contador do programa.
    Registro de endereço de memória: O MAR copia o conteúdo do PC e o envia para a RAM através dos pinos de endereçamento da CPU, que são conectados aos pinos de endereçamento da própria RAM.
    3 Registro de dados de memória ou registro de dados de memória : Caso a CPU tenha que realizar uma leitura de memória, o que o MDR faz é copiar o conteúdo desse endereço de memória para um registro interno da CPU, que é um registro de passagem temporário antes que seu conteúdo seja copiado para o Registro de Instrução. O MDR, ao contrário do MAR, é conectado aos pinos de dados da RAM e não aos pinos de endereçamento e, no caso de uma instrução de escrita, o conteúdo do que você deseja escrever na RAM também é escrito no MDR
    4 Registro de instrução: A parte final do estágio de busca é a escrita da instrução no registrador de instrução, a partir do qual a unidade de controle do processador copiará seu conteúdo para o segundo estágio do ciclo de instrução.
    
    Decodificação: ciclo de instrução é o mais complexo de todos e aquele que define o tipo de arquitetura. Dependendo se temos um conjunto reduzido ou complexo de instruções, isso afetará a natureza da unidade de controle, dependendo do formato da instrução ou de quantas são processadas ao mesmo tempo na fase de decodificação e, portanto, a unidade de controle terá um natureza diferente. outro.
    A maneira mais fácil de visualizar o que ocorre é pensar nas instruções como trens circulando por uma complexa malha ferroviária e a unidade de controle direcionando-os para uma estação terminal, que é a unidade de execução que se encarregará de resolver a instrução.
    
    Execução:Essa etapa é a execução das instruções, nesta etapa as instruções são resolvidas, mas nem todos os tipos de instruções são resolvidos da mesma forma, pois a forma de usar o hardware dependerá da função de cada uma delas. 
    O outro ponto são os formatos de instrução, uma vez que uma instrução pode ser aplicada a um dado, escalar ou vários dados ao mesmo tempo, que conhecemos como SIMD. Para finalizar e dependendo do formato dos dados, existem diferentes tipos de ALUs para a execução de instruções aritméticas, por exemplo, temos unidades inteiras e de ponto flutuante como unidades diferenciadas hoje.

![Diagrama](https://isaaccomputerscience.org/api/v3.5.0/api/images/content/computer_science/computer_systems/architecture/figures/isaac_cs_sys_arch_cpu_fetch_decode_execute.svg)
