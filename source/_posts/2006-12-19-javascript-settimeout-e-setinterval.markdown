---
author: rogeriolino
comments: true
date: 2006-12-19 17:09:14+00:00
layout: post
slug: javascript-settimeout-e-setinterval
title: 'Javascript: setTimeout() e setInterval()'
wordpress_id: 61
categories:
- Javascript
- Tutorial
tags:
- Javascript
- setinterval
- settimeout
- sorteio
- tutorial
---

São duas funções interessantes do Javascript, com elas podemos definir um intervalo de tempo que um evento irá acontecer.

A sintaxe das duas funções é praticamente idêntica. O que muda é como agem.

Sintaxe:

    
    
    window.setTimeout('funcao()', intervalo_em_milisegundos);
    window.setInterval('funcao()', intervalo_em_milisegundos);
    



As duas funções irão chamar uma segunda função passada por parâmetro no intervalo determinado também por parâmetro.

Sendo a setTimeout() chamando a função uma única vez. Enquanto a setInterval() chama a função "infinitamente" sempre no mesmo intervalo de tempo.

Para pausar a função usa-se clearInterval(). Passando como parâmetro o nome do seu intervalo.

Ex:

    
    
    var intervalo = window.setInterval(lerolero, 1000);
    function lerolero() {
        window.alert("Popup");
    }
    clearInterval(intervalo);
    



Juntando as duas funções podemos "brincar" fazendo por exemplo um script que simula um sorteio.

Ex:

    
    
    var intervalo = window.setInterval(function() {
        // corpo da funcao
    }, 50);
    
    window.setTimeout(function() {
        clearInterval(intervalo);
    }, 3000);
    



Explicando: A setInterval() vai executar o que for definido dentro de uma função passada como parâmetro em 50 em 50 milisegundos. Isso durante 3000 milisegundos (3 segundos), que é o tempo definido na setTimeout() para entrar na função que pausa a setInterval.

Deu pra entender né? Veja o script um pouco mais incrementado em funcionamento [aqui](http://dev.rogeriolino.com/exemplos/javascript/sorteio/index.html).

Você pode usar setInterval() para fazer um relógio também. Agora é só deixar com a criatividade de cada um.

**mais sobre:**

[http://javascript.about.com/library/blstvsi.htm ](http://javascript.about.com/library/blstvsi.htm)

[http://www.w3schools.com/js/js_timing.asp ](http://www.w3schools.com/js/js_timing.asp)
