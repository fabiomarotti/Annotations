# Programação Orientada a Objetos (Delphi)

 [✅] Abstração
 
 [✅] Encapsulamento

 [ ] Herança
  
 [ ] Polimorfismo


# Classe (Abstração)

- `instancia.Create` : Construtor
- `instancia.Free`   : Destrutor

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


## Encapsulamento

> Unidade contendo a Classe Pessoa Encapsulada
~~~Delphi
unit Unit_Pessoa;

{ Declaração }
interface

{ Classe }
type
  TPessoa = class  
    private
      Idade : Integer;
      Nome  : String;
    public
      // não tem, quebraria o conceito de Encapsulamento
     function setIdade : Integer
     procedure getIdade
    
 end;
 
{ Implementação }
implementation

end.
~~~

