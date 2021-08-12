# Packages (.bpl)

### Pre-Configuração
- Pacotes são exibidos em `Project / Options /  Packages / (Design packages)`
- Configurar o tempo de execução/design:
  - Abrir um projeto do tipo __Package__
  - Project / Options / Description / (Designtime and runtime) e (Rebuild as needed)
  - Project / Options / Delphi Compiler / ...
    - DCP output directory: __dcu__
    - Package output directory: __dcu__
    - Unit output directory: __dcu__
- Para Compilar ou Instalar:
  - `btnDireito / Build` : Compilar
  - `btnDireito / Install` : Instalar     


### Informações
- `*.dproj` : arquivo do Projeto do Pacote
- `*.dpk` : arquivo fonte do Projeto do Pacote
- `*.bpl` (Borland Package Library) : é uma biblioteca específica para sistemas desenvolvidos em Delphi. (tipo DLL: Dinamic Link Library) 
- `*.dcp` (Delphi Compiled Package)  : é uma imagem binária que contém um cabeçalho de pacote e a concatenação de todos os arquivos de unidade compilados em Delphi em seu pacote.
  - Local padrão: `C:\Users\Public\Documents\Embarcadero\Studio\21.0\DCP`
- O Projeto Package possui duas pastas:
  - `Contains` : possui arquivos *unit.pas*
  - `Requires` : possui arquivos *rtl.dcp*
  - oculta direotrio de outras pastas 
- Para um TipoClasse aparecer no Object Inspector, precisa ser: TPersistent, TComponent, ..
  - TPersistent: prove funcionalidade para persistit no `dfm` 
  - TComponent herda de TPersistent
- [ver+](https://www.devmedia.com.br/quick-tips-como-trabalhar-com-packages-no-delphi/16421)


---- 


> New / Packages / pkgBotaoPersonalizado <br>
> Construção basica de um Package
~~~Delphi
unit Componente.BotaoPersonalizado

interface

uses
  System.Classes;

type
  TBotaoPersonalizado = class( TComponent );
  // declarações  
  end;

procedure Register;

implementation

procedure Register;
begin
  RegisterComponents('Nome_Aba_Palette', [TNomeComponente]);
end;

end.
~~~


> Propriedades de um Componente
~~~Delphi

type
  TBotaoPersonalizado = class( TComponent );
  private
     FTexto:  String;
     FData:   TDate;
     FValor:  Double;
  published
     property  Texto : String   read FTexto  write FTexto;
     property  Data  : TDate    read FData   write FData;
     property  Valor : Double   read FValor  write FValor;
  end;

procedure Register;

implementation

procedure Register;
begin
  RegisterComponents('Paleta Componente Personalizado', [TBotaoPersonalizado]);
end;

end.
~~~
