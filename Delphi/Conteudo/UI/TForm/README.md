# TForm

- a) `Application.CreateForm(TfmClientes, fmClientes);` : Cria o Form; o proprietário é a aplicação.
- b) `fmClientes := TForm.Create(self);` : Cria o Form; o proprietário é ele mesmo.
- c) `fmClientes := TForm.Create(Application);` : Cria o Form; o proprietário é a aplicação.
- d) `fmClientes := TForm.Create(nil);` : Cria o Form; teoricamente sem proprietário; na prática é a aplicação.
- e) `fmClientes := TfmClientes.Create(self);` : Cria o Form; o proprietário é ele mesmo.
- f) `fmClientes := TfmClientes.Create(Application);` : Cria o Form; o proprietário é a aplicação.
- g) `fmClientes := TfmClientes.Create(nil);` : Cria o Form; teoricamente sem proprietário; na prática é a aplicação.
