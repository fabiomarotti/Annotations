# Configurações importantes para Interface
- Project / Options / Forms / Auto-create Forms (principal)

## Definições e Propriedades em Geral
- `F1` : documentação da propriedade selecionada
- `TAB` avança
- `Alt` + `TAB` : retrocede
- `TabOrder` : Ordenar por indice ou drag-drop
- `TabStop` : Tab inativo para componente especifico
  - Panel ou GroupBox possuem a propriedade para ordenar drag-drop
- `Name` Nome do objeto
- `Caption` Nome de exibição
- `CharCase` deixar campo tudo Maiusculo ou Minusculo
- `ReadOnly` apenas Leitura, pode copiar (Enable não copia)
- `Default` : True habilita em botoões a ação do Enter no teclado.
    

# Componentes
- `TMainMenu`
  - `&nome` gera atalho do teclado  

- `TToolBar` cabeçalho
  - `New Button` Botões para cabeçalho
  - `Images` selecionar `TImageList`
  - Conterá chamdas do `TActionList`

- `TStatusBar` rodapé
-  `TImage`
  - Strech : não cortar a imagem caso seja retangular em um espaço quadrado
  - Proporcional: manter proporcional 

- `TImageList` conjunto de imagens a serem compartilhadas no sistema
  - ColorDepth: cd32bit
  - Width e Height 
  - boa pratica, nomear pelo tamanho da imagem a ser usada
  - sua chamda é na propriedade `Image`

- `TActionList` Cria uma lista de ações pre-configuradas e reaproveitas no codigo
  - `New Action` Cria uma ação (botão)
    - `Caption` Nome exposto ao Usuario
    - `ImagesIndex` associado ao `TImageList`
    - `onExecute` conterá o evento
    - propriedade `Action` nos botões aciona uma evento do `onExecute`

- `TGroupBox` TPainel com label 

- `TBitBtn` : Botão
  - Glyph : Inserir Icone no botão
  - `Layout` relação Texto e Imagem no botão

### `TMaskEdit` [ver +](http://delphiparainiciantes.com.br/como-utilizar-mascaras-maskedit-no-delphi/)
> [regra] **;** [salvar/não os caracteres] **;** [caracter a se exibir]
- **;** (ponto e virgula)
    - Separa os três campos da máscara. 
- **Regra**
    - `A` Caracteres alfanuméricos (A-Z, a-z, 0-9) com preenchimento obrigatório. Ex: AAA;1;_
    - `a` Caracteres alfanuméricos (A-Z, a-z, 0-9) com preenchimento opcional. Ex: aaa;1;_
    - `0` Caracteres numéricos (0-9) com preenchimento obrigatório. Ex: 000;1;_
    - `9` Caracteres numéricos (0-9) com preenchimento opcional. Ex: 999;1;_
    - `L` Caracteres alfabéticos (A-Z, a-z) com preenchimento obrigatório. Ex: LLL;1;_
    - `l` (Letra ele minúscula) Caracteres alfabéticos (A-Z, a-z) com preenchimento opcional. Ex: lll;1;_
    - `>` Todos os caracteres alfabéticos digitados após este símbolo serão convertidos para maiúsculos. Ex:>aaa;0;_
    - `<` Todos os caracteres alfabéticos digitados após este símbolo serão convertidos para minúsculos. Ex:<aaa;0;_
    - `<>` Anula o uso dos caracteres > e <. Ex: >aaa<>aaa;0;_
    - `\` Utilizado para marcar determinado caractere não especial como fixo, não podendo sobrescrevê-lo. Ex:!\(999\)000-0000;0;_
    - `C` Exige preenchimento obrigatório com qualquer caractere para a posição. Ex: CCC;1;_
    - `c` Permite qualquer caractere para a posição com preenchimento opcional. Ex: ccc;1;_
    - `#` Caracteres numéricos (0-9) e os sinais de – ou + com preenchimento opcional. Ex: ###;1;_
    - `:` Utilizado como separador de horas, minutos e segundos. Ex: !00:00:00;1;_
    - `/` Utilizado como separador de dia, mês e ano. Ex: !99/99/9999;1;_
    - `_` Caractere usado normalmente nas posições do campo ainda não preenchidas.
- **salvar/não**
    - **1** : Salvar os caracteres da mascara
    - **0** : Não salvar os caracteres da mascara   
- **caracter a se exibir** (quando estiver vazio/branco)
    - caracter a se exibir no campo em branco

> Boa prática: salvar apenas dados (numeros e letras), sem a máscara.   

# Form
- `Icon`: *.ico
- `FormStyle`:
  - fsNormal (formulários independentes) 
  - fsMDIForm (formulario Pai)
  - fsMDIChild (formulario Filho)  
- `Position`: poScreenCenter, poMainFormCenter,.. (onde o form vai aparecer)
- `WindowsState`: wsNormal, Minimizado e Maximizado



# Ação para um Form

> Procedimento em (TFormPrincipal) para chamar um formulario do (TFormCadastro)
~~~Delphi
procedure TFormPrincipal.Gravar1Click(Sender: TObject);
var cadastro : TFormCadastro;
begin
    cadastro := TFormCadastro.Create(self);
    cadastro.ShowModal;
end;
~~~

# Caixa de Mensagem
~~~Delphi
ShowMessage('Ola Mundo!' + var);
~~~

# Eventos
- `onClick`
- `onChange` 
- `onShow` : quando abrir/exibir (formulario)
- `onExit` validar ao sair/terminar
- `onStateChange` (para DataSource)
- `onKeyDown` na hora que preciona a tecla
- `onKeyUp` na hora que solta a tecla

> `KeyPreview` : true, para funcionar

# Formulário Modelo
- Inheritable Items

# Data Controls
- Componentes que interagem automaticamente com o Banco de Dados.
- `DataSouce` -> [DataSet] (liga o componente com a tabela)
- `DataField` (um campo apenas da tabela)
- `PasswordChar` : Efeito de mascara 
- `DisplayFormat` : Efeito mascara em zTable

## Componentes
- `TDBGrid`
- `TDBNavigator`
- `TDBText` (Label) 
- `TDBEdit` 
- `TDBMemo`
- `TDBImage` 
  - não trabalho com *.jpg
  - trabalha apenas com *.bmp
  - deixa o banco de dados lento
- `TDBListBox`

### `TDBEdit` 

### `TDBComboBox` 
- `Items` : Define os campos validos do ComboBox

### `TDBGrid`
- `Options`:
  - dgIndicator
  - dgRowSelect
  - dgAlwaysShowSelection

> Eventos
- `onTitleClik` : Ao clicar no titulo da tabela



## considerações
- SpeedButton não recebem foco