# Embarcadero Delphi 
[site oficial](https://www.embarcadero.com/br/)
- 1995 Borland (Turbo Pascal) -> para Windows 16-bit 3.1
- 2006 CodeGear 
- 2008 Embarcadero
- Ambiente de Desenvolvimento (ferramenta/conceito)
- RAD (Rapid Applicaiton Development)
- Linguagem Pascal


> versões da IDE RAD Studio 
- RAD Studio 10.0 (Seattle) [2015]
- RAD Studio 10.1 (Berlim) [2016]
- RAD Studio 10.2 (Tokyo)
- RAD Studio 10.3 (Rio)
- RAD Studio 10.4 (Sydney)

> Arquivos 
- Executaveis (Project Manager)
  - `/Win32/Debug` compilar com o Debug selecionado (aquivo maior: Desenvolvimento)
  - `/Win32/Release` compilar com o Release selecionado (arquivo menor : Final)
  - `*.dcu` arquivo pre-compilado, auxiliar o *.exe
- `VCL Form Application` 
  - `Delphi Unit` : 
    - `*.pas` : arquivo de código
    - `*.dfm` : informações complementares de um formulário
    - (../Forms/uFrmPrincipal) -> (Objeto: frmPrincipal)
    - (../Forms/FrmPrincipalU)
  - `Delphi projects` : informações do Projeto
    - `*.dproj` : Usar este arquivo para editar o projeto
    - `*.dproj.local` 
    - `*.dpr`
    - `*.res` : arquivos de icones, imagens, outros
    - (../Projeto/Agenda)
    - `~arquivo` arquivos de backup
- `VCL Form `
  - `Delphi unit (*.pas)` : (../Forms/uFrmCadastrar) -> (Objeto: frmCadsatrar)
- `DataModule`

## Componentes
- `TMainMenu` (Standard)
- `TPanel` (Standard)
- `TButton` (Standard) : Botão
- `TPageControll` (Win32) > (new Page)
- `TDBGrid` (Data Controls)
- `TLabeledEdit` (Additional)
- `TSpeedButton` (Additional) : Botão

## Teclas de Atalho
- `Ctrl` + `seta` : mover componente
- `Ctrl` + `Shift` + `seta` : alterar tamanho do componente
