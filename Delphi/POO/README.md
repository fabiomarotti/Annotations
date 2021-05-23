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
      Nome  : String;
      Idade : Integer;

    public
      procedure setNome(  n  : String );
      procedure setIdade( i : Integer);
      
      function getNome  : String;
      function getIdade : Integer;
      
      constructor CriarObjeto;
      destructor  DestruirObjeto;
 end;
 
{ Implementação }
implementation

{ TPessoa }

constructor TPessoa.construirObjeto;
begin
  Nome  := '';
  Idade := 0;
end;

destructor TPessoa.destruirObjeto;
begin
end;


function TPessoa.getIdade: Integer;
begin
  result := Idade;
end;

function TPessoa.getNome: String;
begin
  result := Nome;
end;


procedure TPessoa.setIdade(i: Integer);
begin
  Idade := i;
end;

procedure TPessoa.setNome(n: String);
begin
  Nome := n;
end;
   

end.
~~~

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

