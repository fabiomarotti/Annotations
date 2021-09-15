# Documentação e Navegabilidade em Delphi


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
- [download](https://sourceforge.net/projects/pasdoc/)
- [GitHub PasDoc](https://github.com/pasdoc/pasdoc)
- [PasDoc io](https://pasdoc.github.io/)


## Region
~~~Delphi
{ $REGION 'Descrição da funcionalidade de um Botão: ACIONAR' }

// sequência de comentários a serem ocultados.
// ...
// ...

{ $ENDREGION }
~~~


