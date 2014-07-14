---
author: rogeriolino
comments: true
date: 2007-02-02 00:08:19+00:00
layout: post
slug: flash-tag-object
title: 'Flash: Tag Object'
wordpress_id: 72
categories:
- Flash
tags:
- embed
- Flash
- html
- object
- param
- swf
- tag
---

Depois do **swf** gerado é hora de colocá-lo no **HTML.** No próprio **Flash** ao apertar o **F12** ele **publica** o filme e já cria um **HTML**. Tudo muito bom, se não fosse pelo código gerado, muito sujo e não é validado pela W3C.

O código gerado é igual a este:


    
    
    <object classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" codebase="http://..." width="550" height="400">
        <param name="allowScriptAccess" value="sameDomain" />
        <param name="movie" value="filme.swf" />
        <param name="quality" value="high" />
        <param name="bgcolor" value="#ffffff" />
        <embed src="filme.swf" quality="high" bgcolor="#ffffff" width="550" height="400" align="middle" allowScriptAccess="sameDomain" type="application/x-shockwave-flash" pluginspage="http://..." />
    </object>
    



O problema em sí não está na tag **object **e sim na **embed** que não é reconhecida pela **W3C**. Beleza, então eu tiro a tag embed e está tudo certo? Errado.

Primeiramente vamos conhecer mais sobre a tag Object.

A tag **object** serve para anexar à página algum dos três tipos de dados (objects, images and applets), mas para alguns existe uma tag mais adequada, como por exemplo uma imagem.


<blockquote>The [ OBJECT](http://www.w3.org/TR/html4/struct/objects.html#edef-OBJECT) element allows authors to specify all three types of data, but authors may not have to specify all three at once. For example, some objects may not require data (e.g., a self-contained applet that performs a small animation). Others may not require run-time initialization. Still others may not require additional implementation information, i.e., the user agent itself may already know how to render that type of data (e.g., GIF images).

link: [http://www.w3.org/TR/html4/struct/objects.html#edef-OBJECT ](http://www.w3.org/TR/html4/struct/objects.html#edef-OBJECT)</blockquote>


Então respondendo a pergunta acima a tag **object** sem a **embed** não irá funcionar, a não ser que o atributo **type** (que no código acima você percebe que ele está na **embed**) esteja definido adequadamente. E também seja colocado o atributo **data** (que funciona igual ao **href**).

Resulmindo o código acima ficaria assim:


    
    
    <object type="application/x-shockwave-flash" data="filme.swf" width="550" height="400">
        <param name="allowScriptAccess" value="sameDomain" />
        <param name="movie" value="filme.swf" />
        <param name="quality" value="high" />
        <param name="bgcolor" value="#ffffff" />
    </object>
    



Pois então com o exemplo acima, além de validar sua página o código fica mais limpo e enxuto.

** Mais sobre:**

[http://www.maujor.com/tutorial/adeus-embed.php](http://www.maujor.com/tutorial/adeus-embed.php)
