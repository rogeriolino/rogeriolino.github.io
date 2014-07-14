---
author: rogeriolino
comments: true
date: 2007-04-01 15:32:22+00:00
layout: post
slug: javascript-graphic-generator
title: 'Javascript: Graphic Generator'
wordpress_id: 84
categories:
- CSS
- Javascript
tags:
- CSS
- DOM
- generator
- graficos
- graphic generator
- Javascript
- XHTML
---

![Gráfico](http://rogeriolino.files.wordpress.com/2007/04/grafico.jpg)

Esses dias um pouco inspirado com a aula de Probabilidade e Estatística, resolvi fazer um script para gerar gráficos de barras.

Você cria um novo objeto **Grafico **(sem acento mesmo - **new Grafico(n);** ) passando o número de barras como parâmetro e então a partir dele com set's e get's você gera o seu gráfico.

Não vou explicar aqui linha por linha porque o código não está pequeno e também porque está bem simples de entender. Mas havendo alguma dúvida é só deixar um comentário que logo eu respondo.

[Clique aqui para vê-lo funcionando](http://dev.rogeriolino.com/exemplos/javascript/grafico/index.html).

O código que gerou o gráfico da imagem ao lado é o seguinte:

    
    
    var grafico = new Grafico(11);
    grafico.setSize("200px");
    grafico.setTitle("Grafico de Barras");
    grafico.setSource("Fonte: Fictícia");
    grafico.setBarraSize(0, "80%");
    grafico.setBarraLabel(0, "manga");
    grafico.setBarraSize(1, "30%");
    grafico.setBarraLabel(1, "banana");
    grafico.setBarraSize(2, "50%");
    grafico.setBarraLabel(2, "maracuja");
    grafico.setBarraSize(3, "100%");
    grafico.setBarraLabel(3, "melancia");
    grafico.setBarraSize(4, "70%");
    grafico.setBarraLabel(4, "maracuja");
    grafico.setBarraSize(5, "76%");
    grafico.setBarraLabel(5, "pera");
    grafico.setBarraSize(6, "30%");
    grafico.setBarraLabel(6, "uva");
    grafico.setBarraSize(7, "47%");
    grafico.setBarraLabel(7, "melao");
    grafico.setBarraSize(8, "25%");
    grafico.setBarraLabel(8, "laranja");
    grafico.setBarraSize(9, "90%");
    grafico.setBarraLabel(9, "abacaxi");
    grafico.setBarraSize(10, "10%");
    grafico.setBarraLabel(10, "kiwi");
    



**[update]**

[Faça o download do exemplo aqui (.rar)](http://dev.rogeriolino.com/exemplos/javascript/grafico/Grafico.rar)

**[/update]**

