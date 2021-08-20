# Thread
- Processamento bruto (banco de dados, arquivos, verificações constantes) deixe na Thread
- Manipulação da Tela deixa com o Main


- Synchronize:  É garantir que uma região crítica seja acessada por apenas um indivíduo por vez. Também chamado de exclusão mútua
  - consome Main Thread
- Main Thread: (estar desocupado) deixar o processamento pesado para o Thread, pois o Main Thread precisa receber as mensagens do Windows e respondê-las para não aparentar estar congelado ou não respondendo
- Thread-safe : só um Thread pode manipular o visual por vez


### Referência
[link 1](https://extremeprogramming.wordpress.com/2011/12/19/o-que-voce-precisa-saber-sobre-threads-delphi/)
