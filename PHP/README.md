#  PHP
Repositório com os estudos realizados sobre a linguagem PHP.

- PHP ( Personal Home Page )  - 1994
- PHP: Hypertext Preprocessor
- versão 5 (2004)
- versão 7 (2015) : `->` ,  `[]` , `()` , {}` , `::` , `foreach`
- versão 8 (2020)

[Documentação](https://www.php.net/manual/pt_BR/)

# Sintaxe Básica
- `<?php` `echo 'Ola Mundo';` `?>`
- `<?=` `'imprima essa string' ` `?>` : short_open_tag
- Comentários:
  - `//` Comentário
  - `/*` Comentários `*/`
  - `#` Comentário


# Tipos
- **Escalares:**
  - `bool` : `$a_bool = TRUE;`
  - `int` : `$an_int = 12;`
  - `float` (ou double) : `$a_double = 1_234.567;` (a partir do PHP 7.4.0)
  - `string` : `$a_str  = "foo";`
- **Compostos:**
  - `array`
  - `object`
  - `callable` (callbacks) 
    - `call_user_func()`
    - `usort()`
  - `iterable` : [ver +](https://www.php.net/manual/pt_BR/language.types.iterable.php)
- **outros:**
  - `resouce`
  - `NULL` : 
    - `is_null()` 
    - `unset()`
  - `mixed` : um parâmetro pode aceitar vários tipos.
  - `void` : não há valor a ser retornado.

- Conversão de tipos
  - `(int)`, `(integer)` - molde para inteiro
  - `(bool)`, `(boolean)` - converte para booleano
  - `(float)`, `(double)`, `(real)` - converte para número de ponto flutuante
  - `(string)` - converte para string
  - `(array)` - converte para array
  - `(object)` - converte para objeto
  - `(unset)` - converte para NULL

~~~PHP
<?php
  $x = 10;             // $x é um inteiro
  $y = (boolean) $x;   // $y é um booleano
?>
~~~
[ver +](https://www.php.net/manual/pt_BR/language.types.type-juggling.php#language.types.typecasting)




# Variáveis

## `array()` 
- [ver +](https://www.php.net/manual/pt_BR/language.types.array.php)
- `var_dump($lista)`
- `print_r($lista)`

~~~PHP
// Acessando
$lista[0]
~~~

~~~PHP
// (chave) => (valor)

$lista = array(
            "foo"   =>  "bar" ,
            "bar"   =>  "foo" ,
            100     =>  -100  ,
            -100    =>  100   
         );
~~~

~~~PHP
// a partir do PHP 5.4

$lista = [
    "foo" => "bar",
    "bar" => "foo",
];
~~~

~~~PHP
$lista = array("foo", "bar", "hello", "world");
~~~

~~~PHP
$Capitulo = array(
            "nome"           => "Zé",
             42              => 24,
             "SubCapitulo"   => array(
                                "Topico" => array(
                                            "cor" => "red"
                                            )
                                )
            );
~~~


# Funções
- `isset()` : Informa se a variável foi iniciada.
- `empty()` : Informa se a variável é vazia.
- `eval()` : Executa uma string como código PHP. [ver +](https://www.php.net/manual/pt_BR/function.eval.php)
- `call_user_func()` : Chama uma função de usuário dada pelo primeiro parâmetro.
- `include()` : Adiciona um arquivo dentro de outro
- `array_pad()`
- `aray_keys()`
- `implode()`
- `count()`
- `die()`


# Utilitários
- `@` : supressão de erros [ver +](https://pt.stackoverflow.com/questions/50166/qual-a-fun%C3%A7%C3%A3o-do-arroba-no-inicio-de-express%C3%B5es-em-php)
- `->`
- `=>`
- `::`
- `namespace`
  - `include` 
  - `use` x `as` y
  - `\` namespace `\` classe `::` função() 
- `__DIR__`
- `define`
- `const`
- `self::`
- `$this`


## Funçoes para Banco de Dados
- `mysqli_connect()` : `host`,`username`,`passwd`,`dbname`,`port`,`socket`
  - `mysqli::connect`
  - `mysqli::__construct`
- `mysqli_real_connect()` - Opens a connection to a mysql server
- `mysqli_options()` - Set options
- `mysqli_connect_errno()` - Retorna o código de erro da ultima chamada a função connect
- `mysqli_connect_error()` - Retorna uma string descrevendo o ultimo erro da função connect
- `mysqli_close()` - Fecha uma conexão aberta anteriormente com o banco de dados

- `mysqli_set_charset()`
- `mysqli_change_user()`
- `mysqli_init()`

# Variáveis pré-definidas
- `$GLOBALS` — Referencia todas variáveis disponíveis no escopo global
- `$_SERVER` — Informação do servidor e ambiente de execução [ver +](https://www.php.net/manual/pt_BR/reserved.variables.server.php)
- `$_GET` — HTTP GET variáveis
- `$_POST` — HTTP POST variables [ver +](https://www.php.net/manual/pt_BR/language.variables.external.php)
- `$_REQUEST` — Variáveis de requisição HTTP 
- `$_SESSION` — Variáveis de sessão
- `$_FILES` — HTTP File Upload variáveis
- `$_ENV` — Environment variables
- `$_COOKIE` — HTTP Cookies
- `$php_errormsg` — A mensagem de erro anterior
- `$http_response_header` — Cabeçalhos de resposta HTTP
- `$argc` — O número de argumentos passados para o script
- `$argv` — Array de argumentos passados para o script

# POO - Classes e Objetos
- [ver+](https://www.php.net/manual/pt_BR/language.oop5.php)

~~~PHP
// Classe
class Pessoa
{
    // Construtor
    public function __construct() { }
    
    // Variaveis
    public      $var01   = 'Valor01';
    protected   $var02   = 'Valor02';
    private     $var03   = 'Valor03';

    // Métodos
    function exibirDados()
    {
        echo $this->var01;
        echo $this->var02;
        echo $this->var03;
    }
}
~~~

~~~PHP
// Instância
$p = new Pessoa();

// Acesso aos Dados 
echo $p->var01; // Funciona
echo $p->var02; // Erro Fatal
echo $p->var03; // Erro Fatal

// Acesso aos Métodos 
     $p->exibirDados(); 
echo Pessoa::exibirDados();
~~~


~~~PHP
// Herança de Classe
class Mutante extends Pessoa
{

}
~~~


~~~PHP
// Classe Abstrata
abstract class Viver 
{

}
~~~




----------
Tópicos
- Sintaxe Básica
- Tipos
- Variáveis
- Constantes
- Expressões
- Operadores
- Estruturas de Controle
- Funções
- Classes e Objetos
- Namespaces
- Erros
- Exceções
- Generators
- Attributes
- Referências
- Variáveis pré-definidas
- Exceções pré-definidas
- Interfaces e Classes pré-definidas
- Opções e parâmetros de contexto
- Protocolos e Wrappers suportados
