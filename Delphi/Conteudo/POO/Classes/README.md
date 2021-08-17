# Classes

- `uses` System.Classes;


#### Declaração de uma classe vazia
~~~Delphi
type
  TPessoa = class;
~~~

#### Declaração com classes auto-relacionadas (cross-references)
~~~Delphi
type
  // Classe apenas declarada
  TMarido = class;
  
  TEsposa = class
    marido: TMarido;
  end;
  
  // Classe Implementada
  TMarido class
    esposa: TEsposa;
  end;
~~~

#### Construtor e Destrutor
- Construtor Primário e Secundário.

> o construtor Secundário faz uso do construtor Primário. 
~~~Delphi
type
  TPessoa = class
  public 
      constructor Create(const Nome, Telefone: String);
      constructor Create(const Nome: SAtring);
      function Nome: String;
      function Telefone: String;
  private
      FNome: String;
      FTelefone: String;
  end;
   
implementation

constructor TPessoa.Create(const Nome: String);
Begin
  Create(Login, '(19) 55334499');
End;

// implementações das funções.
~~~

#### Property (Getters e Setters) : exemplo 1
~~~Delphi
type

  TPesosa = class
  private
    FNome: String;
    function OlaNome: String;
  public
    property Nome: String read FNome write FNome;
  protected
    function NomeValido: Bolean;
  end;

end.
~~~


#### Property (Getters e Setters) : exemplo 2
~~~Delphi
type

  TPesosa = class
  private
    FNome: String;
    procedure SetNome(const Value: string);
  public
    property Nome: String read FNome write SetNome;
  end;

implementation

procedure TPessoa.SetNome(const Value: string);
begin
  FNome := Value;
end;

end.
~~~



