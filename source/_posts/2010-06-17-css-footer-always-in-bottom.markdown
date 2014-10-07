---
author: rogeriolino
comments: true
date: 2010-06-17 14:51:50+00:00
layout: post
slug: css-footer-always-in-bottom
title: 'CSS: Footer always in bottom'
wordpress_id: 303
categories:
- CSS
tags:
- always
- baixo
- bottom
- CSS
- div
- footer
- posicao
- position
- relative
- rodape
- sempre
---

É muito comum vermos pessoas procurando saber como deixar um elemento HTML sempre no final da página, mas caso a página seja redimensionada criando rolagem, esse elemento continue no final dela. Ou seja, não apenas colocar o elemento com position fixed.

Para tal exemplo vamos precisar de um HTML simples:

    
``` html    
<html>
    <head>
    </head>
    <body>
        <div id="page">
            <div id="content">
                <h1>Footer always in bottom</h1>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla aliquet imperdiet justo, quis congue velit egestas quis. Suspendisse ac tellus vitae est ultrices imperdiet eget at dolor. Donec sit amet viverra arcu. Aenean pulvinar vehicula justo, tincidunt congue nisi pharetra eu. Suspendisse potenti. Sed libero quam, lacinia at facilisis eu, egestas sodales dolor. Duis gravida, diam interdum cursus dictum, ligula libero pellentesque lacus, vitae viverra nulla metus id erat. Suspendisse fermentum aliquam hendrerit. Sed vulputate massa ut felis sagittis molestie. Suspendisse facilisis condimentum diam, a hendrerit urna venenatis sit amet. Cras orci diam, aliquam quis fringilla ac, euismod vel orci. Quisque ac pharetra nisi. Quisque et orci ligula. Praesent lacus felis, bibendum ac varius ac, eleifend in nulla. Aliquam sodales porttitor iaculis. Aliquam pretium risus ac neque egestas convallis. Sed dignissim massa ut odio vestibulum gravida ut vel nulla.</p>
                <p>Sed non lacus in nibh lobortis imperdiet. Aliquam auctor tellus quis elit adipiscing consequat. Ut in elit at orci dapibus gravida interdum eget sapien. Sed lobortis, massa nec aliquet aliquet, nulla mi tincidunt quam, id iaculis turpis nibh interdum leo. Curabitur in lorem et risus ultrices pharetra. Mauris adipiscing eros vitae diam sodales et rutrum velit consequat. Fusce adipiscing congue ultrices. Nullam fermentum ullamcorper urna a malesuada. Sed sit amet congue tortor. Nulla accumsan blandit diam sed feugiat. Morbi lobortis fermentum metus, ac pulvinar dui commodo ut.</p>
            </div>
            <div id="footer">
                <p>footer here</p>
            </div>
        </div>
    </body>
</html>
```    

E o CSS abaixo:


``` css   
    
* {
    padding: 0px;
    margin: 0px;
}

html, body {
    height: 100%;
}

#page {
    min-height: 100%;
    position: relative;
}

#footer {
    width: 100%;
    bottom: 0;
    position: absolute;
}
```

O [exemplo funcionando você confere aqui](http://dev.rogeriolino.com/exemplos/css/footer_bottom/index.html).
