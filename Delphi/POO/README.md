# Programação Orientada a Objetos (Delphi)
> 1986 : Object Pascal

- ✅ Abstração (modelar o que interessa)
  - Niveis de Abstração
    - **Nivel de Domínio** : os nomes das classes
    - **Nível de Análise** : nomes e atributos
    - **Nivel de Sign** : nomes, atributos e métodos
    - **Generalização** : polimorfirmo 
    - **Classes Abstratas** : apenas implementação as "sobreescritas"

- ✅ Encapsulamento (não permitir modificações externas)
  - **Public**
  - **Protected**
  - **Private**
  
- ✅ Herança

- ✅ Polimorfismo (uma ação pode ser exercida de varias formas)
  - **Subtyping** (_Override_) : _Sobreescrita_, do método herdado.
  - **Overloading** (Sobrecarga): Método com o mesmo nome, porem com assinaturas diferentes.
  - **Coercion Polymorphism** (Casting): Conversão de tipos de objetos ou primitivos.
  - **Parametric Polymofirsm** (Generics/Templates): otimiza os codigo

> Sinônimos utilizados

- **Generalização**: da _Sub Classe_ para **Super Classe**
- **Especialização**: da _Super Classe_ para **Sub Classe**
- **Herança**: (é um tipo de) : as propriedades são herdadas
  - _Simples_: Herdar apenas uma Super Classe 
  - _Multipla_: Herdar varias Super Classes
- **Agregação**: (Dependência Fraca) : (Usam um) : Remover o TODO, não necessariamente suas PARTES seram removidas. 
- **Composição**: (Dependência Forte) : (Composto por) : Remover o TODO, suas PARTES tambem seram removidas. 

> Convenção
- Toda classe tem o nome iniciado pela letra T

> Atalhos
- `Ctrl` + `Shift` + `A` : gera os imports das classes

[continuar video](https://www.youtube.com/watch?v=3ugwf8FQqVo)

## Hierarquia simplificada das classes Delphi:
- `TObject`
  - `TPersistent`
   - `TComponent`
     - `TControl`
       - `TForm`
       - `TButton`
       - `TListBox`



# Classes

### Propriedades das Classes
- **Construtor:**         `instancia` `:=` `Classe`.`Create` 
- **Destrutor:**          `instancia`.`Free` 
- **Variavel de Classe:** `class var`

## Manipuladores de Acesso
- `Public` (Default) Acesso por qualquer Unit no projeto
  - `Automated` Acesso por qualquer classe, geralmente usado em classes derivadas da classe TAutoObject
  - `Published` Acesso por qualquer classe e seu valor pode ser visualizado no Object Inspector (acesso via RTTI) (RunTime Type Information) [ver +](https://www.devmedia.com.br/conhecendo-a-rtti/24547)
- `Private` Acesso apenas pela propria Unit em que a classe foi definida.
- `Protected` Acesso pelas classes herdadas, alem do private poder acessar
- `Property`



> Unidade contendo a Classe Pessoa
~~~Delphi
unit Unit_Pessoa;

{ Declaração }
interface

{ Classe }
type
  TPessoa = class  // TPessoa = class(TOjbect) {Herda implicitamente a classe TObject}
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
unit Unidade_Principal;

interface

uses
  Unidade_Pessoa;
  
implementation 
  // Criando uma instancia da classe TPessoa.  
  pessoa := TPessoa.Create;
  
  try
    // Acessando a variavel Nome, da instancia da classe TPessoa;
    pessoa.Nome := 'Fulano';
    ShowMessage(pessoa.Nome);
  finally
    // Destruindo uma instancia da classe TPessoa.
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

## `Property`
- Omitir metodo de Escrita : Read-Only
- Omitir metodo de Leitura : Write-Only
- Campo no lugar dos metodos : Acesso direto ao valor de um campo


> - Classe `TCliente` com variaveis `public` definidas como `property` <br>
~~~Delphi
unit uCliente;

interface 
  use SysUtils;

Type
  TCliente = class
  public
      property ID       :String;
      property Nome     :String;
      property CPF      :String;
end;      
~~~

> - `Ctrl` + `Shift` + `C` : Implementação automática

> - Cria-se variaveis `private`, denominadas Fields `F_nome_variavel_` <br>
> - Declara e Implementa os procedimentos de atribuição `Set` 
> - Atribui-se `read` e `write` nas variaveis <br>
~~~Delphi
private
    FID:    String;
    FNome:  String;
    FCEP:   String;
    procedure SetID(const   Value: String);
    procedure SetNome(const Value: String);
    procedure SetCPF(const  Value: String); 

public
    property ID       :String   read FID    write SetID;
    property Nome     :String   read FNome  write SetNome;
    property CPF      :String   read FCPF   write SetCPF;    


implementation

  procedure TCliente.SetID(const Value: String);
  begin
    FID := Value;
  end;

  procedure TCliente.SetNome(const Value: String);
  begin
    FNome := Value;
  end;

  procedure TCliente.SetCPF(const Value: String);
  begin
    FCPF := Value;
  end;
~~~

[ver +](http://docwiki.embarcadero.com/RADStudio/Sydney/en/Properties_(Delphi))



# Polimorfismo
- `virtual` : permissão de `override` (reescrita) nas clases derivadas

> Exemplo
~~~Delphi
Unit Unit1;

Interface

Uses
  extCtrls, graphics, classes;

Type
  // Super Classe
  TClassFigura = class(TObject)
    private
       MinhaImagem: TImage;
    public
        property Imagem: TImage read MinhaImagem write MinhaImagem;
        procedure Desenhar; virtual;  // Permissão para reescrita
  end;

  // Sub Classe herdando a SuperClasse
  TClassQuadrado = class(TClassFigura)
     public
         procedure Criar; override;  // Reescrita
  end;

  // Sub Classe herdando a SuperClasse
  TClassCirculo = class(TClassFigura)
      public
          procedure Criar; override;  // Rescrita
   end;

Implementation
{...}
~~~


# Operadores com Objetos

## `Is`
- Verificar se um objeto é uma instância de uma classe derivada de uma classe-base.
- Retorna um valor booleano
~~~Delphi
 if (form1.Components[i]  is  TEdit)
~~~


## `As`
- Tratar um objeto como uma instância de uma das suas classes-base
- Utilizado para acessar um método ou propriedade da classe-base.
- typecasting
> (nome_objeto  As  nome_classe).nome_método <br>
> (nome_objeto  As  nome_classe).nome_propriedade

~~~Delphi
with  Sender  as  TButton  do
Begin
  Caption := '&Ok';
  OnClick := OkClick;
End; 
~~~

## `Self`
- Referência a instância corrente de uma classe 
- semelhante ao `this` (em C)





