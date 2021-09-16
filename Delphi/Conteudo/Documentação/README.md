# Documentação em Delphi
- `Region`
- `Help Insight`
- `PasDoc`


## Region
~~~Delphi
{ $REGION 'Descrição da funcionalidade de um Botão: ACIONAR' }
// sequência de comentários a serem ocultados.
// ...
// ...
{ $ENDREGION }
~~~

## Help Insight - XML Documentation Comments
- [Help Insight Embarcadero](https://docwiki.embarcadero.com/RADStudio/Sydney/en/Help_Insight)
- Exibir uma caixa de diálogo com informações sobre a Função/Procedimento.
- `Ctrl` + `Shift` + `H` ou `parar o mouse em cima do nome da função`: para visualizar as funcionalidades de uma função.
- Realizar a marcação sobre Declaração da função.
- Parâmetros utilizados no XML Documentation:
  - `<sumary>` `</sumary>` : Criação do Sumário.
  - `<para>` `</para>` : Criação de parágrafos no sumário.
  - `<c>` `</c>`: Alterar a fonte da letra para parecer como a de um código.
  - `<code>` `</code>` : Escrever trechos de códigos.
  - `<param name="varivel">` `</param>` : Descrição dos parâmetros da função.
  - `<return>` `</return>` : Informa sobre o Retorno da função.
  - `<remarks>` `</remarks>` : Exibi uma observação na função.
  - `<see cref='nome_classe' />` : Cria um link para a/as classes que estão chamando a função.
  - `<exception cref="nome_exception">` `<exception>` : Informar sobre a exeção criada.
  - `<permission cref="nome_permissao">` `</permission>` : Informar o nível de permissão para utilizar a função.

> Exemplo:
~~~Delphi
public
    /// <summary> A função <c>Dividir</c> realiza a divisão de dois números inteiros. Está sendo utilizada em:
    ///   <see cref='uNomeClasseUtilizando'/>
    ///   <para>
    ///     Veja o exemplo a baixo de como utilizar a função:
    ///   </para>
    ///   <code>
    ///       <para> var </para>
    ///       <para> resultado : Real; </para>
    ///       <para> ... </para>
    ///       <para> resultado := TformPrincipal.Dividir(3,2);   </para>
    ///   </code>
    /// </summary>
    /// <param name="x">
    ///     Variavel de valor Inteiro.
    /// </param>
    /// <param name="y">
    ///     Variavel de valor Inteiro.
    /// </param>
    /// <returns>
    ///     A função retorna uma valor do tipo <c>Real</c>.
    /// </returns>
    /// <exception cref='EExcepctionTeste'>
    ///     Essa exceção foi gerada para teste.
    /// </exception>
    /// <permission cref='Administrado'>
    ///     Essa função só poder ser utilizada por um nivel de Administrador.
    /// </permission>
    ///  <remarks>
    ///     Obs.: Atenção para não utilizar 'zero' no parâmetro Y.
    ///  </remarks>
    function Dividir(x, y: Integer): Real;
~~~
> Referências:
[ver+ 01](http://docwiki.embarcadero.com/RADStudio/XE3/en/XML_Documentation_Comments)
[ver+ 02](https://www.youtube.com/watch?v=bQ5dSiLfwZI)



## PasDoc
> Referências:
- [download](https://github.com/pasdoc/pasdoc/releases/tag/v0.16.0)
- [GitHub PasDoc](https://github.com/pasdoc/pasdoc)
- [PasDoc io](https://pasdoc.github.io/)


- `@param @returns @raises`
~~~Delphi
{ Do something with name and value.
  @param(Name is a string with the item's name)
  @param(Value is a string with the item's value)
  @returns(@true on success, @false otherwise)
  @raises(EUnknownItem if the name can not be found) }
function DoSomething(const Name: string; const Value: string): boolean;
~~~

- `@abstract`
~~~Delphi
type
  { @abstract(This class does some very useful thing.)
    With the help of this class you can ...
    (more text that describes how very very
    useful is this class follows). }
  TMyClass = class ...
~~~  

- `@Author`
~~~Delphi
@author(Johannes Berg <email@address.here>)
@author(John Doe (www.somewhere.on.the.net))
@author(Jane Doe (http://jane.doe.org))
~~~

- `@bold @italic`
~~~Delphi
@bold(This is bold text. @italic(This is bold and italic text.))
~~~

- `@br`
~~~Delphi
{ 1st paragraph. @br Second line of 1st paragraph.

  2nd paragraph. Blah blah blah.

  3rd paragraph. @br
  Second line of 3rd paragraph. }
procedure TestLineBreak;
~~~

- `@code`
~~~Delphi
{ Declare your variables like @code(var SomeVariable: SomeType;) }
~~~

- `@created @lastmod`
~~~Delphi
{ @created(2003-05-30)
  @lastmod(2003-07-01) }
unit SomeUnit;
~~~

- `@deprecated`
~~~Delphi
{ @deprecated This procedure is only for backward-compatibility,
  it may be removed in future versions of this unit. You should use
  @link(ConvertString) in new code. }
procedure OldConvertString(var MyString: ShortString);
~~~

- `@excluted`
~~~Delphi
// excluir da documentação
type
  { @exclude }
  TSomeHiddenClass = class ... end;

  TSomeVisibleClass = class
  public
    { @exclude }
    procedure SomeHiddenMethod;
  end;
~~~  

- `@html`
~~~Delphi
var
  { See the YouTube for demonstration of this technique.
    @html(<iframe width="560" height="315" src="https://www.youtube.com/embed/..." frameborder="0" allowfullscreen></iframe>)
  }
  MyVariable: Integer;
~~~

- ´@image`
~~~Delphi
{ Diagram below shows how this procedure works:
  @image(diagram.png) }
procedure DoSomething;
~~~

- `@includeCode`
~~~Delphi
{ Loads the image from file, creating new TImage instance.
  Remember to free it later. Example usage:
  @includeCode(load_image_example.pas) }
function LoadImage: TImage;
~~~

- `@include`
~~~Delphi
{ This is some procedure.
  @include(some_procedure_large_docs.txt) }
procedure SomeProcedure;
~~~

- `@classname @inheritedClass @inherited`
~~~Delphi
{ @name is a method of @classname which overrides the method
  @inherited to do something completely different... }
~~~   

- `@latex`
~~~Delphi
(* Text visible in every output format.

   @latex(Some \{bf test} text, visible only in LaTeX/latex2rtf output.)

   @html(Some <b>test</b> text, visible only in HTML output.)
*)
~~~


