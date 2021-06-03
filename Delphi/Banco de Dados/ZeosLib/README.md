# Zeos Lib Access 
### Instalação
- [download](https://sourceforge.net/projects/zeoslib/)
- Criar um diretório proprio para as Livrarias do Delphi
- Descompactar arquivo
- Abrir projeto Delphi: `zeos__/packages/Delphi__/ZeosDbo`
- Project Manager: ZeosDbo / btn_direito / Build All 
- Project Manager: ZeosDbo / ZComponentDesign__.bpl / btn_direito / Install
- Library
  - v10.2 : `Tools / Options / Envirment Options / Delphi Options / Library` 
  - v10.3 : `Tools / Options / Language / Delphi / Library` 
    - `C:/pasta../src/Component`
    - `C:/pasta../src/Core`
    - `C:/pasta../src/dbc`
    - `C:/pasta../src/parsesql`
    - `C:/pasta../src/plain` 

### Componentes

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
  - Filter : exemplo: 
    - SQL :`cli_nome LIKE '%fulano%'`
    - ZEOS : `cli_nome LIKE '* fulano *'`
  - Filtered : True or False
 
# Configuração Zeos com SQL Server
### Pre-Configuração
- (Windows) Fonte de Dados ODBC (64bit) / DSN de Usuário / Add 
   - Nome: conexaoSQL
   - Descrição : conexao sql
   - Servidor: [nomePc\nomeInstancia] : FULANO-PC\SQLEXPRESS
### Configuração Zeos
- Protocol: `ado`
- HostName: `localhost`
- Port: `1433`
- User: `sa`
- Password: `senha`
- Database: `Provider=SQLOLEDB.1;Password='senha';Persist Security Info=True;User ID='SA';Initial Catalog='nome_banco_dados';Data Source='nomePC\SQLEXPRESS'; ` 
