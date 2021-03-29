# Tabela de Referência de Seletores do CSS


| Seletor	                        | Exemplo	                            | Descrição |
|---                              |---                                  |---        |
|.class	                          | .intro	                            |Seleciona todos os elementos com class="intro"|
|#id	                            | #firstname                          |Seleciona o elemento com id = " firstname "|
|*                                |*	                                  |Seleciona todos os elementos|
|elemento	                        |p	                                  |Seleciona todos < p >|
|elemento, elemento	              |div, p	                              |Seleciona todos < div > e todos elementos < p >|
|elemento elemento	              |div p	                              |Seleciona todos elementos < p > dentro de elementos < div >|
|elemento > elemento              |div > p                              |Seleciona todos < p > onde o pai é um elemento < div >|
|elemento+elemento                |div + p	                            |Seleciona todos < p > que estão imediatamente depois de um elemento < div >|
|elemento1 ~ elemento2	          |p ~ ul	                              |Seleciona todo elemento < ul > que precede um elemento < p > |
| [ attribute ]	                  |[target]	                            |Seleciona todos os elementos com um atributo target|
| [ attribute=value ]	            |[target=_blank]	                    |Seleciona todos os elementos com target = " _ blank " |
| [ attribute~=value ]	            |[title~=flower]	                    |Seleciona todos os elementos com um atributo title contendo a palavra "flower"|
| [ attribute|=value ]|	          |[lang|=pt-br]	                      |Seleciona todos os elementos com um atributo lang, cujo o atributo valor comece ||com "pt-br"|
| [ attribute^=value ]|	          |a[href^="https"]	                    |Seleciona todo elemento < a > que tem um atributo href com o valor começando ||com "https"|
| [ attribute$=value ]|	          |a[href$=".pdf"]	                    |Seleciona todo elemento < a > que tem um atributo href com o valor termina com ".||pdf"|
| [ attribute*=value ]|	          |a[href*="tableless"]	                |Seleciona todo elemento < a > que tem um atributo href com o valor contém ||"tableless"|
| :active	                        |a:active	                            |Seleciona o link ativo|
| ::after	                        |p::after	                            |Insere conteúdo depois de cada elemento < p>|
| ::before	                        |p::before	                          |Insere conteúdo antes de cada elemento < p>|
| :checked	                        |input:checked	                      |Seleciona todo elemento < input > checked|
| :default	                        |input:default	                      |Seleciona os < input > padrão|
| :disabled	                      |input:disabled	                      |Seleciona todo < input > desabilitado|
| :empty	                          |p:empty	                            |Seleciona todo elemento < p> que não tem filhos, incluindo texto|
| :enabled	                        |input:enabled	                      |Seleciona todo < input > habilitado|
| :first-child	                    |p:first-child	                      |Seleciona todo elemento < p > que é o primeiro filho do seu pai|
| ::first-letter	                  |p::first-letter	                    |Seleciona a primeira letra de todo elemento < p >|
| ::first-line	                    |p::first-line	                      |Seleciona a primeira linha de todo elemento < p >|
| ype.asp">:first-of-type	        |p:first-of-type	                    |Seleciona todo elemento <p> que é o primeiro filho do seu pai|
| :focus	                          |input:focus	                        |Seleciona o < input > que tem focus|
| :hover	                          |a:hover	                            |Seleciona links quando o mouse passa por cima|
| sp">:in-range	                  |input:in-range	                      |Seleciona o elemento < input > com o atributo value dentro de um range especificado|
| :indeterminate	                  |input:indeterminate	                |Seleciona o elemento < input > tem um estado indeterminado|
| :invalid	                        |input:invalid	                      |Seleciona todos < input> elementos com um valor inválido|
| :lang(language)	                |p:lang(pt-br)	                      |Seleciona todo elemento < p > com a atributo lang igual a "pt-br"|
| sp">:last-child	                |p:last-child	                        |Seleciona todo elemento < p > que é o último filho de seu pai|
| ype.asp">:last-of-type	          |p:last-of-type	                      |Seleciona todo elemento < p > que é o último elemento do tipo <p> do seu pai|
| :link	                          |a:link	                              |Seleciona todos links não visitados|
| :not(Seletor)	                  |:not(p)	                            |Seleciona todo elemento elemento que não é um elemento < p >|
| sp">:nth-child(n)	              |p:nth-child(2)                       |Seleciona todo elemento < p > que é o segundo filho do seu pai|
| hild.asp">:nth-last-child(n)	    |p:nth-last-child(2)	                |Seleciona todo elemento < p > que é o segundo filho do seu pai, ||contando com o último filho|
| f-type.asp">:nth-last-of-type(n)	|p:nth-last-of-type(2)	              |Seleciona todo elemento < p > que é o segundo < p > of its ||parent, contando com o último filho|
| ype.asp">:nth-of-type(n)	        |p:nth-of-type(2)	                    |Seleciona todo elemento < p > que é o segundo < p > do seu pai|
| ype.asp">:only-of-type	          |p:only-of-type	                      |Seleciona todo elemento < p > that is the only <p> do seu pai|
| sp">:only-child	                |p:only-child	                        |Seleciona todo elemento < p > que é o único filho do seu pai|
| :optional	                      |input:optional	                      |Seleciona o elemento < input > com sem o atributo "required"|
| ange.asp">:out-of-range	        |input:out-of-range	                  |Seleciona o elemento < input > com o atributo value fora do range ||especificado|
| ::placeholder	                  |input::placeholder	                  |Seleciona o elemento < input > com texto placeholder|
| sp">:read-only	                  |input:read-only	                    |Seleciona o elemento < input > com o atributo "readonly" especificado|
| sp">:read-write	                |input:read-write	                    |Seleciona o elemento < input > com o atributo "readonly" não especificado|
| :required	                      |input:required	                      |Seleciona o elemento < input > com the "required" atributo especificado|
| :root	                          |:root	                              |Seleciona o elemento root|
| ::selection	                    |::selection	                        |Seleciona a porção de um elemento que está selecionado pelo usuário|
| :target	                        |#news:target	                        |Seleciona o elemento atual ativo #news ( clicado pelo usuário na URL contendo o nome |ancora)
| :valid	                          |input:valid	                        |Seleciona todos < input > elementos com um valor válido|
| :visited	                        |a:visited	                          |Seleciona todos links já visitados| 


# Referência 
[Sobre](https://tableless.com.br/referencia-seletores-css/)
