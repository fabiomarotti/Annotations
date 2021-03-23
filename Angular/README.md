# AngularJS
Repositório com os estudos realizados sobre o framework Angular.

- https://www.youtube.com/c/EscolaFrontend/playlists
- https://angular.io/
- https://cli.angular.io/
- Angular Schematics (plugin para VS code)

> Requesitos: Node.js -> npm (Node Package Manager)

`$ node -v` versão do Node.js 

`$ npm -v` versão do Gerenciados de Pacotes

`$ ng -v` versão do Angular

`$ ng help` ajuda do Angular

## Instalar Angular CLI :: Command-Lin Interface

`$ npm install -g @angular/cli`  (-g: Instalação de modo Global)

## Criar um workspace "pasta do projeto" :: [+ detalhes](https://angular.io/guide/strict-mode)

`$ ng new nome_projeto`  gera um skeleton (esqueto de pastas/conteudo) -> Angular router -> CSS

`$ cd nome_projeto`    acessar pasta para executar os proximos comandos

## Abrir/iniciar o servidor :: http://localhost:4200/

`$ ng serve --open`  [+ detalhes](https://angular.io/cli/serve )

`$ ng serve -o` comando abreviado

## Estrutura das pastas
- `/` : raiz (nome_projeto)
- `/e2e` : fazer testes unitários
- `/node_modules` : todos os pacotes necessários para tralhar ou instalar posteriormente <br>
(pasta a ser contida no arquivo: **gitignore** -> pasta muito grande)
- `/src` : Pasta Principal
    **main.ts**
    **polyfills.ts** : traduzida no transpilar
    **style.css** : reflete na aplicação toda
    **test.ts** : parametros de teste (arquivos de teste)
- `/src/app` : todos os aquivos/componentes da aplicação
    - **app-routing.module.ts** : definir as rotas dos componentes
    - **app.module.ts** : registro de todos os componentes
    - ***app.component.ts*** Componente Principal (Classe)
    - ***app.component.html*** Componente Principal (HTML)
    - ***app.component.css*** Componente Principal (CSS)
    - ***app.component.spec.ts*** Componente Principal (seila XD)
- `src/assets` : todos os arquivos externos (img, css, ..)
- `src/environments` : gerando **build**, variaveis de ambiente, app em produção,..
- **angular.json** : todas as configurações do angular
- **karma.cong.js** : configurar ara teste unitário
- **package.json** : lista todos os pacotes e versões contidos na aplicação.
- **tsconfig.json** : qual a versão do ECMAScript.

Um componente X é composto por três arquivos:
- **x.html**
- **x.css**
- **x.spec.ts**
 
O componente principal chama: `app.component`, composto por:
- **app.component.html**
- **app.component.css**
- **app.component.spec.ts**


# Sintaxe

# Criando um Commponent via CLI
* 
## Generate [+ detalhes](https://angular.io/cli/generate)

* Component
* Service
* Module
* _outros_

`$ ng generate nome_componente`

`$ ng g nome_componente` abreviado


