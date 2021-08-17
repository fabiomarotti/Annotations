# Interfaces

> Interface
~~~Delphi
type
  IPessoa = interface
      function Nome: String;
      function Telefone: String;
  end;
  
  TPessoa = class(TInterfaceObject, IUser)
  public 
      constructor Create(const Nome, Telefone: String);
       class function New(const Nome, Telefone: String) : IPessoa;
       class function New(const Nome: String) : IPessoa;
      function Nome: String;
      function Telefone: String;
  private
      FNome: String;
      FTelefone: String;
  end;
~~~

> Declaração da interface
~~~Delphi
unit exemplo_interface_A;
interface
uses
// importação de classes

type

  iExemploInterfaceA = interface
  ['{77EC9951-645E-4900-B685-5EF76B53ED5E}']  // Ctrl + Shif + G : gerar ID
    function Listar : String;
  end;

implementation
// não havera implementação

end.
~~~

> Implementação Interface
~~~Delphi
unit exemplo_classe_interface;
interface
uses
  exemplo_interface_A;

type
  TExemploClasse = class(TInterfacedObject, iExemploInterfaceA)
    function DizerOla : String;  virtual;
end;

implementation

function TExemploClasse.DizerOla(): String;
begin
  Result := "Ola Mundo";
end;
~~~

