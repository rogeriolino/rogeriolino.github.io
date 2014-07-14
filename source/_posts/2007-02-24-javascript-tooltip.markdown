---
author: rogeriolino
comments: true
date: 2007-02-24 22:50:26+00:00
layout: post
slug: javascript-tooltip
title: 'Javascript: Tooltip'
wordpress_id: 76
categories:
- CSS
- Javascript
- XHTML
tags:
- CSS
- Javascript
- tooltip
- XHTML
---

Há algum tempo eu fiz um script de uma tooltip (aquela caixa que abre ao passar o mouse sobre algum link). Infelizmente o código não é dos menores, o que deixaria muito grande o post e sua explicação.

Mas não está difícil de entender. Qualquer dúvida é só deixar um comentário que eu comento logo abaixo explicando.

O seu funcionamento é bem simples. No HTML é adicionado uma **div** com **position absolute** com **display** igual a **none**. Com o **document.onmousemove **a posição do mouse é guardada em uma variável então ao passar o mouse sobre qualquer link o **display** da **div** (tooltip) muda para block e sua posição (x,y) é setada pela do mouse.

Para ver o [exemplo clique aqui](http://dev.rogeriolino.com/exemplos/javascript/tooltip/index.html).

_obs: o código (javascript) está junto com o HTML e o CSS._
