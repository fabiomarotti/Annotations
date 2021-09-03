# Arquivos

- `arq: TextFile` : representará, por meio de uma varaivel, o nome lógico de um arquivo texto.
- `AssignFile(arq, nomeArquivo.txt)` : associa o nome lógico ao arquivo texto existente.
- `Rewrite(arq)` : Cria um novo arquivo, se ja existe, irá substituir; coloca um ponteiro de arquivo no inicio do arquivo 
- `Reset(arq)` : Prepara um arquivo existente para leitura, colocando o ponteiro de arquivo no início.
- `Append(arq)` : Abre o arquivo.
- `CloseFile(arq)` : Fecha o arquivo.
- `ReadLn(arq, sLinha)` : Le um linha do arquivo arq e atribui em sLinha
- `WriteLn(arq, lista_valores)` : Grava um ou mais valores. Marca final-delinha no final da lista
- `Write(arq, lista_valores)` : Grava um ou mais valores em sequência.
- `EoIn(arq)` : retorna Tur se for final de linha; (CR/LF)
- `Eof(arq)` : 
