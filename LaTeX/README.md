# LaTeX
 Repositório com os estudos realizados sobre o sistema de edição de texto LaTeX. 
 
 - [MikTeX - Compilador (windows)](https://miktex.org/)
 - [TeXstudio - editor desktop](https://www.texstudio.org/)
 - [Texmaker - editor desktop](https://www.xm1math.net/texmaker/)
 - [Overlife - editor online](https://pt.overleaf.com/)

# Sintaxe

~~~
\documentstyle[twocolumn,12pt,a4]{article}
\usepackage{pacote}
\begin{document}
.
.
% comentário
.
\end{document}
~~~

## Secções
~~~
\part{parte}

\chapter{capítulo}

\section{secção}

\subsection{sub-secção}

\subsubsection{sub-sub-secção}

\paragraph

\subparagraph

~~~

## Formulas
~~~
$ \formula $
~~~

~~~
\[  \formula   \]
~~~

## Simbolos

~~~tex
$ a * x^2 +  b * x + c $
~~~
- Quantificadores
~~~
\exists
\infty
~~~

- Sobescrito e Sobrescrito
~~~
x^{2}  % x ao quadrado

x_{i}  % x indice i
~~~

- Frações
~~~
\frac{a}{b}  % a sobre b
~~~

- Raízes
~~~
\sqrt{x}     % raiz quadrada de x

\sqrt[3]{x}  % raiz cubica de x
~~~

- Funções
~~~
\log10
\sen
~~~

- Somatorio
~~~
\sum_{ n=0 }^{ \infty }  a_{n}^{2}
~~~

- Limite
~~~
\lim_{ x \rightarrow \infty }  \frac{ x^2 }{ x+1 }
~~~

- Integral
~~~
\int
~~~

# Pre-configurações de texto
~~~
% pré configurações
\author{Autor do documento}
\title{Titulo do documento}
\date{data}

% inserir atributos no texto
\maketitle

~~~

# Pacotes
~~~
\usepackage[portuguese]{babel} 
\usepackage[latin1]{inputenc}
\usepackage[utf8]{inputenc} 
\usepackage[T1]{fontenc} 
~~~

# Importações
~~~
\input{arquivo.tex}

~~~

# Referência
[Apostila de LaTeX UFF](http://each.uspnet.usp.br/sarajane/wp-content/uploads/2016/10/manual-latex-1.pdf)

[Prof. Thiago de Melo](http://www.rc.unesp.br/tmelo/latex/)

