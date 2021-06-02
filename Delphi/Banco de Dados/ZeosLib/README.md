# Zeos Lib Access 

[download](https://sourceforge.net/projects/zeoslib/)

# Componentes

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
  - 
 
