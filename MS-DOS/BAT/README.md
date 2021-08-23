# .BAT (Batch: Lote)

- Salvar como: " Arquivo`.bat` "
- Encoding : ANSI

## Comandos

- `Echo` :  exibe comandos ou resultados na tela
- `Echo off` : desliga as mensagens nativas do prompt, desabilitar a exibição dos comandos no prompt do Windows de todas as instruções presentes no arquivo
- `Echo on` : mostra informações e mensagens nativas do prompt, habilita a exibição das instruções no prompt do Windows
- `Echo.` : é utilizado para pular uma linha
- `@Echo` : Faz com que o prompt fique oculto durante toda execução

- `Set`  : Cria variveis e atribui valores, sua referencia é por meio de `%` nome_variavel `%` 
- `REM` : Adiciona comentário no script, o texto inserido após a instrução REM não é exibido na tela.
- `CLS` : (Clear Screen) : Limpar tela

- `IF` e `ELSE` : Estrutura condicional
- `FOR` : Loops
- `GOTO`  :direcionar a execução do script para diferentes pontos do código.

- `PAUSE` : "Pressione qualquer tecla para continuar"

- `START` : Inicializar um certo programa ja instalado no computador
- `MOVE` : Move (recorta) um arquivo de um diretório para outro.
- `DEL`  : Excluir um ou mais arquivos de uma determianda parta
- 


> 
~~~MSDOS
@echo off
echo Uso do comando set para criar variaveis.
SET numero=2
echo O valor da variavel numero e %numero%.
/* Resultado na tela:
Uso do comando set para criar variaveis.
O valor da variavel numero e 2.
*/
~~~

> Exemplo goto
~~~MSDOS
@echo off
set /p numero=Digite o numero 1 ou outro valor:
if %numero% == 1 (goto :opcao1) else (goto :opcao2)
:opcao1
echo Voce digitou 1
goto :fim
:opcao2
echo Voce digitou %numero%
:fim
~~~

> Exemplo REM
~~~~MSDOS
@echo off
start notepad.exe
rem Inicializa o Notepad do Windows
~~~

> Exemplo MOVE
~~~MSDOS
@echo off
move c:\temp\teste.bat c:\temp\teste\
rem Movimenta o arquivo c:\temp\teste.bat para c:\temp\teste
~~~ 

[link](https://www.youtube.com/watch?v=srP7Y3OGjtU&t=98s)
