# React



## Informações
- [site oficial React](https://pt-br.reactjs.org/)

 - `Componentes` React podem ser declarados por meio de `Classes` ou `Funções` 
 - `Elementos` são variaveis que incorporam:
   - `Componentes`
   - `Componentes definidos pelo usuário`
   - `JSX`
- `JSX` é uma sintaxe hibrida de __HTML__ com __JavaScript__  [  ver + ](https://pt-br.reactjs.org/docs/introducing-jsx.html)

 
### Ferramentas que estão relacionadas
- `npm`ou `Yarn`são os Gerenciadores de pacotes
  - `npx` faz parte do `npm` (versão >= v5.2)
  - `npx create-react-app <NOME_PROJETO>` cria estrutura de diretórios
  - `npm build` 
- `webpack` ou `Parcel`Bundler - otimiza o tempo de carregamento das páginas
- `Babel` Habilita escrever código JavaScript moderno, mas que funciona em navegadores mais antigos
- `Next.JS` [ver +](https://nextjs.org/learn/basics/create-nextjs-app)
  - aplicativos estáticos e renderizados por servidor
  - soluções de estilo e roteamento
- `Gatsby` [ver +](https://www.gatsbyjs.com/)
  -  usa componentes React, mas gera HTML e CSS pré-renderizados  
  -  [Galeria de exemplos](https://www.gatsbyjs.com/starters/?)


### Editores online
- [CodePen](https://codepen.io/pen?&editors=0010)
- [CodeSandbox](https://codesandbox.io/s/new)
- [Stackblitz](https://stackblitz.com/edit/react-ym9zdj)

# Tópicos
- `JSX`
  - pode ser usado dentro de `if`e `for`
  - usar `{` `}` para incorporar atributos JavaScript ao HTML (não usar aspas, apenas em atributos como String)
  - fechar Tags vazias com `/>`
  - pode conter elementos HTML filho
- `Elementos`
  - são imutaveis
  - atulizar a interface é criar um novo elemento e passa-lo para `ReactDOM.render()`
  
- `Componentes` 
  - `Componentes de função`
  - `Componentes de classe`
  - transformam `props`em `UI`
- 
- `Componentes de estado e Ciclo de Vida` [ver +](https://pt-br.reactjs.org/docs/state-and-lifecycle.html)
- 
- `HOCs` (Higher-Order Component) [ver +](https://pt-br.reactjs.org/docs/higher-order-components.html)
  - transformam `Componentes`em outros `Componentes`  
- `Refs` [ver +](https://pt-br.reactjs.org/docs/refs-and-the-dom.html)
- `State`
- `Function Components`
- `Props`
- `Hooks`

# Chamadas React

> React sem ES6 : `create-react-class` [ver +](https://pt-br.reactjs.org/docs/react-without-es6.html) <br>

> React com ES6:
- `React.Component` **Classe base** Usando ES6
- `React.PureComponent` 
  - esta Classe implementa o método `shouldComponentUpdate()` 
  - (estruturas simples) comparação superficial de objetos
  - (estruturas complexas) usar `forceUpdate()`
  - garantir que todos os descendentes sejão "puros"
  
- `React.memo` componentes em React definidos como funções

- **Cria Elementos**
  - `React.createElement()` 
  - `React.createFactory()` 

- **Manipula Elementos**
  - `React.cloneElement()`
  - `React.isValidElement()`
  - `React.Children` 

- **Renderizar multiplos elementos**
  - `React.Fragment`

- **Refs**
  - `React.createRef`
  - `React.forwardRef`

- **Suspender por algo antes de renderizar**
  - `React.lazy`
  - `React.Suspense`

[continuar em ..] (https://pt-br.reactjs.org/docs/react-api.html#cloneelement)

> **Hooks**
- __Hooks Básicos__
  - `useState`
  - `useEffect`
  - `useContext`

- __Hooks Adicionais__
  - `useReducer`
  - `useCallback`
  - `useMemo`
  - `useRef`
  - `useImperativeHandle`
  - `useLayoutEffect`
  - `useDebugValue`


---

- `ReactDOMServer`
- `ReactDOM`
  - `ReactDOM.render()` [ver +](https://pt-br.reactjs.org/docs/react-dom.html#render)
  - `ReactDOM.hydrate()`
  - `ReactDOM.unmountComponentAtNode()`
  - `ReactDOM.findDOMNode()`
  - `ReactDOM.createPortal()`





## `React.createElement()`

~~~JavaScript
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
~~~

> equivale a ...

~~~JavaScript
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
~~~

> que significa..

~~~JavaScript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
~~~

> isto são os `Elementos React` <br>
> `Componentes` são feitos de `Elementos`
 

~~~
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
~~~




# Sintaxe
 [Hello world](https://pt-br.reactjs.org/docs/hello-world.html)

> Resumidamente temos um arquivo **HTML** e um **JavaScript**. <br>
> <br>
> O arquivo JS se comunica com o HTML por meio de __funções JS__. <br>
> exemplo: `document.getElementById('identificador')`
> <br>


## Hello World

- Exemplo 01
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

> passando as variaveis por parâmetro
~~~JavaScript
const elemento = <h1>Hello, world!</h1>;
const conteudo = document.getElementById('root');
ReactDOM.render( elemento , conteudo );
~~~

- Exemplo 02
~~~JavaScript
// -- Funções a serem incorporadas

// Função 01
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

// Função 02
function getGreeting(user) {
  if (user) {
    return <h1>Hello, {formatName(user)}!</h1>;
  }
  return <h1>Hello, Stranger.</h1>;
}

// Variavel User
const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

//Variavel Element, incorporada com uma função
const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

// Função React: Render
ReactDOM.render(
  element,
  document.getElementById('root')
);
~~~

## Incorporando Expressões em JSX

> Variável
~~~JavaScript
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
~~~

> Representação de Objetos

~~~JavaScript
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
~~~

~~~JavaScript
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
~~~

~~~
// Nota: esta estrutura está simplificada
const element = {
  type: 'h1',
  props: {
    className: 'greeting',
    children: 'Hello, world!'
  }
};
~~~~ 

# Componentes: Renderizando

~~~
function tick() {
  const element = (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {new Date().toLocaleTimeString()}.</h2>
    </div>
  );
  // usa-se Render() apenas uma vez - por isso o callback
  ReactDOM.render(element, document.getElementById('root'));
}

// callback: chama o ReacDOM.Render() a cada segundo
setInterval(tick, 1000);
~~~

# Componentes: Estado e Ciclo de Vida

~~~

function Clock(props) {
  return (
    <div>
      <h1>Hello, world!</h1>
      <h2>It is {props.date.toLocaleTimeString()}.</h2>
    </div>
  );
}

// Utiliza o componente Clock em seu callback
function tick() {
  ReactDOM.render(
    <Clock date={new Date()} />,
    document.getElementById('root')
  );
}

setInterval(tick, 1000);

~~~


## Componentes de Função
~~~JavaScript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
~~~


## Componentes de Classe

~~~React
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
~~~


## Componentes definidos pelo usuário

> são elementos que incorporam componentes classes ou componentes funções.
> passa-se **atributos JSX** e **componentes filhos** como objeto unico (`props`)


~~~JavaScript
// componente
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

// elemento que recebe um componente, 
// se torna um componente definido pelo usuário
const element = <Welcome name="Sara" />;

ReactDOM.render(
  element,
  document.getElementById('root')
);
~~~

- Nós chamamos ReactDOM.render() com o elemento <Welcome name="Sara" />.
- React chama o componente Welcome com {name: 'Sara'} como props.
- Nosso componente Welcome retorna um elemento <h1>Hello, Sara</h1> como resultado.
- React DOM atualiza eficientemente o DOM para corresponder <h1>Hello, Sara</h1>.

## Composição de Componentes

~~~
// Componente A02
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}

// Componente A01, compoem A02
function App() {
  return (
    <div>
      <Welcome name="Sara" />
      <Welcome name="Cahal" />
      <Welcome name="Edite" />
    </div>
  );
}

// Renderização
ReactDOM.render(
  <App />,
  document.getElementById('root')
);

~~~

- Exemplo de Composiçao de Componentes

~~~
// Componente a ser analisado
function Comment(props) {
  return (
    <div className="Comment">
      <div className="UserInfo">
        <img className="Avatar"
          src={props.author.avatarUrl}
          alt={props.author.name}
        />
        <div className="UserInfo-name">
          {props.author.name}
        </div>
      </div>
      <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
~~~

- quebra-se em componentes menores: 
 
> Componente: Avatar
~~~
function Avatar(props) {
  return (
    <img className="Avatar"
      src={props.user.avatarUrl}
      alt={props.user.name}
    />
  );
}
~~~

> Componente: UserInfo,         <br>
> que compoem Componente Avatar
~~~
function UserInfo(props) {
  return (
    <div className="UserInfo">
      
      // Componente Avatar
      <Avatar user={props.user} />
      
      <div className="UserInfo-name">
        {props.user.name}
      </div>
    </div>
  );
}
~~~

> incorporando os Componentes UserInfor > Avatar   <br>
> Componente Comment
~~~
function Comment(props) {
  return (
    <div className="Comment">
    
    // Componente UserInfo
    <UserInfo user={props.author} />
    
    <div className="Comment-text">
        {props.text}
      </div>
      <div className="Comment-date">
        {formatDate(props.date)}
      </div>
    </div>
  );
}
~~~



-
- t
- t
- t
- t
- https://pt-br.reactjs.org/docs/rendering-elements.html

continuar


### Conversor JSX

- [`Babel conversor JSX`](https://babeljs.io/en/repl#?browsers=&build=&builtIns=false&spec=false&loose=false&code_lz=DwIwrgLhD2B2AEcDCAbAlgYwNYF4DeAFAJTw4B88EAFmgM4B0tAphAMoQCGETBe86WJgBMAXJQBOYJvAC-RGWQBQ8FfAAyaQYuAB6cFDhkgA&debug=false&forceAllTransforms=false&shippedProposals=false&circleciRepo=&evaluate=false&fileSize=false&timeTravel=false&sourceType=module&lineWrap=true&presets=es2015%2Creact%2Cstage-2&prettier=false&targets=&version=7.4.3&externalPlugins=)

### Pré-processador JSX


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

### `Bundle` (empacotamento)

- ferramentas de empacotamento: 
  - [Webpack](https://webpack.js.org/) - funciona com Angular, Vue, NodeJS e Web Assembly 
    - 
  - [Rollup](https://rollupjs.org/guide/en/), 
  - [Browserify](http://browserify.org/) 


- Empacotadores:
  - [Create React App](https://create-react-app.dev/)
  - [Next.js](https://nextjs.org/)
  - [Gatsby](https://www.gatsbyjs.com/)


<hr>

- App:

~~~JavaScript
// app.js
import { add } from './math.js';

console.log(add(16, 26)); // 42
~~~

~~~JavaScript
// math.js
export function add(a, b) {
  return a + b;
}
~~~

- Bundle:
~~~JavaScript
function add(a, b) {
  return a + b;
}

console.log(add(16, 26)); // 42
~~~


# CDN Links

-  carrega o React de um CDN, recomenda-se manter o atributo `crossorigin`
-  verificar se o CDN define o cabeçalho HTTP como `Access-Control-Allow-Origin: *`
-  Para carregar uma versão específica do react e react-dom, substitua 17 com o número da versão que você deseja


~~~HTML
<!-- Desenvolvimento -->
<script crossorigin src="https://unpkg.com/react@17/umd/react.development.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.development.js"></script>
~~~

~~~HMTL
<!-- Produção -->
<script crossorigin src="https://unpkg.com/react@17/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js"></script>
~~~

# ES6 - comentários

> As **Classes** podem ser definidas como `expression` ou `declarations`
> [ver +](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

- `expression`

~~~JavaScript
const Rectangle = class {
  constructor(height, width) {
    this.height = height;
    this.width = width;
  }
  area() {
    return this.height * this.width;
  }
};

console.log(new Rectangle(5, 8).area());
// expected output: 40
~~~

- `declaration`

~~~JavaScript
class Polygon {
  constructor(height, width) {
    this.area = height * width;
  }
}

console.log(new Polygon(4, 3).area);
// expected output: 12
~~~





# Dicionário
- `Code-splitting` dividindo o código
- transpilar seu código React + ES6 em plan-vanilla JS
- `bundling` empacotamento
- `CamelCase` cada palavra é iniciada com maiúsculas e unidas sem espaços
- `Elemento` é um objeto descrevendo uma instância de um componente ou um nó DOM e suas propriedades 
  - possui apenas 2 campos: 
    - `type` (string | Componente) 
      - se String: representa um nó DOM com uma tag de mesmo nome 
    - `props` | Objeto 
      - são seus atributos
- `props` Propriedades, parâmetro dos componentes``(funçoes JS)
- `state`
- `Componentes de função` 
  - são funções JavaScript com um único argumento de entrada ( `Props` ) 
  - retorna um elemento React
- `Componentes de classe`




