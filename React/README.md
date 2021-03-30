# React

## Informações
- [React : site oficial](https://pt-br.reactjs.org/)
- `JSX` é uma sintaxe hibrida de __HTML__ com __JavaScript__  [  ver + ](https://pt-br.reactjs.org/docs/introducing-jsx.html)
- `npx` faz parte do `npm` > v5.2
  - `npx create-react-app projeto` cria estrutura de diretórios
  - `npm build`

add babel
add better coments
add css peaker
add debug for glrome
add drawr io
add eslint
add git lens (espiar os commits na linha)
add html css suport
add live server
add material icon theme
add mithril emm
add pretier
add react native tools



## Editores online
- [CodePen](https://codepen.io/pen?&editors=0010)
- [CodeSandbox](https://codesandbox.io/s/new)
- [Stackblitz](https://stackblitz.com/edit/react-ym9zdj)

# Sintaxe
 [helo world](https://pt-br.reactjs.org/docs/hello-world.html)

- HTML e JavaScript (modo tradicional)
- JSX (modo prático, porem precisa ser incorporado)

> Resumidamente temos um arquivo **HTML** e um **JavaScript**. <br>
> O arquivo JS se comunica com o HTML por meio de __funções JS__. (exemplo: `document.getElementById('identificador')` )



~~~HTML
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Hello World</title>
 
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>

 </head>
  <body>

   
   <div id="root"></div>
   
   
   <script type="text/babel">
    // Código React
    ReactDOM.render(
        <h1>Hello, world!</h1>,
        document.getElementById('root')
      );
   </script>

   
  </body>
</html>
~~~

- passando variavel por parâmetro
~~~~JavaScript
const elemento = <h1>Hello, world!</h1>;
const conteudo = document.getElementById('root');
ReactDOM.render( elemento , conteudo );
~~~


~~~
   <!--
      Note: this page is a great way to try React but it's not suitable for production.
      It slowly compiles JSX with Babel in the browser and uses a large development build of React.

      Read this section for a production-ready setup with JSX:
      https://reactjs.org/docs/add-react-to-a-website.html#add-jsx-to-a-project

      In a larger project, you can use an integrated toolchain that includes JSX instead:
      https://reactjs.org/docs/create-a-new-react-app.html

      You can also use React without JSX, in which case you can remove Babel:
      https://reactjs.org/docs/react-without-jsx.html
    -->
~~~


- Criando classes
~~~
<script type="text/babel">

    // Código React (componente Uauario)
    class Usuario extends React.Component{
      render(){
         return( 

           // codigo JSX
           <div><h1> Ola Mundo </h1></div>
           
         );
      }
    }
    // Reinderizar no HTML
    ReactDOM.render( <Usuario />, document.querySelector("#app") );
</script>
~~~
