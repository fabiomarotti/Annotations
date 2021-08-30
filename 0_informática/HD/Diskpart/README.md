# Diskpart

- `DISKPART`: logar
- `ACTIVE`      - Marcar a partição selecionada como ativa.
  - Apenas partições podem ser marcadas como ativas.
  - informa ao sistema básico de entrada / saída (BIOS) ou à interface de firmware extensível (EFI) que a partição ou volume é uma partição ou volume de sistema válido. 
- `ADD`         - Adiciona um espelho a um volume simples.
- `ASSIGN`      - Atribua uma letra de unidade ou um ponto de montagem ao volume selecionado.
  - `assign letter=c`
- `ATTRIBUTES`  - Manipular atributos de volume ou de disco.
  - `Attributes disk` 
    - `attributes disk set readonly` : Deixar um disco setado apenas par leitura
  - `Attributes volume` : Exibe os atributos atuais do volume
    - `attributes volume set hidden readonly` : Definir como Oculto e Somente leitura
    - `attributes volume clear hidden readonly` : Remover os atributos Ocultos e Somente leitura
- `ATTACH`      - Anexa um arquivo de disco virtual.
- `AUTOMOUNT`   - Habilitar ou desabilitar a montagem automática de volumes básicos.
- `BREAK`       - Quebrar um conjunto de espelhos.
- `CLEAN`       - Limpar as informações de configuração ou todas as informações do disco.
  - Use o comando select disk 
  - remover toda a formatação do disco selecionado 
- `COMPACT`     - Tentativas para reduzir o tamanho físico do arquivo.
- `CONVERT`     - Converter formatos de disco diferentes.
  - O disco deve estar vazio para ser convertido em um disco GPT
    - `convert gpt` : Converte para GPT
    - `convert mbr` : Converte para MBR    - 
- `CREATE`      - Criar um volume, partição ou disco virtual.
- `DELETE`      - Excluir um objeto.
- `DETAIL`      - Fornecer detalhes sobre um objeto.
- `DETACH`      - Desanexa um arquivo de disco virtual.
- `EXIT`        - Sair do DiskPart.
- `EXTEND`      - Estender um volume.
- `EXPAND`      - Expande o tamanho máximo disponível em um disco virtual.
- `FILESYSTEMS` - Exibir os sistemas de arquivos atuais e com suporte no volume.
- `FORMAT`      - Formatar o volume ou a partição.
  - [ver+](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc753770(v=ws.11))
- `GPT`         - Designar atributos à partição GPT selecionada.
- `HELP`        - Exibir uma lista de comandos.
- `IMPORT`      - Importar um grupo de discos.
- `INACTIVE`    - Marcar a partição selecionada como inativa.
- `LIST`        - Exibir uma lista de objetos.
- `MERGE`       - Mescla um disco filho com seus pais.
- `ONLINE`      - Colocar online um objeto marcado como offline.
- `OFFLINE`     - Colocar offline um objeto marcado como online.
- `RECOVER`     - Atualiza o estado de todos os discos do pacote selecionado. Tenta a recuperação em discos do pacote inválido e sincroniza novamente os volumes espelhados e os volumes RAID5 com plex ou dados de paridade obsoletos.
- `REM`         - Não faz nada. Usado para scripts de comentário.
- `REMOVE`      - Remover uma atribuição de letra de unidade ou de ponto de montagem.
- `REPAIR`      - Reparar um volume RAID-5 com um membro danificado.
- `RESCAN`      - Examinar novamente discos e volumes do computador.
- `RETAIN`      - Colocar uma partição retida em um volume simples.
- `SAN`         - Exibir ou definir a política SAN para o sistema operacional inicializado no momento.
- `SELECT`      - Deslocar o foco para um objeto.
- `SETID`       - Alterar o tipo de partição.
- `SHRINK`      - Reduzir o tamanho do volume selecionado.
- `UNIQUEID`    - Exibe ou define o identificador da GPT (Tabela de Partição GUID) ou a assinatura do MBR (Registro Mestre de Inicialização) de um disco.
  - `UNIQUEID DISK` : Exibir assinatura do disco MBR com foco
  - `UNIQUEID DISK ID=5fxxxx` : Definir assinatura do disco MBR ou GPT com foco para 5fxxxxx


### + usados
- `LIST`
  - `LIST DISK` : Listar Discos
  - `LIST PARTITION` : Listar Partição

- `SELECT`
  - `SELECT DISK x` : Selecionar Disco
  - `SELECT PARTITION x` : Selecionar Partição

- `DELETE PARTITON OVERRIDE`: Excluir Partição
- `ACTIVE` : Ativar partição selecionada
- `ASSIGN` : Atribuir letra de unidade ou ponto de montagem ao volume selecionado.


### Exemplos
~~~DOS
select disk 0
clean
convert gpt
create partition primary size=300
format quick fs=ntfs label="Windows RE tools"
assign letter="T"
~~~
- `CLEAN`
- `CRETE PARTITION PRIMARY`
- `SELECT PARTITION x`
- `ACTIVE`
- `FORMAT FS=NTFS QUICK`
- `ASSIGN`

 # Referência
 [link](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/cc730793(v=ws.11))
