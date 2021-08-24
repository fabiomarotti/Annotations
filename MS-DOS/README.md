# MS-DOS (Microsoft Disk Operation System)

Principais Extensões de arquivos
- `.com` - Arquivos executáveis (pequenos e rápidos).
- `.exe` - Arquivos executáveis (padrão, podendo conter códigos tanto para 16, 32 ou 64Bits).
- `.bat` - Arquivos de lote (normalmente possuem uma sequencia de comandos que são executados em Lote, um pós o outro e seu uso é bem amplo e funcional).
- `.txt` - Arquivos de texto (normalmente texto puro, legível pelo editor oficial do DOS, EDIT).


#### Os principais comandos do MS-DOS são:

- `dir` - Exibe a lista de arquivos (com informações como tamanho, data, hora).
- `md` - Cria uma nova pasta.
- `cd` - Entra em determinada pasta.
- `rd` - Exclui determinada pasta.
- `date` - Edita ou exibe a data do computador.
- `time` - Edita ou exibe a hora do computador.
- `mkdir` - Cria um diretório (pasta) novo. Ex. md pasta
- `chdir` - Muda de diretório (pasta). Ex. cd pasta
- `cls` - Limpa o conteúdo da tela.
- `echo` - Exibe um conteúdo texto na tela. EX. echo "conteudo"
- `help` - Exibe a relação completa dos comandos.
- `icacls` : Permissões e acesso
- `systeminfo` : Informações do PC
- `tasklist` : lista de procesor
- `where` busca nome de arquivos pelo pc
- `color`

---- 

- `ASSOC`
- `BREAK`
- `CALL`

- `CD` ou `CHDIR` (Change Directory)
  - cd %USERPROFILE%

- `CLS` (Clears Screen)

- `COLOR` : Altera cor do fundo e letra.

| Valor | Cor Fundo   | Valor |  Cor Letra    |    
|---    |---          | ---   |---            | 
| 0	    | Black       | a	    | Light green   | 
| 1	    | Blue        | b	    | Light aqua    | 
| 2	    | Green       | c	    | Light red     | 
| 3	    | Aqua        | d	    | Light purple  | 
| 4	    | Red         | e	    | Light yellow  | 
| 5	    | Purple      | f	    | Bright white  | 
| 6	    | Yellow      |       |               | 
| 7	    | White       |       |               | 
| 8	    | Gray        |       |               | 
| 9	    | Light blue  |       |               | 

- `COPY` : (origem) (destino)

- `DEL` (Delete)

- `DIR` (List Directory)
  - `DIR /a`:
    - `DIR /ad` : Diretórios
    - `DIR /ah` : Arquivos Ocultos
    - `DIR /as` : Arquivos do Sistema
    - `DIR /al` : Pontos de nova análise
    - `DIR /ar` : Arquivos somente de Leitura
    - `DIR /aa` : Arquivos prontos para arquivamento
    - `DIR /ai` : Arquivos sem conteudo indexado
  - `DIR /o`: (Ordenado)
    - `DIR /on` : por nome (alfabética)
    - `DIR /oe` : por extensão (alfabética)
    - `DIR /og` : por grupo
    - `DIR /os` : por tamanho
    - `DIR /od` : por data/hora
  - `DIR /b` : Lista apenas os Nomes
  - `DIR /c`
  - `DIR /d` : Lista por Colunas
  - `DIR /l`
  - `DIR /n`
  - `DIR /p` : Lista arquivos com PAUSE
  - `DIR /q` : Lista arquivos com seu Proprietário (PC\User)
  - `DIR /r` : 
  - `DIR /s` : Lista arquivos e seus SubDiretórios

- `DATE` Exibir e Alterar data [apenas Enter não antera a data]
  - `DATE /t` Exibir data
  - `echo %DATE%"` Exibe data

- `ECHO` Exibe se a configuração do ECHO está ativado ou desativado.
  - `ECHO ON` (Ativado) exibe o formato : `PROMPT $p$g`
  - `ECHO OFF` (Desativado) : não exibe nenum formato de Prompt
  - `ECHO.` Linha vazia
  - `@ECHO OFF` : Evitar todos os comandos de um arquivo de Lote sejam exibidos.

- `IF` e `ELSE` (Se.. Senão)
- `exist` : arquivo existe
- `==` : palavras são iguais
- `equ` (equals) : expressões iguais
- `neq` (not equal) : expressões diferentes
- `lss` (less than) : Menor que
- `leq` (less than or equal) : Menor ou igual que
- `gtr` (greater than) : Maior que
- `geq` (greater than or equal) : Maior ou igual que
- `defined` : variavel definida
  -  %errorlevel% 
  -  %cmdcmdline% 
  -  %cmdextversion%
- `errorlevel` : número
- `cmdextversion` : número

> Exemplo
~~~
IF NOT EXIST %targetpath% (
  ECHO Caminho não encontrado.
  EXIST /b
)
~~~

> Exemplo
~~~
IF EXIST file.txt (
    ECHO  Arquivo existe.
) ELSE (
    ECHO  Arquivo não existe.
)
~~~

- `ENDLOCAL`
- `SETLOCAL`
- `ERASE`

- `EXIT` : Saí do cmd.exe
  - `EXIT /b` : Saí do arquivo de lote ao inves do cmd.exe 

- `FOR`
  - `%i` : para prompt
  - `%%i` : para arquivos de lote
> Percorre o conjunto (1,2,3) e exibe seus elementos (apenas números)
~~~
FOR  %i  IN  (1,2,3)   DO   @ECHO %i  
~~~

> Exibe todos arquivos no formato _*.txt_
~~~
FOR  %i  IN  (*.txt)   DO   @ECHO %i
~~~

> Exibe todos arquivos _*.exe_ do diretorio
~~~
FOR   %i  IN ("C:\Windows\system32\*.exe")    DO    @ECHO %i
~~~

> Exibe arquivo e seu caminho
~~~
FOR /r %i   IN (*.txt)   DO    @ECHO  %i
~~~

> Exibe números de 1 a 10
~~~
FOR /l %i   IN (1,1,10)   DO   @ECHO  %i
~~~

> Exibe o conteúdo de um arquivo
~~~
FOR /f "tokens=*" %i  IN (file.txt)   DO    @ECHO %i
~~~

> pensar
~~~
FOR /f "tokens=1-3* delims=:" %a  IN ("First:Second::Third:Fourth:Fifth")   DO    @ECHO   %c-%b-%a: %d
~~~ 

> pensar 2
~~~
FOR /f "tokens=1-3" %a  IN ("First Second Third,item")  DO    @ECHO %c-%b-%a
~~~


- `FTYPE`
- `GOTO` : (Vai para um rótulo)
  - `:rotulo` 

> Exemplo de GOTO e rotulos
~~~
GOTO :rotulo_1
ECHO Ola Mundo!
REM #Ola Mundo nunca sera exibido.

:rotulo_1
ECHO Ola Planeta!
GOTO :eof

ECHO Ola Universo!
REM Ola Universo nunca sera exibido.
REM Eof é um rotulo virtual padrão para ir direto ao fim do arquivo.
~~~

- `MD` ou `MKDIR` (Make Directory) : Construir Diretório
  - `MD dir1`
  - `MD dir1 dir2`
  - `MD "Meu Diretório"`

- `MKLINK` ?

- `MOVE` : Move Arquivos ou Diretórios, ou tambe pode renomea-los
  - `MOVE X:file1.txt` : Move para o diretório atual
  - `MOVE file1.txt file2.txt`  : Renomea arquivos
  - `MOVE Dir1 Dir2`  : (Caso Dir2 não existe) Renomeia diretórios 
  - `MOVE file1.txt Dir1`  : (Caso Dir1 e Dir2 ja existam) Move para o Diretório
  
- `PATH`

- `PAUSE`
  - `Ctrl`+`C` : Parar uma arquivo de lote.

- `POPD`

- `PROMPT` : Alterar exibição do prompt ou `PROMPT $p$g`
  - `PROMPT Fabio$G` : Fabio>

- `PUSHD`

- `RD` (Remove Directory)


- `REN` ou `RENAME` : Renomear Arquivos ou Diretórios


- `REM` (Remarks) : Cria *Observações* no arquivo de lote
> Exemplo
~~~
@ECHO OFF
REM   Um comentário, comando que não sera executado
ECHO  Bom Dia     REM Apesar de ser uma comentário, ele será exibido
ECHO  Boa Noite & REM Será comentado por causa do operador &
:: Está sentença tambem será um comentário.

PAUSE
~~~


- `RMDIR`
- `SET`

- `SHIFT`
- `START`
- `TIME`
- `TITLE`
- `TYPE`
- `VER`
- `VERIFY`
- `VOL`
- `External commands`
- `ARP`
- `AT`
- `ATTRIB`
- `BCDEDIT`
- `CACLS`
- `CHCP`
- `CHKDSK`
- `CHKNTFS`
- `CHOICE`
- `CIPHER`
- `CLIP`
- `CMD`
- `COMP`
- `COMPACT`
- `CONVERT`
- `DEBUG`
- `DISKCOMP`
- `DISKCOPY`
- `DISKPART`
- `DOSKEY`
- `DRIVERQUERY`
- `EXPAND`
- `FC`
- `FIND`
- `FINDSTR`
- `FORFILES`
- `FORMAT`
- `FSUTIL`
- `GPRESULT`
- `GRAFTABL`
- `HELP`
- `ICACLS`
- `IPCONFIG`
- `LABEL`
- `MAKECAB`
- `MODE`
- `MORE`
- `NET`
- `OPENFILES`
- `PING`
- `RECOVER`
- `REG`
- `REPLACE`
- `ROBOCOPY`
- `RUNDLL32`
- `SC`
- `SCHTASKS`
- `SETX`
- `SHUTDOWN`
- `SORT`
- `SUBST`
- `SYSTEMINFO`
- `TASKKILL`
- `TASKLIST`
- `TIMEOUT`
- `TREE`
- `WHERE`
- `WMIC`




---- 

Comunicação paralela
As comunicações paralelas podem ser testadas no dos usando-se comandos com desvio direto para a porta paralela: DIR >LPT1123

Após o comando acima se você possui uma impressora na porta LPT1 a mesma deverá imprimir o conteúdo do diretório atual.

#### Default
- `PROMPT $p$g`
- `TITLE %comspec%`
- `COLOR`

[referencia wiki](https://en.wikibooks.org/wiki/Windows_Batch_Scripting)
