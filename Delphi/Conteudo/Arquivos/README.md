# Arquivos

### Comandos
- `File` : 
- `arq: TextFile` : _variavel de arquivo_ que representará o nome lógico de um _arquivo texto_.
- `AssignFile(arq, caminho_nomeArquivo.txt)` : associa a _variavel de arquivo_ ao _arquivo texto_ existente.
- `ReWrite(arq)` : Cria um _novo arquivo_ no caminho informado em _AssignFile_, se ja existe, irá substitui-lo;
- `Append(arq)` : _Abre um arquivo_ já existente.
- `Reset(arq)` : _Prepara um arquivo existente para leitura_, colocando o ponteiro de arquivo no início. Gera erro se o arquivo não existir.
  - `{$I-}` e ` {$I+}` , `IOResult <> 0`
- `CloseFile(arq)` : _Fecha o arquivo_.
- `ReadLn(arq, sLinha)` : Le um linha do arquivo arq e atribui em sLinha
- `WriteLn(arq, lista_valores)` : _Grava_ um ou mais valores e pula linha.
- `Write(arq, lista_valores)` : _Grava_ um ou mais valores em sequência.

- `EoIn(arq)` : retorna True se for _final de linha_; (CR/LF)
- `EoF(arq)` : retorna True se for _final de arquivo_


### Extras
- `OpenDialog` : Caminho do arquivo
  - _Title_ : Titulo da janela de busca do arquivo
  -  _Filter_  : Arquivos de Texto (*.txt) 
  - _DefaultExt_ : txt
