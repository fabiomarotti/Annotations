# Windows Messages 

[link 1](http://theclub.com.br/Restrito/Revistas/201007/wind1007.aspx)

- Todos os controles VCL Delphi possuem um método chamado `Perform`, que é utilizado para o envio de mensagens tendo como destino o próprio controle.
-  parâmetros para uma mensagem devem ser do tipo int, integer ou word

- `SendMessage` : envio de mensagens para o aplicativo. Possui 4 parâmetros:
  - `Handle`: que é o endereço da janela destino da mensagem; 
  - `Msg`: onde passamos a constante que define a mensagem;   
  - `wParam` e `lParam` que são os parâmetros que a mensagem utiliza.

- Para adicionar uma mensagem à fila do thread associado a outra janela, você precisa usar a PostMessagefunção API do Windows.
~~~Delphi
PostMessage(WindowHandle, Msg, WParam, LParam);
~~~

> pula para o proximo controle da aplicação
~~~Delphi
// No evento OnKeyDown do Form

if (Key = Vk_return) then Perform(Wm_NExtDlgCtl,0,0);
~~~
