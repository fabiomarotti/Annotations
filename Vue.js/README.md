# Vue.js
Repositório com os estudos realizados sobre o framework Vue.js

- https://vuejs.org/
- https://cli.vuejs.org/
- Framework Reativo
- Framerowk SPA (Single Page Applications)
- Plugin para VS Code: Vetur (Pine Wu)


> Requesitos: Node.js -> npm (Node Package Manager)

`$ node -v` versão do Node.js

`$ npm -v` versão do Gerenciados de Pacotes

`$ vue -v` versão do Vue.js

`$ vue --help` ajuda do Vue.js

# Instalando Vue.js

`$ npm install -g @vue/cli` via Prompt

* Pre-configuração no PowerShell: <br> 
 `Set-ExecutionPolicy RemoteSigned` : (A)

# Criar um workspace "pasta do projeto"
`$ mkdir nome_pasta` : criar pasta

`$ vue create nome_projeto` : criar projeto

# Iniciar o Servidor de Desenvolvimento

`$ npm run serve`

Hot Reload : não precisa atulizar a página toda hora.

# Estrutura das pastas

- `/` : raiz (nome_projeto)
- `/node_modules` : Módulos do Node.js
- **babel.config.js** : biblioteca que deixar atualizado a versão do JavaScript (ES11)
 
<br>

- `/public` : **index.html** e **favicon.ico** : arquivo de injeção de códigos do Vue.js <br> (por ser um framework SPA contem apenas uma página)

- `/src`

  - **main.js** : Arquivo que se instala bibliotecas adicionais, cria instâncias
  - **App.vue** : Componente Raiz. <br> Arquivo principal ao qual se injeta códigos no **index.html**
  - `/src/assets` : conter arquivos estátivos, videos, imagens, ...
  - `/src/components` : local recomendado para criar os novos componentes Vue.js

<br>

## Estrutura do arquivo: **App.vue**
- HTML       : < template >
- CSS        : < style >
- JavaScript : < script > 

## Criando um componentes __.vue
- estar contido em : `/src/components/`
- criar o arquivo: **__.vue**
- **__.vue** conterá essa estrutura:
  - HTML          <br>
  - CSS           <br>
  - JavaScript

<br>

### Exemplo: Componente Usuario

> arquivo: Usuario.vue

~~~HTML
// arquivo: Usuario.vue

// ----------------- HTML : Usuario
<template>
<!-- só existe uma Tag para o componente: Usuario -->
<!-- Tag: div contorna essa situação              -->
    <div>
        <h2> Usuario X </h2>  
    </div>
</template>


// ----------------- JavaScript : Usuario
<script>
    // torna o componente exportavel
    export default {       
    }
</script>


// -----------------  CSS : Usuario
<style scoped>
/* Scoped: Style pertence apenas ao componente Usuario*/

</style>
~~~

> App.vue

~~~HTML
// arquivo: App.vue

// -------------------  HTML : App.vue
<template>
    <div id="app">
        <!-- Componente: Usuario -->
        <Usuario/>
    </div>
</template>

// ------------------- Java Script : App.vue
<script>  
    // importar o componente: Usuario
    import Cliente from './components/Cliente'

    // adicionar sua exportação
    export default {
        name:   'App',
                components: {
                    Cliente
                }
    }
</script>

// ------------------- CSS : App.vue
<style>
#app { 
    font-family: Avenir;
}
</style>
~~~
