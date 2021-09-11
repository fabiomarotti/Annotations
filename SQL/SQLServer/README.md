# SQL Server

### Comandos

~~~SQL
-- Comentário em uma linha 
~~~

~~~SQL
/* Comentário em multiplas linhas */
~~~

# Tabelas Temporárias
- `#` Visibilidade Local
- `##` Visbilidade Global

[continuar](https://www.youtube.com/watch?v=_gEeh3lPhl0&list=PLsI_Jctnji3XawyHvU2WUBzBvUKAcs9Mg&index=3)


# Comandos para Banco de Dados
~~~SQL
-- Criar o Banco de Dados
CREATE DATABASE db_nome_banco
~~~ 

~~~SQL
-- Acessar o Banco de Dados para o uso
USE db_nome_banco
~~~



~~~SQL
-- Excluir Banco de Dados
DROP DATABASE db_nome_banco
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




## Comandos para Tabelas
- `AUTOINCREMENT` : gerar valor automatico e incremental
- `REFERENCES`
- `IDENTITY` : enumerar automaticamente
  - Exemplo: `IDENTITY (1,1)` : começar em 1 e ter o incremento +1 .

# CONSTRAINT
> Constraint possuem nomes, exemplo: pk_cidades <br>

- `CONSTRAINT` : criar regras/restrições para uma coluna de uma tabela
  - `PRIMARY KEY` : chave primária : (ID) : (UNIQUE + NOT NULL)
    - `pk_tb_nome_tabela` 
  - `FOREIGN KEY` : chave secundária : identifica/referência a um campo (linha) em outra tabela.
    - `fk_tb_nome_tabela`
- `NOT NULL` : Não permite nulos.
- `UNIQUE` : Todos os valores em uma coluna sejam diferentes.
- `CHECK` : Garante que os valores de uma coluna satisfaçam uma condição  ( >, <, =, MAX, ...) 
- `DEFAULT` : insere um _valor padrão_ para o caso o usuario nao tenha inserido algum.
- `CREATE INDEX` : Criar e Recuperar rapidamente os dados no BD

### Manipulando Constraint

~~~SQL
-- Busca todos os campos de CONSTRAINT
SELECT * FROM information_schema.referential_constraints
    WHERE constraint_schema = 'db_nome_banco_dados'
~~~

~~~SQL
-- Busca o nome da tabela por meio do nome_constraint
SELECT COLUMN_NAME,TABLE_NAME FROM INFORMATION_SCHEMA.CONSTRAINT_COLUMN_USAGE
  WHERE CONSTRAINT_name = 'nome_constraint'
~~~

~~~SQL
ALTER TABLE tb_nome_tabela DROP CONSTRAINT [FK_cod_criado_constraint]
~~~

# `CREATE`
> Exemplo:
~~~SQL
CREATE TABLE tb_nome_tabela (
  campo_1   INT           PRIMARY KEY,
  campo_2   VARCHAR(255)  NOT NULL,
  campo_3   INT           DEFAULT 0,
  campo_4   DATETIME      NOT NULL
);
~~~

> Exemplo: Relação PK e FK
~~~SQL
CREATE TABLE tb_estados (
   id_estado   INT           PRIMARY KEY, 
   uf_estado   VARCHAR(2)
   dsc_estado  VARCHAR(255)
);
~~~

~~~SQL
CREATE TABLE tb_cidades (
       id_cidade   INT  PRIMARY KEY, 
       dsc_cidade  VARCHAR(255),
       id_estado   INT  FOREIGN KEY   REFERENCES tb_estado(id_estado)      
-- id_estado INT       
-- FOREIGN KEY(id_estado) REFERENCES tb_estado(id_estado)       
);

~~~       

> Exemplo: 
  - Constraint: Cria-se automaticamente
  - Identity: Enumera campo_1 automaticamente
~~~SQL
CREATE TABLE tb_nome_tabela (
       campo_1  INT    NOT NUL   PRIMARY KEY   IDENTITY, 
       campo_2  VARCHAR(50)
       );
~~~



# `ALTER`
- ALTER
  - ADD
    - ADD CONSTRAINT
  - ALTER
  - DROP
  - 
~~~SQL
-- Adiciona um campo a tabela.
ALTER TABLE tb_nome_tabela 
      ADD campo_x VARCHAR(20) NOT NULL;
~~~

~~~SQL
-- Altera um campo (coluna ja existente) na tabela.
ALTER TABLE tb_nome_tabela 
      ALTER COLUMN campo_x VARCHAR(21);
~~~

~~~SQL
-- Apaga um campo (coluna) na tabela.
ALTER TABLE tb_nome_tabela 
      DROP COLUMN campo_x;
~~~

~~~SQL
-- Adiciona Primary Key.
ALTER TABLE tb_nome_tabela 
      ADD CONSTRAINT pk_campo_pk PRIMARY KEY (campo_pk);
~~~

~~~SQL
-- Adiciona Foreign Key
ALTER TABLE tb_nome_tabela_com_pk 
      ADD CONSTRAINT fk_campo_fk FOREIGN KEY (campo_fk)
      REFERENCES tabela_fk (campo_fk_tabela_fk) ON DELETE CASCADE;
~~~

#### Utilitários ALTER
> Alterando campo da tabela para Primary Key
~~~SQL
-- Define a Primary Key sem CONSTRAINT
ALTER TABLE tb_nomeA	ADD PRIMARY KEY (id_campo_tb_nomeA);

-- Pesquisa o nome da Primary Key (Chave: Constraint)
SELECT name  
    FROM sys.key_constraints  
    WHERE type = 'PK';  
~~~

> Alterando campo da tabela para Foreign Key
~~~SQL
ALTER TABLE tb_nomeA	ADD PRIMARY KEY (id_campo_tb_nomeA);
~~~

# `INSERT`
~~~SQL
INSERT INTO nome_tabela (campo_1, campo_2, .., campo_n) VALUES (valor_1, valor_2, ..., valor_n);
~~~

~~~SQL
INSERT INTO tb_nome_tabela (campo_A1, campo_A2, .., campo_An) 
       VALUES (valor_A1, valor_A2, ... , valor_An),
              (valor_B1, valor_B2, ... , valor_Bn),
              (valor_C1, valor_C2, ... , valor_Cn);
~~~
 
# `DELETE`
~~~SQL
DELETE tb_nome_tabela WHERE campo=valor;
~~~

- Apaga todos os registros da tabela
~~~SQL
DELETE tb_nome_tabela;
~~~

# `UPDATE`
~~~SQL
UPDATE tb_nome_tabela SET   campo_1 = valor_1 , ... , campo_n = valor_n   WHERE   campo_x = valor_x;
~~~


# `SELECT`
> - `DISTINCT` : filtra, não retornando os dados duplicados (linhas repetidas) da Coluna de uma Tabela.
> - `COUNT(col_name)` : Contagem de Linhas de uma Coluna de uma Tabela (`*`: todas as coluas)
>   - `COUNT(DISTINCT col_name)` 
> - `TOP --` : Filtras as primeiras -- linhas   
> - `WHERE` : filtrar por condição (operadores lógicos: = , <> , >= , AND, ..)
>   - `BETWEEN` : valores **entre** uma faixa, equivale a AND
>   - `IN(valor_1,..,valor_n)` : filtra se contem algum, equivale a OR
> - `ORDER BY` : Ordenar a Coluna
>   - `ASC` ou `DESC`
> - `INNER JOIN` `ON` 
  


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

~~~SQL
-- sem nome do campo
SELECT  c.cidade + ' - ' + e.estado   FROM   tb_cidade AS c   INNER JOIN   tb_estado AS e   ON   c.id_estado = c.id_estado
~~~

~~~SQL
-- com nome do campo: Cidade_Estado
SELECT  c.cidade + ' - ' + e.estado  Cidade_Estado  FROM   tb_cidade AS c   INNER JOIN   tb_estado AS e   ON   c.id_estado = c.id_estado
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




# Refêrencias 
- [link 01](https://www.youtube.com/watch?v=DEh0B6PRn5k&list=PLsI_Jctnji3XawyHvU2WUBzBvUKAcs9Mg&index=1)
- [link 02](https://www.youtube.com/watch?v=rX2I7OjLqWE&t=4359s)
- [ver +](https://www.youtube.com/watch?v=RqlIpwpHWHA)
- [sql ++](https://www.youtube.com/watch?v=MdYX5wojC-s&list=PLegVz0fLdvBqFGheCpqCau21kR2U5zBeh)

# +
~~~SQL
-- realiza operação aritmética
SELECT 2+2

-- Contar linhas da tabela
SELECT COUNT(*) FROM tb_nome;

~~~
