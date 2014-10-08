---
author: rogeriolino
comments: true
date: 2013-01-02 12:08:47+00:00
layout: post
slug: css3-selection-background-color
title: 'CSS3: Selection background color'
wordpress_id: 740
categories:
- CSS
- HTML5
- Quickpost
- Tutorial
tags:
- background
- color
- CSS
- css3
- highlight
- selection
- tutorial
---

Com o seletor **selection** podemos definir a cor do texto e de fundo do texto quando o selecionamos.



<blockquote>
The ::-moz-selection (::selection) pseudo-element applies to the portion of a document that has been highlighted (e.g. selected with the mouse) by the user.

Gecko/Firefox supports ::-moz-selection, use also ::selection other browsers. The following properties apply to ::-moz-selection:  color, background and background-color (background-image is ignored).

[http://dochub.io/#css/selection](http://dochub.io/#css/selection)
</blockquote>



**CSS**

    
```css
p::selection  { color: #000; }
p::-moz-selection { color: #000; }

p.yellow::selection  { background: yellow; }
p.yellow::-moz-selection { background: yellow; }

p.green::selection { background: #58FF4B; }
p.green::-moz-selection { background: #58FF4B; }

p.pink::selection { background: #E2189C; }
p.pink::-moz-selection { background: #E2189C; }
```



**HTML**
    
```html    
<p class="yellow">Lorem ipsum dolor sit amet, consectetur adipiscing elit...</p>

<p class="green">Aliquam erat volutpat. Donec in elit at magna venenatis venenatis...</p>

<p class="pink">Donec interdum placerat urna at aliquet...</p>
```


**Exemplo**
[http://dev.rogeriolino.com/exemplos/css/selection/index.html](http://dev.rogeriolino.com/exemplos/css/selection/index.html)
