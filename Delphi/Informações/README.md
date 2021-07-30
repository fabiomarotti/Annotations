# Informações sobre o Embarcadero Delphi

[Site (oficial)](https://www.embarcadero.com/br/), [DocWiki Embarcadero](http://docwiki.embarcadero.com/), [Exemplos (oficial)](http://docwiki.embarcadero.com/CodeExamples/Sydney/en/Code_Examples_Index), [Trechos a estudar](http://www.linhadecodigo.com.br/delphi.aspx)

> Informações:
- Delphi é um Ambiente de Desenvolvimento (ferramenta/conceito)
- RAD (Rapid Applicaiton Development)
- Linguagem Pascal
- VCL (Visual Component Library)
- CLX (Component Library for Cross Platform) 
  - Borland Kylix 

> História:
- 1995 : Borland (Turbo Pascal) -> para Windows 3.1 (16 bits)
- 2006 : CodeGear 
- 2008 : Embarcadero

> versões: 
- Delphi 1 [1995]
- Delphi 7 [2002]
- Delphi 2010
- Delphi XE
- Delphi XE2 [2011] *
- Delphi XE8 [2015]
- RAD Studio 10.0 (Seattle) [2015]
- RAD Studio 10.1 (Berlim) [2016]
- RAD Studio 10.2 (Tokyo) [2017] *
- RAD Studio 10.3 (Rio)
- RAD Studio 10.4 (Sydney)

> Arquivos importantes no Delphi:
- Executaveis (Project Manager)
  - `/Win32/Debug` compilar com o Debug selecionado (aquivo maior: Desenvolvimento)
  - `/Win32/Release` compilar com o Release selecionado (arquivo menor : Final)
  - `*.dcu` arquivo pre-compilado, para linkar/construir o arquivo `*.exe`
- `VCL Form Application` 
  - `Delphi Unit` : 
    - `*.pas` : arquivo de código
    - `*.dfm` : informações complementares de um formulário
      - ../Forms/uFrmPrincipal -> (Objeto: frmPrincipal)
      - ../Forms/FrmPrincipalU
  - `Delphi projects` : informações do Projeto
    - `*.dproj` : Usar este arquivo para editar o projeto
      - ../Projeto/Nome_Projeto 
    - `*.dproj.local` 
    - `*.dpr` : **Arquivo para se abrir os projetos**
    - `*.res` : arquivos de icones, imagens, outros
    - `~arquivo` : arquivos de backup
- `VCL Form `
  - `Delphi unit (*.pas)`
    -  ../Forms/uFrmCadastrar -> (Objeto: frmCadsatrar)
- `Unit` arquivo: *.pas

> Principais Abas para Componentes:
- `Standard` : Componentes como botões, botões de rádio, caixa de lista, caixa Box, barras de rolagem, recursos para edição de texto
- `Additional` : Complementa o Standar com exibição  de  textos,  imagens, botões
- `Win32` : Componentes como zoom, controle deslizantes, barras de progresso, barras de status, ícones, barras de ferramenta
- `System` : Componentes avançados para sistema operacional, como conexão OLE, DDE, multimídia e temporização
- `Data Access` : Conexão com banco de dados e controles de exibição de dados.
- `Data Control` :  Recursos **Standard** e **Additional**, porem os componentes estão ligados ao Banco de Dados
- `dbExpress` : conexão  com  bancos  de  dados  SQL
- `DataSnap` :
- `ADO` : ActiveX Data Objects
  - OLE DB (drivers  de  acesso) 
  - MDAC (Microsoft  Data  Access  Components)
- `Interbase`: SGBD Embarcadero (Sistemas de Banco de Dados da Embarcadeiro)
- `WebServices`: conexão Web services aseados em XML/SOAP
- `Internet` e `Internet Express`: recursos para navegadores

> `Two-Way-Tool` (ferramenta de duas vias)
- Conforme  o  formulário  recebe  componentes  a  Unit  instantaneamente  é  alterada. 
