---
author: rogeriolino
comments: true
date: 2012-01-23 19:44:50+00:00
slug: jquery-vertical-scroller-plugin
title: 'jQuery: Vertical Scroller Plugin'
wordpress_id: 461
categories:
- Javascript
- Quickpost
tags:
- Javascript
- jquery
- js
- plugin
- scroller
- vertical
- vscroller
old_url: /2012/01/23/jquery-vertical-scroller-plugin/
redirect_from:
  - /2012/01/23/jquery-vertical-scroller-plugin/
---

![](/uploads/2012/01/vscroller.png)

Hoje criei um novo projeto no Github, para um plugin para jQuery (1.7+) que desenvolvi (estou e estarei desenvolvendo). Trata-se um scroller vertical que pode ser aplicado a qualquer tag block.

    
```js
$('#news').vScroller({
  width: 300,
  height: 400
});
```



Conforme surgir demanda, necessidade de mais funcionalidades, callbacks, eu irei incrementando o projeto. Embora simples, está funcional, e serve como estudo.

_[update 2012-01-24]_
**Features:**


  * MouseWheel

  * Drag&Drop;

  * Keys (UP, DOWN, PG_UP, PG_DOWN, HOME, END)


**Compatibility (tested):**


  * Chrome 12+

  * Firefox 8+

  * Opera 11+


_[/update]_

**Demo:**
[http://dev.rogeriolino.com/js/vscroller.html](http://dev.rogeriolino.com/js/vscroller.html)
