# Problema exemplo

Fazer um programa para ler os dados de uma reserva de hotel (número do quarto, data
de entrada e data de saída) e mostrar os dados da reserva, inclusive sua duração em
dias. Em seguida, ler novas datas de entrada e saída, atualizar a reserva, e mostrar
novamente a reserva com os dados atualizados. O programa não deve aceitar dados
inválidos para a reserva, conforme as seguintes regras:
- Alterações de reserva só podem ocorrer para datas futuras
- A data de saída deve ser maior que a data de entrada

Examples: 

> - Room number: 8021
> - Check-in date (dd/MM/yyyy): 23/09/2019
> - Check-out date (dd/MM/yyyy): 26/09/2019
> - Reservation: Room 8021, check-in: 23/09/2019, check-out: 26/09/2019, 3 nights
> 
> 
> - Enter data to update the reservation:
> - Check-in date (dd/MM/yyyy): 24/09/2019
> - Check-out date (dd/MM/yyyy): 29/09/2019
> - Reservation: Room 8021, check-in: 24/09/2019, check-out: 29/09/2019, 5 nights

> - Room number: 8021
> - Check-in date (dd/MM/yyyy): 23/09/2019
> - Check-out date (dd/MM/yyyy): 21/09/2019
> - Error in reservation: Check-out date must be after check-in date

Examples:

> - Room number: 8021
> - Check-in date (dd/MM/yyyy): 23/09/2019
> - Check-out date (dd/MM/yyyy): 26/09/2019
> - Reservation: Room 8021, check-in: 23/09/2019, check-out: 26/09/2019, 3 nights
> 
> 
> - Enter data to update the reservation:
> - Check-in date (dd/MM/yyyy): 24/09/2015
> - Check-out date (dd/MM/yyyy): 29/09/2015
> - Error in reservation: Reservation dates for update must be future dates

> - Room number: 8021
> - Check-in date (dd/MM/yyyy): 23/09/2019
> - Check-out date (dd/MM/yyyy): 26/09/2019
> - Reservation: Room 8021, check-in: 23/09/2019, check-out: 26/09/2019, 3 nights
>
>
> - Enter data to update the reservation:
> - Check-in date (dd/MM/yyyy): 24/09/2020
> - Check-out date (dd/MM/yyyy): 22/09/2020
> - Error in reservation: Check-out date must be after check-in date

# Soluções:

### Solução 1 (Muito Ruim)
- Lógica de validação no programa principal
    
  - Lógica de validação não delegada à reserva

### Solução 2 (Ruim)
- Método retornando string

    - A semântica da operação é prejudicada
      - Retornar string não tem nada a ver com atualização de reserva
      - E se a operação tivesse que retornar um string?
    - Ainda não é possível tratar exceções em construtores
    - Ainda não há auxílio do compilador: o programador deve "lembrar" de verificar se houve erro
    - A lógica fica estruturada em condicionais aninhadas

### Solução 3 (Boa)
- Tratamento de exceções


# Resumo da aula

- Cláusula throws: propaga a exceção ao invés de trata-la
- Cláusula throw: lança a exceção / "corta" o método
- Exception: compilador obriga a tratar ou propagar
- RuntimeException: compilador não obriga
- O modelo de tratamento de exceções permite que erros sejam tratados de forma consistente e flexível, usando boas práticas


- Vantagens:

  - Lógica delegada
  - Construtores podem ter tratamento de exceções
  - Possibilidade de auxílio do compilador (Exception)
  - Código mais simples. Não há aninhamento de condicionais: a qualquer momento que uma exceção for disparada, a execução é interrompida e cai no bloco catch correspondente.
  - É possível capturar inclusive outras exceções de sistema