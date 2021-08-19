# Configurações do Delphi

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

- `Configurar o tempo de execução/design`:
  - Setar um projeto do tipo __Package__
  - Project / Options / Description / (Usage Options) / (Designtime and runtime) e (Rebuild as needed)

- `Configurar o local dos arquivos _dcu_`:
  - Project / Options / Delphi Compiler / ...:
    - (DCP output directory): __dcu__
    - (Package output directory): __dcu__
    - (Unit output directory) : __dcu__
