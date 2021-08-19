
## Teclas de Atalho

- `F9`  : Executar
- `F11` : Object Inspecto 
- `F12` : Alternar entre Código-View

- `Alt` + `G` : Ir para um número de linha    

- `Shift` + `seta` : Altera o tamanho de componetes (altura/largura) 

- `Ctrl` + `seta` : mover componente
- `Ctrl` + `F2`   : Cancelar Execução
- `Ctrl` + `H`    : Selecionar multiplos componentes
- `Ctrl` + `R`    : Buscar com substituir
- `Ctrl` + `J`    : Exibir lista de templates de "códigos", exemplo.: if, for, case,..
- `Ctrl` + `F`    : Buscar com caixa de dialogo.
- `Ctrl` + `E`    : Buscar sem caixa de dialogo.
- `Ctrl` + `O + U`  : Alternar letra/frase selecionada entre maiúscula/minúsculas.
- `Ctrl` + `K + E`  : Alternar frase para minúscula.
- `Ctrl` + `K + F`  : Alternar frase para maiúscula.

- `Ctrl` + `Shift` + `F9`   : Executar sem Debug
- `Ctrl` + `Shift` + `seta` : Alternar entre a Declaração e a Implementação de uma função/procedimento. (tambem move componentes na tela)
- `Ctrl` + `Shift` + `A`    : Importar no campo __uses__ bibliotecas referente a palavra sobre o curso do teclado.
- `Ctrl` + `Shift` + `C`    : (Class Completion) gerar implementação ou declaração de funções/procedimentos/property.
- `Ctrl` + `Shift` + `G`    : gerar ID para __interfaces__ (identifica caso aja outros executaveis)
- `Ctrl` + `Shift` + `I`    : Avança multiplas linhas selecionadas.
- `Ctrl` + `Shift` + `L`    : Refatoração de uma variavel (testar pag 56mc)
- `Ctrl` + `Shift` + `U`    : Recua multiplas linhas selecinadas.
- `Ctrl` + `Shift` + `V`    : Declara no campo __var__ a palavra posicionada posteriorente ao cursor do teclado.
- `Ctrl` + `Shift` + `0..9` : Adicionar/Remover uma BookMarker
- `Ctrl` +           `0..9` : Exibir o BookMarker 
- `Ctrl` + `Alt` + `F11`  : Project Manager 
- `Ctrl` + `Alt` + `P`    : Tool Palet

- `Alt` + `Shift` + `seta` : selecionar codigo, forma quadrada
- `Alt` + `Shift` + `F11`  : Structure

# BookMarks
- `Ctrl` + `Shift` + `0..9` : Cria/Remove uma marcação.
- `Ctrl` + `0..9` : Navega pelas macações.

# Debug
- `F9`: **Run** - Executar em Modo de Debug.
  - Executa todo o código ate o próximo breakpoint.
- `F8`: **Step Over** - (Passar por cima) : ir para proxima instrução.
- `F7`: **Trace Into** - (Rastrear em) : entrar no método em execução na linha atual.
- `Ctrl` + `F2`: **Program Reset** - Parar (não pausar) o debug.

# Configurações do Delphi (10.3)
- `ALterar tema da IDE (Dark)`
  - Tools / Options / Theme Manager / (Dark)

- `Habilitar Pacote Office`
  - Project / Options / Packages / (Microsoft Office 2000)

- `Limite do Desfazer (Ctrl + Z)`
  - Tools / Options / User Interface / Editor / (Undo limit)

- `Alterar resolução da tela ao Debugar` 
  - Tools / Options / User Interface / Form Designer / (Embedded designer)

- `Cria automaticamente os formulario em: Projects / Options / Application / Forms / (auto-create forms)`
  - Tools / Options / User Interface / Form Designer / (Auto create forms & data modules)

- `Alterar local de criação do Executavel da projeto`
  - Project / Options / Building / Delphi Compiler / (Output directory)
  - Project / Options / Building / Delphi Compiler / (Unit output directory)
    - Padrão:  `.\$(Platform)\$(Config)`
  - Project / Options / Building / Delphi Compiler / (Search Path) (*dcu* do projeto)
    - modules;
    - modules\.dcp;
    - modules\.dcu;
    - modules\dataset-serialize\src;
    - modules\restrequest4delphi\src


