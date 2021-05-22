# Embarcadero Delphi 
[site (oficial)](https://www.embarcadero.com/br/)

- 1995 Borland (Turbo Pascal) -> para Windows 3.1 (16 bits)
- 2006 CodeGear 
- 2008 Embarcadero
- Ambiente de Desenvolvimento (ferramenta/conceito)
- RAD (Rapid Applicaiton Development)
- Linguagem Pascal

> versões da IDE RAD Studio 
- RAD Studio 10.0 (Seattle) [2015]
- RAD Studio 10.1 (Berlim) [2016]
- RAD Studio 10.2 (Tokyo) *
- RAD Studio 10.3 (Rio)
- RAD Studio 10.4 (Sydney)

> Arquivos 
- Executaveis (Project Manager)
  - `/Win32/Debug` compilar com o Debug selecionado (aquivo maior: Desenvolvimento)
  - `/Win32/Release` compilar com o Release selecionado (arquivo menor : Final)
  - `*.dcu` arquivo pre-compilado, auxiliar o *.exe
- `VCL Form Application` 
  - `Delphi Unit` : 
    - `*.pas` : arquivo de código
    - `*.dfm` : informações complementares de um formulário
    - ../Forms/uFrmPrincipal -> (Objeto: frmPrincipal)
    - ../Forms/FrmPrincipalU
  - `Delphi projects` : informações do Projeto
    - `*.dproj` : Usar este arquivo para editar o projeto
    - `*.dproj.local` 
    - `*.dpr` : **Arquivo para se abrir os projetos**
    - `*.res` : arquivos de icones, imagens, outros
    - ../Projeto/Agenda
    - `~arquivo` arquivos de backup
- `VCL Form `
  - `Delphi unit (*.pas)` : ../Forms/uFrmCadastrar -> (Objeto: frmCadsatrar)
- `Unit` arquivo: *.pas
- `DataModule` : Drag-and-Drop


## Comentários e Regiões
> Comentar
~~~Delphi
// Comentário em uma linha
~~~

~~~Delphi
{ 
  Comentário em múltiplas linhas
}

{* 
  Comentário em múltiplas linhas
*}
~~~

> Ocultar uma região
~~~Delphi
{$REGION 'NomeRegion'}
  // código a ser ocultado
{$ENDREGION}
~~~

## Tipos de Dados

- Inteiras
  - Integer
  - Cardinal
  - Shortint
  - Smallint
  - Longint
  - Int64
  - Byte
  - Word
  - LongWord

- Reais
  - Real48
  - Single
  - Double
  - Extended
  - Comp
  - Currency
  - Real equivale a double

- Booleanas
  - Boolean
  - ByteBool
  - WordBool
  - LongBool

- Caracter
  - Char
  - AnsiChar
  - WideChar
  - ShortString
  - AnsiString
  - WideString

- Genéricas
  - Variant (não compensa)
  
- Arquivo
  - File
  - TextFile
  
- Vetores


## Operadores Aritméticos
- `*` multiplicação 
- `/` divisão entre variaveis reais
- `+` soma
- `-` subtração
- `div` divisão entre variaveis inteiras
- `mod` resto da divisão

## Classes
- Estrutura básica de um código:
  - `unit` : nome do arquivo
  - `interface` declaração
    - `uses`: Bibliotecas
    - `Type` e `TClasse = class` , `end;` : Classes
  - `implementation`: Implementação

> Exemplo 01
~~~Delphi
unit nome_unidade; 

  interface
  // região de declaração de bibliotecas, classes, funções, procedimento e variáveis.
  
  implementation
  // região de implementação de código

end. // fim unidade
~~~

> Exemplo 02
~~~Delphi
unit nome_unidade; 

  interface  // declaração de bibliotecas, funções, procedimento.
    uses System.classes;
    function calcular : Real;
    procedure escreverNome ( n : String);
  
  implementation // região de implementação
    
    // função implementada
    function calcular : Real;
    begin
    // código da função calcular
    end;

    // procedimento implementado
    procedure escreverNome( n : String);
    begin
      println("Ola "), n;
    end;
    
end. // fim unidade
~~~

> Exemplo 03
~~~Delphi
unit nome_unidade; 

  interface  // declaração de bibliotecas, funções, procedimento.
    uses System.classes;
    function calcular : Real;
    procedure escreverNome ( n : String);
  
  implementation // região de implementação
    
    // função implementada
    function calcular : Real;
    begin
    // código da função calcular
    end;

    // procedimento implementado
    procedure escreverNome( n : String);
    begin
      println("Ola "), n;
    end;
    
end. // fim unidade
~~~


> Exemplo 04
~~~Delphi
unit PessoaU; 

interface
  uses System.classes; 
  
    // Classes
    Type
        TPessoa = class         // inicio da classe
          // declaração variáveis da classe TPessoa
          Private
            Nome   : String;
            Idade  : Integer;
            Altura : Real;
            Outros : TStringList;
          Public
            function getNome : String;
            procedure setNome(vNome : String );
        end;                    // final da classe TPessoa
  
implementation  // região de implementação

    // função implementada
    function TPessoa.getNome : String;
    begin
      resultado := Nome;
    end;
 
    // procedimento implementado
    procedure TPessoa.setNome( n : String);
    begin
      Nome := n;
    end;
    
    
end. // fim unidade
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

> Para Banco de Dados:
- `FireDac`
- `Zeos Access` multidirecional
- `DBExpress` 

## Teclas de Atalho
- `Ctrl` + `seta` : mover componente
- `Ctrl` + `Shift` + `seta` : alterar tamanho do componente
- `Alt`  + `Shift` + `seta` : selecionar codigo, forma quadrada
- `Ctrl` + `Shift` + `C`    : gerar Gets e Sets
