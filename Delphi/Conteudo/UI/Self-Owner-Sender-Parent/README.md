# Self - Owner - Sender - Parent

# Self (si memso)
- Referece ao "dono" da declaração / implementação / chamada.
- O _self_ pode ser omitido.

> Exemplo: Criando uma instância de um Form
~~~delphi
 FormPrincipal := TFormPrincipal.Create(Self);
~~~ 

> Exemplo: Self em diferentes Classes
~~~Delphi
type
   TPessoa = class
      nome : String;
      procedure nomePessoa;
   end;
 
   TAnimal = class
      nome : String;
      procedure nomeAnimal;
   end;
 
// implementation
{ TPessoa }
procedure TPessoa.nomePessoa;
begin
   Self.nomePessoa := 'Fulano';
   // TPessoa.nomePessoa := 'Fulano';
end;
 
{ TAnimal }
procedure TAnimal.nomeAnimal;
begin
   Self.nomeAnimal := 'Bixo Liso';
   // TAnimal.nomeAnimal := 'Bixo Liso';
end;
~~~
[link sobre Self](https://extremeprogramming.wordpress.com/2011/01/25/guia-iniciante-parte-1-self-o-que-e-delphi/)


# Owner (Proprietário)
- indica o Componente X que é proprietário de outro Componente Y
- Como identificar o Owner: 
  - `MeuObjeto.Owner.Name`
  - Clica no Componente + ESC 

> Exemplo: atribuindo Owners
~~~Delphi
procedure TFormPrincipal.btnCriarClick(Sender:TObject);
var B1, B2, B3 : TButton;
begin
   B1 := TButton.Create(Self);        // o Owner deste botão é o FormPrincipal
   B2 := TButton.Create(B1);          // o Owner deste botão é o B1
   B3 := TButton.Create(Application)  // o Owner deste botão é a Aplicação
end;
~~~
[link sobre Owner](https://extremeprogramming.wordpress.com/2011/01/28/guia-iniciante-parte-2-owner-o-que-e-delphi/)


# Sender (Remetente)
- Sender é o parâmetro de algumas funções, e ele é do Tipo TObject
- Sender é o Objeto que chamou aquela função

[link sobre Sender](https://extremeprogramming.wordpress.com/2011/02/03/guia-iniciante-parte-3-sender-o-que-e-delphi/)

# Parent (Pai)
- Parent faz referência ao componente que contém ele
- Parent é usado para trocar-se de Owner
- Alterar um Parent faz com que se altere o seu Owner
[link sobre Parent](https://extremeprogramming.wordpress.com/2011/02/08/a-propriedade-parent-delphi/)
