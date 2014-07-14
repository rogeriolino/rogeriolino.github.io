---
author: rogeriolino
comments: true
date: 2007-03-16 18:27:11+00:00
layout: post
slug: css-loading-image
title: 'CSS: Loading Image'
wordpress_id: 80
categories:
- CSS
tags:
- CSS
- image
- loading
- XHTML
---

Podemos simular um pré-carregamento de uma imagem utilizando a propriedade CSS** background** setando um outra imagem, na qual informará o carregamento da imagem.

    
    
    img {
        background: #ffffff url(loading.gif) no-repeat center center;
    }
    



E pronto, mas uma observação um tanto lógica e óbvia que deve se fazer é sobre o tamanho da imagem de fundo, que deve ser pequena para ser mostrada rapidamente.

[Aqui você vê um exemplo](http://dev.rogeriolino.com/exemplos/css/loading_image/index.html)

Uma maneira mais útil de utilizar isso seria com **javascript** com a função **onLoad** para só mostrar a imagem depois dela totalmente carregada.

Liberando um tempo vago darei um update nesse post com o exemplo já utilizando javascript.

**[update]**
Link para o exemplo com Javascript:
[http://rogeriolino.com/2007/03/21/javascript-image-preloader/](http://rogeriolino.com/2007/03/21/javascript-image-preloader/)
**[/update]**
