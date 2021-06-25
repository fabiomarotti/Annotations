# SQL Server
- Dialeto: T-SQL
- Super Usuario: `sa`
- Porta Padrão : `1433`
- Valores Float: 123.456
- Colunas = Campos

### Downloads
- [Download SSEI - SQL 2019 Express](https://go.microsoft.com/fwlink/?linkid=866658)
- [Download SSMS - SQL Server Management Studio 18.9.1](https://docs.microsoft.com/pt-br/sql/ssms/download-sql-server-management-studio-ssms?redirectedfrom=MSDN&view=sql-server-ver15)

### Pre-Configurações
- **Configuração da Instância** : .\SQLSPRESS, \SQLTrabalho
- **Configuração do Servidor** : SQL Server Browser : Automático e Agrupamento: Latin1_General_CI_AS
- **Configuração do Mecanismo de Banco de Dados** : Modo Misto: usuario master : **sa** e inserir senha
- **SQL Management Studio**:
  - Nome do servidor: nomePC\Instancia
  - Autenticação do SQL Server: sa e senha

### Comandos uteis
- `sp_helpdb nome_banco` informações sobre o Banco de Dados, Tamanho, Quem criou, localização, ...

### Informações
> Comentários:
~~~SQL
-- Comentário em uma linha 
~~~

~~~SQL
/* Comentário em multiplas linhas */
~~~

> Tipo de Dados:
- `NULL`
- `int`
- `varchar`

> Backups:
- `Restore Database` / `Device` / `arquivo_bkp.BAK` 

# Tabelas Temporárias
- `#` Visibilidade Local
- `##` Visbilidade Global

[continuar](https://www.youtube.com/watch?v=_gEeh3lPhl0&list=PLsI_Jctnji3XawyHvU2WUBzBvUKAcs9Mg&index=3)


# Comandos para Banco de Dados

> Criar Banco de Dados:
~~~SQL
CREATE DATABASE db_nome_banco
~~~ 

> Acessar o BD para uso:
~~~SQL
USE db_nome_banco
~~~

> Criar BD com Detalhes e Limitações:
> - `db_nome_banco.mdf` Banco de Dados <br>
> - `db_nome_banco.ldf` Log do Bando de Dados <br>
> - Criar a pasta antes de executar o comando

~~~SQL
CREATE DATABASE nome_banco
  ON ( NAME       = nome_banco, 
       FILENAME   ='c:\SQL\nome_banco.mdf',
       SIZE       = 5,
       MAXSIZE    = 20,
       FILEGROWTH = 5)
LOG ON
  ( NAME       = nome_banco,               // Nome do arquivo
    FILENAME   = 'C:\SQL\nome_banco.ldf',  // Local de criação
    SIZE       = 10,       // Tamanho Inicial MB
    MAXSIZE    = 50,       // Tamanho final MB
    FILEGROWTH = 10 )      // Crescimento de 10%
~~~

> Excluir BD:
~~~SQL
DROP DATABASE db_nome_banco
~~~


# Comandos para Tabelas

- `IDENTITY` enumerar automaticamente
  - `IDENTITY (1,1)` começar em 1 e incrementar em 1  
- `CONSTRAINT` criar
- `UNIQ` registro na tabela tem que ser unico
- `DEFAULT` inserir um valor padrão caso o usuario nao tenha inserido o dado 

### CREATE
~~~SQL
CREATE TABLE tb_nome_tabela (
       campo_1  INT NOT NUL, 
       campo_2  VARCHAR(50)
       CONSTRAINT pk_campo_1 PRIMARY KEY (campo_1)
       );
~~~

- Constraint: Cria-se automaticamente
- Identity: Enumera campo_1 automaticamente
~~~SQL
CREATE TABLE tb_nome_tabela (
       campo_1  INT    NOT NUL   PRIMARY KEY   IDENTITY, 
       campo_2  VARCHAR(50)
       );
~~~

### ALTER
~~~SQL
ALTER TABLE tb_nome_tabela ADD campo_x VARCHAR(20) NOT NULL;
~~~

~~~SQL
ALTER TABLE tb_nome_tabela ALTER COLUMN campo_x VARCHAR(21);
~~~

~~~SQL
ALTER TABLE tb_nome_tabela DROP COLUMN campo_x;
~~~

~~~SQL
ALTER TABLE tb_nome_tabela ADD CONSTRAINT pk_campo_pk PRIMARY KEY (campo_pk);
~~~

~~~SQL
ALTER TABLE tb_nome_tabela_com_pk 
      ADD CONSTRAINT fk_campo_fk FOREIGN KEY (campo_fk)
      REFERENCES tabela_fk (campo_fk_tabela_fk) ON DELETE CASCADE;
~~~


### INSERT
~~~SQL
INSERT INTO nome_tabela (campo_1, campo_2, .., campo_n) VALUES (valor_1, valor_2, ..., valor_n);
~~~

~~~SQL
INSERT INTO tb_nome_tabela (campo_A1, campo_A2, .., campo_An) 
       VALUES (valor_A1, valor_A2, ... , valor_An),
              (valor_B1, valor_B2, ... , valor_Bn),
              (valor_C1, valor_C2, ... , valor_Cn);
~~~
 
### DELETE
~~~SQL
DELETE tb_nome_tabela WHERE campo=valor;
~~~

- Apaga todos os registros da tabela
~~~SQL
DELETE tb_nome_tabela;
~~~

### UPDATE
~~~SQL
UPDATE tb_nome_tabela SET   campo_1 = valor_1 , ... , campo_n = valor_n   WHERE   campo_x = valor_x;
~~~


### SELECT
> `DISTINCT` : filtra, não retornando os dados duplicados (linhas repetidas) da Coluna de uma Tabela.
- Mostrar Colunas das Tabelas:
~~~SQL
-- Mostrar todas as Tabelas do Banco de Dados corrente
SELECT * FROM Sys.Tables;

-- Mostrar todas as Tabelas de um BD específico
SELECT * FROM [db_nome_banco].Information_Schema.Tables;

-- Mostrar tabelas do BD com informaçoes de Data da ciração
SELECT * FROM SysObjects WHERE xtype='U' 
~~~

- Mostrar Campos das Tabelas
~~~SQL
-- Mostrar Campos de uma tabela
SELECT * FROM Sys.Columns WHERE object_id = object_id('tb_nome_tabela')

-- Mostrar Campos de uma tabela por Schema
SELECT * FROM Information_Schema.Columns WHERE table_name = 'tb_nome_tabela'
~~~

~~~SQL
SELECT campo_1, ... , campo_n  FROM tb_nome_tabela;
~~~

~~~SQL
SELECT * FROM tb_nome_tabela;
~~~

- Pesquisa pelos Campos das Tabelas
~~~SQL
SELECT * FROM tb_nome_tabela WHERE campo_1=valor_1;
~~~

~~~SQL
SELECT * FROM tb_nome_tabela WHERE campo_1=valor_1 OR campo_2=valor_2;
~~~

~~~SQL
SELECT * FROM tb_nome_tabela WHERE campo_1=valor_1 AND campo_2=valor_2;
~~~

~~~SQL
SELECT * FROM tb_nome_tabela WHERE campo_A IN (valor_A1, ... ,valor_An);
~~~

> Decrescente
~~~SQL
SELECT * FROM tb_nome_tabela ORDER BY campo_A DESC;
~~~

> Crescente
~~~SQL
SELECT * FROM nome_tabela ORDER BY campo_A ASC;
~~~

> Retorna apenas o primeiro registro 
~~~SQL
SELECT TOP 1 * FROM tb_nome_tabela;
~~~

~~~SQL
SELECT * FROM tabela_A ;
~~~

# Comandos 2

> Seleciona todos os Banco de Dados do SQLServer
- `name` nome da coluna com os nomes dos Banco de Dados
 
~~~SQL
SELECT name FROM master.sys.databases
~~~

~~~SQL
SELECT name FROM master.dbo.sysdatabases
~~~

# Comandos Encadeados

~~~SQL
-- Excluir banco, caso ja exista
use master 

go 

if exists (SELECT 1 FROM sys.databases WHERE name = 'db_nome_banco')
  DROP DATABASE db_nome_banco
~~~

[ver +](https://www.youtube.com/watch?v=RqlIpwpHWHA)


# Refêrencias 
[link 01](https://www.youtube.com/watch?v=DEh0B6PRn5k&list=PLsI_Jctnji3XawyHvU2WUBzBvUKAcs9Mg&index=1)

[link 02](https://www.youtube.com/watch?v=rX2I7OjLqWE&t=4359s)
