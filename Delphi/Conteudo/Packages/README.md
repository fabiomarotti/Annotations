# Packages (.bpl)

### Pre-Configuração
- Pacotes são exibidos em `Project / Options /  Packages / (Design packages) / (Caminho do .bpl)`
- Configurar o tempo de execução/design:
  - Setar um projeto do tipo __Package__
  - `Project / Options / Description / (Usage Options) / (Designtime and runtime) e (Rebuild as needed)`
- Configurar o local dos arquivos _dcu_:
  - `Project / Options / Delphi Compiler / `:
    - `(DCP output directory)`: __dcu__
    - `(Package output directory)`: __dcu__
    - `(Unit output directory)` : __dcu__
- Para Compilar ou Instalar um Package:
  - `btnDireito / Build` : Compilar
  - `btnDireito / Install` : Instalar     


### Informações sobre Packages
- `*.dproj` (Delphi Project) : arquivo fonte (Nutela) do Projeto do Pacote
- `*.dpk` (Delphi Package) : arquivo fonte (Raiz) do Projeto do Pacote [ver+](http://docwiki.embarcadero.com/RADStudio/Sydney/en/Delphi_Package_Source_File_(*.dpk))
- `*.bpl` (Borland Package Library) : é uma biblioteca específica para sistemas desenvolvidos em Delphi. (tipo DLL: Dinamic Link Library) [ver+](http://docwiki.embarcadero.com/RADStudio/Sydney/en/API_(*.bpl,_*.dylib,_*.so))
- `*.dcu` (Delphi Compiled Unit) : são arquivos compilados de cada unit em um projeto. [ver+](http://docwiki.embarcadero.com/RADStudio/Sydney/en/Delphi_Compiled_Unit_File_(*.dcu))
- `*.dcp` (Delphi Compiled Package)  : é um arquivo de pacote compilado, que consiste em ser uma imagem binária que contém um cabeçalho de pacote e a concatenação de todos os arquivos de unidade compilados em Delphi em seu pacote. [ver+](http://docwiki.embarcadero.com/RADStudio/Sydney/en/Delphi_Compiled_Package_File_(*.dcp))
  - Local padrão da DCP: `C:\Users\Public\Documents\Embarcadero\Studio\21.0\DCP`
- O Projeto Package possui duas pastas:
  - `Contains` : possui arquivos *unit.pas*
  - `Requires` : possui arquivos *rtl.dcp*
  - oculta o diretrio de outras pastas ao projeto 
- Para um TipoClasse aparecer no Object Inspector, precisa ser: TPersistent, TComponent, ..
  - TPersistent: prove funcionalidade para persistit no `dfm` 
  - TComponent herda de TPersistent
- [ver+](https://www.devmedia.com.br/quick-tips-como-trabalhar-com-packages-no-delphi/16421)


---- 






