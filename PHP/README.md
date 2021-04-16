#  PHP
Repositório com os estudos realizados sobre a linguagem PHP.

- PHP ( Personal Home Page )  - 1994
- PHP: Hypertext Preprocessor
- versão 5 (2004)
- versão 7 (2015) : `->` ,  `[]` , `()` , {}` , `::` , `foreach`
- versão 8 (2020)

[Documentação](https://www.php.net/manual/pt_BR/)

# Sintaxe Básica
- `<?php echo 'Ola Mundo'; ?>`
- `short_open_tag` <?= 'imprima essa string' ?>
- Comentários:
  - `// Comentário`
  - `/* Comentários */`
  - `# Comnetário`


# Tipos
- Escalares:
  - bool : `$a_bool = TRUE;`
  - int : `$an_int = 12;`
  - float (ou double) : `$a_double = 1_234.567;` (a partir do PHP 7.4.0)
  - string : `$a_str  = "foo";`
- Compostos:
  - array
  - object
  - callable (callbacks) 
    - `call_user_func()`
    - `usort()`
  - iterable : [ver +](https://www.php.net/manual/pt_BR/language.types.iterable.php)
- outros:
  - resouce
  - NULL : 
    - `is_null()` 
    - `unset()`
  - mixed
  - void

## conversão de tipos

- (int), (integer) - molde para inteiro
- (bool), (boolean) - converte para booleano
- (float), (double), (real) - converte para número de ponto flutuante
- (string) - converte para string
- (array) - converte para array
- (object) - converte para objeto
- (unset) - converte para NULL

~~~PHP
<?php
  $x = 10;             // $x é um inteiro
  $y = (boolean) $x;   // $y é um booleano
?>
~~~
[ver +](https://www.php.net/manual/pt_BR/language.types.type-juggling.php#language.types.typecasting)




# Variáveis

- `array()` [ver +](https://www.php.net/manual/pt_BR/language.types.array.php)
~~~
array(
    chave  => valor,
    chave2 => valor2,
    chave3 => valor3,
    ...
)
~~~

~~~PHP
<?php
$array = array(
    "foo" => "bar",
    "bar" => "foo",
    100   => -100,
    -100  => 100,
);
var_dump($array);
?>
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
