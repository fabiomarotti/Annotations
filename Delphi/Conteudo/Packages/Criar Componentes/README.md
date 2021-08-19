# Criar Componentes 

- `New / Packages / pkgBotaoPersonalizado`
- Para Compilar ou Instalar:
  - `btnDireito / Build` : Compilar (tempo de Designer)
  - `btnDireito / Install` : Instalar   

#### Criando um Componente em uma Unit
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
  RegisterComponents('Nome_Aba_Palette', [ TNomeComponente ]);
end;

end.
~~~

#### Criando Componente em Units separadas
> Unit para Register
~~~Delphi
unit uRegistros;

interface
uses Systm.Classes;
procedure Register

implementation
uses uBotaoPersonalizado_1, uBotaoPersonalizado_2;
procedure Register;
begin
  RegisterComponents('Nome na Palette de Components', [ TBotaoPersonalizado_1, TBotaoPersonalizado_2 ]);
end;

end.
~~~

> Unit para os Componentes
~~~Delphi
unit uBotaoPersonalizado_x;

interface
uses System.Classes;
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
  
implementation
// ---

end.
~~~





- [ video 1](https://www.youtube.com/watch?v=vYImVt4b8eY)
- [ vidoe 2 mask fazer ](https://www.youtube.com/watch?v=CRAkAaFcf0Q&list=PLCdWRZy2Tc1q9b6jdh5695BaNkImvKKOS)
- [link 1 ](https://www.codeproject.com/Articles/1060345/DFM-serialization-in-depth)
