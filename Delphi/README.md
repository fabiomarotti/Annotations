# Embarcadero Delphi 
[site (oficial)](https://www.embarcadero.com/br/)

> Informações
- Delphi é um Ambiente de Desenvolvimento (ferramenta/conceito)
- RAD (Rapid Applicaiton Development)
- Linguagem Pascal
- VCL (Visual Component Library)
- CLX (Component Library for Cross Platform) 
  - Borland Kylix 

> História
- 1995 : Borland (Turbo Pascal) -> para Windows 3.1 (16 bits)
- 2006 : CodeGear 
- 2008 : Embarcadero

> versões da IDE RAD Studio 
- Delphi 1 [1994]
- ...
- Delphi 7 [2002]
- ...
- Delphi 2010
- Delphi XE
- Delphi XE2 [2011] *
- ...
- Delphi XE8 [2015]
- RAD Studio 10.0 (Seattle) [2015]
- RAD Studio 10.1 (Berlim) [2016]
- RAD Studio 10.2 (Tokyo) *
- RAD Studio 10.3 (Rio)
- RAD Studio 10.4 (Sydney)

> Arquivos 
- Executaveis (Project Manager)
  - `/Win32/Debug` compilar com o Debug selecionado (aquivo maior: Desenvolvimento)
  - `/Win32/Release` compilar com o Release selecionado (arquivo menor : Final)
  - `*.dcu` arquivo pre-compilado, para auxiliar o `*.exe`
- `VCL Form Application` 
  - `Delphi Unit` : 
    - `*.pas` : arquivo de código
    - `*.dfm` : informações complementares de um formulário
      - ../Forms/uFrmPrincipal -> (Objeto: frmPrincipal)
      - ../Forms/FrmPrincipalU
  - `Delphi projects` : informações do Projeto
    - `*.dproj` : Usar este arquivo para editar o projeto
      - ../Projeto/Nome_Projeto 
    - `*.dproj.local` 
    - `*.dpr` : **Arquivo para se abrir os projetos**
    - `*.res` : arquivos de icones, imagens, outros
    - `~arquivo` : arquivos de backup
- `VCL Form `
  - `Delphi unit (*.pas)`
    -  ../Forms/uFrmCadastrar -> (Objeto: frmCadsatrar)
- `Unit` arquivo: *.pas


## Data Module
- Formulario centralizador de componetes não visuais
- componentes de Banco de Dados
- boa prática, nomear como:
  - `dmModulo` : objeto
  - `dmUnidadeMdoulo` : arquivo

## Comentários e Regiões
> Comentar
~~~Delphi
// Comentário em uma linha
~~~

~~~Delphi
{ 
  Comentário em múltiplas linhas
}
~~~

~~~Delphi
{* 
  Comentário em múltiplas linhas
*}
~~~

> Região: possibilidade de Ocultar código
~~~Delphi
{$REGION 'NomeRegion'}
  // código a ser ocultado
{$ENDREGION}
~~~

## Declaração de Variáveis
~~~Delphi
var 
  Nome: string;
Nome := 'Fábio Marotti';
~~~ 

~~~Delphi
var 
  Nome: string := 'Fábio Marotti';
~~~ 

~~~Delphi
var Idade := 20; // compilador infere que é um tipo inteiro
~~~ 

~~~Delphi
for var Contador := 0 to 10 do { ... }
~~~



## Tipos de Dados 
[1 ver +](http://norbertoifsul.blogspot.com/2011/11/tipos-de-dados-no-delphi.html)
[2 ver +](http://www.delphibasics.co.uk/Article.asp?Name=DataTypes)

- Numéricos
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
   Dec1 : Single;   //  7  significant digits, exponent   -38 to +38
   Dec2 : Currency; // 50+ significant digits, fixed 4 decimal places
   Dec3 : Double;   // 15  significant digits, exponent  -308 to +308
   Dec4 : Extended; // 19  significant digits, exponent -4932 to +4932
~~~

- Texto
~~~Delphi
var
   Str1 : Char;        // Holds a single character, small alphabet
   Str2 : WideChar;    // Holds a single character, International alphabet
   Str3 : AnsiChar;    // Holds a single character, small alphabet
   Str4 : ShortString; // Holds a string of up to 255 Char's
   Str5 : String;      // Holds strings of Char's of any size desired
   Str6 : AnsiString;  // Holds strings of AnsiChar's any size desired
   Str7 : WideString;  // Holds strings of WideChar's of any size desired
~~~   

- Lógico
~~~Delphi
 var
   Log1 : Boolean;     // Can be 'True' or 'False'
~~~

- Conjuntos, Enumerados e Subtipos
~~~Delphi
type
   TSuit = (Hearts, Diamonds, Clubs, Spades);    // Defines the enumeration
 var
   suit : TSuit;                                 // An enumeration variable
~~~   

~~~Delphi
type
   TWeek = Set of 1..7;             // Set comprising the days of the week, by number
 var
   week : TWeek;
 begin
   week := [1,2,3,4,5];      // Switch on the first 5 days of the week
 end;
 ~~~

- Constantes
~~~Delphi
const
   FRED          = 'Fred';       // String constant
   YOUNG_AGE     = 23;           // Integer constant
   TALL : Single = 196.9;        // Decimal constant
   NO            = False;        // Boolean constant
~~~   

### Arrays
~~~Delphi
var 
  A: array[0..5] of Integer;
~~~



## Operadores Aritméticos
- `*` multiplicação 
- `/` divisão entre variaveis reais
- `+` soma
- `-` subtração
- `div` divisão entre variaveis inteiras
- `mod` resto da divisão

## Estruturas logicas

> Estrutura de Repetição FOR
~~~Delphi
var
  i: Integer;
  
for i := 0  to  10   do
begin
  ShowMessage( IntToStr(i) );
end;
~~~~

~~~Delphi
var
  i: Integer;
  
for i := 10  DownTo   0  do
begin
  ShowMessage( IntToStr(i) );
end;
~~~   

> Estrutura de Repetição UNTIL
~~~Delphi
i := 10;

repeat
  ShowMessage( IntToStr(i) );
  Inc( i );
until ( i >= 10 );
~~~   

## Unidades (Unit)
>  Estrutura de uma Unit:
- `unit` : nome do arquivo
- `interface` : Declarações
  - `uses`: Declarar Bibliotecas
  - `type` 
    - `TClasse = class` , `end;` : Declarar Classe
  - `var` : Declarar variaveis
  - `implementation`: Implementação de métodos ou procedimentos

> Exemplo da estrutura de uma Unit
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

## Funções

- são declaradas na seção `interface`
- `Result` ou `nome_função`para trabalhar o Retorno da função

> Função 
~~~Delphi
unit nome_unidade; 

interface 
    function  Somar   (a,b: Integer);
  
implementation 
  function Somar(a, b: Integer): Integer;
  begin
      Result := a + b;
  end;
    
end. // fim unidade
~~~

> Chamando a Função
~~~Delphi
var
   resultado: Integer;
  { ... }
  resultado := Somar(10, 20);
~~~

## Procedimetnos
- Pode receber um ou nenhum parâmetro


> Procedimento
~~~Delphi
unit nome_unidade; 

interface 
    procedure escreverNome ( n := String );

implementation 
  procedure escreverNome( n );
  begin
    println( "Ola ", n );
  end;
    
    
end. // fim unidade
~~~

> Pasagem por Referencia
- `var`
- `out`
~~~Delphi
function TForm1.SomaValor(var x: integer): Integer;
begin
     //Adiciona 1000 ao valor de a
     x := x + 1000;
     //Retorna o valor de a
     Result := x;
end;
~~~

## Componentes
> Interface
- `TMainMenu` (Standard)
- `TPanel` (Standard)
- `TButton` (Standard) : Botão
- `TPageControll` (Win32) > (new Page)
- `TDBGrid` (Data Controls)
- `TLabeledEdit` (Additional)
- `TSpeedButton` (Additional) : Botão

  
## Funções do Delphi
- `INC(x)` : x := x + 1;
- `DEC(x)` : x := x - 1;
- `LOW(x)` : retorna o valor mais baixo
- `StrToInt(x)` : de String para Integer
- `IntToStr(x)` : de Integer para String


## Teclas de Atalho
- `F12` : Alternar entre Código-View
- `F9` : Executar
- `Ctrl` + `Shift` + `F9` : Executar sem Debug
- `Ctrl` + `seta` : mover componente
- `Ctrl` + `Shift` + `seta` : alterar tamanho do componente
- `Alt`  + `Shift` + `seta` : selecionar codigo, forma quadrada
- `Ctrl` + `Shift` + `C`    : gerar Gets e Sets

> Exibir Ferramentas
- `Ctrl` + `Alt` + `F11`  : Project Manager 
- `Shift` + `Alt` + `F11` : Structure
- `F11`                   : Object Inspecto
- `Ctrl` + `Alt` + `P`    : Tool Palet

# Links
[Conteudo basico para pesquisa](http://www.delphibasics.co.uk/RTL.asp?Name=Low)
