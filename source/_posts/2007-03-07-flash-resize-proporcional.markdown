---
author: rogeriolino
comments: true
date: 2007-03-07 02:41:33+00:00
layout: post
slug: flash-resize-proporcional
title: 'Flash: Resize Proporcional'
wordpress_id: 77
categories:
- ActionScript
- Flash
tags:
- altura
- chivalrous
- Flash
- flashmasters
- forum
- height
- largura
- proporciona
- prototype
- resize
- width
---

Acabei de responder no [forum da FlashMasters](http://www.flashmasters.com.br/forum/) um tópico que se tratava sobre a seguinte dúvida:

O membro queria saber alguma função que redimensiona-se um determinado objeto mas mantendo a sua proporção. Por exemplo um MovieClip de tamanho 400x200 se eu aumentar a largura em 100 tenho que aumentar a altura em 50. Isso devido a razão entre os dois valores.

Então com um lápis na mão podemos chegar a seguinte fórmula para uma nova altura caso altere sua largura:


<blockquote>
**H =  dW . H/W + H**
Aonde:
_ H: Altura_
_W: Largura_
_dX:  delta da variável "X"_
</blockquote>



_Sabendo a fórmula para uma nova altura é facil chegar na da nova largura:_


<blockquote>**W = dH . W/H + W**</blockquote>


Agora então mãos a obra com as Actions:


    
    
    MovieClip.prototype.resizeW = function(w) {
        var dw = w - this._width;
        this._height += dw * (this._height / this._width);
        this._width = w;
    }
    
    MovieClip.prototype.resizeH = function(h) {
        var dh = h - this._height;
        this._width += dh * (this._width / this._height);
        this._height = h;
    }
    



Para utilizar:

    
    
    // redimensionando a partir da largura
    MovieClip.resizeW(novaLargura);
    
    // redimensionando a partir da altura
    MovieClip.resizeH(novaAltura);
    



Espero que seja útil.
