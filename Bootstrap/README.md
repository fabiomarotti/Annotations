# Bootstrap
Repositório com estudos realizados sobre o framework BOOTSTRAP


# Containers
- class="container"
- class="container-fluid"

~~~HTML
<div class="container">
  <!-- Conteúdo aqui -->
</div>
~~~

# Breakpoints

| Breakpoint	|Class infix	| Dimensions
|---          |---          |--- 
|X-Small	          |None	  | <576px
|Small	            | sm	  | ≥576px
|Medium	            | md	  | ≥768px
|Large	            | lg	  | ≥992px
|Extra large	      | xl	  | ≥1200px
|Extra extra large  |	xxl	  | ≥1400px

~~~HTML
// Dispositivos extra small (telefones em modo retrato, com menos de 576px)
// Sem media query para `xs`, já que este é o padrão, no Bootstrap.

// Dispositivos small (telefones em modo paisagem, com 576px ou mais)
@media (min-width: 576px) { ... }

// Dispositivos médios (tablets com 768px ou mais)
@media (min-width: 768px) { ... }

// Dispositivos large (desktops com 992px ou mais)
@media (min-width: 992px) { ... }

// Dispositivos extra large (desktops grandes com 1200px ou mais)
@media (min-width: 1200px) { ... }
~~~

# Grid

- Maximo de 12 colunas por linha (col/row)

~~~HTML
<!-- Colunas sempre com metade da largura disponível, em dispositivos móveis e desktop -->
<div class="row">
  <div class="col-6">.col-6</div>
  <div class="col-6">.col-6</div>
</div>
~~~

## De empilhado Para horizontal

~~~HTML
<div class="row">
  <div class="col-sm-8">col-sm-8</div>
  <div class="col-sm-4">col-sm-4</div>
</div>
<div class="row">
  <div class="col-sm">col-sm</div>
  <div class="col-sm">col-sm</div>
  <div class="col-sm">col-sm</div>
</div>
~~~

# Navbar

[ver +](https://getbootstrap.com.br/docs/4.1/components/navbar/)



# ReferÊncias

- https://css-tricks.com/snippets/css/a-guide-to-flexbox/#flexbox-background

