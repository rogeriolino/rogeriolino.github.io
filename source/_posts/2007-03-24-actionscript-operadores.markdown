---
author: rogeriolino
comments: true
date: 2007-03-24 21:40:27+00:00
layout: post
slug: actionscript-operadores
title: 'ActionScript: Operadores'
wordpress_id: 82
categories:
- ActionScript
- Flash
tags:
- ActionScript
- adobe
- ajuda
- exemplo
- Flash
- help
- livedocs
- operadores
---

Operadores são caracteres que servem para especificar como combinar, comparar ou modificar os valores de um expressão.
**Operadores Mais Utilizados:**

**+** (adição)

Adiciona um número, variável numérica, à expressão ou concatena (une) Strings.
**Ex.:**

    
    
    var n:Number = A + 10;
    var s:String = "Foo" + "bar";
    



**+=** (atribuição)

Atribui à expressão1 o valor da expressão1 mais o valor da expressão2.
**Ex.:**

    
    
    var s:String = "Foo";
    s += " bar";
    trace(s) // "Foo bar"
    
    var n:Number = 10;
    n += 2; 
    trace(n) // 12
    



**[]** (acesso à array)

Inicialize uma nova array (vetor ou matriz) com os elementos especificados, ou acessa os elementos através de um índice (inteiro).
**Ex.:**

    
    
    // inicializando um vetor com 3 posições
    var frutas:Array = ["banana", "manga", "uva"];
    
    // minhaFruta irá receber "manga"
    var minhaFruta:String = frutas[1];
    
    // alterou o valor da posição 0 do vetor de "banana" para "abacaxi"
    frutas[0] = "abacaxi";
    
    // inicializando uma matriz 3 por 3
    var matriz:Array = [
        [1, 2, 3], 
        [4, 5, 6], 
        [7, 8, 9]
    ]; 
    
    // n recebe o valor da posição 2,2 da matriz, n = 5
    var n:Number = matriz[2, 2]; 
    



**=** (atribui/recebe)

Atribui o valor da expressão2 (direita) à expressão1 (esquerda).
**Ex.:**

    
    
    var str:String = "Foobar";
    var n:Number = 15;
    



**--** (decremento)

Decrementa em 1 a variável. Caso venha antes da expressão (esquerda) terá maior relevância, a variável será decrementada primeiro, caso venha depois da expressão (direita) só será feita depois.
**Ex.:**

    
    
    var n1:Number = 10;
    trace(--n1); // 9
    
    var n2:Number = 10;
    trace(n2--); // 10
    



**/** (divisão)

Divide a expressão1 pela expressão2.
**Ex.:**

    
    
    var a:Number = 12;
    var b:Number = 3;
    trace(a / b); // saída: 4
    



**==** (igualdade)

Testa a igualdade de duas expressões.
**Ex.:**

    
    
    var a:Number = 5;
    var b:Number = 10;
    var c:Number = 5;
    
    trace(a == b); // false
    trace(a == c); // true
    



**>** (maior que)

Compara duas expressções e determina se a expressão1 é maior que a expressão2, se for retorna true.
**Ex.:**

    
    
    var a:Number = 5;
    var b:Number = 10;
    
    trace(a > b); // false
    trace(b > a); // true
    



**>=** (maior ou igual que)

Compara duas expressões e determina se a expressão1 é maior ou igual que a expressão2, se for retorna true.
**Ex.:**

    
    
    var a:Number = 5;
    var b:Number = 5;
    var c:Number = 7;
    
    trace(a >= b); // true
    trace(c >= b); // true
    



**++** (incremento)

Incrementa em 1 a variável. Caso venha antes da expressão (esquerda) terá maior relevância, a variável será incrementada primeiro, caso venha depois da expressão (direita) só será feita depois.

**Ex.:**

    
    
    var n1:Number = 10;
    trace(++n1); // 11
    
    var n2:Number = 10;
    trace(n2++); // 10
    



**!=** (desigualdade/diferente)

Testa a desigualdade de duas expressões.
**Ex.:**

    
    
    var a:Number = 5;
    var b:Number = 10;
    var c:Number = 5;
    
    trace(a != b); // true
    trace(a != c); // false
    



**<** (menor que)

Compara duas expressções e determina se a expressão1 é menor que a expressão2, se for retorna true.
**Ex.:**

    
    
    var a:Number = 5;
    var b:Number = 10;
    
    trace(a < b); // true
    trace(b < a); // false
    



**<=** (menor igual que)

Compara duas expressões e determina se a expressão1 é menor ou igual que a expressão2, se for retorna true.
**Ex.:**

    
    
    var a:Number = 5;
    var b:Number = 5;
    var c:Number = 7;
    
    trace(a <= b); // true
    trace(b <= c); // true
    



**&&** (E lógico)

Executa uma operação booleana nos valores de ambas expressões.
**Ex.:**

    
    
    var n:Number = 50;
    if ((n > 10) && (n < 80)) {
        trace("n está entre 10 e 80");
    }
    



**!** (NÃO lógico)

Inverte o valor booleano da variável ou expressão (negação).
**Ex.:**

    
    
    var b:Boolean = false;
    if (!b) {
        trace("Condição passada como true");
    }
    



**||** (OU lógico)

Executa uma operação booleana nos valores de ambas expressões.
**Ex.:**

    
    
    var n:Number = 100;
    if ((n < 10) && (n > 80)) {
        trace("n é menor que 10 ou maior que 80");
    }
    



**%** (módulo/mod)

Calcula o resto da divisão entre a expressão1 pela expressão2.
**Ex.:**

    
    
    var a:Number = 10;
    var b:Number = 3;
    
    trace(a%b); // 1
    



***** (multiplicação)

Multiplica a expressão1 pela expressão2.
**Ex.:**

    
    
    var a:Number = 4;
    var b:Number = 3;
    
    trace(a*b); // 12
    



**-** (subtração)

Usado para subtrair ou negar, transformar em negativo, expressões.
**Ex.:**

    
    
    var a:Number = 8;
    var b:Number = 2;
    
    trace(a-b); // 6
    trace(-(a-b)); // -6
    



**-=** (atribuição de decremento)

Atribui à expressão1 o valor da expressão1 menos a expressão2.
**Ex.:**

    
    
    var a:Number = 5;
    a -= 3;
    
    trace(a); // 2
    




Para saber mais sobre operadores do Actionscript veja no próprio help do Flash, ou no [LiveDocs da Adobe](http://livedocs.adobe.com/flash/8/)

