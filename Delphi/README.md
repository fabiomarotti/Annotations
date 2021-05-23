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
    - ../Projeto/Nome_Projeto
    - `~arquivo` arquivos de backup
- `VCL Form `
  - `Delphi unit (*.pas)` : ../Forms/uFrmCadastrar -> (Objeto: frmCadsatrar)
- `Unit` arquivo: *.pas

- `DataModule` : Drag-and-Drop

## Data Module
- Formulario centralizador de componetes não visuais
- componentes de Banco de Dados
- boa ptrática nomear como 
  - `dmModulo` objeto
  - `dmUnidadeMdoulo` arquivo

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

## Varáveis
~~~
var 
  Nome: string;
Nome := 'Fábio Marotti';
~~~ 

~~~
var 
  Nome: string := 'Fábio Marotti';
~~~ 

~~~
var Idade := 20; // compilador infere que é um tipo inteiro
~~~ 

~~~
for var Contador := 0 to 10 do { ... }
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

- String : usar aspas simples *

- Genéricas
  - Variant (não compensa)
  
- Arquivo
  - File
  - TextFile
  
- Vetores


### Converter tipos

- `IntToStr()`

## Operadores Aritméticos
- `*` multiplicação 
- `/` divisão entre variaveis reais
- `+` soma
- `-` subtração
- `div` divisão entre variaveis inteiras
- `mod` resto da divisão


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

## Funções e Procedimentos

~~~Delphi
unit nome_unidade; 

interface 
  
    function  calcDividir   (a,b: Integer);
    procedure escreverNome ();
  
  
implementation 
  
  function calcDividir(a,b: Integer);
  begin
    result := a / b;
  end;

  procedure escreverNome();
  begin
    println("Ola Mundo!");
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
- `DBExpress` 

### `Zeos Access` multidirecional
- `TZConection` (zConexao)
  - HostName: localhost
  - User: root
  - Password: -
  - Port: 3306 (padrão)
  - Protocol: mysql-5 (banco usado)
  - Database: bd_nomeBanco
  - Connected: True
 
 - `TZTable` (ztbPessoa)
  - Connection: TZConnection
  - TableName:  vincula a tabela no banco de dados ao componente (qnd BD estiver ativo)
  - Active: True
  - Add All Fields 
  - OBS.: carrega a tabela inteira na memoria. Pode acabar travando se haver muitos registros.
  - Centraliza a formatação para futuras chamadas multiplas nos formularios.
  
## Teclas de Atalho
- `F12` : Alternar entre Código-View
- `F9` : Executar
- `Ctrl` + `Shift` + `F9` : Executar sem Debug
- `Ctrl` + `seta` : mover componente
- `Ctrl` + `Shift` + `seta` : alterar tamanho do componente
- `Alt`  + `Shift` + `seta` : selecionar codigo, forma quadrada
- `Ctrl` + `Shift` + `C`    : gerar Gets e Sets
