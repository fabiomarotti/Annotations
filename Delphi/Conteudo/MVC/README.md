# MVC
- Model - View - Controller
- `DTO`: (Data Transfer Object) alimenta o Controller com apenas um parâmetro.
- 



## Model

## View
- atualização de textos
- preenchimento de listas
- exibição de mensagens 
- controle do estado de componentes

## Controller



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
