# Informações sobre o Embarcadero Delphi

- [Site (oficial)](https://www.embarcadero.com/br/), 
- [DocWiki Embarcadero](http://docwiki.embarcadero.com/), 
- [Exemplos (oficial)](http://docwiki.embarcadero.com/CodeExamples/Sydney/en/Code_Examples_Index), 
- [Trechos a estudar](http://www.linhadecodigo.com.br/delphi.aspx)
- [Delphi Basic - Estudo](http://www.delphibasics.co.uk/)

> Informações:
- Delphi é um Ambiente de Desenvolvimento (ferramenta/conceito)
- RAD (Rapid Applicaiton Development)
- Linguagem Pascal
- VCL (Visual Component Library)
- CLX (Component Library for Cross Platform) 
  - Borland Kylix 
- Delphi RTL (Run-Time Library) : unidades básicas que dão suporte a VCL e FireMonkey [saiba+](http://docwiki.embarcadero.com/RADStudio/Sydney/en/Using_the_RTL_(Run-Time_Library)), como:
  -  TObject 
  -  TPersistent 
  -  TComponent 
----

> História:
- 1995 : Borland (Turbo Pascal) -> para Windows 3.1 (16 bits)
- 2006 : CodeGear 
- 2008 : Embarcadero

> versões: 
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
- RAD Studio 10.4.2 (Sydney) [2021]

---- 

> Arquivos importantes no Delphi:

- `Project Group`

- `Project.exe`
  - `Build Configuration (Debug/Release)`
    - `Debug` : selecionar o Debug e compilar, gera arquivo em: `/Win32/Debug`
    - `Release` : selecinar o Release e compilar, gera arquivo em: `/Win32/Release`
  - `Target Plataforms (Windows 32/64-bit)`
  - `../pastas_src/...`
  - Informações dos arquivos de um Projeto:
    - `*.dproj` : arquivo para editar o projeto
      - ../Projeto/Nome_Projeto.dproj 
    - `*.dproj.local` : arquivo nutela do projeto 
    - `*.dpr` : **Arquivo para se abrir o projeto**
    - `*.res` : Arquivo de icones, imagens, outros
    - `~arquivo` : arquivos de backup

- `Windows VCL Application - Delphi` ou `VCL Form`
  - `Delphi Unit` : 
    - `*.pas` : arquivo de código
    - `*.dfm` : informações complementares do arquivo .pas de um Formulário (Alt + F12)
    - ../Forms/uPrincipal.pas  ->  (Objeto: TformPrincipal)

- `Package - Delphi`
  - `RunTime Packages` : Fornecem as funcionalidades de um programa ao mesmo tempo que o programa esta sendo executado.
  - `Design-Time Packages` : Estes pacotes sevem apenas para a IDE do Delphi, são os componentes ou editores de propriedade especiais para componentes que podem ser personalizados.
  - Arquivos gerados:
    - `.bpl`  
    - `.dcp`
    - `.dcu`

- `Unit` arquivo: *.pas



# Arquivos de Projeto
- `.dpr` (Delphi Project) : arquivo que, de fato, possui o código do programa
- `.dsk` (Desktop) : Informações sobre a Area de Trabalho do Delphi
- `.pas` (Arquivo Pascal)
- `.res` (arquivo Recurso)
- `.dfm` (Delphi Form File) : Arquivo Delphi de formulário
- `.exe` (Executabel) : Produto Final
- `.dcu` (Delphi Compiled Unit) arquivo criado para cada *.pas*, destinado a tornar o processo de compilação mais rapido, pois o compilador busca apenas o *.dcu* alterado, não compilando *.dcu* ja compilados e não alterados.
  - C:\Users\<user>\Documents\Embarcadero\Studio\Projects\<project>\<platform>\<build configuration> 
- `.bpl` (Borland Package Library)
- `.dcp` (Delphi compiled Package) :  imagem binária que contém um cabeçalho de pacote e a concatenação de todos os arquivos de unidade compilados em Delphi 
  - C:\Users\Public\Documents\Embarcadero\Studio\21.0\DCP 
- `.dll` (Dinamic Link Library)

--- 
# `Uses`
- SysUtils = biblioteca de utilitários do sistema (strings, data/hora, gerar arquivos).
- WinProcs = biblioteca. Unite onde encontramos codificação para acesso a GDI, USER e KERNEL do Windows.
- Wintypes = Biblioteca, tipos de dados e valores constantes.
- Messages = Biblioteca de constantes com os números das mensagens do Windows e tipos de dados das Mensagens.

# `Type`
- Declaração dos tipos definidos pelo usuário

# `Var`
- Declaração das variáveis
- a visibilidade delas será dependente das seções “interface” ou “implementation” que definirá se elas serão privadas ou não 
- depende do Escopo de Visibilidade

# `{$S+}`
- Diretiva de compilação que ativa verificação de pilha.

# `{$R*.DFM}`
- Diretiva de compilação que indica a utilização de um arquivo de recurso. Neste caso, trastando-se de um form é necessário compilar junto o arquivo que contem as informações visuais do mesmo. Elas estão defindas no *.DFM, homonimo a unit.
- Por exemplo, os “.dfm” de cada arquivo “.pas” onde esta definos um form.



--- 

> Principais Abas para Componentes:
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

# Palavras recorrentes
- `Two-Way-Tool` (ferramenta de duas vias)
  - Conforme  o  formulário  recebe  componentes  a  Unit  instantaneamente  é  alterada. 

## Acess Violation e seus problemas
- `Acess Violation` : Violçao de acesso.
- `Call Stack` : Pilha de chamadas de métodos (histórioco de chamadas) 
  - pode ser devido a endereços de memória que não existem, ou seja, Objetos não instanciados ou ja destruidos.
  - (View > Debug Windows > Call Stack)
  - Leitura de Baixo para Cima.
- `memleaks` : Vazamento de memória
  - ReportMemoryLeaksOnShutdown := True;
- `Assigned()` : identifica se o objeto passado por parâmetro está alocado na memória.
- `FreeAndNil()` : Destruição de objetos no Delphi.
- `Tratamento de Exceções`: Try..finally (usar FreeAnd Nil)
- `Destructor` : 
- `Out of Memory`
[ver+](https://www.andrecelestino.com/delphi-access-violation-o-que-fazer/)
