# DesafioControleFluxo

Este projeto é um exemplo de controle de fluxo em Java, onde o sistema recebe dois parâmetros via terminal que representam dois números inteiros. Com esses dois números, o programa realiza uma contagem e imprime no console os números incrementados.

## Estrutura do Projeto
```plaintext
DesafioControleFluxo
├── .idea
├── src
│   └── main
│       └── java
│           └── org
│               └── example
│                   ├── Contador.java
│                   └── ParametrosInvalidosException.java
├── resources
├── test
│   └── java
├── target
├── .gitignore
└── pom.xml
```

## Classes

### Contador.java

```java
package org.example;

import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();
        
        try {
            // Chamando o método contendo a lógica de contagem
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) {
            // Imprimir a mensagem: O segundo parâmetro deve ser maior que o primeiro
            System.out.println(exception.getMessage());
        }
        
        terminal.close();
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        // Validar se parametroUm é MAIOR que parametroDois e lançar a exceção
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro");
        }
        
        int contagem = parametroDois - parametroUm;
        // Realizar o for para imprimir os números com base na variável contagem
        for (int i = 1; i <= contagem; i++) {
            System.out.printf("Imprimindo o número %d%n", i);
        }
    }
}

```
### ParametrosInvalidosException.java
```
package org.example;

public class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException(String mensagem) {
        super(mensagem);
    }
}

```

## Como Executar

1. Clone o repositório para o seu ambiente local.
2. Navegue até o diretório do projeto.
3. Compile as classes Java:
```bash
javac src/main/java/org/example/*.java -d out
```

4. Execute o programa:
```bash
java -cp out org.example.Contador
```

5. Siga as instruções no terminal para inserir os dois parâmetros.

## Exemplo de Uso
Ao executar o programa, você verá a seguinte interação no terminal:

```
Digite o primeiro parâmetro:
3
Digite o segundo parâmetro:
8
Resultado:
Imprimindo o número 1
Imprimindo o número 2
Imprimindo o número 3
Imprimindo o número 4
Imprimindo o número 5
```
#### Imagem de Exemplo Teste:
![image](https://github.com/user-attachments/assets/4dde41c8-f506-4918-9e8b-71a998ebbd8a)


Se o primeiro parâmetro for maior que o segundo, a seguinte mensagem de erro será exibida:
O segundo parâmetro deve ser maior que o primeiro

### Requisitos
- Java 8 ou superior
- IDE ou editor de texto para desenvolvimento Java (opcional)

```
Esse arquivo `README.md` oferece uma visão geral do projeto, incluindo a estrutura do projeto, o código das classes, instruções sobre como executar o programa, e um exemplo de uso.
```
