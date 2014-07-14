---
author: rogeriolino
comments: true
date: 2008-02-18 20:11:09+00:00
layout: post
slug: javascript-rate-this
title: 'Javascript: Rate this'
wordpress_id: 106
categories:
- CSS
- Javascript
tags:
- classificar
- CSS
- DOM
- estrelas
- Javascript
- rate
- this
---

![Rate](http://rogeriolino.files.wordpress.com/2008/02/rate.png)


Quem nunca viu aquelas "_5 estrelas_" logo após algum artigo, foto, etc?

Pois então, esse script cria uma  sequência de links (**<a>**) de uma quantidade pré-definida para que o visitante possa taxar, classificar, o conteúdo da página. Seu visual é totalmente customizável através de folhas de estilos (**CSS**).

O código está contido na própria página do exemplo, e para usá-lo basta instanciar o objeto definindo a quantidade de "_estrelas_" e adicioná-lo em alguma tag (**append**):


    
    
    var r1 = new Rate(5);
    
    r1.onclick = function() {
        // input here your action
        alert(r1.getValue());
    }
    
    r1.setDefault(3);
    
    r1.append("example1");
    



Para visualizar o exemplo [clique aqui](http://dev.rogeriolino.com/exemplos/javascript/rate/index.html).
