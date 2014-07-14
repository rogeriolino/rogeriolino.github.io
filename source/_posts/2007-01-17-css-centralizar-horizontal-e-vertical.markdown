---
author: rogeriolino
comments: true
date: 2007-01-17 23:50:22+00:00
layout: post
slug: css-centralizar-horizontal-e-vertical
title: 'CSS: Centralizar Horizontal e Vertical'
wordpress_id: 66
categories:
- CSS
- Tableless
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
- vertical
- vertical-align
---

Uma grande dúvida que sempre surge é como centralizar um elemento no HTML, tanto verticalmente quanto horizontalmente, usando CSS.

Há duas maneiras de se fazer isso sem muito trabalho.

A primeira consiste em definir a posição do objeto como **absolute** e suas posições **top** e** left **com **50% **e tirando a diferença (subtraindo) da metade de sua altura e metade de sua largura na margem. Por exemplo se um elemento tem **500px** de **largura **e **400px** de **altura** na margem vai ter um valor **negativo** (para **top **e **left**) igual a metade destes valores:


    
    
    #minhaDiv {
        width: 500px;
        height: 400px;
        top: 50%;
        left: 50%;
        margin-top: -200px;
        margin-left: -250px;
        position: absolute;
        border: 1px solid black;
    }
    



Ou resumindo: _**margin: **-200px auto auto -250px; _

Pronto sua div vai ficar centralizada na janela. Mas temos um problema com isso.

Nesse caso sabemos o valor da altura do objeto, então tiramos a diferença na margem. Mas e se tivessemos um objeto em que sua altura pode variar (ou seja não sabemos o valor da altura) ?

Podemos solucionar isso usando o **vertical-align**, mas para ele funcionar temos que definir o** display **da div como **table**. A má notícia é que o nosso amigo **IE** não reconhece essa propriedade (e nem o valor table como display). A boa notícia que usando um hack para o IE dá pra acertar isso.

A estrutura para simular uma tabela fica assim:


    
    
    <div id="tabela">
        <div id="cell">
            <div id="conteudo">
                <p>parágrafo</p>
            </div>
        </div>
    </div>
    



E definimos no CSS o display da div **tabela** como **table** e da div **cell** como **table-cell**. Mas antes temos que acertar o **html, body** e a **tabela** para **100%** (largura e altura).


    
    
    html, body {
        width: 100%;
        height: 100%;
        margin: 0px; /* retirando a margem padrão */
        padding: 0px; /* retirando o padding padrão */
    }
    
    #table {
        width: 100%;
        height: 100%;
        display: table;
    }
    
    #cell { 
        display: table-cell; 
    }
    



Com as divs já funcionando como tabela vamos definir a **vertical-align** como **middle**, isso na div **cell**.


    
    
    #cell {
        vertical-align: middle;
        display: table-cell;
    }
    



Falta agora setar a **margin** do conteudo como **auto**. E colocar um valor para largura, senão vai ficar 100%.


    
    
    #conteudo {
        width: 500px;
        margin: auto;
    }
    



Pronto, a div já vai aparecer centralizada no browser. Mas ainda está faltando o nosso amigo **IE**.

A idéia é quase a mesma da primeira situação. Como antes do **conteudo** temos uma div (**cell**), a gente defini seu **position **como **absolute**, e **top** como **50%**. E na conteudo com **position** como **relative**, e **top** como **-50%**.

Lembrando que para não atrapalhar a definição correta, usaremos um hack que só influenciará no Internet Explorer.

Ficando o **CSS final** assim:


    
    
    html, body {
        width: 100%;
        height: 100%;
        margin: 0px;
        padding: 0px;
    }
    
    #table {
        width: 100%;
        height: 100%;
        display: table;
        background: #f1f1f1;
    }
    
    #cell {
        vertical-align: middle;
        display: table-cell;
        _position: absolute;
        _top: 50%;
    }
    
    #conteudo {
        width: 500px;
        margin: auto;
        padding: 20px;
        border: 1px solid black;
        _position: relative;
        _top: -50%;
    }
    



E o **HTML**:

    
    
    <div id="table">
        <div id="cell">
            <div id="conteudo">
                <p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
            </div>
        </div>
    </div>
    



Mais **sobre**:

[Exemplo com a primeira situação](http://dev.rogeriolino.com/exemplos/css/vertical_align/index.html)

[Maujor - Centralizar Vertical ](http://www.maujor.com/tutorial/centrar-vertical.php)

**[update testado="IE6, IE7, FIREFOX 2 e OPERA 9"]**


    
    
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
    


**[/update] **
