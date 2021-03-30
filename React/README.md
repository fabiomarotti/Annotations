# React

## Informações

- [site React](https://pt-br.reactjs.org/)
- `JSX` sintaxe hibrida de HTML com JavaScript [ver +](https://pt-br.reactjs.org/docs/introducing-jsx.html)

# Editores online

- [CodePen](https://codepen.io/pen?&editors=0010)
- [CodeSandbox](https://codesandbox.io/s/new)
- [Stackblitz](https://stackblitz.com/edit/react-ym9zdj)

# Sintaxe
> Resumidamente temos um arquivo HTML e um JavaScript. <br>
> O arquivo JS se comunica com o HTML por meio de funções JS. (exemplo: `document.getElementById('identificador')` )
> 


 [helo world](https://pt-br.reactjs.org/docs/hello-world.html)

- HTML e JavaScript (modo tradicional)
- JSX (modo prático, porem precisa ser incorporado)

~~~HTML

<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>Hello World</title>
    <script src="https://unpkg.com/react@17/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>

    <!-- Don't use this in production: -->
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
  </head>
  <body>
    <div id="root"></div>
    <script type="text/babel">

      ReactDOM.render(
        <h1>Hello, world!</h1>,
        document.getElementById('root')
      );

    </script>
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
  </body>
</html>

~~~
