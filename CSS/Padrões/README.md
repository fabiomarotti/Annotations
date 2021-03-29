# Padrões CSS
- Metodologias para organizar códigos CSS.

- Namespaces CSS


# Padrões de Nomenclatura

## `BEM` (Block Element Modifier) 

- `Bloco`
  - é uma entidade independente;
  - qualquer elemento HTML pode ser um bloco;
  - assimilação com **Componente** ou **Módulo**
  
~~~
<div class="bloco"></div>
~~~


- `Elemento` 
  - faz parte de um **Bloco**, é um elemento-filho 
  - um elemento é semanticamente vinculado ao seu bloco
  - não tem significado sozinho. 
  - separa-se o bloco do elemento com _ _ 
    - [Bloco] __ [Elemento]
~~~
<div class="bloco">
      <p class="bloco__elemento"></p>
</div>
~~~


- `Modificador`
  - modifica um bloco ou elemento 
  - modifica a aparência, comportamento ou estado de um bloco ou de um elemento.
    - [Bloco|Elemento]--[Modificador]
    
~~~ 
<div class="bloco">
      <p class="bloco__elemento"></p>
      <p class="bloco__elemento--modificador"></p>
</div>
~~~


Exemplo prático:
~~~HTML
  <div class="c-menu__item">
    <a href="#" class="c-menu__link">Home</a>
  </div>
 
  <div class="c-menu__item">
    <a href="#" class="c-menu__link c-menu__link--disabled">Sobre</a>
  </div>
 
  <div class="c-menu__item">
    <a href="#" class="c-menu__link">Contato</a>
  </div>
</ul>
~~~

~~~CSS
.c-menu {}
 
.c-menu__item {}
 
.c-menu__link {}
 
.c-menu__link--disabled {}
~~~

### Boas práticas: BEM
- não precisa replicar exatamente a hierarquia do HTML
- possibilidade de usar nomes compostos
- Blocos dentro de Blocos (quando não for usar/afetar em outros lugares/componentes do site)
- lidar com estados
- Sass lida nativamente com o padrão BEM



## `OOCSS` (Object Oriented CSS)
- visa componentizar todo o código
- separar a **Estrutura** do **Visual** (skin)
- criar independência do **Container** em relação ao **Conteúdo**






## `RSCSS`

# Padrões de Estrutura 

- modularizar o css
  - um css para cada página ou modulo
  - CSS (geral) usando varios `@import URL(arquio.css)`
  - CSS_Cor e CSS_Estrutura
  
  
## `SMACSS`
## `ITCSS`



# Referência
[Geral sobre Padrões](http://www.andrefelizardo.com.br/blog/padroes-css/)
[sobre BEM](http://getbem.com/introduction/)
[sobre OOCSS](http://oocss.org/)

