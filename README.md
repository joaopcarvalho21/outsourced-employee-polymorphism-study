Aqui está um modelo de README para o seu projeto:

---

# Employee Payment System

Este projeto implementa um sistema simples para cálculo de pagamentos de funcionários. O sistema permite que os usuários insiram dados de funcionários, tanto funcionários regulares quanto terceirizados, e calcula seus pagamentos com base nas horas trabalhadas e no valor por hora.

## Funcionalidades

- Cadastro de funcionários com nome, horas trabalhadas e valor por hora.
- Suporte para funcionários terceirizados, que possuem um adicional sobre o pagamento.
- Cálculo automático do pagamento de cada funcionário, considerando o adicional no caso de funcionários terceirizados.

## Estrutura do Projeto

O projeto é composto pelas seguintes classes:

1. **Employee** (classe base):
   - Armazena o nome do funcionário, as horas trabalhadas e o valor por hora.
   - Contém o método `payment()` que calcula o pagamento baseado nas horas e no valor por hora.

2. **OutsourcedEmployee** (subclasse de `Employee`):
   - Extende a classe `Employee` para incluir um adicional de pagamento para funcionários terceirizados.
   - O método `payment()` calcula o pagamento base mais 110% do adicional.

3. **Program** (classe principal):
   - Permite a entrada de dados via console, registra os funcionários (regulares ou terceirizados), e imprime o pagamento de cada um.

## Como Funciona

1. O programa solicita ao usuário o número de funcionários.
2. Para cada funcionário, ele pergunta:
   - Se o funcionário é terceirizado (`y` para sim, `n` para não).
   - O nome do funcionário.
   - As horas trabalhadas.
   - O valor por hora.
   - Se for terceirizado, o valor adicional.
3. O programa calcula o pagamento:
   - Para funcionários regulares, o pagamento é simplesmente o produto das horas pelo valor por hora.
   - Para funcionários terceirizados, o pagamento inclui 110% do valor adicional informado.
4. O programa imprime uma lista de pagamentos com o nome do funcionário e o valor total a ser pago.

## Exemplo de Execução

```
Enter the number of employees: 2
Employee #1 data:
Outsourced (y/n)? y
Name: John
Hours: 50
Value per hour: 20.00
Additional charge: 200.00

Employee #2 data:
Outsourced (y/n)? n
Name: Maria
Hours: 60
Value per hour: 15.00

Payments:
John - $1200.00
Maria - $900.00
```

Neste exemplo, `John` é um funcionário terceirizado que trabalhou 50 horas a uma taxa de $20.00 por hora, com um adicional de $200.00. O pagamento final dele será $1200.00, que inclui as horas trabalhadas mais o adicional. Já `Maria`, que não é terceirizada, trabalhou 60 horas a $15.00 por hora e receberá $900.00.

## Como Rodar o Projeto

1. Clone o repositório.
2. Compile e execute o programa em um ambiente que suporte Java (JDK 11 ou superior).
3. Insira os dados conforme solicitado pelo programa.

## Requisitos

- **Java 11+**

## Estrutura do Código

```
src/
│
├── entities/
│   ├── Employee.java
│   ├── OutsourcedEmployee.java
│
└── application/
    └── Program.java
```

### Employee.java

```java
package entities;

public class Employee {
    private String name;
    private Integer hours;
    private Double valuePerHour;

    public Employee(String name, Integer hours, Double valuePerHour) {
        this.name = name;
        this.hours = hours;
        this.valuePerHour = valuePerHour;
    }

    public String getName() {
        return name;
    }

    public double payment() {
        return hours * valuePerHour;
    }
}
```

### OutsourcedEmployee.java

```java
package entities;

public class OutsourcedEmployee extends Employee {
    private Double additionalCharge;

    public OutsourcedEmployee(String name, Integer hours, Double valuePerHour, Double additionalCharge) {
        super(name, hours, valuePerHour);
        this.additionalCharge = additionalCharge;
    }

    @Override
    public double payment() {
        return super.payment() + additionalCharge * 1.1;
    }
}
```

### Program.java

```java
package application;

import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
import entities.Employee;
import entities.OutsourcedEmployee;

public class Program {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        List<Employee> list = new ArrayList<>();

        System.out.print("Enter the number of employees: ");
        int n = sc.nextInt();

        for (int i = 1; i <= n; i++) {
            System.out.println("Employee #" + i + " data:");
            System.out.print("Outsourced (y/n)? ");
            char outSourced = sc.next().charAt(0);
            System.out.print("Name: ");
            sc.nextLine();
            String name = sc.nextLine();
            System.out.print("Hours: ");
            Integer hours = sc.nextInt();
            System.out.print("Value per hour: ");
            double valuePerHour = sc.nextDouble();

            if (outSourced == 'y') {
                System.out.print("Additional charge: ");
                double additionalCharge = sc.nextDouble();
                list.add(new OutsourcedEmployee(name, hours, valuePerHour, additionalCharge));
            } else {
                list.add(new Employee(name, hours, valuePerHour));
            }
        }

        System.out.println("\nPayments:");
        for (Employee emp : list) {
            System.out.println(emp.getName() + " - $" + String.format("%.2f", emp.payment()));
        }

        sc.close();
    }
}
```

## Licença

Este projeto está sob a licença MIT.

---

Com isso, o seu projeto terá uma documentação clara e organizada para que outras pessoas possam entender e utilizá-lo facilmente.
