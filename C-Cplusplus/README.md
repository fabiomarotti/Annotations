# C / C++

## IDE - Compiladores
- [Dev-C++](https://sourceforge.net/projects/orwelldevcpp/)
- [Falcon C++](https://sourceforge.net/projects/falconcpp/)
- [Code Blocks](https://www.codeblocks.org/)
  - Settings / Compiler / C:\Program Files\CodeBlocks\MinGW 
- [MSYS2](https://www.msys2.org/)
- [eclipse](https://www.eclipse.org/downloads/)

# conf
- -std=c99 (versão de 1999)

# Hello World
~~~C
#include <stdio.h>
#include <stdlib.h>

int main(){
    printf("Ola Mundo! \n");
    return 0;
}
~~~


# Variaveis de Ambiente (MSYS2)
- [ver](https://www.youtube.com/watch?v=HF95fQaQUDU)

# Declaraçaõ de Variaveis
> [Tipo_Variavel] : [Nome_Variavel]
~~~C
int       : inteiro;       // i% ou %d
short     : inteiro;       // i% ou %d
long      : inteiro;       // i% ou %d
double    : decimal;       // %f
float     : decimal;       // %f
char      : caracter;      // %c
string    : string;        // %s

  // %p       (endereço de memória)
  // %e ou %E (notação cientifica)
  // %%       (imprimi %)

void      : vazio;
signed    : + e -
unsigned  : +     // %u (modulo do numero)
~~~

# Operadores
- `+` , `-` , `*` , `/` , `%` (módulo)
- `==`, `!=`, `&&`, `||`, `>=`, `<=`, `>`, `<`

#### Grau de precedencia
- Associação da esquerda para direita  
  - 1. ()
  - 2. *, / , %
  - 3. +, - 
  - 4. <, <=, >, >=
  - 5. ==, !=
- Associação da direita pra esquerda
  - --, ++
  - = , += , -+ , *= , /= , %=  


~~~C
x += 1;  // x = x + 1;
x -= 1;  // x = x - 1;
x *= 1;  // x = x * 1;
x /= 1;  // x = x / 1;
x %= 1;  // x = x % 1;
//-------------------
++i;  //pre-incremento: incrementa antes de executar
i++;  //pos-incremento: incrementa depois de executar
~~~


# Bibliotecas
- `#include <stdio.h>`  : para printf
- `#include <stclib.h>` : malloc, sizof
- `#include <cctype>`   : para Uppcase
- `#include <ctype>`    : para depuração 
- `#include <string>`   : para manipular Strings
- `#include <vector>`   : ??
- `#include <deque>`    : ??
- `#include <cmath>`    : para constante pi, cos, sin, tan, acos, asin

# Caracteres representados por seqüências de escape
- `\n` : nova linha 
- `\t` : tabulação
- `\b` : retrocesso 
- `\r` : retorno de carro
- `\f` : alimentação de formulário 
- `\\` : contrabarra
- `\’` : apóstrofo 
- `\"` : aspas
- `\0` : o caráter NULL
- `\xxx` : qualquer padrão de bits xxx em octal

# Entrada e Saída
~~~C
scanf(""
scanf("%var1%var2", &v1 
~~~

~~~C
printf("Ola %s", nome);
~~~

# Estrutura Condicionais
~~~C
if (x > 0){
  // codigo
}

if(x>0){
  // codigo
}else{
  // codigo
}
~~~

~~~C
while(i<5){
  i = i+1;
  // codigo
}
~~~

~~~C
do{
 cont += 1;
 // codigo
}while(cont < 5);
~~~

~~~C
switch( cond ){
  case("A") :
      // codigo
      break;
  case("B"):
      // codigo
      break;
  default:
  // executar
}

~~~C
// FOR e suas partes
for( parte3 ; parte2 ; parte1 ){
    parte1 -> atualização (declaração e iniciação de variavel: executador apenas uma vez)
    parte2 -> condição
    parte3 -> inicialização (sofre alterações)
}

// FOR omitido a inicialização
for(  ; parte2 ; parte1 ){
    parte1 -> atualização (declaração e iniciação de variavel: executador apenas uma vez)
    parte2 -> condição
 }

for (int i=1, j=1 ; i<5 ; i++, j++){
// codigo
}
~~~

# Funções
- `sizeof(x)`     : tamanho em bytes de memoria de uma variavel x
- `getchar()`     : ler caracter;
- `system("cls")` : comandos de PROMPT

# Depuração
- (Code Blocks) : Debug / Step Into
# Referências
[Continuar apostila](file:///C:/Users/Fabio/Downloads/Estrutura%20de%20dados%20-%20Unicamp%20Prof%20Ivan.pdf)
[recursão](https://www.youtube.com/watch?v=5SHGxN7_Snc)



