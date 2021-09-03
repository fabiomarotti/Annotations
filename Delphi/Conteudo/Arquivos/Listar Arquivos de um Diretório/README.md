# Listar Arquivos de um Diretório

~~~Delphi
procedure ListarArquivos(Diretorio: string; Sub:Boolean);
var
  F: TSearchRec;
  Ret: Integer;
  TempNome: string;

begin
  Ret := FindFirst(Diretorio+'\*.*', faAnyFile, F);
  try
    while Ret = 0 do
    begin
      if TemAtributo(F.Attr, faDirectory) then
      begin
        if (F.Name <> '.') And (F.Name <> '..') then
          if Sub = True then
          begin
            TempNome := Diretorio+'\' + F.Name;
            ListarArquivos(TempNome, True);
          end;
      end
      else
      begin
        memLista.Lines.Add(Diretorio+'\'+F.Name);
      end;
        Ret := FindNext(F);
    end;
  finally
  begin
    FindClose(F);
  end;
end;
~~~~ 
