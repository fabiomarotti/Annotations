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
