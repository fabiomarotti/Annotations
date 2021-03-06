# Windows Messages 
- `SendMessage` : Envia uma mensagem para a janela e aguarda o retorno para continuar a execução. (Sincrono) 
  - `Perform` :  envia-se uma mensagem para a própria janela
- `PostMessage` : Envia uma mensagem para a janela e não aguarda o retorno para continuar a execução. (Assíncrono)






- Todos os controles VCL Delphi possuem um método chamado `Perform`, que é utilizado para o envio de mensagens tendo como destino o próprio controle.
-  parâmetros para uma mensagem devem ser do tipo int, integer ou word

- `SendMessage` : envio de mensagens para o aplicativo. Possui 4 parâmetros:
  - `Handle`: que é o endereço da janela destino da mensagem; 
  - `Msg`: onde passamos a constante que define a mensagem;   
  - `wParam` e `lParam` que são os parâmetros que a mensagem utiliza.

~~~Delphi
function SendMessage(
                        hWnd: HWND     ; 
                        Msg: UINT      ; 
                        wParam: WPARAM ; 
                        lParam: LPARAM  )   : LRESULT;  stdcall;
~~~                      


- Para adicionar uma mensagem à fila do thread associado a outra janela, você precisa usar a PostMessagefunção API do Windows.
~~~Delphi
PostMessage(WindowHandle, Msg, WParam, LParam);
~~~

> pula para o proximo controle da aplicação
~~~Delphi
// No evento OnKeyDown do Form

if (Key = Vk_return) then Perform(Wm_NExtDlgCtl,0,0);
~~~

------ 

#### Passar o foco usando Enter
> O método SendMessage envia uma mensagem *WM_NEXTDLGCTL* ao handle do próprio formulário para que o mesmo passe o foco do componente ativo para o próximo da janela. <br>
> Envia-se uma mensagem para a própria janela.

- Formulário VLC:
  - Propriedade: `KeyPreview`: True.
  - Evento: `OnKeyPress` : (Codigo abaixo)
  
~~~Delphi
// Enter #13
if Key = #13 then 
begin
  Key := #0;
  SendMessage(handle, WM_NEXTDLGCTL, 0, 0);
end;
~~~~ 

> Modo alternativo, utilizando-se do `Perform` da classe `TControl`. <br>
> Não há a necessidade de passar o *handle* da janela visto que este método envia mensagens apenas para sua própria janela.

~~~Delphi
// Enter #13
 if Key = #13 then 
 begin
  Key := #0;
  Perform( WM_NEXTDLGCTL ,  0 ,   0 );
end;
~~~~ 

# Referências
[link 1](http://theclub.com.br/Restrito/Revistas/201007/wind1007.aspx)
[link 2](https://www.devmedia.com.br/windows-messages/1243)
