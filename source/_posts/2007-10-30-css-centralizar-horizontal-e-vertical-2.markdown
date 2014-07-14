---
author: rogeriolino
comments: true
date: 2007-10-30 01:30:47+00:00
layout: post
slug: css-centralizar-horizontal-e-vertical-2
title: 'CSS: Centralizar Horizontal e Vertical #2'
wordpress_id: 97
categories:
- CSS
- Tableless
- Tutorial
- XHTML
tags:
- absolute
- centralizar
- CSS
- firefox
- hack
- horizontal
- ie
- opera
- table-cell
- Tableless
- tutorial
- vertical
- vertical-align
---

Há algum tempo postei sobre como centralizar verticalmente e horizontalmente usando CSS, o que gerou alguns posts de visitantes revoltados porque não funcionava no IE7, fato que na época eu não tinha testado para essa versão do IE.

Então, mesmo depois de muito tempo da versão já lançada, deixo um novo post testados nos browsers Firefox 2, IE6, IE7 e Opera 9.


    
    
    html, body {
        width: 100%;
        height: 100%;
        padding: 0px;
        margin: 0px;
    }
    
    #table {
        width: 100%;
        height: 100%;
        position: static;
        display: table;
        *overflow: hidden; /* hack para o IE6 e IE7 */
        *position: relative; /* hack para o IE6 e IE7 */
    }
    
    #cell {
        vertical-align: middle;
        display: table-cell;
        position: static;
        *top: 50%; /* hack para o IE6 e IE7 */
        *position: absolute; /* hack para o IE6 e IE7 */
    }
    
    #conteudo {
        top: -50%;
        width: 500px;
        margin: auto;
        position: relative;
        background: red;
    }
    



[link para o outro post e comentários](http://rogeriolino.com/2007/01/17/css-centralizar-horizontal-e-vertical/)
