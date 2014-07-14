---
author: rogeriolino
comments: true
date: 2007-01-19 19:57:38+00:00
layout: post
slug: javascript-classe-math
title: 'Javascript: Classe Math'
wordpress_id: 67
categories:
- Javascript
tags:
- classe
- euler
- Javascript
- math
- max
- min
- pi
- random
- round
- util
---

Assim como a [classe Date()](http://rogeriolino.com/2007/01/11/javascript-classe-date/) uma outra classe nativa em várias linguagens que quebra um galho legal é a Math (Mathematical).

Além de contar com algumas funções ela também fornece valores de constantes ou valores matemáticos, como por exemplo PI e raiz quadrada de 2.

**Funções:**

**Math.round() **: Arredonda um valor real para inteiro. Se o valor da casa depois do ponto for maior ou igual a 5 é arredondado para cima, caso contrário para baixo;


    
    
    Math.round(4.5); // retorna 5
    Math.round(3.49); // retorna 3
    



**Math.random()** : Retorna um valor real e aleatório entre 0 e 1.


    
    
    Math.random(); // ex 0.56766776... (até 17 números depois do ponto)
    



**Math.max() **: Retorna o número de maior valor entre dois.


    
    
    Math.max(4,7); // retorna 7
    



**Math.min()** : Retorna o número de menor valor entre dois.

    
    
    Math.min(4,7); // retorna 4
    



**Constantes Matemáticas: **

    
    
    Math.E // valor de Euler (Oiler)
    Math.PI // valor de PI
    Math.SQRT2 // valor da raiz quadrada de 2
    Math.SQRT1_2 // valor da raiz quadrada de 0.5 (1/2)
    Math.LN2 // valor do Logaritmo Natural de 2 (ln 2)
    Math.LN10 // valor do Logaritmo Natural de 10 (ln 10)
    Math.LOG2E // valor do Logaritmo de E (Math.E) na base 2
    Math.LOG10E // valor do Logaritmo de E na base 10.
    



**Veja em ação:**

[Clique aqui](http://dev.rogeriolino.com/exemplos/javascript/math/index.html) para ver esses exemplos funcionando.

