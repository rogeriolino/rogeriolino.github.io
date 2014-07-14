---
author: rogeriolino
comments: true
date: 2007-03-21 03:27:44+00:00
layout: post
slug: javascript-image-preloader
title: 'Javascript: Image Preloader'
wordpress_id: 81
categories:
- Javascript
tags:
- carregando
- DOM
- image
- imagem
- Javascript
- preloader
- style
---

Conforme prometido aqui um exemplo de preloader de imagem feito em Javascript:

[Clique aqui para visualizar](http://dev.rogeriolino.com/exemplos/javascript/image_preloader/index.html)


    
    
    var bgColor = "#FFFFFF";
    var bgImage = "http://www.../loading.gif";
    var bgRepeat = "no-repeat";
    var bgPosition = "center center";
    var borderWidth = "3px";
    var borderStyle = "solid";
    var borderColor = "#3366FF";
    
    var loadImage = function(w, h, url, target) {
        var img = new Image(w, h);
        img.src = url;
        img.style.visibility = "hidden";
        var molde = document.createElement("div");
        molde.setAttribute("id", "molde");
    
        var style = molde.style;
        style.border = borderWidth+" "+borderStyle+" "+borderColor;
        style.background = bgColor+" url("+bgImage+") "+bgRepeat+" "+bgPosition;
        style.width = img.width+"px";
        style.height = img.height+"px";
    
        document.getElementById(target).appendChild(molde);
        molde.appendChild(img);
        img.onload = function() {
            this.style.visibility = "visible";
            molde.style.background = bgColor;
        }
    }
    



Nesse caso ao invés de aplicar o **background** na tag **img**, apliquei numa **div** que funciona como uma **moldura**. E está de fácil personalização, bastando apenas alterar as variáveis globais.

O código é de fácil entendimento, deixa-se a imagem transparente e quando ela carregada (**onload**) ela "volta" a ser visível.

Para usar coloque isso no HTML:

    
    
    /*
     * largura: largura da imagem em pixel
     * altura: altura da imagem em pixel
     * url: caminho para a imagem
     * alvo: id da tag aonde deverá ser adicionada a imagem
     */
    var imagem = new loadImage(largura, altura, url, alvo);
    



Qualquer dúvida ou sugestão só comentar.
