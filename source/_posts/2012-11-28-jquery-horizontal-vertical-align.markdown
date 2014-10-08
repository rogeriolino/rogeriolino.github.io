---
author: rogeriolino
comments: true
date: 2012-11-28 10:23:58+00:00
layout: post
slug: jquery-horizontal-vertical-align
title: 'jQuery: Horizontal + Vertical align'
wordpress_id: 727
categories:
- Javascript
- Quickpost
- Tutorial
tags:
- aligin
- align
- center
- horizontal
- Javascript
- jquery
- tutorial
- vertical
---

Função jQuery para alinhar horizontalmente e verticalmente o elemento.


    
```js
jQuery.fn.center = function () {
    this.css("position","absolute");
    this.css({
        top: '50%',
        left: '50%', 
        margin: '-' + (this.height() / 2) + 'px 0 0 -' + (this.width() / 2) + 'px'
    });
    return this;
}
```

Exemplo:


```html
<div id="centered_div">
    <p>My div content here</p>
</div>
```

```js    
    $('#centered_div').center()
```


Edit on jsFiddle: [http://jsfiddle.net/rc6kS/](http://jsfiddle.net/rc6kS/)
