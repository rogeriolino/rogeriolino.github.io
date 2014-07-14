---
author: rogeriolino
comments: true
date: 2008-01-15 12:55:01+00:00
layout: post
slug: javascript-fade-in-fade-out
title: 'Javascript: Fade in, Fade out'
wordpress_id: 105
categories:
- CSS
- Javascript
tags:
- alpha
- CSS
- fade
- filter
- in
- Javascript
- opacity
- out
- style
- transição
---

Um efeito muito legal de transição é o fade, aonde o objeto surge gradativamente (in) ou some (out). Com o auxílio do CSS, definido pelo próprio javascript, usando opacity (alpha) conseguimos montar um exemplo.

Passando dois parâmetros a gente define o alvo (id do elemento HTML) e o tempo de demora da execução do efeito.

Código: 

    
    
    function fadeOut(id, time) {
        fade(id, time, 100, 0);
    }
    
    function fadeIn(id, time) {
        fade(id, time, 0, 100);
    }
    
    function fade(id, time, ini, fin) {
        var target = document.getElementById(id);
        var alpha = ini;
        var inc;
        if (fin >= ini) { 
            inc = 2; 
        } else {
            inc = -2;
        }
        timer = (time * 1000) / 50;
        var i = setInterval(
            function() {
                if ((inc > 0 && alpha >= fin) || (inc < 0 && alpha <= fin)) {
                    clearInterval(i);
                }
                setAlpha(target, alpha);
                alpha += inc;
            }, timer);
    }
    
    function setAlpha(target, alpha) {
    	target.style.filter = "alpha(opacity="+ alpha +")";
    	target.style.opacity = alpha/100;
    }
    



Exemplo:

    
    
    fadeOut("foto", 0.6);
    fadeIn("popup", 1);
    



[ Exemplo em funcionamento aqui.](http://dev.rogeriolino.com/exemplos/javascript/fade/index.html)
