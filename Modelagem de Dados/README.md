# Modelagem de Dados

- Modelo Hierárquico (tipo de arvore)
- Modelo em Rede (tipo de Grafo)
- **Modelo Relacional**

### Siglas 
- `Dados`
  - Fatos em uma forma primária.
- `Informação`
  - Fatos organizados em algum meio.
- `Metadados` 
  - Dados sobre os Dados
  - São mantidos em dicionários de dados (Catálogo de dados)
- `BD` (Banco de Dados)
- `DBA` (Data Base Administrator)
- `SGBD` Sistema de Gerenciamento de Banco de Dados
- `SGBDR` Sistema de Gerenciamento de Banco de Dados Relacional
- `MER` (Modelo Entidade Relacionamento) e Atributos
  - listas de entidades, atributos e relacionamento, ... 
- `DER` (Diagrama Entidade Relacionamento)
  - modo gráfico
- `Schema` (Esquema) definição do BD especificada durante o projeto, armazenada no **Dicionário de Dados**. 
  - Alem do MFD, aqui se defini funçoes, visões, ...

### Níveis da Modelagem de Dados
> Arquitetura de três niveis

- `MCD` (Modelo Conceitual de Dados) (alto nivel)
  - Representação do mundo real por meio de uma visão simplificada.
  - Projeto é independente de um SGBD.
  
- `MLD` (Modelo Lógico de Dados)
  - Diagrama (Diagrama Entidade Relacionamento)
  - Especificação Lógica
  - Projeto é independente de um SGBD.

- `MFD` (Modelo Físico de Dados) (baixo nivel)
  - Derivado do MLD, cria-se as tabelas, atributos, tipos de dados, tamanho

### MER
- `Entidade` (Retângulo)
  - Instância de Entidade
    - Ocorrência especifica de uma entidade
    - cada "Produto" é uma Instância
    - Classe de Objetos (lembrando da OO)
  - palavra no singular
  - caracteres permitidos (`$`,`#`,`_`)
  - nomes das entidades e colunas devem ser unicos

- `Atributos` 
> Descrevem caracteristicas da entidade
- **Simples**: (atômico/indivisivel) (nome, CPF)
- **Composto**: (Endereço :(subdividido em atributos simples): Rua, Bairro, CEP)
- **Multivalorado**: (Para a mesma instência, pode-se ter mais de um registro do mesmo atributo) (Telefone) (usar `*`)
- **Determinante**: Garante que os registros não se repitam (Atributo sublinhado) (Código de Produto)
- **Identificador**(Chaves): é um tipo de Determinante
  - __Único__ (Determinante) valor é unico na entidade e não se repete (chave-primária)
  - __Não-único__ agrupar instâncias de classe em categorias (chave-estrangeira)
  
- `Relaciomento` (Losângo)   

