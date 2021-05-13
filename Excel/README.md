# Excel
[Documentação VB](https://docs.microsoft.com/pt-br/dotnet/visual-basic/)

[Documentação VBA](https://docs.microsoft.com/pt-br/office/vba/api/overview/excel)

[Funções VBA](https://www.techonthenet.com/excel/formulas/index_vba.php)

[Conteúdo Geral](https://sites.google.com/a/gcloud.fe.up.pt/excel/Excel/vba)

- VBA: Visual Basic for Application
- VBE: Visual Vasic Editor
- Versões anteriores ao Excel 2007 tinham 65.536 linhas e 255 colunas (a última célula é IV65536)



## Conceitos
- Arquivo / Opções / Personalizar Faixa de Opções / Desenvolvedor
- Salvar como `arquivo.xlsm` (Pasta de trabalho habilitada para Macro do Excel)
- Suplementos são bibliotecas DLL utilizadas pelo VBA.
- Estrutura 
  - Microsoft Excel Objetos
  - `UserForm`
  - `Módulo`não se instancia como objeto
  - `Módulo Classe` pode ser instanciada como objeto

## Atalhos
- Alt + F8
- Ctrl + Shift + N
- Ctrl + R : exibir janela do Projeto
- Ctrl + E : exportar arquivo
- Alt + F11 : Alternar VBA-Excel
- Ctrl + Shift + F: gravar Macro
- 



### Comentário e outros
- comentário em linha: apóstrofo (‘)
- quebrar um alinha de codigo: termine a primeira linha com um espaço seguido de um underline (_)
~~~VBA
Selection.Sort Key1:=Range(“A1”), _
Order1:=xlAscending, Header:=xlGuess, _
Orientation:=xlTopToBottom
~~~

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

### Função e Procedimento
~~~VBA
`Função
Function nome_função(arg1, arg2)
  ` Código
  nome_função = arg1 + arg2
End Function
~~~

~~~VBA
`Procedimento
Sub nome_Procedimento()
  ` Código
End Sub
~~~

### Funções do Excel
- =AGORA()

### Fuçoes do VBA
- `MsgBox`

### Objetos do Excel
- `Application` o proprio excel é um objeto
- ThisWorkbook
- `Workbook` arquivo
- `Worksheet` página
- `Range` celula
- `PivotTable` tabela principal
- `Commet` Comentarios
- `PageSetup` Configuração da Página
- `Hiperlink`
- `Name`nome
- `Worksheets(“Sheet2”).Cells(2, 3)`
- `Selection.Font.Bold = True`




### Exemplos
~~~VBA
Worksheets(“Plan1”).Activate
Range(“A1”).Copy Range(“B1”)
Workbooks.Add
Application.Workbooks(“Arquivo.xlsx”).Worksheets(“Página1”).Range(“A1”).Value
~~~

~~~VBA
`Limpar conteúdo
Worksheets(“Sheet1”).Range(“A1”).ClearContents
~~~


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




### Módulos
- Declaração : variaveis
- Procedimentos Sub: não retornam valor
- Procedimentos Function: retornam valor
- limite de 64.000 caracteres por módulo

