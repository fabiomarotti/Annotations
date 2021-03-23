# JavaScript
Repositório com os estudos realizados sobre a linguagem JavaScript.

# Adicionando o JavaScript ao HTML (3 formas)

## Inline (no elemento)

~~~HTML
// arquivo: index.html
<!DOCTYPE html>
<html lang="en-US">
<head>
    <meta charset="UTF-8">
</head>
<body>

<button type="button" onclick="alert('Ola Mundo!')" >   

</body>
</html>
~~~

## Interno (incorporado no arquivo HTML)
### Entre as tags HEAD ou BODY

~~~HTML
// arquivo: index.html
<!DOCTYPE html>
<html lang="en-US">
<head>
    <meta charset="UTF-8">

    <script>  
    // Código JavaScript aqui, ter precaução com o DOM!    
    // JavaScript será lido antes dos elementos do DOM estarem disponiveis.
    </script>

</head>
<body>

<script>  // Código JavaScript aqui!  </script>
</body>
</html>
~~~

## Externo (no arquivo JS)
~~~HTML
// arquivo: index.html
<!DOCTYPE html>
<html lang="en-US">
<head>
    <meta charset="UTF-8">

    <script type="text/javascript" src="script.js"></script>

</head>
<body>
</body>
</html>
~~~


## >> Considerações
- O ideal é ter o código JavaScript imediatamente antes da tag de fechamento do **body**
- Observar se as funções precisam que os elementos do DOM ja existam ou não (página totalmente carregada ou não).
- Para o pre-carregamento, usar o 
  - `window.load()`
  - `ready()` da API jQuery. [+ detalhes](https://api.jquery.com/ready/)


# Referências
