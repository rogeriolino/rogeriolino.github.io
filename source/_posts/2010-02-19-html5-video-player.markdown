---
author: rogeriolino
comments: true
date: 2010-02-19 17:23:46+00:00
layout: post
slug: html5-video-player
title: 'HTML5: Video Player'
wordpress_id: 183
categories:
- Flash
- HTML5
- Javascript
tags:
- chrome
- dailymotion
- firefox
- google
- h.264
- html5
- ie8
- ogg
- safari
- theora
- video
- vimeo
- vorbis
- youtube
---

Para todos aqueles que odeiam o [flash player](http://get.adobe.com/flashplayer) e adoram assistir vídeos pela Internet, alguns portais de vídeos possuem uma alternativa ao plugin da Adobe para que os usuários possam assistir seus vídeos sem precisar de um plugin externo que pode deixar o browser mais lento e ocasionar travamentos. Isso se dá com a utilização da [tag video do HTML5](http://www.w3schools.com/html5/html5_reference.asp) que por sua vez varia dependendo da implementação de cada navegador.

No [Youtube por exemplo há uma página para sua versão experimental](http://www.youtube.com/html5). Ao acessar esta página destinada a habilitar o player em HTML5, eis que surgem algumas considerações e uma lista de browsers que o suportam:




	
  * [Google Chrome](http://www.google.com/chrome)

	
  * [Apple Safari](http://www.apple.com/safari/download/) (versão 4+)

	
  * Internet Explorer com o Google Chrome Frame



Não incluindo o [Firefox](http://www.getfirefox.com/), um dos browsers mais utilizados no mundo e que suporta o HTML5. Mas para isso há uma explicação: O padrão de compressão adotado pelo Youtube é o [H.264](http://pt.wikipedia.org/wiki/H.264) que não é suportado pelo Firefox devido ao fato deste formato ser proprietário e o pessoal da Mozilla utilizar [Ogg Theora](http://en.wikipedia.org/wiki/Theora) como padrão. Motivo que _sem querer querendo_ acaba ajudando o browser do Google, curiosamente, mesmo dono do Youtube.

Outros pontos ruins nessa versão do Youtube são a nítida perda de qualidade entre os players em Flash e em HTML5, e o fato de não suportar fullscreen (limitação do HTML5 e não do player). Além do Youtube o [Vimeo](http://vimeo.com/blog:268) também possui uma versão em HTML5, seguindo as mesmas restrições do Youtube, porém, com uma perda de qualidade menor. Já o [Dailymotion](http://blog.dailymotion.com/2009/05/27/watch-videowithout-flash/) utiliza os formatos Ogg, Theora + Vorbis, funcionando em todos os navegadores decentes e com algumas travadas irritantes.

Mas nem tudo está perdido para os players feitos em HTML5, um grupo de desenvolvedores e designers denominado [Jilion](http://jilion.com/) desenvolveu um excelente player (bonito e funcional) chamado [SublimeVideo](http://jilion.com/sublime/video). Suportando todos os browsers listados na página do Youtube/Vimeo incluindo o Firefox.

[caption id="attachment_184" align="aligncenter" width="604" caption="SublimeVideo - HTML5 Video Player"][![SublimeVideo](http://rogeriolino.com/wp-content/uploads/2010/02/sublimevideo.jpg)](http://rogeriolino.com/wp-content/uploads/2010/02/sublimevideo.jpg)[/caption]

Mais sobre [HTML5 video e codecs](http://shaver.off.net/diary/2010/01/23/html5-video-and-codecs/).
