---
author: rogeriolino
comments: true
date: 2006-12-16 13:30:25+00:00
layout: post
slug: pullquote
title: Pullquote
wordpress_id: 60
categories:
- CSS
- Tableless
- XHTML
tags:
- blockquote
- CSS
- Javascript
- jornal
- pullquote
- quote
- Tableless
- XHTML
---

Pullquote é um efeito utilizado em jornais (revistas) para destacar uma certa parte do texto. Um exemplo aqui: [link](http://www.mykiss.de/figs/css.1111.gif).

Esses efeitos podem ser criados na sua página usando CSS, há quem use também Javascript. Nesse exemplo usaremos apenas CSS.

Crie um novo arquivo HTML.  O texto que receberá um destaque ficará assim, dentro da tag blockquote:


<blockquote><blockquote class="pull">Texto aqui dentro</blockquote></blockquote>


No CSS definimos o tamanho (largura) da caixa, uma borda em cima e em baixo, texto alinhado ao centro. E pronto.


    
     
    blockquote.pull {
        width: 170px;
        border-top: 3px solid #CC0099;
        border-bottom: 3px solid #CC0099;
        text-align: center;
        float: right;
        margin: 0px 20px;
        padding: 15px;
    }
    



Aí como podemos ver a caixa irá flutuar para a direita, podendo ser alterado como prefirir (left/right).

O exemplo final desse tutorial você confere aqui: [pullquote](http://dev.rogeriolino.com/exemplos/css/pullquote/index.html).

** Veja mais sobre:**

Pullquote apenas com CSS:


<blockquote>[http://www.sitepoint.com/test/pullquote.htm](http://www.sitepoint.com/test/pullquote.htm) (inglês)
[ http://www.brpoint.net/arquivo/css/pull-quotes.html](http://www.brpoint.net/arquivo/css/pull-quotes.html) (português)</blockquote>


Pullquote com Javascript:


<blockquote>[http://www.fiftyfoureleven.com/sandbox/weblog/2004/jun/javascript-pullquote/](http://www.fiftyfoureleven.com/sandbox/weblog/2004/jun/javascript-pullquote/) (inglês)</blockquote>
