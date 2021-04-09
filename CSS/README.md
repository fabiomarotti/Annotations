# CSS (Cascading Style Sheets)
Repositório com os estudos realizados sobre CSS

# Informações
- Sempre prevalece a ultima propriedade declarada.

# Propriedades 
- `--` declaranado
- `var()` utilizando
- [ver +](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Using_CSS_custom_properties)
- Controle de Herança
  - `inherit` aplica a mesma propriedade do elemento pai
  - `initial` Define para ser o valor inicial
  - `unset` Restaura seu valor natural.
    - se a propriedade é herdada naturalmente, ela age como inherit, caso contrário, age como initial .
  - `all` Aplica a __quase__ todas as propriedades.
  - `revert` 

## Especificidade

|Seletor	|Milhar		|Centena	|Dezena		|Unidade	|Especificidade Total   |
|---		|--- 		|--- 		|--- 		|--- 		|--- 			|
| h1									|0	|0	|0	|1	|0001|
| h1 + p::first-letter 							|0	|0	|0	|3	|0003|
| li > a[href*="en-US"] > .inline-warning				|0	|0	|2	|2	|0022|
| #identifier								|0	|1	|0	|0	|0100|
|Sem seletor, com uma regra dentro do atributo **style** de um elemento	|1	|0	|0	|0	|1000|

## Variáveis CSS
- Global
~~~CSS
:root{    
   --variavel_global : valor; 
} 
~~~

- Local
~~~CSS
elemento{ 
   --variavel_local : valor;
} 
~~~

- Usando
~~~
...
atributo : var( --variavel) ;
...
~~~

## Exemplos

- Variavel Global
~~~
// global
:root{
  --main-color: #FFF;
  --main-font: 'Arial';
}

body{
  color: var(--main-color);
  font-family: var(--main-font);
}
~~~

- Variavel Local
~~~
// local
.classe{
  --main-color: #FFF;
  --main-font: #000;
}
.classe p{
  color: var(--main-color);
  font-family: var(--main-font);
}
~~~






# Unidades de medida
- `px` 	: pixel de referência, não é o pixel da tela [ver +](https://alistapart.com/article/a-pixel-identity-crisis/)
- `%` 	: relativo ao elemento pai
- `em` 	: relativo ao elemento pai
- `rem` : relativo ao elemento raiz HTML (root em)
- `vw` 	: relativo a largura (variable width)
- `vh` 	: relativo a altura (variable height)
- `vmin` : 
- `vmax` : 
- `ex` : 
- `ch` : character unit 
- `fr` : fração do espaço disponivel (usado no Grid Layout)

## detalhes das unidades
- `px`, `em`, `rem`  : usados para  margens, preenchimento, espaçamento e larguras / alturas, quando não for redimencionavel 
- `vw`, `vh` - 1% da (largura/altura) da janela (width-height/ fonte pixel) * %
- `vmin`, `vmax` é o (menor/maior) valor.


## padrão
16px = 1.0000em = 100.0% [ver +](https://www.w3schools.com/tags/ref_pxtoemconversion.asp)


# Adicionando o CSS ao HTML (3 formas)
## Inline (no elemento)
~~~HTML
// arquivo: index.html

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>CSS Inline</title>
</head>
<body>

    <h1 style="color:red;padding:30px;"> Titulo </h1>
    <p style="color:blue;"> Paragrafo </p>
  
</body>
</html>
~~~

## Interno (no arquivo HTML)

~~~HTML
<style type="text/css">
 // código CSS
</style>
~~~

## Externo (no arquivo CSS)
~~~HTML
// arquivo: index.html

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <link rel="stylesheet" type="text/css" href="style.css" />
    <title>CSS Externo</title>
</head>
<body>

  <div class="trapezio"></div>
  
</body>
</html>
~~~

~~~HTML
// arquivo style.css

.trapezio {
  border-bottom: 70px solid #c1c1c1;
  border-left: 30px solid transparent;
  border-right: 15px solid transparent;
  height: 0;
  width: 120px;
}
~~~


## Background
- `border-box`: fundo fica embaixo da borda
- `padding-box` : fundo termina onde começa a borda
- `content-box`: fundo permanece aonde tiver conteudo
- `initial`: rompe a herança, indo para o origem inical (preto)

## Position
- `static` :  não sofre alterações dos posicionamentos: right, bottom, left, top;
- `relative` : é usado com os posicionamentos: right, bottom, left, top;
- `absolute`:  é usado com os posicionamentos: right, bottom, left, top; e sua relação é baseada no elemento ancestral (anterior)
- `sticky` : ( mistura de relative e fixed) sofre alteração da rolagem (relative) mas não sai da tela, sobrepondo os outros elementos (fixed).
- `fixed` :  é posicionado em relação à janela de visualização, não se move nas rolagens;

## Overflow (texto que estoura uma caixa)
- `visible` : o texto não é cortado
- `hidden` : o texto é ocultado
- `scroll` : a caixa gera um scroll na caixa (horizontal e vertical)
- `auto` : a caixa gera um scroll onde for necessario.

## Float
- `left` a esquerda
- `right` a direita
- `none` não flutua
- `inherit` herdao valor flutuante de sue pai

- `flex-basis`
- `flex-direction` [ver +](https://developer.mozilla.org/pt-BR/docs/Web/CSS/flex-direction)
  - `row ` em linha
  - `column` em coluna
  - `row-reverse` em linha, ordem invertida
  - `column-reverse` em coluna, ordem invertida
- `flex-flow`
- `flex-shrink`
- `flex-wrap` : (embrulho) permanece na div ou (nowrap) estoura;
- `flex`
- `order`


# Pseudo Classes
> Pseudo Classes alteram o estado de um Seletor/Elemento.
> Por se tratar de um Estado, usa-se `:`, diferente de `::` para Elementos.

- Exemplo:
~~~
/* Pairar o ponteiro do mouse sobre qualquer botão */

button:hover {
  color: blue;
}
~~~

|       		|       			|       		|
|---    		|---    			|---    		|
| :active 		| :indeterminate (en-US) 	| :only-child 		|
| :checked 		| :in-range (en-US) 		| :only-of-type 	|
| :default (en-US) 	| :invalid 			| :optional 		|
| :dir() (en-US) 	| :lang() (en-US) 		| :out-of-range 	|
| :disabled 		| :last-child 			| :read-only (en-US) 	|
| :empty 		| :last-of-type 		| :read-write 		|
| :enabled 		| :left (en-US) 		| :required 		|
| :first (en-US) 	| :link 			| :right (en-US) 	|
| :first-child 		| :not() 			| :root 		|
| :first-of-type 	| :nth-child() 			| :scope (en-US) 	|
| :fullscreen 		| :nth-last-child() 		| :target 		|
| :focus 		| :nth-last-of-type() (en-US) 	| :valid 		|
| :hover 		| :nth-of-type() 		| :visited 		|

[ver +](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Pseudo-classes)


# Pseudo Elementos
> Acrescenta modificações a um Seletor/Elemento, sem a necessidade de cria-lo no HTML. <br>
> Por se tratar de um Elemento, usa-se `::`, diferente de `:` para Estados dos Elementos.

- Exemplo:
~~~
/* Seleciona a primeira linha dentro da tag <p> */

p::first-line {
  color: red;
}
~~~

- Lista de Pseudo Elementos

|       	  |       		|       			|
|---    	  |---    		|---    			|
| ::after 	  | ::first-line 	| ::placeholder (en-US) 	|
| ::before 	  | ::selection 	| ::marker (en-US)  		|
| ::cue (en-US)   | ::slotted (en-US) 	| ::spelling-error (en-US)  	|
| ::first-letter  | ::backdrop  	| ::grammar-error (en-US)    	|

[ver +](https://developer.mozilla.org/pt-BR/docs/Web/CSS/Pseudo-elements)




# Resumo de Animações

> Animações se resumem em **Transformação (2D/3D)**, **Transição** e **Animação**.

## Transformações
- `transform-origin` 
- transform-style VER
- `transform` 
- 2D
  - `translate()`   // movimento
    - `translateX()`
    - `translateY()`
    - `translateZ()`
    - `translate3d()`
  - `perspecive()`  // perspectiva distancia entre usuario e plano z=o
  - `rotate()`      // rotação
    - `rotateX()`
    - `rotateY()`
    - `rotateZ()`
    - `rotate3d()`
  - `scale()`       // Dimensionamento (redimensionamento)
    - `scaleX()` 
    - `scaleY()` 
    - `scaleZ()`  
    - `scale3d()` 
  - `skew()`        // Inclinação (distorção)
    - `skewX()`
    - `skewY()`
  - `matrix()`      // transformação de matriz
    - `matrix3d()`
  
- 3D
  - `rotate()`
  - `rotateX()`
  - `rotateY()`
  - `rotateZ()`
  - `rotate3d()`
## Transições  
- `transition`
- `transition-delay`
- `transition-duration`
- `transition-property`
- `transition-timing-function`
  -  `ease`
  -  `linear`
  -  `ease-in`
  -  `ease-out`
  -  `ease-in-out`
  -  `cubic-bezier(n,n,n,n)`

## Animações



# Transformações 2D
> - Transformação 2D e 3D: são deformações realizadas de forma estática.  
> - Classe `transform` possui os seguintes métodos como parametros:
  
  <br>

- `transform-origin`
  - Define o ponto de Origem da forma.
  - % em relação ao eixo X seguida do eixo Y

~~~HTML
  /* origem no centro do elemento*/ 
  transform-origin: 50% 50%;
  
  /* origem no canto inferior direito */ 
  transform-origin: 100% 100%;
~~~

- `translate()`
  - Move o elemento pelas coordenadas X e Y de um eixo cartesiano
~~~HTML
	/* eixo X: 100px ,  eixo Y: 500px */
	transform: translate(100px,500px);
~~~

- `rotate()`
  - Rotação baseada no eixo central do elemento
~~~HTML
	transform: rotate(45deg);
~~~

- `scale()`
  - Multiplica o valor de cada eixo
  - Escala Horizontal e Vertical
  - Escalas isoladas: `scaleX()` e  `scaleY()`
 
~~~HTML
   /* dobra o valor do width e heigth */
   transform: scale(2); 

   /* 2 vezes na width e 3 vezes na heigth */
   transform: scale(2,3); 
~~~

- `skew()`
  - tomba o elemento em relação ao eixo X e Y.
  - Transformações isoladas: `skewX()` e `skewY()`
~~~HTML
   transform: skew(20deg,10deg);
~~~
~~~HTML
  /* tomba o elemento em relação ao eixo X. */
  /* baseia-se no meio do elemento em relação ao eixo Y. */
   transform: skewX(25deg);
~~~

~~~HTML
  /* tomba o elemento em relação ao eixo Y. */
  /* baseia-se no meio do elemento em relação ao eixo X. */
   transform: skewY(25deg);
~~~

- `matrix()`
  - Combina todos os outros metodos por meio de 6 parametros na seguinte ordem:
    - **scaleX**
    - **skewY**
    - **skewX**
    - **scaleY**
    - **translateX**
    - **translateY**
~~~HTML
   transform: matrix(0.2, -0.3, 0, 1, 0, 0);
~~~



# Transformações 3D
> - São as rotações em 180º dos elementos nos eixos X, Y e Z fixados.
> - Angulos são valores com o sufixo: `deg`, `rad` e `turn`.
> - Angulos negativos seguem o sentido anti-horário.
  
  - `rotateX()` espelhamento vertical
  - `rotateY()` espelhamento horizontal
  - `rotateZ()` equivale a uma rotação

~~~HTML
   rotate(180deg)
~~~


# Transições
> Transições: alteram de um estado A para estado B por meio de uma ação, tipo hove

- `transition`
- `transition-delay`
- `transition-duration`
- `transition-property`
- `transition-timing-function`
  -  `ease`
  -  `linear`
  -  `ease-in`
  -  `ease-out`
  -  `ease-in-out`
  -  `cubic-bezier(n,n,n,n)`
  

# Animações
> Animações: executão **transformações** e **transições** de forma automatica, sem o gatilho de um evento.

- `animation-name` : nome de um @keyframes
- `animation-duration` unidade em segundo
- `animation-timing-function`
- `animation-delay`
- `animation-iteration-count`
- `animation-play-state`
- `animation-direction` : 
  - `normal` : sentido definido
  - `reverse` : sentido inverso do definido
  - `alternate` : (normal + reverse)
  - `alternate-reverse` : (reverse + normal)
  
- `animation-fill-mode` 
  - `none` : Inicia em A e (executa), vai para `from B` e vai para o `to C` e estaciona em A
  - `forwards` : Inicia em A e (executa), vai para `from B` e estaciona no `to C`
  - `backwards` : Inicia em `from B` e (executa), vai para `to C` e estaciona pra A.
  - `both`: Inicia em `from B`e (executa), vai para `to C` e estaciona no `to C`
  
> - legenda: 
>    - Inicia: posição consolidada inicialmente
>    - (executa): execução de animations externa ao from e to
>    - from: execução do bloco
>    - to: execução do bloco
>    - estaciona: posição de parada




# Centralizar - (4 formas)

## 1º forma (centralizar)
> A centralização gera uma sobreposição de elementos (absolute).

~~~
.center-div {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}	    
~~~


## 2º forma (centralizar)
> Centraliza em linha, podendo ser redimencionado em coluna.

~~~
.center-div_pai {
    text-align: center;
}

.center-div_filho {
    display: inline-block;
}
~~~

## 3º forma (centralizar)
> Centraliza em colunas caso haja mais de uma div. <br>
> Não sobrepoem os elementos

~~~
.center-div {
	margin: 0 auto;
}
~~~


## 4º forma (centralizar)
> distorce background, border-radius

~~~
.center-div {
    display: flex;
    justify-content: center;
    align-items: center;
}
~~~

# Dicionário
- Pseduo Elemento
- Seletor
- 


# Referências

[Documentação](https://devdocs.io/css)

[w3schools.com](https://www.w3schools.com/css/)

[Maujor](https://maujor.com/tutorial)

[Coordenadas Homogeneas](https://en.wikipedia.org/wiki/Homogeneous_coordinates)

[W3C DOM Level 2](https://www.w3.org/TR/DOM-Level-2-Core/)

[CSSOM - CSS Object Model](https://developer.mozilla.org/pt-BR/docs/Web/API/CSS_Object_Model)

