# SQL Server

### Downloads
- [Download SSEI - SQL 2019 Express](https://go.microsoft.com/fwlink/?linkid=866658)
- [Download SSMS - SQL Server Management Studio 18.9.1](https://docs.microsoft.com/pt-br/sql/ssms/download-sql-server-management-studio-ssms?redirectedfrom=MSDN&view=sql-server-ver15)

### Pre-Configurações
- **Configuração da Instância** : SQLSPRESS, SQLTrabalho
- **Configuração do Servidor** : SQL Server Browser : Automático e Agrupamento: Latin1_General_CI_AS
- **Configuração do Mecanismo de Banco de Dados** : Modo Misto: usuario master : **sa** e inserir senha
- **SQL Management Studio**:
  - Nome do servidor: nomePC\Instancia
  - Autenticação do SQL Server: sa e senha

### Comandos de Informações
- `sp_helpdb nome_banco` informações sobre o Banco de Dados, Tamanho, Quem criou, localização, ...


# Tabelas Temporárias
- `#` Visibilidade Local
- `##` Visbilidade Global

[continuar](https://www.youtube.com/watch?v=_gEeh3lPhl0&list=PLsI_Jctnji3XawyHvU2WUBzBvUKAcs9Mg&index=3)

# Comandos para Banco de Dados

> Criar Banco de Dados
~~~SQL
CREATE DATABASE nome_banco
~~~ 

> Acessar para uso 
~~~SQL
USE nome_banco
~~~

> Criar Banco com Detalhes e Limitações
> - `nome_banco.mdf` Banco de Dados <br>
> - `nome_banco.ldf` Log do Bando de Dados <br>
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

> Excluir Banco de Dados
~~~SQL
DROP DATABASE nome_banco
~~~




# Refêrencias 
[link 01](https://www.youtube.com/watch?v=DEh0B6PRn5k&list=PLsI_Jctnji3XawyHvU2WUBzBvUKAcs9Mg&index=1)
