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
  - Retangulo: Entidade
  - Losango: Relacionamento
  - Elipse: Atributo
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
