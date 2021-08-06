# Design Patterns (Padrões de Projeto)

# Variaveis
- Camel Case: primeira letra minuscula seguida de Iniciais maiusculas. Ex.: nomeDeVariavel
- Pascal Case: as letras iniciais em maiusculas. E.: NomeDeVariavel
- `Notação Hungara` [ver+](https://en.wikipedia.org/wiki/Hungarian_notation)



## Padrões
- `PO` : (Persistent Object) : Semelhante a VO ou TO porem sem referência a códigos de transação com banco de dados.
- `POJO` : (Plain Old Java Object)
- `BO` : (Business Object)
- `DAO` : (Data Acess Object) : contem o acesso ao banco de dados. (ver Padrão Factory)
- `DTO` : (Data Transfer Object) : Objeto simples para transferir dados entre as camadas lógicas (view-controller-model), sem lógica de negócios em seus objetos. 
  - `VO` : (Value Object)
  - `TO` : (Transfer Object) : Objeto de Transporte.

- `Separated Interface` (Código para Interface) [ver+](https://martinfowler.com/eaaCatalog/separatedInterface.html)
- `Dependency Injection` (Injeção de Dependência)
- `Dependency Inversion` (Inversão de Dependência: Principio SOLID)

## Categorias
- **Criacionais** 
  - Abstract Factory, 
  - Factory Method, 
  - Builder, 
  - Prototype, 
  - `Singleton`;
- **Estruturais** 
  - Composite, 
  - `Adapter`, 
  - Bridge, 
  - Decorator, 
  - Facade, 
  - Flyweight, 
  - Proxy;
- **Comportamentais** 
  - Chain of Responsability, 
  - Strategy, 
  - Interpreter, 
  - `Template Method`, 
  - Command, 
  - Iterator, 
  - Mediator, 
  - Memento, 
  - Observer, 
  - State, 
  - Visitor.
 



### Singleton
- Garante que uma classe possuirá apenas uma instância, e proverá um único ponto de acesso global a mesma.

# Referência
[site 01](https://portaldesenvolvedor.com/blog/design-patterns-em-delphi-padroes-de-projeto/)
