---
author: rogeriolino
comments: true
date: 2007-01-23 17:15:28+00:00
layout: post
slug: css-position-fixed-ie
title: 'CSS: Position Fixed IE'
wordpress_id: 68
categories:
- CSS
tags:
- CSS
- fixa
- fixed
- ie
- ie6
- posicao
- position
- Tableless
- XHTML
---

Um **atributo** muito interessante quem tem na propriedade position é o **fixed**.

Com ele você pode posicionar um objeto no palco (como se fosse absolute) só que ele sempre estará na "mesma posição", mesmo rolando a tela.

Infelizmente o IE (até o 6) não reconhece esse atributo, mas antes de sairmos tentando bolar um código em javascript para ficar posicionando a janela quando o usuário rolar a tela. Vamos usar só o CSS.

**Pensando: **Poderíamos usar como **position** o **absolute** já que com ele a gente tem uma liberdade maior para posicionar o objeto. Mas ainda temos o problema com a rolagem.

Mas tem o **overflow**, podemos colocar como **auto** para criar uma barra de rolagem para o que ultrapassar o limite, e o nosso objeto continuará sempre no mesmo lugar.  **Pronto!**

Nos **browser espertos** (smarts) fica assim:


    
    
    #menu {
        top: 15%;
        left: 50px;
        width: 200px;
        padding: 20px 0px;
        border: 2px solid #CCCCCC;
        position: fixed;
    }
    



Dá para notar que é como estivéssemos colocando como absolute mesmo (_left, top_). Só isso basta.

Agora para o **IE** vamos colocar o CSS dentro de um comentário do HTML (que por sua vez só ele mesmo para ler como código o comentário):

    
    
    <!--[if IE]>
    <style type="text/css">
    html, body {
        height: 100%;
        overflow: auto;
    }
    #menu {
        position: absolute;
    }
    </style>
    <![endif]-->
    



Colocamos o **body** e o **html** com **overflow auto** e **altura 100%** para confirmar que sua altura é toda a janela (a visão do usuário). E definimos o objeto com **postion absolute**, não precisamos colocar **left** nem **top**, porque já foram passados acima, e só estamos **sobrescrevendo** (position).

[Veja esse exemplo funcionando](http://dev.rogeriolino.com/exemplos/css/position_fixed/index.html). Dê uma olhada no código-fonte.

Na internet podemos encontrar outros métodos para isto. Vi um que continha expressões javascript no CSS (coisa do IE) e outro que usava javascript puro para posicionar.

**Para mais exemplos, resultado da busca:**

[Powered Google](http://www.google.com.br/search?q=position+fixed+ie&ie=utf-8&oe=utf-8&rls=org.mozilla:t-BR;%20Alexa:official&client=firefox-a)
