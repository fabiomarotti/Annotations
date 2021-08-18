
# Delphi (10.3) :: Sintaxe e Comandos

## Comentários e Regiões
> Comentar:
~~~Delphi
// Comentário em uma linha
~~~

~~~Delphi
{ Comentário em múltiplas linhas }

{* Comentário em múltiplas linhas *}
~~~

> Região: possibilidade de Ocultar código
~~~Delphi
{$REGION 'NomeRegion'}
  // código a ser ocultado
{$ENDREGION}
~~~

## Subáreas
- `var`
- `uses`
  - crt
- `label`
- `const`
- `type` (Proprio tipo de dados)
  - Scalar (semelhante ao array de mesmo tipo)
  - Subrange, 
  - Set, 
  - Record (tipos variados) [ver+](https://www.youtube.com/watch?v=Qe4ERd1ECtw&list=PLIz6mntaZSG1aTBEg1g6RkBO5HZALcGy-&index=17)
- `procedure`
- `function`
- Record  : Registros,  é uma forma de criar uma estrutura que possa armazenar valores de diferentes tipos de dados
- File    : Arquivos
- Set     : Conjuntos
- Pointer : Ponteiros
- `with` : [exemplo](https://www.devmedia.com.br/forum/como-usar-o-comando-with/146587)


## Hereditariedade TObject
- TObject
  - TPersistent
    - TComponent
    - TCollection
      - TOwnedCollection
    - TCollectionItem
      - TControl
        - TWinControl
          - TCustomControl
            - TCustomPanel

## Controle de Componentes

- `Owner` (Proprietário)
> Quando inserimos um componente no formulário em tempo de design, ou seja, quando um componente é arrastado para o formulário, o Delphi cria uma instância do mesmo, passando o formulário como parâmetro no construtor do componente, indicando que ele é o owner do component. <br>
> se torna o Pai, responsavel pelos componentes Filhos (liberação de memória). <br>
> Chamar o Desctructor do Owner aciona o desctructor dos filhos.

~~~Delphi
constructor Tcomponent.Create(AOwner: TComponent);
begin
  FComponentStyle := [csInheritable];
  if AOwner <> nil then
    AOwner.InsertComponent(Self);
end;
~~~
[ver exemplo](https://www.devmedia.com.br/delphi-parent-e-owner-o-que-sao/13887)

> se AOwner for <> nil, então é executado o método InsertComponent do AOwner, passando o próprio objeto que está sendo criado como parâmetro. Este método por sua vez, se encarregará de adicionar o componente criado na lista de componentes dos quais o Owner é o responsável. Pronto, assim está estabelecida a relação “Pai“ e “Filho” dos componentes.

- `Parent` (Pai)
  - estabelece também uma relação de conteúdo e container

- `Self`
  - Self.Parent ?


## Unit
~~~Delphi
Unit exemplo_unit;

Interface
  // declaração
  procedure EscreverTexto;

Implementation
  // implementação
  procedure EscreverTexto
  Begin
    WriteLn('Ola Mundo');
  End;
  
End. // Fechamento do Implementation
~~~

## Declaração de Variáveis
~~~Delphi
var 
  Nome: string = 'Fábio Marotti'; // testar
~~~ 

~~~Delphi
var 
  Nome: string;
Begin
  Nome := 'Fábio Marotti'; // variavel inicializada
End;
~~~ 

~~~Delphi
var Idade := 20; // compilador infere que é um tipo inteiro
~~~ 

## Modificadores de Acesso:
- `Private`
- `Protected`
- `Public`
  - `Property` (ver + em POO)
- `Published`
- `Const`
- `Resourcestring` parecida com **const**, porem possui um gerenciamento de memoria melhor em ambito do sistema 

## Operadores Aritméticos:
- `+`, `-`, `*`, `/` (real), `div` (inteiro), `mod` (resto da divisão)

## Operadores Lógicos:
- `=` , `<>` , `>=`, `<=`, `AND`, `OR`, `NOT`, `True`, `False`
- `:=` (atribuição)

## Tipos de Dados 
### Types:
- Define-se um **tipo** 

~~~Delphi
type
  // Letras se torna um tipo vetor de caracteres
  Letras  = Array[1 .. 23] Of Char;
~~~

> Instanciando uma varaivel do tipo criada
~~~Delphi
var
  // alfabeto é uma instância do tipo Letras
  alfabeto : Letras;

alfabeto[1] := 'a';
alfabeto[2] := 'b';
alfabeto[3] := 'c';
~~~

[1 ver +](http://norbertoifsul.blogspot.com/2011/11/tipos-de-dados-no-delphi.html)

[2 ver +](http://www.delphibasics.co.uk/Article.asp?Name=DataTypes)

### Numéricos:
~~~Delphi
var
   // Integer data types :
   Int1 : Byte;     //                        0 to 255
   Int2 : ShortInt; //                     -127 to 127
   Int3 : Word;     //                        0 to 65,535
   Int4 : SmallInt; //                  -32,768 to 32,767
   Int5 : LongWord; //                        0 to 4,294,967,295
   Int6 : Cardinal; //                        0 to 4,294,967,295
   Int7 : LongInt;  //           -2,147,483,648 to 2,147,483,647
   Int8 : Integer;  //           -2,147,483,648 to 2,147,483,647
   Int9 : Int64;  // -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807
~~~   

~~~Delphi
var 
   // Decimal data types :
   Dec1 : Single;     //  7      significant digits, exponent   -38 to +38
   Dec2 : Currency;   // 50+     significant digits, fixed 4 decimal places
   Dec3 : Double;     // 15      significant digits, exponent  -308 to +308
   Dec4 : Extended;   // 19      significant digits, exponent -4932 to +4932
   Dec5 : Real;       // 11/12   significant digits,           2,9 E-39 a 1,7 E+38
~~~

> Delimitar numero no modo Console
~~~Delphi
WriteLn('numero: ', x:2:2);
~~~

### Texto:
~~~Delphi
var
   Str1 : Char;        // Holds a single character, small alphabet (1 byte)
   Str2 : WideChar;    // Holds a single character, International alphabet
   Str3 : AnsiChar;    // Holds a single character, small alphabet
   Str4 : ShortString; // Holds a string of up to 255 Char's
   Str5 : String;      // Holds strings of Char's of any size desired  (max 256 bytes)
   Str6 : String[n];   // Holds strings of Char's of any size desired  (2 a 256 bytes)
   Str7 : AnsiString;  // Holds strings of AnsiChar's any size desired
   Str8 : WideString;  // Holds strings of WideChar's of any size desired
~~~   


### Vetores e Matrizes (Array Unidimensional e Array Multidimensional):

> Vetores (Array Unidimensional)
~~~Delphi
var 
  lista : Array[0 .. 3]   Of   String;

lista[0] := 'Fulano';
lista[1] := 'Beltrano';
lista[2] := 'Ciclano';
lista[3] := 'Mariano';
~~~

> Matrizes (Arrays Multidimensionais)
~~~Delphi
var
  matriz_2x2 : Array[1..2 , 1..2]  Of  Integer
  matriz_3x3 : Array[1..3]         Of  Array[1..3]   Of    Integer;

// atribuição de valores matriz 2x2
matriz_2x2 : = [
                  [ 1 , 2 ],
                  [ 3 , 4 ]
               ];

// atribuição de valores matriz 3x3
matriz_3x3 :=  [
                 [ 1 , 2 , 3 ] ,
                 [ 4 , 5 , 6 ] ,
                 [ 7 , 8 , 9 ]
               ]; 
~~~

> Declaração do tamanho o Array pela função SetLength:
~~~Delphi
var
  vetor       : Array Of   Integer;
  matriz      : Array Of   Array Of   Real;
  matrizMulti : Array Of   Array Of   Array Of  Char;
  
 // Setando tamanho dos Arrays
 SetLength(vetor       ,3          );
 SetLength(matriz      ,3  ,3      );
 SetLength(matrizMulti ,3  ,3  ,3  );
~~~

### Lógico:
~~~Delphi
 var
   Log1 : Boolean;     // Can be 'True' or 'False'
~~~

### Enumerados: 
- São uma Lista organizada de itens 
- Sao acessados por um nome de valor e não por um número
 
~~~Delphi
type
   TDiasDaSemana = (Domingo, Segunda, Terca, Quarta, Quinta, Sexta, Sabado);    
 
 var
   dia : TDiasDaSemana;
   dia := Segunda;
~~~   

### Conjuntos e Sub Conjutnos
- Os elementos não se repetem
- Operações:
  - `+` retorna a **união** de dois conjuntos
  - `-` retorna a **diferença** entre dois cnojutnos
  - `*` retorna a **interseção** de dois conjuntos
  - `=` retorna True caso os dois conjuntos são **iguais** (Tem os mesmos elementos)
  - `<=` retorna True, se o primeiro conjunto é **Sub Conjunto** do segundo conjunto.
  - `>=` retorna True, se o primeiro conjunto é **Super Conjunto** do segundo conjunto
  - `<>` retorna True se os dois conjutnos não forem identicos
  - `IN` retorna True se um elemento está **incluso** em um conjunto

~~~Delphi
type
  TFrutas   = (Maça, Abacaxi, Pera, Banana);
  TConjunto = Set of TFrutas;

var
  // Declaração das variaveis como do tipo Conjunto
  segunda : TConjunto;
  terça   : TConjunto;
  quarta  : TConjunto;
  quinta  : TConjunto;
  sexta   : TConjunto;
  sabado  : TConjunto;
  domingo : TConjunto;
~~~

~~~Delphi
  // inicializando as varaiveis
  segunda := [];
  terça   := [];
  quarta  := [];
  quinta  := [];
  sexta   := [];
  sabado  := [];
  domingo := [];
~~~

~~~Delphi
  // atribuindo os elementos ao TConjunto
  Include(segunda , Maça);
  Include(terça   , Maça);
  Include(quarta  , Abacaxi);
  Include(domingo , Maça);
~~~

~~~Delphi
  // exemplo: Operação de Igualdade de Conjuntos
  If (segunda = domingo) Then
    // Conjuntos iguais  
  Else
    // Conjuntos diferentes
  End;
~~~

~~~Delphi  
  // exemplo: Elemento pertence ao Conjunto
  If (Maça in segunda) Then
    // Segunda contem Maça
  Else
    // Segunda não contem Maça
  End;
 ~~~
 
### Constantes
~~~Delphi
const
   PI : Single   = 3.14;         // Decimal tipo Single constant
   FRED          = 'Fred';       // String constant
   YOUNG_AGE     = 23;           // Integer constant
   NO            = False;        // Boolean constant
~~~   


## Ponteiros :
- `@` : acessa o Endereço de Memória de uma variavel. Exemplo: `@variavel`
- `^` : Declarar uma variável do tipo ponteiro e/ou Acessar o Valor de um ponteiro.
  - (Define) ` ponteiro : ^interger `
  - (Acessa) ` ponteiro^ ` 
- Atribuição de Endereço de Memória : ` ponteiro := @variavel; `
- Um ponteiro recém declarado que não aponta para nenhum lugar tem o valor `nil` (sem referência a um endereço de memória)

> Declaração das variaveis:
~~~Delphi
var 
  x_variavel  :  Integer ;
  x_ponteiro  : ^Integer ;
~~~

> Endereço de Memória:
~~~Delphi
// O Endereço de Memória da x_variavel é: 
IntToStr( Integer( @x_variavel ) ) ;

// O Endereço de Memória do x_ponteiro é: 
IntTosSr( Integer( x_ponteiro ) );
~~~

> Valor:
~~~Delphi
// O valor da varaivel x_varaivel é:
IntToStr( Integer( x_varaivel ) );

// O valor apontado pela variavel x_ponteiro é: 
IntToStr( Integer( x_ponteiro^ ) );
~~~

> Tamanho em Memória:
~~~
// O tamanho da x_variavel é: 
IntToStr( SizeOf( x_variavel) );

// O tamanho do x_ponteiro é: 
IntToStr( SizeOf( x_ponteiro ) );
~~~



## Estruturas de Programação:
> `Break`, `Abort` , `Continue`, `Exit`
- For .. (To/Downto) .. Do
- While .. Do
- Repeat .. Until
- Case .. Of .. Else
- If .. Then .. Else

### For .. (To/Downto) .. Do: 
> For .. to .. do (crescente):
~~~Delphi
For   var i := 0    To      10    Do
Begin
  ShowMessage( IntToStr(i) );
End;
~~~~

> For .. dowto .. do (decrescente):
~~~Delphi
For   var i := 10    DownTo   0    Do
Begin
  ShowMessage( IntToStr(i) );
End;
~~~~

### While .. Do
> Whie .. Do:
~~~Delphi
var contador := 0;
  
While   contador <= 10    Do
Begin
  Contador:= Contador + 1;
End;
~~~

~~~Delphi
While True Do
Begin

  If [condição] Then
    continue;
  
Break;
End;
~~~

### Repeat .. Until
> Repeat .. Until:
~~~Delphi
contador := 10;

Repeat
Begin
  ShowMessage('Contandor em: '+ contador );
  Inc( contador );  // Função de Incremento
End;  
Until (i <= 10);
~~~  

### Case .. Of .. Else 
~~~Delphi
Case <expressão> Of   
  
    Valor_1: <Bloco de comandos>    
    Valor_2: <Bloco de comandos>   
    ......
    Valor_n: <Bloco de comandos>  
  
Else: 
  <Bloco de comandos> 
End;
~~~


### If .. Then .. Else
~~~
if (x > 10) then
begin
 // codigo
end;
~~~

~~~
if (x > 10) then
begin
 // se Sim
end
else
begin
  // se Não
end;
~~~


# Unidades (Unit)
>  Estrutura de uma Unit:
- `unit` : nome do arquivo
- `interface` : Declarações
  - `uses`: Declarar Bibliotecas
  - `type` 
    - `TClasse = class` , `end;` : Declarar Classe
  - `var` : Declarar variaveis
  - `implementation`: Implementação de métodos ou procedimentos

> Exemplo da estrutura de uma Unit:
~~~Delphi
unit nome_unidade; 

  interface
  // região de declaração
  
    uses
    // Bibliotecas do Sistema e Componentes
    // Ex.: System.Classes, System.SysUtils
    
    type
    // Classes
    
    var
    // Variaveis
  
  implementation
  // região de implementação de código
  
    uses
    // Bibliotecas Implementadas para o Sistemas
    // Ex.: uTelaPrincipal

end. // fim unidade
~~~

# Função e Procedimentos
~~~Delphi
procedure Mostrar1 (      str: string);
procedure Mostrar2 (var   str: string);
procedure Mostrar3 (const str: string);
~~~

## Função

- são declaradas na seção `interface`
- `Result` ou `nome_funcao` para trabalhar com o Retorno da função

> Função retornando valor pelo Result: 
~~~Delphi
interface 
    Function  Somar  (a,b: Integer) : Integer;
  
implementation 
    Function Somar(a, b: Integer): Integer;
    Begin
      Result := a + b;
    End;
~~~

> Chamando a Função:
~~~Delphi
var
   resultado: Integer;
   
Begin
  resultado := Somar(10, 20);
end;
~~~

## Procedimento

> Procedimento (sem parametro):
~~~Delphi
interface 
  // Declaração do Procedimento
  Procedure escreverNome( );

implementation 
  // Instanciação do Procedimento
  Procedure escreverNome( );
  Begin
    println('Ola Mundo!');
  End;
~~~

> Procedimento (com parametro):
~~~Delphi
interface 
  // Declaração do Procedimento
  Procedure escreverNome( n : String );

implementation 
  // Instanciação do Procedimento
  Procedure escreverNome( n );
  Begin
    println('Ola ' + n );
  End;
~~~

> Pasagem por Referencia em Funções ou Procedimentos:
- `var`
- `out`

~~~Delphi
Function TForm1.SomaValor(var x: integer): Integer;
Begin
     //Adiciona 1000 ao valor de a
     x := x + 1000;
     //Retorna o valor de a
     Result := x;
End;
~~~



  
## Funções do Delphi: 
- `INC(x)` : x := x + 1;
- `DEC(x)` : x := x - 1;
- `LOW(x)` : retorna o valor mais baixo
- `DATE()` : retorna Data autal
- `NOW()` : Data e Hora atual
- `IncDay(data , dias)` : Incrementa dias a uma data
- `DaysBetween(data1 , data2)` : numero de dias entre duas datas

> Para Strings:
- `SetLength` Redefine o comprimento da String
- `Trim` Remove os espaços em brancos
- `Insert` Inserir String a partir de um indice
- `Length` número de caracteres da string
- `LowerCase` minusculas
- `UpperCase` maiuscula

> Conversões:
- `StrToIntDef(texto, -1)`
  - x := StrToInt(texto, -1) **(caso não converta, x := -1)** 
- `CurrToStr` monetário para String 
- `IntToStr(x)`   
- `FloatToStr(x)` 
- `FloatToStrF` : String formatada 
- `StrToInt(x)`   
- `StrToFloat`
- `DateToStr`
- `StrToDate`
- `DateTimeToStr`
- `TimeToStr`
- `Parse` converte para valor representativo
- `TryParse` Tenta converter String para um numero


- `RANDOM()` : Valor aleatório (usar Randomize)
- `QuotedStr(x)`  : deixa entre aspas simples
  - ex.:  `QuotedStr('*'+campo+'*' ) `



# Imagens

- Hint : dica
- ShowHint : Mostrar dica
- TJPEGImage , uses JPEG
- TMemoryStream

# Arquivos
~~~Delphi
// Apagar arquivo
Windows.DeleteFile('c:arquivo.txt');

// Apagar Pasta
Windows.RemoveDirectory('c:pasta');
~~~



# Design Patterns
[DP - Strategy](https://drgarcia1986.wordpress.com/2014/04/25/design-pattern-strategy-com-delphi/)

# Links
[Conteudo basico para pesquisa](http://www.delphibasics.co.uk/RTL.asp?Name=Low)

[dicas prontas](http://www.planetadelphi.com.br/dicas/2)

