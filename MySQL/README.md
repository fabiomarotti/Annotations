# MySQL
Repositório com os estudos realizados sobre MySQL

- [site (Oficial)](https://www.mysql.com/)
- [Documentação MySql 5.6](https://dev.mysql.com/doc/refman/5.6/en/)

- SQL - "Structured Query Language" (Linguagem Estruturada de Consulta)

- DML - "Data Manipulation Language" (Linguagem de Manipulação de Dados)
- DCL - "Data Control Language" (Linguagem de Controle de Dados)
- DDL - "Data Definition Language" (Linguagem de Definição de Dados) 


# Configurações e Comandos

> Configurações
- `utf8_general_ci`
- `utf8_bin` comparação bit-a-bit dos caracteres, comparação **case-sensitive**.

> Tabelas
- `MyISAM` *
  - com proteção de tabelas (table locking). 
  - melhor performance para tabelas fixas (pouco acesso a tabela, Exemplo: tb_cidade)
  - check / repair : resolve problemas
- `InnoDB` 
  - maior complexidade (arquivo com histórico de transações)
  - mais propício a corrompimento irrecuperável 
  - baseado em transações (transaction locking).
  - mais rapido para tabelas em constantes mudanças
  - observa-se diferença em grandes bancos de dados

> Comandos
- `\. c:/banco_dados.sql` : Executar um arquivo via terminal MySQL  
  
- mysql -u `usuário` -p `senha` -h `servidor`

- mysqlshow -u root -p
  - ver banco de dados disponiveis

- mysqlshow -u `usuário` -p [ `banco` [ `tabela` [ `coluna` ] ] ]
  - opera diretamente no Shell do Linux

- **DUMP: Exportar** (Backup)
  - mysqldump -u `usuário` -p `senha` `nome_banco` > `nome_banco_bkp.sql`; <br> 
    // DUMP: um **banco + dados**
  - mysqldump -u `usuario` -p `senha` `nome_banco` --no-data > `nome_banco_bkp.sql`; <br> 
    // DUMP: apenas da estrutura de **um banco**
  - mysqldump -u `usuário` -p `senha` --all-databases > `caminho\nome_arquivo.sql`; <br>
    // DUMP: **todos os bancos** 

- **DUMP: Importar** 
  - mysqldump -u `usuário` -p `senha` `nome_banco` < `nome_banco_bkp.sql`; 

- `--comentado` Comentário ANSI SQL
- `#comentário` , `/*comentário*/`  Comentários aceitos
- `/*!40101 Comando comentado*/` 
  - o comando, mesmo que comentado, será executado apenas por versões do MySQL ≥ 4.1.1
- `\! cls` limpar tela (Prompt Windows)
- `exit` sair



# Tipos de Dados [Ver +](https://dev.mysql.com/doc/refman/8.0/en/precision-math-numbers.html)

|Tipo            | Tamanho  | Range    | 
|--              |--        |--        |
| TINYINT        |	1 byte	| 127 | 
| SMALLINT       |	2 bytes	| 32767|
| MEDIUMINT      |	3 bytes	| 8388607 |
| INT ou inteiro |	4 bytes	| 2147483647|
| BIGINT         |	8 bytes	| 2^(63) |
| FLOAT          |	4 bytes	| |
| DUPLO          |	8 bytes	| |
| DATA           |	3 bytes	| 1000/01/01 / 9999-12-31                    |
| TEMPO          |	3 bytes	| '-838: 59: 59' / '838: 59: 59'             |
| ANO            |	1 bytes	| 1901/2155                                  |
| DATETIME       |	8 bytes	| 1000-01-0100: 00: 00 / 9999-12-31 23:59:59 |
| TIMESTAMP      |	4 bytes	| Algum 00/2037 Ano: 1970-01-01 00:00        |


# Banco de Dados

> SHOW DATABASES;

> CREATE DATABASE `nome_do_banco`;

> USE `nome_do_banco`;

> DROP DATABASE `nome_banco`;

> Editar: `CREATE` seguido de um `DROP` 


# Tabelas

> SHOW TABLES;

> SHOW COLUMNS FROM `nome_tabela`;
> DESCRIBE `nome_tabela`;
> DESC `nome_tabela`;

> SELECT `campo` FROM `nome_tabela`;

> CREATE TABLE `nome_tabela` ( `campo` `tipo` );

> INSERT INTO `nome_tabela` ( `campo` ) VALUES ( `valor` );

> UPDATE `nome_tabela` SET `campo`=`novo_valor` WHERE `campo`=`condição`;

> DELETE FROM `nome_tabela` WHERE `campo`=`parametro`;

> DROP TABLE `nome_tabela`;

> Exemplo - Criar Tabela
~~~MySQL
CREATE TABLE nome_tabela (  campo_01 INT 
                                NOT NULL 
                                AUTO_INCREMENT,
                            campo_02 VARCHAR( 255 ),
                            campo_03 DEFAULT NUL,
                            PRIMARY KEY( campo_O1 )  
                            );
~~~

> Exemplo - Inserir
~~~MySQL
INSERT INTO tb_usuarios (user_nome, user_email) VALUES ( 'valor01' , 'valor02' );
~~~

> Exemplo - Atualizar
~~~MySQL
UPDATE tb_usuarios SET user_nome='valor011' , user_email='valor022';
~~~
~~~MySQL
UPDATE tb_usuarios SET user_nome='valor011' WHERE user_id=123;
~~~

> Exemplo - Apagar
~~~MySQL
DELETE FROM tb_contatos WHERE user_id=123;
~~~

> Exemplo - Pesquisar
~~~MySQL 
SELECT user_nome, user_email FROM tb_usuarios;
~~~

~~~MySQL
SELECT * FROM tb_usuarios;
~~~

# Filtros de busca
- LIKE
- DES
- ASC


# continuar ...
- SHOW [FULL] COLUMNS FROM tbl_editoras;
- SHOW COLUMNS FROM tbl_Livro LIKE ‘I%’;
- SHOW COLUMNS FROM tbl_Livro WHERE Type like ‘varchar%’;

> Mostrar os privilégios de acesso ao Banco de Dados <br>
> SHOW GRANTS FOR root@localhost;

> `SELECT * FROM tb_pessoa\G` mostra dados organizados (prompt mysql)

> `SELECT * FROM tb_pessoa WHERE nome LIKE 'f%' `
