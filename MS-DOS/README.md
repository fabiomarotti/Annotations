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
    - *DIR /ad* : Diretórios
    - *DIR /ah* : Arquivos Ocultos
    - *DIR /as* : Arquivos do Sistema
    - *DIR /al* : Pontos de nova análise
    - *DIR /ar* : Arquivos somente de Leitura
    - *DIR /aa* : Arquivos prontos para arquivamento
    - *DIR /ai* : Arquivos sem conteudo indexado
  - *DIR /b* : Lista apenas os Nomes
  - *DIR /c*
  - *DIR /d* : Lista por Colunas
  - *DIR /l*
  - *DIR /n*
  - `DIR /o`:
    - *DIR /on* : por nome (alfabética)
    - *DIR /oe* : por extensão (alfabética)
    - *DIR /og* : por grupo
    - *DIR /os* : por tamanho
    - *DIR /od* : por data/hora
  - DIR /p : Lista arquivos com PAUSE
  - DIR /q : Lista arquivos com seu Proprietário (PC\User)
  - DIR /r : 
  - DIR /s : Lista arquivos e seus SubDiretórios
- `DATE`
- `ECHO`
- `ELSE`
- `ENDLOCAL`
- `ERASE`
- `EXIT`
- `FOR`
- `FTYPE`
- `GOTO`
- `IF`
- `MD`
- `MKDIR`
- `MKLINK`
- `MOVE`
- `PATH`
- `PAUSE`
- `POPD`
- `PROMPT`
- `PUSHD`
- `RD`
- `REN`
- `RENAME`
- `REM`
- `RMDIR`
- `SET`
- `SETLOCAL`
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
