# TForm

### Instânciando um TForm

- a) `Application.CreateForm(TfmClientes, fmClientes);` : Cria o Form; o proprietário é a aplicação.
- b) `fmClientes := TForm.Create(self);` : Cria o Form; o proprietário é ele mesmo.
- c) `fmClientes := TForm.Create(Application);` : Cria o Form; o proprietário é a aplicação.
- d) `fmClientes := TForm.Create(nil);` : Cria o Form; teoricamente sem proprietário; na prática é a aplicação.
- e) `fmClientes := TfmClientes.Create(self);` : Cria o Form; o proprietário é ele mesmo.
- f) `fmClientes := TfmClientes.Create(Application);` : Cria o Form; o proprietário é a aplicação.
- g) `fmClientes := TfmClientes.Create(nil);` : Cria o Form; teoricamente sem proprietário; na prática é a aplicação.

----

- 1) se criar através de CreateForm, que é um método de TApplication, você passa como parâmetro a instância da classe e o nome do seu objeto (TfmClientes, fmClientes);
- 2) se criar através de Create - método de TForm, entre outros - você passa como parâmetro o proprietário do componente criado (no caso o Form).
  - 2.1.) se o proprietário for a aplicação, o Form só será destruído quando você finalizar o aplicativo ou se você declarar Free ou Destroy no seu programa; (casos a, c, d, f, g);
  - 2.2.) se o proprietário for ele mesmo (self), o form terá que ser destruído por você;
  - 2.3.) se você criar, por exemplo, Form2 e passar como proprietário Form1; no momento em que Form1 for destruído, Form2 também o será.

> Quanto à melhor maneira, depende de como você quer controlar a aplicação, mas leve em conta que enquanto um objeto não é destruído, ele está na memória.
