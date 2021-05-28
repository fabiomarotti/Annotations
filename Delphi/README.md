# Embarcadero Delphi 
[Site (oficial)](https://www.embarcadero.com/br/)

[Exemplos (oficial)](http://docwiki.embarcadero.com/CodeExamples/Sydney/en/Code_Examples_Index)

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

> versões 
- Delphi 1 [1995]
- Delphi 7 [2002]
- Delphi 2010
- Delphi XE
- Delphi XE2 [2011] *
- Delphi XE8 [2015]
- RAD Studio 10.0 (Seattle) [2015]
- RAD Studio 10.1 (Berlim) [2016]
- RAD Studio 10.2 (Tokyo) [2017] *
- RAD Studio 10.3 (Rio)
- RAD Studio 10.4 (Sydney)

> Arquivos importantes no Delphi
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

> Principais Abas para Componentes
- `Standard` : Componentes como botões, botões de rádio, caixa de lista, caixa Box, barras de rolagem, recursos para edição de texto
- `Additional` : Complementa o Standar com exibição  de  textos,  imagens, botões
- `Win32` : Componentes como zoom, controle deslizantes, barras de progresso, barras de status, ícones, barras de ferramenta
- `System` : Componentes avançados para sistema operacional, como conexão OLE, DDE, multimídia e temporização
- `Data Access` : Conexão com banco de dados e controles de exibição de dados.
- `Data Control` :  Recursos **Standard** e **Additional**, porem os componentes estão ligados ao Banco de Dados
- `dbExpress` : conexão  com  bancos  de  dados  SQL
- `DataSnap` :
- `ADO` : ActiveX Data Objects
  - OLE DB (drivers  de  acesso) 
  - MDAC (Microsoft  Data  Access  Components)
- `Interbase`: SGBD Embarcadero (Sistemas de Banco de Dados da Embarcadeiro)
- `WebServices`: conexão Web services aseados em XML/SOAP
- `Internet` e `Internet Express`: recursos para navegadores

> `Two-Way-Tool` (ferramenta de duas vias)
- Conforme  o  formulário  recebe  componentes  a  Unit  instantaneamente  é  alterada. 


## Comentários e Regiões
> Comentar
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

## Declaração de Variáveis
~~~Delphi
var 
  Nome: string := 'Fábio Marotti';
~~~ 

~~~Delphi
var Idade := 20; // compilador infere que é um tipo inteiro
~~~ 

## Operadores Aritméticos
- `*` multiplicação 
- `/` divisão entre variaveis reais
- `+` soma
- `-` subtração
- `div` divisão entre variaveis inteiras
- `mod` resto da divisão

> Obs.: `:=` atribuição

## Operadores Logicos
- `=` , `<>` , `>=`, `<=`
- `AND`, `OR`, `NOT`  
- `True`, `False`


## Tipos de Dados 

### Numéricos
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

### Texto
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

### Lógico
~~~Delphi
 var
   Log1 : Boolean;     // Can be 'True' or 'False'
~~~

### Conjuntos, Enumerados e Subtipos
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

### Constantes
~~~Delphi
const
   PI : Single   = 3.14;         // Decimal tipo Single constant
   FRED          = 'Fred';       // String constant
   YOUNG_AGE     = 23;           // Integer constant
   NO            = False;        // Boolean constant
~~~   

### Arrays
~~~Delphi
var 
  lista : Array[ 0 .. 3 ] Of String;

lista[0] := 'Fulano';
lista[1] := 'Beltrano';
lista[2] := 'Ciclano';
lista[3] := 'Mariano';
~~~

> Arrays Multidimensionais
~~~Delphi
var
  vetor_inteiros : Array Of   Integer;
  matriz_2x2     : Array Of   Array Of   Real;
  multidimencional : Array Of   Array Of   Array Of  Char;
  
~~~

### Types
> Definindo um tipo 
~~~Delphi
type
  letras  = array[1 .. 23] Of Char;
~~~

> Instanciando uma varaivel do tipo criada
~~~Delphi
var 
  alfabeto : letras;

alfabeto[1] := 'a';
alfabeto[2] := 'b';
alfabeto[3] := 'c';
~~~

[1 ver +](http://norbertoifsul.blogspot.com/2011/11/tipos-de-dados-no-delphi.html)

[2 ver +](http://www.delphibasics.co.uk/Article.asp?Name=DataTypes)




## Estruturas de Programação

> `Break` , `Continue`, `Exit`

### For 
> For .. to .. do (crescente)
~~~Delphi
For   var i := 0    To   10    Do
Begin
  ShowMessage( IntToStr(i) );
End;
~~~~

> For .. dowto .. do (decrescente)
~~~Delphi
For   var i := 10    Downto   0    Do
Begin
  ShowMessage( IntToStr(i) );
End;
~~~~

### While
> Whie .. Do
~~~Delphi
var contador := 0;
  
While   contador <= 10    Do
Begin
  Contador:= Contador + 1;
End;
~~~

### Repeat 
> Repeat .. Until
~~~Delphi
contador := 10;

Repeat
Begin
  ShowMessage('Contandor em: '+ contador );
  Inc( contador );  // Função de Incremento
End;  
Until (i <= 10);
~~~  

### Case
~~~Delphi
Case <expressão> Of   
  
  Valor_1: <Bloco de comandos>    
  Valor_2: <Bloco de comandos>   
  ......
  Valor_n: <Bloco de comandos>  
  
  else: <Bloco de comandos> 
  
End;
~~~


### If Then Else
~~~
if x >10 then
begin
 // codigo
end;
~~~

~~~
if x >10 then
begin
 // se Sim
end
else
begin
  // se Não
end;
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

## Função

- são declaradas na seção `interface`
- `Result` ou `nome_funcao` para trabalhar com o Retorno da função

> Função retornando valor pelo Result 
~~~Delphi
interface 
    Function  Somar  (a,b: Integer) : Integer;
  
implementation 
    Function Somar(a, b: Integer): Integer;
    Begin
      Result := a + b;
    End;
~~~

> Chamando a Função
~~~Delphi
var
   resultado: Integer;

resultado := Somar(10, 20);
~~~

## Procedimento

> Procedimento sem parametro
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

> Procedimento com parametro
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

> Pasagem por Referencia em Funções ou Procedimentos
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

## Data Module
- Formulario centralizador de componetes não visuais
- componentes de Banco de Dados
- boa prática, nomear como:
  - `dmModulo` : objeto
  - `dmUnidadeMdoulo` : arquivo
  
## Componentes
> Interface
- `TMainMenu` (Standard)
- `TPanel` (Standard)
- `TButton` (Standard) : Botão
- `TBitBtn` : permite imagem
- `TPageControll` (Win32) > (new Page)
- `TDBGrid` (Data Controls)
- `TLabeledEdit` (Additional)
- `TSpeedButton` (Additional) : Botão
- `TMaskEdit`
- `TMemo` Caixa para textos longos
- `TOpenDialog` abertura de arquivos
- `TSaveDialog` gravação de arquivos

  
## Funções do Delphi
- `INC(x)` : x := x + 1;
- `DEC(x)` : x := x - 1;
- `LOW(x)` : retorna o valor mais baixo
- `DATE()` : retorna Data autal
- `NOW()` : Data e Hora atual
- `IncDay(data , dias)` : Incrementa dias a uma data
- `DaysBetween(data1 , data2)` : numero de dias entre duas datas
> Conversões
- `IntToStr(x)`   
- `FloatToStr(x)` 
- `FloatToStrF` : String formatada 
- `StrToInt(x)`   
- `StrToFloat`
- `DateToStr`
- `StrToDate`
- `DateTimeToStr`
- `TimeToStr`


- `RANDOM()` : Valor aleatório (usar Randomize)
- `QuotedStr(x)`  : deixa entre aspas simples
  - ex.:  `QuotedStr('*'+campo+'*' ) `


## Teclas de Atalho
- `F12` : Alternar entre Código-View
- `F9`  : Executar
- `Ctrl` + `F2`   : Cancelar Execução
- `Ctrl` + `seta` : mover componente
- `Ctrl` + `Shift` + `F9`   : Executar sem Debug
- `Ctrl` + `Shift` + `seta` : alterar tamanho do componente
- `Alt`  + `Shift` + `seta` : selecionar codigo, forma quadrada
- `Ctrl` + `Shift` + `C`    : gerar Gets e Sets

> Exibir Ferramentas
- `F11`                   : Object Inspecto
- `Ctrl` + `Alt` + `F11`  : Project Manager 
- `Shift` + `Alt` + `F11` : Structure
- `Ctrl` + `Alt` + `P`    : Tool Palet

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

