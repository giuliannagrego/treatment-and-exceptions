# Exceções

- Uma exceção é qualquer condição de erro ou comportamento inesperado encontrado por um programa **em execução**
- Em Java, uma exceção é um objeto herdado da classe:

  - java.lang.exception - _o compilador obriga a tratar ou propagar_
  - java.lang.RuntimeException - _o compilador **não** obriga a tratar ou propagar_
- Quando lançada, uma exceão é propagada na pilha de chamadas de métodos em execução até que seja capturada (tratada) ou o programa seja encerrado


## Hierarquia de exceções do Java

> Exemplo de hierarquia:

- **Throwable** - Superclasse genérica de todas as exceções e erros

  - **Error** - Erros que não se espera que o programador vá tratar: Não tem a possibilidade de tratar

    - **_OutOfMemoryError_** - "Estourou a memória" : O programa nem vai ter memória para tratar esse erro  
    - **_VirtualMachineError_** - "Deu um erro na máquina virtual do Java" : O programa não tem que tratar o erro, é um erro _inesperado_
    
  - **Exception** - São os erros que ocorrem no programa que se espera o tratamento: Tem a possibilidade de tratar

    - **_IOException_** -  Algum erro de entrada/saída
    - **_RunTimeException_** - Especifica exceções que o programa não necessariamente teria que tratar (o compilador não obriga a tratar)

        - _IndexOutOfBoundsException_ - Quando tenta acessar uma posição no array que não existe
        - _NullPointerException_ - Quando tenta acessar uma exceção com valor null
 
## Por que exceções?

- O modelo de tratamento de exceções permite que erros sejam tratados de forma consistente e flexível, usando boas práticas
- Vantagens:

    - Delega a lógica do erro para a classe responsável por conhecer as regras que podem ocasionar o erro
    - Trata de forma organizada (inclusive hierárquica) exceções de tipos diferentes
    - A exceção pode carregar dados quaisquer
