# Sass
Repositório com estudos realizados sobre a linguagem de script para folhas de estilo, SASS.

SASS (Syntactically Awesome StyleSheets) :: (Folha de estilo sintaticamente incrivel)

* https://sass-lang.com/documentation



# Sintaxe

* arquivo.scss
* arquivo.sass  //arquivo identado

* Declaração de variaveis
$var: valor

* Fluxo de controle e regras
@if 
@else
@each
@for
@while

### Valores
* Numeros (numero-unidade)
@debug 100; // 100
@debug 0.8; // 0.8
@debug 16px; // 16px
@debug 5px * 2px; // 10px*px (read "square pixels")
@debug 5.2e3; // 5200
@debug 6e-2; // 0.06

* Unidade
@debug 4px * 6px; // 24px*px (read "square pixels")
@debug 5px / 2s; // 2.5px/s (read "pixels per second")
@debug 5px * 30deg / 2s / 24em; // 3.125px*deg/s*em
                                // (read "pixel-degrees per second-em")

$degrees-per-second: 20deg/1s;
@debug $degrees-per-second; // 20deg/s
@debug 1 / $degrees-per-second; // 0.05s/deg
@debug 1in + 6px  // 102px or 1.0625in

@debug 1in + 1s
//     ^^^^^^^^
// Error: Incompatibilidade entre as unidades:  s 'e' lin.

@debug 0.012345678912345  // 0.0123456789
@debug 0.01234567891 == 0.01234567899  // true
@debug 1.00000000009  // 1
@debug 0.99999999991  // 1


* String
@debug 0.012345678912345  // 0.0123456789
@debug 0.01234567891 == 0.01234567899  // true
@debug 1.00000000009  // 1
@debug 0.99999999991  // 1

@debug "\""; // '"'
@debug \.widget; // \.widget
@debug "\a"; // "\a" (a string containing only a newline)
@debug "line1\a line2"; // "line1\a line2"
@debug "Nat + Liz \1F46D"; // "Nat + Liz 👭"

@debug "Helvetica Neue"; // "Helvetica Neue"
@debug "C:\\Program Files"; // "C:\\Program Files"
@debug "\"Don't Fear the Reaper\""; // "\"Don't Fear the Reaper\""
@debug "line1\a line2"; // "line1\a line2"

$roboto-variant: "Mono";
@debug "Roboto #{$roboto-variant}"; // "Roboto Mono"

@debug bold; // bold
@debug -webkit-flex; // -webkit-flex
@debug --123; // --123

$prefix: ms;
@debug -#{$prefix}-flex; // -ms-flex

@use "sass:string";

@debug \1F46D; // 👭
@debug \21; // \!
@debug \7Fx; // \7f x
@debug string.length(\7Fx); // 5

@use "sass:string";

@debug string.index("Helvetica Neue", "Helvetica"); // 1
@debug string.index("Helvetica Neue", "Neue"); // 11
@debug string.slice("Roboto Mono", -4); // "Mono"

* Cores

@debug #f2ece4; // #f2ece4
@debug #b37399aa; // rgba(179, 115, 153, 67%)
@debug midnightblue; // #191970
@debug rgb(204, 102, 153); // #c69
@debug rgba(107, 113, 127, 0.8); // rgba(107, 113, 127, 0.8)
@debug hsl(228, 7%, 86%); // #dadbdf
@debug hsla(20, 20%, 85%, 0.7); // rgb(225, 215, 210, 0.7)

$venus: #998099;

@debug scale-color($venus, $lightness: +15%); // #a893a8
@debug mix($venus, midnightblue); // #594d85


* Listas
@debug list.nth(10px 12px 16px, 2); // 12px
@debug list.nth([line1, line2, line3], -1); // line3

$sizes: 40px, 50px, 80px;
@each $size in $sizes {
  .icon-#{$size} {
    font-size: $size;
    height: $size;
    width: $size;
  }
}

$sizes: 40px, 50px, 80px;
@each $size in $sizes {
  .icon-#{$size} {
    font-size: $size;
    height: $size;
    width: $size;
  }
}

@debug list.index(1px solid red, 1px); // 1
@debug list.index(1px solid red, solid); // 2
@debug list.index(1px solid red, dashed); // null








Mapas
booleanos

### Operadores
* Igual
* Relacional
* Numerico
* String
* Boolean

### Contruindo Modulo
* sass:color
* sass:list
* sass:map
* sass:math
* sass:meta
* sass:selector
* sass:string


// geral
@forward
@extend
@warn
@at-root
@error
@warn
@debug
@media
@supports
@keyframes
@font-face
@include
@use
@import
@mixin
@function  :: https://sass-lang.com/documentation/at-rules/function


h1 { /* código :: comentado */ }

### Sass Linha de Comando :: https://sass-lang.com/documentation/cli/dart-sass
--stdin
--indented
--no-indented
--load-path
--style (expanded/commpressed)
--no-charset
--error-css
--update
--no-source-map
--source-map-urls
--embed-sources
--embed-source-map
--watch
--poll
--stop-on-error
--interactive
--color
--no-unicode
--quiet
--trace
--help
--version



sass <input.scss> <output.css>
sass < <input.css>:<output.css> >< <input/>:<output/> >...



