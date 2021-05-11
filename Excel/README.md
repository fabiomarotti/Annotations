# Excel

## Conceitos
- Suplementos são bibliotecas DLL utilizadas pelo VBA.

### Comentários
- comentário em linha: apóstrofo (‘)
### Variaveis
- Impor a tarefa de declação de variaveis (nicio do modulo): `Option Explicit`

- Tipos:
  - `Boolean`
  - `Integer` -32.768 a 32.767
  - `Long` -2.147.483.648 a 2.147.483.647
  - `Single` -3.402823E38 a 1.401298E45
  - `Double (negativo)` -1.79769313486232E308 a -4.94065645841247E-324
  - `Double (positivo)` 4.94065645841247E-324 a 1.79769313486232E308
  - `Currency (Moeda)` -922.337.203.685.477.5808 a 922.337.203.685.477.5807
  - `Date` 1/1/100 a 12/31/9999
  - `String`
  - `Object`
  - `Variant`
  - `User Defined`

~~~
// Exemplo
Dim nome_variavel As tipo
Dim nome As String
Dim idade As Long
~~~

### Comandos

`nome_objeto_vba(nome_planilha)`
~~~ 
nome_objeto_vba.Select
~~~
