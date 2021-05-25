# Configurações importantes para Interface
- Project / Options / Forms / Auto-create Forms (principal)

## Definições
- Name: Nome do objeto
- Caption: Nome de exibição
    

# Componentes
- `TMainMenu`
  - `&nome` gera atalho do teclado  

- `TToolBar` cabeçalho
  - `New Button` Botões para cabeçalho
  - `Images` selecionar `TImageList`
  - Conterá chamdas do `TActionList`

- `TStatusBar` rodapé

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
- `Position`: poScreenCenter (onde o form vai aparecer)
- `WindowsState`: wsNormal, Minimizado e Maximizado

# TDBGrid
- `Options`:
  - dgIndicator
  - dgRowSelect
  - dgAlwaysShowSelection

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
- `onExit` validar ao sair/terminar

## considerações
- SpeedButton não recebem foco
