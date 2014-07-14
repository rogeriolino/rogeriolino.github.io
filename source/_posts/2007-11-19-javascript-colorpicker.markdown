---
author: rogeriolino
comments: true
date: 2007-11-19 19:43:09+00:00
layout: post
slug: javascript-colorpicker
title: 'Javascript: Colorpicker'
wordpress_id: 99
categories:
- CSS
- Javascript
- XHTML
tags:
- color
- colorpicker
- CSS
- DOM
- html
- Javascript
- picker
- XHTML
---

![colorpicker.jpg](http://rogeriolino.com/wp-content/uploads/2007/11/colorpicker.jpg)

Para quem não conhece, **colorpicker **é um **seletor de cores**. Ou seja uma "janela" com **n cores predefinidas**.

Esse exemplo simula o **colorpicker** da **Macromedia**, disponível no _Flash, Dreamweaver, Fireworks_ e etc. Como o picker da Macromedia, ele possui um **display** para **pre-visualizar** a cor e o seu **valor hexadecimal** ao passar o mouse sobre ela (**onmouseover**).

Possui métodos **getColor** para resgatar o valor escolhido, **onchange** para efetuar uma ação ao escolher uma determinada cor, entre outros.

É totalmente estilizado por **CSS**, logo poderá deixá-lo como quiser. Personalizando-o.

Para utilizá-lo basta indexar-lo a sua página com a **tag <script> **e depois criar uma nova variável do tipo **Colorpicker()**.

Ex:

    
    
    <script type="text/javascript" src="colorpicker.js"></script>
    



    
    
    var picker = new ColorPicker(100, 38); // x , y
    picker.setVisible(true);
    



Para visualizar-lo funcionando [clique aqui](http://dev.rogeriolino.com/exemplos/javascript/colorpicker/index.html).

