# Java

## Sintaxe
~~~Java
public class Classe{
    public static void main(String[] args){
         System.out.println("Ola mundo! ");
    }
}
~~~ 

~~~Java
// Procedimetno
public void dizerBomdia(){
    System.out.println("Bom dia");
}
~~~

~~~Java
// Método
public int somar(int a, int b){
    return a+b
}
~~~

~~~Java
public class Pessoa{
    // Atributos da classe Pessoa
    String nome;
    
    // Método Construtor explicito (classe Pessoa)
    public Pessoa(String n){
        // inicializa a classe ao ser instanciada, sem usar metodos setters
        this.nome = n;
    }
    
    // Métodos de acesso as variaveis (getters e setters)
    // ---
    
    // Métodos da Classe Pessoa
    // ---
}
~~~
## Herança, Polimorfismo, Reescrita

#### Herança
~~~Java
public class Pessoa{
    String  nome;
    int     idade;
}
~~~

~~~Java
public class Aluno extends Pessoa{
    String matricula;
}
~~~
* Pessoa:   Super classe 
* Aluno:    Sub classe
* Agora aluno possui 3 atributos: nome, idade e matrícula.

#### Interface: 
* Não possui atributos.
* Possui apenas chamadas (assinaturas) dos metodos a serem implementados -> (Override) de método.
* Uma classe pode implementar varias interfaces, mas apenas uma SuperClasse.
* Muito usado em classes DAO -> CRUDs

## Modificadores de acesso

| Visibilidade                      | `public` | `protected` | `default` | `private` |
|---                                |---     |---        |---        |---    |
| A partir da mesma classe          |sim     |sim |sim  |sim  |
| do mesmo pacote                   |sim     |sim |sim  |x    |
|classe filha no mesmo pacote       |sim     |sim |sim  |x    |
|classe filha em pacotes diferentes |sim     |sim |x    |x    |
|qualquer classe em pacote diferente|sim     |x   |x    |x    |

* Niveis de acesso: Classe < Pacote < Global
* `abstrac`:    impedir que a classe seja instanciada.
* `abstract`:   obriga os métodos das classes filhas a serem reescritos.  
* `final`:      variavel constante.
* `static`:     varivel da classe e nao da instância.
* `private static final` e `private final` : ambas sao imutáveis.

## Tipos de dados

#### Tipo Primitivo

* `boolean` : true ou false 
* `char`    : notação Unicode 16 bits : valores na faixa entre 0 e 65535
* `byte`    : inteiro de 8 bits. Valores entre -2^7 e 2^7, ou seja, -128 e 128. 
* `short`   : inteiro de 16 bits. Valores entre -2^15 e 2^15, ou seja, -32768 e 32768.
* `int`     : inteiro de 32 bits. Valores entre -2^31 e 2^31, ou seja, (+/-) 2.147.483.648
* `long`    : inteiro de 64 bits. Valores entre -2^63 e 2^63
* `float`   : ponto flutuante normalizada com precisão simples de 32 bits. (e-38 , e+38) : 6 dígitos.
* `double`  : ponto flutuante normalizada com precisão dupla de 64 bits. (e-308 , e+308) : 15 dígitos.

#### Tipo Objeto (Classe Wrappers)

* Boolean
* Caracter
* Byte
* Short
* Integer
* Long
* Float
* Double

Possuem metodos para a sua manipulação. São bons para deixar valores nulos.

~~~Java
Integer x = new Integer(4);
x++
System.out.println(x)
~~~

~~~Java
x.intValue();
Integer.valueOf();

~~~

## Array, ArrayList e List (pacote: java.util)
* Array
~~~Java
// Terá sempre um tamanho fixo, exemplo [3]

int[]    x    =  new int[3];
int[][]  xy   = new int[2][2];

x = {34, 65, 88};
xy = { {1,2,3) , {4,5,6} };

x[0] = 34;
x[1] = 65;
x[2] = 88;

// tamanho total da lista: lista.Count;
~~~

* ArrayList
~~~Java
// Tamanho dinâmico, assume tipos diferentes
ArrayList   lista  =   new ArrayList();

lista.add("Fulano");    
lista.add(10);
lista.add(true);
~~~

* List
~~~Java
// List<Tipo>
List <int> lista = new List<int>();

lista.add(23);
lista.add(44);
lista.add(23);
~~~

* Principais metodos
###### Array 
~~~Java 
// Array:
lista[indice].
    .equals();
    .toString();
    .length;
    
lista[].length;
lista[][].length;
~~~

###### ArrayList 
~~~Java
// ArrayList:
lista.
        .add();         // adicionar
        .remove();      // remover
        .clear();       // remover tudo
        .size();        // número total de elementos
        .indexOf();     // posição de indice da ocorrencia
        .trimToSize()   // ajusta a capacidade do arryList de acordo com o momento
        .get()          // retorna o elemento no indice passado por parametro
        .contains()     // retorna boolean caso encontra o elemento especificado
        
~~~

###### List<T> ou  Set
~~~Java
// List<T>  é uma interface, ou seja, implementa metodos do ArrayList.
// Set      é uma interface, ou seja, implementa metodos do HashSet.
~~~
