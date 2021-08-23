# Arquivos .BAT (Batch) : Arquivos de Lote
- Um arquivo.bat é um código Script executado pelo utilitário do Windows built-in, chamado Windows Command-Line Interpreter (CLI).
- Escrever e executar comandos DOS.
- Execução sequencial por meio do *cmd.exe*
- *.exe* faz com que o Windows coloca o código executável em Memória , em seguida, executa o programa
- Em contrapartida, os arquivo *.exe* são códigos binários armazenados no formato Portable Executable (PE), que inclui vários cabeçalhos e seções
- Salvar como: `"Arquivo.bat"`
- Encoding : ANSI

# Comandos

#### Comentários
- `REM` : comentário em uma linha ( comando é lido e depois ingnorado) (usar OFF)
- `/* comentario */` : comentário em varias linhas (não precisa usar OFF)
- `::` : comentário em uma linha (são ignorados todo o caminho) (não precisa usar OFF) (usar *&* caso prosida de um comando)

- `MSG * oi` : Menssage Box (Titulo: Usuário, Data e hora)
- `SHUTDOWN -r -t 15 -c "Mensagem teste"`

#### Saida na tela
- `ECHO` :  exibe comandos ou resultados na tela
- `ECHO OFF` : desliga as mensagens nativas do prompt
- `ECHO ON` : mostra informações e mensagens nativas do prompt, habilita a exibição das instruções no prompt do Windows
- `ECHO.` : é utilizado para pular uma linha
- `@ECHO` : Faz com que o prompt fique oculto durante toda execução

#### Variáveis
- `SET`  : Exibe todas as variáveis de ambiente
- `SET x` : Exibe todas as variáveis iniciadas com a letra _x
- `SET /A` (Arithmetic) : (nome_variavel)=(expressão aritmetica)
- `SET /P` (Prompt)     : (nome_variavel)=(cadeia do prompt)
- Aceso a variável:  `%nome_variavel%` 

| Operador              | Descrição                |
|---                    |---                       |
|   `(` `)`             | agrupamento              |
|    `!` `~` `-`        | operadores unários       |
|   `+` `-` `*` `/` `%` | operadores aritméticos   |
|    `<<` `>>`          | alternância lógica       |
|    `&`                | bit a bit E              |
|    `^`                | bit a bit exclusivo OU   |
|     pipe /             | bit a bit OU            |
| `=`  `*=` `/=` `%=` `+=` `-=`  `&`= `^=` `|=` `<<=` `>>=`   | atribuição |
|  `,`                  | separador de expressões   |

- `REM` : Adiciona comentário no script, o texto inserido após a instrução REM não é exibido na tela.
- `CLS` : (Clear Screen) : Limpar tela

- `IF` e `ELSE` : Estrutura condicional
- `FOR` : Loops
- `GOTO`  :direcionar a execução do script para diferentes pontos do código.
  - `:` utilizada como pondo destino do goto

- `PAUSE` : "Pressione qualquer tecla para continuar"
- `PAUSE > NUL` : Não exibe  mensagem na tela

- `START` : Inicializar um certo programa ja instalado no computador
  - `/min`
  - `/max`
- `MOVE` : Move (recorta) um arquivo de um diretório para outro.
- `DEL`  : Excluir um ou mais arquivos de uma determianda parta

> Arquivo .bat para ativar modo admnistrador do windows
~~~
@echo off
cls
echo.
echo.
echo Digite o numero da opcao desejada
echo.
echo [1] Ativar o usuario Adminsitrador
acho [2] Desativar o usario adminsitrador
echo [3] Sair sem fazer nada

set /p opcao=Digite a opcao desejada:

if "%opcao%" == "1" goto op1
if "%opcao%" == "2" goto op2
if "%opcao%" == "3" goto op3

:op1 
net  user administrador /active:yes > nul
echo executada op1
goto fim

:op2
net user administrador /active:no > nul
echo executada op2
goto fim

:op3
exit

:fim
echo.
echo Operação executada com sucesso!
echo.
echo Pressione qualquer tecla para encerrar...
pause > nul

~~~


> variavel opcao   
~~~
set /p opcao=Digite a opcao desejada:
~~~

> Exemplo Echo off
~~~
@echo off
calc
pause
~~~ 


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
~~~
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
~~~
@echo off
start notepad.exe
rem Inicializa o Notepad do Windows
~~~

> Exemplo MOVE
~~~
@echo off
move c:\temp\teste.bat c:\temp\teste\
rem Movimenta o arquivo c:\temp\teste.bat para c:\temp\teste
~~~ 

## Variaveis do sistema
- %username% - nome da conta do usuário logado
- %userprofile% - pasta do perfil do usuário
- %temp% - pasta temporária
- %windir% - pasta de instalação do Windows
- %systemroot% - pasta raiz do sistema
- %time% - hora do sistema
- %date% - data do sistema
- %homedrive% - letra do drive com o diretório de usuários
- %userdomain% - nome do domínio
- %systemdrive% - letra do drive onde o sistema está instalado
- %cd% - retorna o caminho do .bat

- [link 1](https://www.youtube.com/watch?v=srP7Y3OGjtU&t=98s)
- [link 2](http://hardware.rbtech.info/programando-arquivos-bat/)
- [pdf MS-DOS Batch File](https://pdf4pro.com/view/batch-file-programming-4d5959.html)
- [referencia completa](https://en.wikibooks.org/wiki/Windows_Batch_Scripting)
