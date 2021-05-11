# Excel

## Conceitos
- Suplementos são bibliotecas DLL utilizadas pelo VBA.

### Comentários
- comentário em linha: apóstrofo (‘)

### Operadores Regulares
- `+` , `-`, `*`, `/` 
- `^` : exponenciação
- `&` : concatenação
- `\` : divisão de um inteiro
- `Mod` : Módulo aritmético

### Operadores Lógicos
- `Not`, `And`, `Or`, `XoR`
- `Eqv` : Equivalência
- `Imp` : Implicação

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
` Exemplo geral
Dim nome_variavel As tipo
Public nome As String
Static idade As Long
Public estado As String * 2   ` limite de 2 caracteres
Private x   'será tratada como o tipo Variant (qualquer coisa)
~~~

~~~
` Exemplo para Datas
Dim hoje As Date
Const primeiroDia As Date = #1/1/2010”
Const noite = #12:00:00#
~~~

- Controladores de acesso / escopo:
  - `Dim` / procedimento e módulo
  - `Static` / procedimento
  - `Private` / módulo (antes da primeira declaração Sub ou Function)
  - `Public`
  
### Arrays e Matrizes 
- `Option Base 1`: Aceitar o `1` como inicio ao inves do `0`

~~~ 
` unidimesional
Dim lista_1 (1 To 100) As Integer  ` 100 elementos
Dim lista_2 (0 To 100) As Integer  ` 101 elementos
Dim lista_3 (100) As Integer       ` 101 elementos

` Multidimensionais
Dim matriz_A (1 To 9, 1 To 9) As Integer
Dim matriz_B (1 To 10, 1 To 10, 1 To 10) As Integer

~~~

- Arrays Dinâmicos usam `ReDim`
~~~
` Array dinâmicos

Dim   matriz_X () As Integer
ReDim matriz_X (1 To NumElements)
~~~

### Labels (Etiquetas)


### Comandos

`nome_objeto_vba(nome_planilha)`
~~~ 
nome_objeto_vba.Select
~~~

### Funções

~~~
Sub nome_função()
  ` Código
End Sub
~~~


### Objetos
- `Range`
- `Worksheets(“Sheet2”).Cells(2, 3)`
~~~
Range(“A1:C5”)
~~~

