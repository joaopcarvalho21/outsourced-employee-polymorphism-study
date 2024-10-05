
# Sistema de Pagamento de Funcionários

Projeto para estudo do curso de Java completo, Java POO - Polimorfismo e Herança.
Este projeto é um sistema simples de gestão de pagamento de funcionários, escrito em Java. Ele permite que o usuário insira uma lista de funcionários e calcule seus respectivos pagamentos. O sistema diferencia entre funcionários regulares e terceirizados, aplicando regras de pagamento diferentes para cada tipo.

## Funcionalidades

- **Funcionário Regular**: O pagamento é calculado com base no número de horas trabalhadas multiplicado pelo valor por hora.
- **Funcionário Terceirizado**: Além do pagamento regular, um funcionário terceirizado recebe uma cobrança adicional, que é incrementada em 10%.

## Classes

O sistema inclui três classes principais:

1. **Employee**: Classe base que representa um funcionário regular, com atributos como nome, horas trabalhadas e valor por hora.
2. **OutsourcedEmployee**: Subclasse de `Employee` que representa um funcionário terceirizado e inclui uma cobrança adicional que é incrementada em 10%.
3. **Program**: Classe principal que interage com o usuário, processa as entradas e exibe os detalhes de pagamento de cada funcionário.

## Como Funciona

1. O programa solicita ao usuário o número de funcionários.
2. Para cada funcionário, o usuário informa se ele é terceirizado ou não, o nome, o número de horas trabalhadas e o valor por hora. Para os funcionários terceirizados, também é fornecida uma cobrança adicional.
3. O sistema calcula o pagamento de cada funcionário e exibe o resultado.

## Exemplo de Entrada e Saída

```bash
Digite o número de funcionários: 3
Dados do funcionário #1:
Terceirizado (y/n)? n
Nome: João
Horas: 40
Valor por hora: 20.00

Dados do funcionário #2:
Terceirizado (y/n)? y
Nome: Ana
Horas: 40
Valor por hora: 25.00
Cobrança adicional: 200.00

Dados do funcionário #3:
Terceirizado (y/n)? n
Nome: Bob
Horas: 30
Valor por hora: 15.00

Pagamentos:
João - R$800.00
Ana - R$2700.00
Bob - R$450.00
```

## Estrutura do Projeto

```
/src
  /application
    Program.java  # Classe principal para executar a aplicação
  /entities
    Employee.java  # Classe que representa um funcionário regular
    OutsourcedEmployee.java  # Classe que representa um funcionário terceirizado
```

## Requisitos

- **Java**: Certifique-se de ter a versão mais recente do Kit de Desenvolvimento Java (JDK) instalada para compilar e executar o projeto.

## Executando o Projeto

1. Clone este repositório.
   ```bash
   git clone https://github.com/seu-usuario/sistema-pagamento-funcionarios.git
   ```
2. Compile e execute o programa:
   ```bash
   javac application/Program.java
   java application.Program
   ```

Isso vai fornecer uma descrição completa e clara para o seu projeto em português no GitHub!
# Employee Payment System

This project is a simple employee payment management system written in Java. It allows users to input a list of employees and calculate their respective payments. The system distinguishes between regular employees and outsourced employees, applying different payment rules.

## Features

- **Regular Employee**: Payment is calculated based on the number of hours worked multiplied by the value per hour.
- **Outsourced Employee**: In addition to the regular payment, an outsourced employee receives an additional charge, which is incremented by 10%.

## Classes

The system includes three main classes:

1. **Employee**: The base class representing a regular employee with attributes such as name, hours worked, and value per hour.
2. **OutsourcedEmployee**: A subclass of `Employee` that represents an outsourced employee and includes an additional charge that is incremented by 10%.
3. **Program**: The main class that interacts with the user, processes input, and displays the payment details for each employee.

## How It Works

1. The program asks the user for the number of employees.
2. For each employee, the user specifies whether they are outsourced or not, their name, hours worked, and value per hour. For outsourced employees, an additional charge is also provided.
3. The system calculates the payment for each employee and displays the result.

## Example Input and Output

```bash
Enter the number of employees: 3
Employee #1 data:
Outsourced (y/n)? n
Name: John
Hours: 40
Value per hour: 20.00

Employee #2 data:
Outsourced (y/n)? y
Name: Anna
Hours: 40
Value per hour: 25.00
Additional charge: 200.00

Employee #3 data:
Outsourced (y/n)? n
Name: Bob
Hours: 30
Value per hour: 15.00

Payments:
John - $800.00
Anna - $2700.00
Bob - $450.00
```

## Project Structure

```
/src
  /application
    Program.java  # Main class to run the application
  /entities
    Employee.java  # Class representing a regular employee
    OutsourcedEmployee.java  # Class representing an outsourced employee
```

## Requirements

- **Java**: Make sure you have the latest version of the Java Development Kit (JDK) installed to compile and run the project.
  
## Running the Project

1. Clone this repository.
   ```bash
   git clone https://github.com/seu-usuario/employee-payment-system.git
   ```
2. Compile and run the program:
   ```bash
   javac application/Program.java
   java application.Program
   ```
