# Banco de Dados:
### `FireDac`

### `DBExpress` 
- `TSQLConnection` 
- `TSQLDataSet`
  - CommandText : Linha de comando SQL
  - CommandType : ?

- `TClientDataSet`
- `DataAccess` ?
- [ver +](https://www.youtube.com/watch?v=rrxT3P7MTBQ)

### `Zeos Access` multidirecional
- `TZConection` (zConexao)
  - HostName: localhost
  - User: root
  - Password: -
  - Port: 3306 (padrão)
  - Protocol: mysql-5 (banco usado)
  - Database: bd_nomeBanco
  - Connected: True
 
 - `TZTable` (ztbPessoa)
  - Connection: `TZConnection`
  - TableName:  vincula a tabela no banco de dados ao componente (qnd BD estiver ativo)
  - Active: True
  - Add All Fields 
  - DisplayLabel : Nome a ser exibido para o usuário
  - Alignment : taCenter
  - Required : Campo obrigatorio (puxa direto do banco de dados)
  - ReadOnly : Apenas Ler e nao alterar os dados
  - EditMask : Mascara para os dados tipo Data
  - DisplayFormat : Mascara para Números
 
 > OBS.: 
  - carrega a tabela inteira na memoria. Pode acabar travando se haver muitos registros.
  - Centraliza a formatação da exibição dos dados para futuras chamadas multiplas nos formularios.
