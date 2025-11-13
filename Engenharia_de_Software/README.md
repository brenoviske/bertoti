Primeiro Trecho-1

Em meio ao primeiro trecho do livro Software Engineering at Google, Oreilly discorre acerca da importante comparação entre Engenharia Software e Programação.
Engenharia de Software se refere a um processo rígido, regrado, focado em trasformar conhecimento e análises de códigos em soluções inovadoras e práticas para o ambiente real.
Programação por si só não se orienta a um processo tão rígido, apesar de se intercalar de várias formas em meio a área de Engenharia de Software, é extremamente relevante ressaltar e entender a distinção entre os dois.

Segundo Trecho - 2 

O segundo trecho do livro software engineering at google, retrata um aspecto de vida e manutenção de um software, e os desafios enfrentados ao longo do tempo para manter o mesmo 
software ativo e escalável , em uma tentativa de manter o seu valor. Em meio a este trecho, Oreilly afirma que grandes empresas de tecnologia ainda não possuem todas as repostas para estes problemas, mas cultivar este pensamento é um grande passo para entender melhor como podemos alongar a 'expectativa de vida ' de determinado software.


Exemplos de tradeoffs

1 - Execução de códigos mais simples e diretos, em uma tentativa de manter e escalar melhor, usando linguagens low-level para obter tal feito

2 - Calcular valores em meio ao código pode salvar mémoria mas reduzir 
a velocidade 

3 - Sistemas feitos em uma grande simplicidade podem ser mais fáceis de se desenvolver porém menos adaptável a grandes mudanças ou requisitos.


EXERCÍCIO - 4

DIAGRAMA DE CLASSE PARA POSTERIOR CONSTRUÇÃO EM CÓDIGO JAVA

```yaml

+-------------------+
|    Calculadora    |
+-------------------+
|                   |
+-------------------+
| + somar(a: int, b: int): int      |
| + subtrair(a: int, b: int): int   |
| + multiplicar(a: int, b: int): int|
| + dividir(a: int, b: int): double |
+-------------------+

```


EXERCÍCIO - 5 

CONSTRUÇÃO DE UMA CLASSE UTILIZANDO CÓDIGOS DO JAVA

```java

public class Calc {
    int n1;
    int n2;
    String op;

    public Calc( int n1 , int n2 , String op ){
        this.n1 = n1;
        this.n2 = n2;
        this.op = op;
    }

    public double Sum(){
        return n1 + n2;
    }

    public double Sub(){
        return n1 - n2;

    }

    public double Mul(){
       return n1 * n2;
    }

    public double Div(){
        if ( n2 == 0){
            return 0;
        }
        return (double) n1 / n2;
    }

    public double Pow(){
        return Math.pow(n1, n2);
    }

```


EXERCÍCIO 6 

AUTOMATIZAÇÃO DE TESTE DESTA CLASSE CRIADA EM QUESTÃO


```java


public class TesteCalculadora {
    public static void main(String[] args) {
        Calculadora calc = new Calculadora();

        // Testando soma
        System.out.println("Soma 5 + 3 = " + calc.somar(5, 3)); // esperado 8

        // Testando subtração
        System.out.println("Subtração 10 - 4 = " + calc.subtrair(10, 4)); // esperado 6

        // Testando multiplicação
        System.out.println("Multiplicação 7 * 6 = " + calc.multiplicar(7, 6)); // esperado 42

        // Testando divisão
        System.out.println("Divisão 20 / 5 = " + calc.dividir(20, 5)); // esperado 4.0

        // Testando divisão por zero (gera exceção)
        try {
            calc.dividir(10, 0);
        } catch (IllegalArgumentException e) {
            System.out.println("Erro esperado: " + e.getMessage());
        }
    }
}

```
EXERCICIO 7 - Criando dois diagramas de classe , onde a segunda classe Manager herda dos atributos e métodos da classe pai Person

CLASSE PERSON
```yaml
    +-----------------------------+
|          Person             |
+-----------------------------+
| - cpf: String               |
| - name: String              |
| - age: int                  |
+-----------------------------+
| + getCpf(): String          |
| + setCpf(cpf: String): void |
| + getName(): String         |
| + setName(name: String):  void|
| + getAge(): int             |
| + setAge(age: int): void    |
+-----------------------------+
```

CLASSE MANAGER 
```yaml
+--------------------------------------+
|              Manager                 |
|--------------------------------------|
| - salary: double                     |
|--------------------------------------|
| + getSalary(): double                |
| + setSalarry( double salary) : void  |
| + bonus( double amount ): double     |  
| + afterBonus(): double               |
+--------------------------------------+
```
O código respectivo para cada classe 

```java
public class Person{
    private String cpf;
    private String name;
    private int age;

    public Person( Stringn cpf , String name , int age){
        this.cpf = cpf ;
        this.name = name;
        this.age  = age;
    }

    public String getCpf(){
        return cpf;
    }

    public void setCpf( String cpf){
        this.cpd = newCpf;
    }

    public String getName(){
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge(){
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }

}
```
```java

public class Manager extends Person {
    private double salary;

    public Manager( String cpf , String cpf , int age , double salary) {
        super(cpf , name , age);
        this.salary = salary
    }

    public double getSalary() {
        return salary;
    }

    public void setSalary( String salary) {
        this.salary = salary
    }

    public double bonus( double amount ) {
        return ( salary * amount ) / 100
    }

    public double afterBonus() {
        salary += bonus()
    }

}

```

PRODUZINDO ENTÃO UM CÓDIGO AUTOMATIZADO DE TESTE DAS CLASSES
```java
public class TestManager {
    public static void main(String[] args) {
        // Create a Manager object
        Manager manager = new Manager("123.456.789-00", "Alice Johnson", 35, 5000.00);

        // Display initial info
        System.out.println("Manager Information:");
        System.out.println("Name: " + manager.getName());
        System.out.println("CPF: " + manager.getCpf());
        System.out.println("Age: " + manager.getAge());
        System.out.println("Base Salary: $" + manager.getSalary());

        // Calculate and display bonus and total salary
        System.out.println("Bonus: $" + manager.bonus());
        System.out.println("Salary after bonus: $" + manager.afterBonus());

        // Update salary using the setter
        manager.setSalary(6000.00);
        System.out.println("\nUpdated Salary: $" + manager.getSalary());
        System.out.println("New Bonus: $" + manager.bonus());
        System.out.println("New Salary after bonus: $" + manager.afterBonus());
    }
}
```


    


