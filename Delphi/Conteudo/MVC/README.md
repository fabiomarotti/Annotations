# MVC
- São camadas lógicas que facilitam para o programador a troca de informações entre a interface do usuário e o banco de dados. 
- Possibilidade de inserir mais camadas lógicas.

### Model: 
- `Business Object Model` (Objeto Modelo de Negócio)
- Gerenciar e controlar o comportamento dos dados por meio de funções, lógica, regras de negócios,..
- Faz a conexão e operações com o Banco de Dados.
 
### View 
- Apresenta as informações de forma visual ao usuário.
- Gerencia a exibição ou ocultamento de componentes, mensagens, botões, telas
- atualização de textos
- preenchimento de listas
- exibição de mensagens 
- controle do estado de componentes
- Possui uma instância do *Controller*

### Controller
- Intermedia as requisições enviadas pela View com as respostas fornecidas pelo Model.
- É um repassador de informação.
- `DTO`: (Data Transfer Object) Utiliza-se para alimentar o Controller com apenas um parâmetro.
- Possui uma instância do *Model*

----- 

# Exemplo
> Sem MVC
~~~Delphi
  DataSet.Append;
  DataSet.FieldByName('Codigo').AsInteger := StrToInt(EditCodigoProduto.Text);
  DataSet.FieldByName('Descricao').AsString := EditDescricao.Text;;
  DataSet.FieldByName('Preco').AsFloat := StrToFloat(EditValor.Text);
  DataSet.Post;
  DataSet.ApplyUpdates(0);
~~~

> Com MVC
- Model


- View
~~~Dlephi
var
  Controller: TProdutoController;
  
begin
  Controller := TProdutoController.Create;
  try
    Controller.IncluirProduto(
        StrToInt(   EditCodigo.Text), 
                    EditDescricao.Text, 
                    StrToFloat(EditPreco.Text)
        );
  finally
    Controller.Free;
  end;
end;
~~~

- Controller
~~~Delphi
TProdutoController = class
public
  procedure IncluirProduto(
                const ACodigo: integer;
                const ADescricao: string; 
                const APreco: real
  );
end;
~~~
