# Generics

### Informações
- `System.Generics.Collections` [saiba+](http://docwiki.embarcadero.com/CodeExamples/Sydney/en/Generics_Collections_TList_(Delphi))
  - `.TList<T>`
  - `.TDictionary<TKey,TValue>`
  - `.TStack<T>`
  - `.IComparable<T>`
  - `.IEnumerator<T>`
  - `.TObjectList<T>`
  - `.TObjectDictionary<TKey,TValue>`
  - `.TObjectStack<T>`

- As validações são feitas no Tipo <T> informado ao Genérico e não a classe.
---- 

- Constraints [saiba+](http://docwiki.embarcadero.com/RADStudio/Sydney/en/Constraints_in_Generics)
~~~Delphi
type
  TExemplo<T> = class ..
  TExemplo<T: class> = class ..
  TExemplo<T: constructor> = class ..
  TExemplo<T: record> = class ..
  TExemplo<T: TClasseBase> = class ..
  TExemplo<T: class,IAlgumaInterface> = class ..
  TExemplo<T: IInterfaceGenerica<T>>  = class ..
~~~

### Construindo Classes Genericas
> Exemplo: Estrutura de uma Classe Generica
~~~Delphi
type
  TExemploGenerico< T > = class
    // ...
  end;
~~~

> Exemplo: Criando e Atribuindo um Tipo ao Generico 
~~~Delphi
type
  TKeyValue< T > = class
    property Key    : String;
    property Value  : T ;
  end;
~~~
~~~Delphi
// Atribuindo o tipo Inteiro ao Genérico
var
  KV : TKeyValue<Interger>;
~~~
~~~Delphi
// Value ira incorporar o tipo Inteiro
KV.Value.ToString;
~~~



[link 1](https://regys.com.br/usando-efetivamente-generics-em-object-pascal/#.YRUR64hKhhE)
[link 2](https://www.youtube.com/watch?v=KeMbPxfWb0Y)

