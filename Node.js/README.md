# Node.js
Repositório com os estudos realizados sobre o interpretador JavaScript, Node.js

- https://nodejs.org/
- Node.js possui o Gerenciador de Pacotes: `npm` (Node Package Manager)
- Node.js pode ser executado via Prompt de Comando (CMD)

# Informações
`$ node -v` versão do Node.js        <br>
`$ npm  -v` versão do npm
`$ node nome_arquivo.js` executar um arquivo.js
`--save` salva no projeto local


# Frameworks/Módulos para Node.js
- Existem Frameworks Minimalistas e Frameworks FullStak.

> `Express.js`      <br>
> `Nodemon`         <br>
> `Sequelize`       <br>
> `handlebars`      <br>
> `body-parser`       <br>
> 


## `Express.js` 
-  Framework orientado a Rotas (caminhos)
-  é instalado localmente em cada aplicação pela tag `--save`
-  `$ npm install express --save`
~~~
- express()
- Apllication
- Request
- Response
- Router
~~~
 [+ detalhes sobre express.js](https://expressjs.com/pt-br/4x/api.html)

  
## `Nodemon`
- Módulo para deixar o servidor com exibição instantânea.
- `$ npm install nodemon -g`
- `$ nodemon nomeArquivo.js` deixar aberto rodando 
  
[+ detalhes sobre nodemon](https://www.npmjs.com/package//nodemon)

## `Sequelize` 
- ORM (Object-Relational Mapping)
- Modulo que auxilia a manipulação com o Banco de Dados via Node.js
- CRUD via Node.js
- `$ npm install sequelize --save`   
- Para usar o módulo MySQL:
- `$ npm install mysql2 --save`
  
[+ detalhes sobre Sequelize](https://www.npmjs.com/package/sequelize)

## `handlebars`
- Template Engine
- Associa comandos de Programação ao HTML
- `$ npm install express-handlebars --save`

## `body-parser`
- Receber dados dos formulario pelo express.js
- `$ npm install body-parser --save`


# Módulos

- Módulos: são arquivos independentes aos quais serão chamados para compor uma aplicação principal.
- Utilizado para carregar bibliotecas, refatorar, orgaznizar projetos.

~~~JavaScript
// arquivo: somar.js

var somar = function (a,b){
    return a + b;
}

// exportar a função para o modulo principal: calculadora.js
module.exports = somar;
~~~

~~~JavaScript
// arquivo: subtrair.js

var subtrair = function (a,b){
    return a - b;
}

// exportar a função para o modulo principal: calculadora.js
module.exports = subtrair;
~~~

~~~JavaScript
// arquivo: calculadora.js

var ModuloSomar     = require("./somar");
var ModuloSubtrair  = require("./subtrair");

var x = 5;
var y = 3;

console.log(ModuloSomar(x,y));
console.log(ModuloSomar(x,y));
~~~


# Protocolo HTTP

- HTTP é um módulo que faz parte do núcleo do Node.js, logo, o seu `require` não precisa especificar o local do módulo.
- [+ detalhes](https://nodejs.org/docs/latest-v13.x/api/http.html)
  
~~~JavaScript
// arquivo: appServidor.js

var http = require('http');

http.createServer().listen(8087); // abrir servidor: 8087

console.log("Servidor HTTP em execução");
// acessaro endereço -> localhost:8087
// Ctrl + C : Parar o servidor no Prompt
~~~

- 
~~~JavaScript
// arquivo: appServidorRes.js

var http = require('http');

http.createServer(
    function(req, res){
        res.end("Olá Mundo");
    }

).listen(8087); // abrir servidor: 8087

console.log("Servidor HTTP em execução");
// acessaro endereço -> localhost:8087
~~~


# Rotas
> Rotas utilizando o módulo do framework `express.js`

 - Abrindo Servidor com framework express.js

~~~JavaScript
// arquivo: index.js

const express = require("express"); //importa o módulo express.js
const app     = express();  // função contida no módulo express.js

// --- 

app.listen(8087); 
// função para abrir o Servidor.
// localhost:8087
~~~

- Criando Rotas
~~~JavaScript
// arquivo: index.js

const express = require("express"); 
const app     = express();  

// caminho para Página Principal (index)
app.get("/",
    function(req,res){
        res.send("Ola Mundo");
    }
);

// caminho para página Contato
app.get("/contato",
    function(req,res){
        res.send("Página Contato");
    }
);

app.listen(8087,
    // função de Callback
    function(){
        console.log("Servidor em execução na url http://localhost:8087");
    }
); // localhost:8087
~~~

# Parâmetros

- Criando Rotas com Parâmetros

~~~JavaScript
// arquivo: index.js

const express = require("express"); 
const app     = express();  

// caminho para Página Principal (index)
app.get("/",function(req,res){ res.send("Ola Mundo"); });

// caminho para página Sobre com Parâmetro Nome
app.get("/contato/:nome/:sobrenome",
    function(req,res){
        res.send(req.params);
    }
);


// caminho para página Sobre com Parâmetro Nome
app.get("/contato/:nome/:sobrenome",
    function(req,res){
        res.send("<h1> Bem vindo "+ req.params.nome +" <h1>");
        // res.send("<h1> Bem vindo "+ req.params.nome +" <h1>");
        // Apenas 1 send pode ser enviado
    }
);


app.listen(8087, function(){ console.log("Servidor em execução na url http://localhost:8087"); }
); // localhost:8087
~~~

# Exibindo HTML

 ~~~JavaScript
// arquivo: index.js

const express = require("express"); 
const app     = express();  

// caminho para Página Principal (index) - Não é o usual
app.get("/",
            function(req,res){ 
                res.sendFile(__dirname + "/html/index.html");
                // __dirname: caminho absoluto para o arquivo
            }
);

app.get("/sobre",
            function(req,res){ 
                res.sendFile(__dirname + "/html/sobre.html");
            }
);

app.listen(8087, function(){ console.log("Servidor em execução na url http://localhost:8087"); }
); // localhost:8087
~~~ 

# Node.js (Sequelize) + MySQL
- Para acessar o MySQL via Promtp, adicionar o caminho da pasta MySQL\bin em variáveis de ambiente (PATH)
- `mysql -h localhost -u root -p`
  > -h: servidor    <br>
  > -u: usuário     <br>
  > -p: senha

## Conectando ao Bando

~~~JavaScript
// arquivo: conexao.js

const Sequelize = require('sequelize')
const sequelize = new Sequelize(
        'bd_teste', 
        'root', 
        'senha123',
        {
            host: "localhost",        
            dialect: "mysql"
        }
);


sequelize.authenticate().then(
        function(){console.log("Conectado com sucesso!")}
    ).catch(
        function(erro){
            console.log("Falha ao se conectar: "+ erro)
        }
    );

~~~

## Model : Referência para tabela no Bando de Dados

~~~JavaScript
// arquivo: conexao.js

const Sequelize = require('sequelize')
const sequelize = new Sequelize('bd_teste', 'root','senha123', {
            host: "localhost",        
            dialect: "mysql"
        });

// tabela: tb_postagens , objeto json: campos
const Postagem = sequelize.define('tb_postagens',{
    titulo:{
        type:Sequelize.STRING
    },
    conteudo{
        type: Sequelize.TEXT
    }
})

// tabela: tb_usuarios , objeto json: campos
const Usuario = sequelize.define('tb_usuarios',{
    nome: {
        type: Sequelize.STRING
    },
    sobrenome: {
        type: Sequelize.STRING
    },
    idade: {
        type: Sequelize.INTEGER
    },
    email: {
        type: Sequelize.STRING
    }
})

// recria a tabela se usar mais de uma vez
Postagem.sync({force: true})

/* 
Obs.: 
Sequelize cria automaticamente os campos:
  - ID
  - createdAt : data que criou
  - updatedAt : data da ultimá modificação
*/
~~~


## Inserir dados na tabela

~~~JavaScript
// arquivo: conexao.js

// inserindo dados da tabela: tb_postagens
Postagem.create({
    titulo: "Nome de um titulo para o campo titulo",
    conteudo: "Rosas sao vermelhas, boboletas são azuis.."
})

// inserindo dados da tabela: tb_usuarios
Usuario.create({
    nome: "Fulano",
    sobrenome: "Silva",
    idade: 20,
    email: "fulano@hotmail.com"
})
~~~

## Handlebars : Programação no HTML
- Criar caminho de pastas:  `views\ layouts\`
- Criar o arquivo: `main.handlebars`
- arquivo com estrutura HTML: `views\ layouts\ main.handlebars` 
- entre outros: `views\ layout\ formulario.handlebars`
  
~~~JavaScript
// arquivo: index.js

// express.js
const express = require("express");
const app = express();
// Handlebars
const handlebars = require('express-handlebars')
// conexão com o Banco de Dados
const Sequelize = require('sequelize')


// Config
    // Templete engine
    app.engine('handlebars', handlerbars({defaultLayout: 'main'}))
    app.set('view engine', 'handlebars')

    // Conexão com o bando de ados MySQL
    const sequelize = new Sequelize('bd_teste', 'root','senha123', {
            host: "localhost",        
            dialect: "mysql"
        });

    // Rotas
        app.get('/cad', function(req,res){
            //res.send('Rota de Cadastro de posts')
            res.render('formulario') // não usar a extenção .handlebars
        })

        app.post('/rotaAdd', function(req,res){
            res.send("Formulário enviado!")
        })


// --
app.listen(8087, function(){
    console.log("Servidor sendo executado na url http://localhost:8087")
});
~~~

~~~HTML
<!-- arquivo: main.handlebars -->
<html>
<head> 
    <title> Postagens </title>
</head>
<body>
    { { { body } } }
</body>
</html>
~~~

## Formulário: GET ou POST
- Rotas do tipo POST não são acessdas via URL
- Rotas do tipo GET podem são acessadas via URL
- 
~~~HTML
<!-- arquivo: formulario.handlebars -->
<form action="/rotaAdd" method="POST">
    <p> Título: </p>
    <input type="text" name="titulo">
    <p> Conteúdo </p>
    <textarea type="text" name="conteudo"></textarea>   

    <button type="submit"> Cadastrar Postagem </button>
</form>
~~~

## Body Parser

~~~JavaScript
// arquivo: index.js

// express.js
const express = require("express");
const app = express();
// Handlebars
const handlebars = require('express-handlebars')
// conexão com o Banco de Dados
const Sequelize = require('sequelize')
// body-parser
const = bodyParser = require('body-parser')


// Config

    // Templete engine
    app.engine('handlebars', handlerbars({defaultLayout: 'main'}))
    app.set('view engine', 'handlebars')

    // Conexão com o bando de ados MySQL
    const sequelize = new Sequelize('bd_teste', 'root','senha123', {
            host: "localhost",        
            dialect: "mysql"
        });
    
    // Body Parser
    app.use(bodyParser.urlencoded({extened: false}))
    app.use(bodyParser.json())



// Rotas

    app.post('/rotaAdd', function(req,res){
        // req.body.conteudo
        res.send("Texxto enviado: "+ req.body.titulo   +
                      " Conteúdo: "+ req.body.conteudo
                )
    })
   

// --
app.listen(8087, function(){
    console.log("Servidor sendo executado na url http://localhost:8087")
});
~~~




# Node.js + MongoDB
