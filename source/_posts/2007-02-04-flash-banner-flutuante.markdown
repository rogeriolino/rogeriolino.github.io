---
author: rogeriolino
comments: true
date: 2007-02-04 20:45:42+00:00
layout: post
slug: flash-banner-flutuante
title: 'Flash e CSS: Banner Flutuante'
wordpress_id: 74
categories:
- CSS
- Flash
- Tableless
- XHTML
tags:
- banner
- CSS
- Flash
- flutuante
- rollover
- swf
- Tableless
- transparente
- XHTML
---

Muitos sites, portais, adotaram o banner flutuante, aquele no qual ao você passar o mouse por cima ele "cresce" pela página e mostra os detalhes da propaganda, promoções, etc.

A idéia então consiste em posicionar o filme por cima dos outros elementos e ele tem que ter o fundo transparente para não "tampar" o  conteúdo.

Então chegamos a **conclusão** que é só deixar o filme com o fundo **transparente** e colocá-lo numa **div** com **position absolute**? Certo.

Primeiramente vamos ao SWF, no Flash crie um novo documento. Nesse exemplo eu criei um de tamanho 468x280.

No primeiro frame coloque a action **stop()** para o filme não começar sozinho.

Desenhei um retângulo que cobre todo o palco na horizontal e com altura de 60 pixels. Dupliquei ele (copia e cola) e apertei o F8 para transformá-lo em um MovieClip. Ele vai ser o nosso botão para quando passar o mouse dar o p**lay()** no filme.

Instanciei de **btn** e apliquei o alpha para 0%, para deixar ele transparente. E adicionei no primeiro frame a seguinte action:


    
    
    btn.onRollOver = function() {
        _root.gotoAndPlay(2);
    }
    



Com essa action definimos que ao **passar o mouse sobre** o botão (**btn**) o filme irá para seguir a partir do segundo frame.

E no frame 2 em diante fiz uma animação simple para dar impressão do fundo estar crescendo para baixo. No último frame da animação também adicionei a action **stop();** para o filme não voltar para o primeiro frame.

Também temos que colocar uma action para ao tirar o mouse (rolar fora) do botão a animação ir e parar no primeiro frame. E também uma para quando clicar. Essa action pode ser colocada no primeiro frame também.


    
    
    btn.onRollOut = function() {
        _root.gotoAndStop(1);
    }
    
    btn.onRelease = function() {
        getURL("http://rogeriolino.com/", "_blank");
    }
    


Na primeira faz com que ao tirar o mouse de cima do botão volte para o primeiro frame mas não continua o filme (stop). Na segunda tem a função **getURL() **que funciona como a tag <a> no html, seus parâmetros são: página/endereço e alvo/target (__blank = nova página / _self = mesma página / _parent = pai do frame_).

Com a nossa animação pronta vamos ao HTML:

Vamos colocar o SWF dentro de uma **div** chamada** banner**:

    
    
    <div id="banner">
        <object type="application/x-shockwave-flash" data="banner.swf" width="480" height="280">
        <param name="movie" value="banner.swf" />
        <param name="allowScriptAcess" value="sameDomain" />
        <param name="wmode" value="transparent" />
        <param name="quality" value="best" />
    </object>
    </div>
    



E o nosso CSS:


    
    
    #banner {
        margin-left: 250px;
        _margin-left: 10px;
        padding: 20px;
        position: absolute;
    }
    



O **hack** na margin é por causa do **IE**.

E pronto, já podemos ver nossa [propaganda flutuante funcionando](http://dev.rogeriolino.com/exemplos/flash/banner_flutuante/index.html). [Download do exemplo](http://dev.rogeriolino.com/exemplos/flash/banner_flutuante/banner_flutuante.rar).
