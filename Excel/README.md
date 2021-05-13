# Excel
[Documentação VB](https://docs.microsoft.com/pt-br/dotnet/visual-basic/)
[Documentação VBA](https://docs.microsoft.com/pt-br/office/vba/api/overview/excel)
[Funções VBA](https://www.techonthenet.com/excel/formulas/index_vba.php)
[Conteúdo Geral](https://sites.google.com/a/gcloud.fe.up.pt/excel/Excel/vba)


## Conceitos
- Arquivo / Opções / Personalizar Faixa de Opções / Desenvolvedor
- Salvar como `arquivo.xlsm` (Pasta de trabalho habilitada para Macro do Excel)
- Suplementos são bibliotecas DLL utilizadas pelo VBA.
- Estrutura 
  - Microsoft Excel Objetos
  - UserForm
  - `Módulo`não se instancia como objeto
  - `Módulo Classe` pode ser instanciada como objeto

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

~~~VBA
` Exemplo geral
Dim nome_variavel As tipo
Public nome As String
Static idade As Long
Public estado As String * 2   ` limite de 2 caracteres
Private x   'será tratada como o tipo Variant (qualquer coisa)
~~~

~~~VBA
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

~~~VBA
` unidimesional
Dim lista_1 (1 To 100) As Integer  ` 100 elementos
Dim lista_2 (0 To 100) As Integer  ` 101 elementos
Dim lista_3 (100) As Integer       ` 101 elementos

` Multidimensionais
Dim matriz_A (1 To 9, 1 To 9) As Integer
Dim matriz_B (1 To 10, 1 To 10, 1 To 10) As Integer

~~~

- Arrays Dinâmicos usam `ReDim`
~~~VBA
` Array dinâmicos

Dim   matriz_X () As Integer
ReDim matriz_X (1 To NumElements)
~~~

### Labels (Etiquetas)


### Comandos

`nome_objeto_vba(nome_planilha)`
~~~VBA 
nome_objeto_vba.Select
~~~

### Funções

~~~VBA
Sub nome_função()
  ` Código
End Sub
~~~


### Objetos
- `Range`
- `Worksheets(“Sheet2”).Cells(2, 3)`
~~~VBA
`Selecionar células
Range(“A1:C5”)
Range(“A1:J10”).Value = 99
Range(Cells(1, 1), Cells(10, 10)).Value = 99

`Atribuir
Range("A1").Value = "Olá Mundo"

Range(“A1”).Offset(1, 2)

`Selecionar Colunas
Columns(“A:C”)

`Selecionar Linhas
Rows(“1:5”)

~~~

