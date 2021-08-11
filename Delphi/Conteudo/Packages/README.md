# Packages (.bpl)
[ver+](https://www.devmedia.com.br/quick-tips-como-trabalhar-com-packages-no-delphi/16421)


## Informações
- `btnDireito / Build` : Compilar
- `btnDireito / Install` : Instalar

- `*.dproj` : arquivo do Projeto do Pacote
- `*.dpk` : arquivo fonte do projeto pacote
- `*.bpl` : 
- `*.dcp`  : ../Requires/trl.dcp
- oculta as pastas ?

---- 

- TipoClasse aparecer no Object Inspector, precisa ser: TPersistent
- TPersistent: prove funcionalidade para persistit no `dfm` 
- TComponent herda de TPersistent

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
