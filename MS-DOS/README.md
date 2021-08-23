# MS-DOS (Microsoft Disk Operation System)

Principais Extensões de arquivos
- `.com` - Arquivos executáveis (pequenos e rápidos).
- `.exe` - Arquivos executáveis (padrão, podendo conter códigos tanto para 16, 32 ou 64Bits).
- `.bat` - Arquivos de lote (normalmente possuem uma sequencia de comandos que são executados em Lote, um pós o outro e seu uso é bem amplo e funcional).
- `.txt` - Arquivos de texto (normalmente texto puro, legível pelo editor oficial do DOS, EDIT).

Os principais comandos do DOS são:
- `dir - Exibe a lista de arquivos (com informações como tamanho, data, hora).
- `md - Cria uma nova pasta.
- `cd - Entra em determinada pasta.
- `rd - Exclui determinada pasta.
- `date - Edita ou exibe a data do computador.
- `time - Edita ou exibe a hora do computador.
- `mkdir - Cria um diretório (pasta) novo. Ex. md pasta
- `chdir - Muda de diretório (pasta). Ex. cd pasta
- `cls - Limpa o conteúdo da tela.
- `echo - Exibe um conteúdo texto na tela. EX. echo "conteudo"
- `help - Exibe a relação completa dos comandos.


Comunicação paralela
As comunicações paralelas podem ser testadas no dos usando-se comandos com desvio direto para a porta paralela: DIR >LPT1123

Após o comando acima se você possui uma impressora na porta LPT1 a mesma deverá imprimir o conteúdo do diretório atual.
