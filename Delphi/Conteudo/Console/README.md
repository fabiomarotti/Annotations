# Console
- File / New / Console Application

> Exemplo de estrutura básica em Delphi
~~~Delphi
program ProjetoConsole;

{$APPTYPE CONSOLE}

{$R *.res}

uses
  System.SysUtils;

var
  x : string;

begin
  Writeln(' Ola Mundo Binário! ');
  Readln(x);
end.
~~~

> Exemplo Console mesclado com interfaces de Form
~~~Delphi
var 
 x : String;

  // ---- Inicio: Código Console
  AllocConsole;
  try
    Write('Informe um valor para variavel X e precione [ENTER]: ') ;
    Readln(x) ;
      ShowMessage('Valor de X é: ' + x) ;
   finally
     FreeConsole;
   end;
   // --- Fim
~~~~ 


## Comandos
- Console.Write();
- Console.Readln();


