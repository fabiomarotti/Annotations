# TDictionary
- Busca no sentido: Chave -> Valor

## Métodos
- `Lista :  TDictionary<String, TPessoa>` : Declaração do tipo (Chave: String, Valor: Integer).
- `Lista := TDictionary<String, TPessoa>.Create;` : Criar do tipo (Chave: String, Valor: Integer).
- `Lista.Add('Fabio', Pessoa)` : Adicionar (Chave: palavra, Valor: 100).
- `ista.AddOrSetValue(Pessoa.CPF, Pessoa);` : Adicionar, verifica se ja existe, se sim, o Substitui (Valor).
- `Lista.Remove('Fabio');` : Remover pela Chave: 'Palavra'.
- `Lista.TryGetValue('Fabio', Pessoa)` : (TPessoa) : Buscar pela (Chave: Palavra), retornando o Valor na variavel previamente instânciada (Pessoa: TPessoar).
- `Lista.ContainsKey('Fabio')` : (Booelan) : Busca pela (Chave: Palavra) e não retorna o Valor.
- `Lista.ContainsValue(Pessoa)` : (Boolean) : Busca pelo (Valor: Pessoa). Pessoa ja deve estar com as insformações instanciadas.

## Exemplo
~~~Delphi
  Lista : TDictionary<String, TPessoa>;
~~~

> Chave: CPF e Valor: TPessoa
~~~Delphi
TPessoa : record
        CPF : String; 
       Nome : String;
end;
~~~

> Percorer uma Lista
~~~Delphi
var
  key : string;
begin
  for Key in Lista.Keys do
    Memo1.Lines.Add(key);
end;
~~~


~~~Delphi
procedure TForm1.Button2Click(Sender: TObject);
var
Pessoa : TPessoa;
begin
  if Lista.TryGetValue(edtCPF.Text, Pessoa) then
    Memo1.Lines.Add(Pessoa.Nome + ' - ' + Pessoa.CPF)
  else
    Memo1.Lines.Add('Usuário não encontrado');
end;
~~~

# Referência
- [docwiki](https://docwiki.embarcadero.com/Libraries/Sydney/en/System.Generics.Collections.TDictionary)
- [ver+](https://thuliobittencourt.com/blog/listas-genericas-tdictionary/)


