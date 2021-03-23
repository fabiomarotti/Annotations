# TypeScript
Repositório com estudos realizados sobre TypeScript

Considerações: TypeScript > ECMScript6 (2015) > ECMAScript5 (2009)

https://www.typescriptlang.org/

* Instalação:

$ npm install -g typescript	    // pre-requesito: Node.js

$ tsc nome_arquivo.ts --watch   // Compilar via terminal

$ tsc --init                    // cria arquivo tsconfig.jason (conf, regras, compatibilidade,..)

# Sintaxe

# Tipos de dados

 * `boolean`
~~~TypeScript
//boolean (true / false)
let conectado: boolean
    conectado = true / false
~~~

* `string`
~~~TypeScript
// String ('texto' , "texto", `texto`) // backstick
let message: string
    message = `texto ${ conectado }`  // incluir variavel isOpen
~~~

* `number`
~~~TypeScript
// number (int, float, hex, binary)
let total: number
   total = 45.6  / 0xff0 (hexa)
~~~

* `Array`
~~~TypeScript
// array
let items: number[]  //array de numeros
    items = [1,2,3]

let items: string[]
    items['um', 'dois']

let total: Array<number>
    items = [1,2,3]

let items: Array<string>	// notação generic
    items['um', 'dois']
~~~

* `tuple`
~~~TypeScript
// tuple: array sabe o numero de elementos e o tipo
let titulo: [number, string, boolen]
    titulo = [5 , "texto", true]
~~~

* `enum`
~~~TypeScript
// enum : conjunto Chave/Valor
enum Cores {
	branco = '#fff',   
	preto  = '#000'
}
~~~

* `any`
~~~TypeSript
// any : QUALQUER COISA
let coisa: any
    coisa = "true" // string
    coisa = true   // boolena
    coisa = 123    // numero
~~~

* `void`
~~~TypeScript
// void
function menssagem(): void{	// tipar a funçao >> retorna nada, float, ..
	console.log('texto')
}
~~~

* `null`
~~~TypeScript
// null / undefined
// tipo não primitivo
type coisa = string | underfined   // pode ser string ou nao definido
~~~

* `never`
~~~TypeScript
// never (nunca vai retornar)
function menssagem(): never {
	throw new messagem("Error");
}
~~~

* `Object`
~~~TypeScript
// Object "qualque coisa não primitiva" (equivale a uma Classe)
let compra: object
    compra = {
	id: 	"identificação",
	valor: 	123.45
    }

~~~ 

* Tipo por Inferência
~~~TypeScript
function passarDetalhes( id: number | string , item: string){
	console.log("Temos identificação: ${id} e o seu item: ${item}.")
}

passarDetalhes(123, "texto")	// correto
passarDetalhes("123", "texto")	// correto tmb devido ao Union |
~~~

* Type Alias (Apelido)
~~~TypeScript
// type aliases
type Uid = number | string | undefined

function passarDetalhes( id: Uid , item: string){
	console.log("Temos identificação: ${id} e o seu item: ${item}.")
}

passarDetalhes(123, "texto")	// correto
passarDetalhes("123", "texto")	// correto tmb devido ao Union |
~~~

~~~TypeScript
type SO = "Windows" | "linux" | "MacOS"

let sistema: SO
~~~

* Type Aliases com Intersection
~~~TypeScript
type Pessoa = {
	id: 	number;
	nome: 	string;
	email?: string; 	// ?: torna opcional de preencher o campo
}

type Bens ={
	dinheiro: number;
	casa: boolean;
}

type PessoaBens: Pessoa & Bens
~~~

~~~TypeScript
// criando variavel
const conta : Pessoa = {
   id: 	  123,
   nome:  "Fulano
}

const contaPB : PessoaBens ={
   id: 456,
   nome: "Ciclano",
   dinheiro: 500,
   casa: true
} 
~~~

# Modificadores de acesso

- `public` 	// acesso total (padrão)
- `private`	// acesso apenas dentro da classe
- `protected`	// acesso apenas dentro da classe e aos seus herdeiros
- `static` 	// acesso nivel de classe e nao de instancia	

- `partial`	// Todas os elementos são opcionais (type)
- `required`	// Todas os elementos são obrigatórios (type)
- `readonly`	// apenas leitura da variavel, não pode ser reatribuido
- `abstract` 
- 
- `recored` <key, type>
- `pick`
- `omit`
- `exclude`
- `extract`
- `NonNullable` <type>
- `parameters` 
`constructorParameters`
`returnType`
`intanceType`



# Classes

* Pre-requesito instalar:

$ npm install -g nodemon

$ nodemon dist/nome_arquivo.js   // onde fica o arquivo JavaScript

~~~TypeScript
class Pessoa{
    nome: string;
    idade: number;
    
    // Construtor
    constructor(n: string, i: number){
        this.nome  = n;
        this.idade = i;
    }
    
    // Método
    dizerBomBia(): void{
      console.log("Bom dia ${this.nome} e idade: ${this.idade} .");
    }
}    
~~~

~~~TypeScript
const p = new Pessoa("Fulano", 30);
    
console.log(p);		// Objeto
console.log(p.nome);	// Propriedade específica do objeto
console.log(p.idade);
p.dizerBomBia();
~~~

~~~TypeScrit
class Funcionario extends Pessoa{
   salario : number;
   cargo   : string;
   
   // Construtor
   constructor(n: string, i:number, s: number, c: string){
	super(n, i);
     	this.salario = s;
     	this.cargo   = c;
   }
   
   // Métodos
   function dadosFuncionario(): void{
    console.log("Funcionário: ${n} , Idade: ${i}, Salário: R$ ${s} ");
   }
}
~~~

~~~TypeScript
 const f = Funcionario("Fulano", 33, 1500.00 , "técnico");
 
 console.log(f.nome);
 console.log(f.idade);
 f.dizerBomBia();
 f.dadosFuncionario();
 ~~~
 
 # Interface
 
 # Modulos
 
