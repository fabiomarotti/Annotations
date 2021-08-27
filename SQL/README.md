# SQL - Structured Query Language

- 1986 padrão ANSI
- 1987 padrão ISO

- Sistemas
  - MySQL
  - SQL Server (T-SQL)
  - Oracle (PL/SQL)
  - Access (JET SQL)
  - PostgreSQL
  - Sybase
  - DB2

- Visões, Stored Procedures e Funções

# Grupos de Comandos

- `DDL` **(Data Definition Language)** - Linguagem de Definição de Dados
  -  comandos que interagem com os objetos do banco de dados.
  - `CREATE`
  - `ALTER`
  - `DROP`

- `DML` **(Data Manipulation Language)** - Linguagem de Manipulação de Dados
  - comandos que interagem com os dados dentro das tabelas.
  - `INSERT`
  - `UPDATE`
  - `DELETE`

- `DQL` **(Data Query Language)** - Linguagem de Consulta de Dados
  - comandos de consulta. (alguns autores sitam como DML)
  - `SELECT`

- `DCL` **(Data Control Language)** - Linguagem de Controle de Dados
  - comandos para controlar a parte de segurança do banco de dados (permissões)
  - `GRANT` : permissão
  - `REVOKE` : retira permissao
  - `DENY`

- `DTL` **(Data Transaction Language)** - Linguagem de Transação de Dados
  - comandos para o controle de transação
  - `BEGIN TRANSACTION` 
  - `COMMIT` 
  - `ROLLBACK`

# Convenções
- Nome da Tabela: `tb_nome`
- Nome de Campos: `campo_tabela` 
- Nome da Tabela com Entidade Mapeada: `tb_nomes` (no Plural)
- Nome da Tabela do tipo Muito-Muitos: `tb_nome` (no Singular)
- Nome de tabela derivada de outras: `tb_nomeA_nomeB` (no Singular) de `tb_nomeAs` e `tb_nomeBs` (no Plural)


# Referência
- [w3schools - SQL](https://www.w3schools.com/sql/sql_view.asp)

