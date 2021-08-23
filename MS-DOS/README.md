# MS-DOS (Microsoft Disk Operation System)

Principais Extensões de arquivos
- `.com` - Arquivos executáveis (pequenos e rápidos).
- `.exe` - Arquivos executáveis (padrão, podendo conter códigos tanto para 16, 32 ou 64Bits).
- `.bat` - Arquivos de lote (normalmente possuem uma sequencia de comandos que são executados em Lote, um pós o outro e seu uso é bem amplo e funcional).
- `.txt` - Arquivos de texto (normalmente texto puro, legível pelo editor oficial do DOS, EDIT).


#### Os principais comandos do DOS são:

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

- `Overview`
- `ASSOC`
- `BREAK`
- `CALL`
- `CD`
- `CHDIR`
- `CLS`
- `COLOR`
- `COPY`
- `DEL`
- `DIR`
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
