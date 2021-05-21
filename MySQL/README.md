# MySQL
Repositório com os estudos realizados sobre MySQL

- https://www.mysql.com/

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
  
- mysql -u `usuário` -p `senha` -h `servidor`

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
- `/*!40101 Comando comentado*/` o comando, mesmo que comentado, será executado apenas por versões do MySQL ≥ 4.1.1
- `\! cls` limpar tela (Prompt Windows)
- `exit` sair



# Tipos de Dados

|Tipo   |Armazenamento  | Range
|--     |--             |--
|||


# Banco de Dados

> SHOW DATABASE;

> CREATE DATABASE `nome_do_banco`;

> USE `nome_do_banco`;

> DROP DATABASE `nome_banco`;

# Tabelas

> SHOW TABLES;

> DESCRIBE `nome_tabela`;

> SELECT `campo` FROM `nome_tabela`;

> CREATE TABLE `nome_tabela` ( `campo` `tipo` );

> INSERT INTO `nome_tabela` ( `campo` ) VALUES ( `valor` );

> UPDATE `nome_tabela` SET `campo`=`novo_valor` WHERE `campo`=`condição`;

> DELETE FROM `nome_tabela` WHERE `campo`=`parametro`;

> DROP TABLE `nome_tabela`;

~~~
CREATE TABLE nome_tabela (  campo_01 INT NOT NULL AUTO_INCREMENT,
                            campo_02 VARCHAR( 255 ),
                            campo_03 DEFAULT NUL,
                            PRIMARY KEY( campo_O1 )  
                            );
~~~
