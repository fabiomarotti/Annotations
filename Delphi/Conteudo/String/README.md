# String

- `System.Classes.TStrings` (Classe Base) [saiba+](http://docwiki.embarcadero.com/Libraries/Sydney/en/System.Classes.TStrings)
- `System.Classes.TStringList` [Saiba+](http://docwiki.embarcadero.com/Libraries/Sydney/en/System.Classes.TStringList)

--- 

- `palavra.Length` : (Integer) Retorna o tamanho total de caracteres.
- `palavra.Remove(x,y)` : (String) Retorna o *texto* cortado entre as posições *x* e *y*. (inicio em zero)
- `palavra.IndexOf('x')` : (Integer) Retorna o número do índice pertencente ao caracter *x* encontrado na palavra, -1 caso não encontre.
- `palavra.Insert(x,w)` : Inseri a String *w* na posição de índice *x* da palavra.
- `palavra.Trim` : Retira espaços em branco (antes/depois) da palavra.
  - `palavra.TrimLeft` : Retira caracteres em branco a Esquerda.
  - `palavra.TrimRight` : Retira caracteres em branco a Direita.
  - `palavra.TrimStart(arrayChar)` : Retira caracteres específicos (arrayChar) do Inicio.
  - `palavra.TrimEnd(arayChar)` : Retira caracteres específicos (arrayChar) do Final.
- `String.Equals(string1 , string2)`: (Boolean) Compara se as *string1* e *string2* são iguais.

## Conversões
- `BoolToStr` : Booelan para String.
- `IntToStr` : Integer para String.
- `FloatToStr` : Float para String.
- `FloatToStrF` : Float para String. (precisão)
- `DateToStr` : Converte uma Data para String 
- `FormatDateTime( x , dataAtual )` : Converte uma Data para uma String personalizada
  - dataAtual := TDateTime.Now;
[ver+](https://stackoverflow.com/questions/6452400/difference-between-comparestr-and-for-strings-in-delphi)


## Comparações
- Equals
- EndWith
- StartWith
- CompareStr
- AnsiCompareText
- Compare()
- NOME_TABELA.FieldByName('NOME_FIELD').AsString = '02'
- NOME_TABELA.FieldByName('NOME_FIELD').AsInteger = 02
- NOME_TABELA.FieldByName('NOME_FIELD').AsBoolean = True
- if ((conexao.FieldValues['complex'] = '02') and (conexao.FieldValues['financ'] = '04')) then
-StrUtils
[ver+ compare prog](https://showdelphi.com.br/comparacao-de-strings-com-o-delphi/)

## Informações
- Length(str1)
