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
- `TRLReport`
- `TRLPDFFilter`

> Salvar Simples
~~~Delphi
var Caminho, NomePdf : String;
  // Preview
  TRLReport .Preview( TRLReport );
  
  // Salvar
  TRLReport .SaveToFile( Caminho + NomePdf );
  TRLReport .Prepare;
  
  // PDF
  TRLPDFFilter .FilterPages( TRLReport.Pages );
~~~

> Salvar com Caixa de Dialogo para Opções de Extensões
~~~Delphi
var
  priorfocus: TWinControl;
  filt: TRLCustomSaveFilter;
  fname: string;
  fext: string;
  firstpg: Integer;
  lastpg: Integer;
  SD    : TRLSaveDialog;
begin
  if not Assigned(FReport) then
  begin
    MessageDlg('Necessário gerar o relatório antes', mtInformation, [mbOk], 0);
    Exit;
  end;

  priorfocus := Screen.ActiveControl;
  try
    SD := TRLSaveDialog.CreateNew(nil);
    try
      SD.MaxPage := RLPreview.Pages.PageCount;
      filt := Nil;
      if (SelectedFilter <> nil) and (SelectedFilter is TRLCustomSaveFilter) then
        filt := TRLCustomSaveFilter(SelectedFilter);

      if Self.RLPreview.Pages.Title <> '' then
         SD.FileName := ExpandFileName(FileNameFromText(Self.RLPreview.Pages.Title))
      else if (filt <> nil) then
        SD.FileName := filt.FileName
      else
        SD.FileName := '';

      if not SD.Execute then
        Exit;

        if (SD.FileName = '') then
          raise Exception.Create(GetLocalizeStr(LocaleStrings.LS_FileNameIsEmpty));

      firstpg := SD.FromPage;
      lastpg := SD.ToPage;
      fname := SD.FileName;
      fext := ExtractFileExt(fname);
      if fext = '' then
      begin
        SD.ApplyExt(fname);
        fext := ExtractFileExt(fname);
      end;

      if (filt = Nil) or (LowerCase(filt.DefaultExt) <> LowerCase(fext)) then
        filt := SaveFilterByFileName(fname);

      if filt <> nil then
      begin
        filt.FileName := fname;
        filt.FilterPages(RLPreview.Pages, firstpg, lastpg, '', PrintOddAndEvenPages);
      end
      else
        RLPreview.Pages.SaveToFile(fname);
    finally
      SD.Free;
    end;
  finally
    if not Assigned(priorfocus) or not ((priorfocus is TCustomEdit) or (priorfocus is TCustomComboBox)) then
      priorfocus := E_PAGE;
    priorfocus.SetFocus;
  end;
~~~

# Imprimir
~~~Delphi
 if Assigned(TRLReport) then
    TRLReport.Print
  else
    MessageDlg('Necessário gerar o relatório antes', mtInformation, [mbOk], 0);    
~~~

# Enviar
