# Programação Orientada a Objetos (Delphi)

# Classe

> Unidade contendo a Classe Pessoa
~~~Delphi
unit Unit_Pessoa;

{ Declaração }
interface

{ Classe }
type
  TPessoa = class
    private
    
    public
 end;
 
{ Implementação }
implementation

end.
~~~

> Unidade contendo a instanciação da classe Pessoa
~~~Delphi
unit Unit_Principal

interface

uses
  Unit_Pessoa;
  
 p := TPessoa.Create;

~~~
