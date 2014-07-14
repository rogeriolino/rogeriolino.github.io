---
author: rogeriolino
comments: true
date: 2007-02-04 20:02:14+00:00
layout: post
slug: flash-swf-com-fundo-transparente
title: 'Flash: SWF com Fundo transparente'
wordpress_id: 73
categories:
- Flash
tags:
- background
- embed
- Flash
- fundo
- html
- object
- param
- swf
- transparente
- wmode
---

Mesmo sendo fácil ainda há gente que não conhece. Através de um parâmetro (**<param>**) dentro da tag object podemos especificar se o arquivo terá o fundo transparente.


    
     
    <param name="wmode" value="transparent" />
    



Para muitos que aindam usam a tag embed para funcionar em todos os browsers tem que colocar o atributo wmode nela também:


    
    
    <embed wmode="transparent" ... />
    



Então o código validado do SWF com fundo transparente ficaria assim:


    
    
    <object type="application/x-shockwave-flash" data="filme.swf" width="550" height="400" >
        <param name="allowScriptAccess" value="sameDomain" />
        <param name="movie" value="filme.swf" />
        <param name="wmode" value="transparent" />
    </object>
    



Uma coisa que acontece também que pode gerar bastante dor de cabeça é quando algum elemento do HTML que deveria ficar por cima do SWF e acaba acontecendo o contrário. E mesmo alterando o z-index não resolve. Sendo a solução apenas deixar o SWF com o fundo transparente.
