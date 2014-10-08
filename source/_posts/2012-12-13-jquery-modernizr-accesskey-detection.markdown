---
author: rogeriolino
comments: true
date: 2012-12-13 16:13:36+00:00
layout: post
slug: jquery-modernizr-accesskey-detection
title: 'jQuery + Modernizr: AccessKey detection'
wordpress_id: 732
categories:
- CSS
- HTML5
- Javascript
- Quickpost
- Tutorial
tags:
- accesskey
- browser
- css3
- detectizr
- html5
- Javascript
- jquery
- modernizr
- tutorial
---

O código abaixo permite exibir no title e na frente das tags que possuem o atributo [accesskey](http://www.w3schools.com/tags/att_global_accesskey.asp) o seu atalho.

Com o uso do CSS é adicionado ao [final do conteúdo da tag](http://www.w3schools.com/cssref/sel_after.asp) o seu atalho. E via Javascript esse atalho também é adicionado ao title. 

Como esses atalhos variam de acordo com o Browser e o Sistema Operacional, fiz uso do Modernizr + Detectizr para adicionar no body a classes informando o ambiente.

**Dependências**


```html
<script src="http://cdnjs.cloudflare.com/ajax/libs/jquery/1.8.3/jquery.min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/modernizr/2.6.2/modernizr.min.js"></script>
<script src="https://raw.github.com/barisaydinoglu/Detectizr/master/detectizr.min.js"></script>
```

**CSS**


```css
*[accesskey]:after {
    margin-left: 0.3em;
    color: #ccc;
    content: "[Alt + " attr(accesskey) "]";
}

body.firefox *[accesskey]:after { content: "[Alt + Shift + " attr(accesskey) "]"; }
body.firefox.mac *[accesskey]:after { content: "[Ctrl + Opt + " attr(accesskey) "]";  }
body.safari.mac *[accesskey]:after { content: "[Ctrl + " attr(accesskey) "]";  }
```


**Javascript**


```js
/**
 * Add browser and OS name to body class, and append the shortcut to element title
 * @author rogeriolino
 */
(function($) {
    $(document).ready(function() {
        Modernizr.Detectizr.detect({detectScreen:false});
        var body = $('body')
        body.addClass(Modernizr.Detectizr.device.browser + ' ' + Modernizr.Detectizr.device.os);
        $('*[accesskey]').each(function(i, e) {
            var elem = $(e);
            prefix = 'Alt';
            if (body.hasClass('firefox')) {
                if (body.hasClass('mac')) {
                    prefix = 'Ctrl + Opt';
                } else {
                    prefix = 'Alt + Shift';
                }
            } else if (body.hasClass('safari mac')) {
                prefix = 'Ctrl';
            }
            elem.prop('title', elem.prop('title') + ' [' + prefix + ' + ' + elem.attr('accesskey') + ']');
        });
    });
})(jQuery);
```


**Demo**

[Clique aqui para visualizar o exemplo no jsFiddle.net](http://jsfiddle.net/qmB3R/)
