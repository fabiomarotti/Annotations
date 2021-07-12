# Relatórios em Delphi


# Force Report
### Instalação

[download](https://github.com/fortesinformatica/fortesreport-ce)

- Criar um diretório proprio para as Livrarias do Delphi
- Descompactar arquivo 
- Abrir projeto Delphi: `fortesreport/Packages/frce.dpk`
- Project Manager: frce.bpl / btn_direito / Build
- Project Manager: frce.bpl / btn_direito / Install
- Library
  - v10.2 : `Tools / Options / Envirment Options / Delphi Options / Library` 
  - v10.3 : `Tools / Options / Language / Delphi / Library`
  - `C:/pasta../Sources`



# Salvar
> Componentes add
- `RLReport`
- `RLPDFFilter`

~~~Delphi
var Caminho, NomePdf : String;
  // Preview
  RLReport .Preview( RLPreview );
  
  // Salvar
  RLReport .SaveToFile( Caminho + NomePdf );
  RLReport .Prepare;
  
  // PDF
  RLPDFFilter .FilterPages( RLReport.Pages );
~~~

# Enviar
