# Programação Orientada a Objetos (Delphi)

[] Abstração
[] Herança
[] Encapsulamento
[] Polimorfismo

# Métodos Construtores e Destrutores
.Create

# Classe
> Unidade contendo a Classe Pessoa
~~~Delphi
unit Unit_Pessoa;

{ Declaração }
interface

{ Classe }
type
  TPessoa = class  // Herda a classe Object
    private
      Idade : Integer;
    public
      Nome : String;
    
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
  
implementation 
  pessoa := TPessoa.Create;
  try
    pessoa.Nome := 'Fulano';
    ShowMessage(pessoa.Nome);
  finally
    pessoa.Free;
  end;
 
end.
~~~
