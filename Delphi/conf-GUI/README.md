# Configurações importantes para Interface
- Name: Nome do objeto
- Caption: Nome de exibição
    

# Componentes
- `TMainMenu`
  - `&nome` gera atalho do teclado  

- `TToolBar` cabeçalho
  - `New Button` Botões para cabeçalho
  - Conterá chamdas do `TActionList`

- `TStatusBar` rodapé

- `TImageList` conjunto de imagens a serem usadas no sistema
  - boa pratica, nomear pelo tamanho da imagem a ser usada
  - sua chamda é na propriedade `Image`

- `TActionList` Uma lista de ações para reaproveitar codigo
  - `New Action` Cria uma ação (botão)
    - `Images` associa ao `TImageList`
    - `onExecute` conterá o evento
    - propriedade `Action` nos botões aciona uma evento do `onExecute`

# Form
- `Icon`: *.ico
- `FormStyle`:
  - fsMDIForm (formulario Pai)
  - fsMDIChild (formulario Filho)  
- `Position`: poScreenCenter (onde aparecer o form)
- `WindowsState`: wsNormal, Minimizado e Maximizado

# TDBGrid
- `Options`:
  - dgIndicator
  - dgRowSelect
  - dgAlwaysShowSelection

