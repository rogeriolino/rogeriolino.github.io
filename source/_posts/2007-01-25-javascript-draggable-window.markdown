---
author: rogeriolino
comments: true
date: 2007-01-25 23:11:33+00:00
layout: post
slug: javascript-draggable-window
title: 'Javascript: Draggable Window'
wordpress_id: 69
categories:
- CSS
- Javascript
tags:
- arrastavel
- CSS
- div
- DOM
- draggable
- flutuante
- janela
- Javascript
- window
- XHTML
---

Tem algum tempo já que estava de bobeira e acabei fazendo um **exemplo** de uma **div** (janela) **arrastável**.

Simulei uma janela padrão em alguns Sistemas Operacionais, tem a barra superior com o título da janela, o espaço ao centro para o conteúdo e uma barra no final, a statusbar (essa só para incrementar mesmo).

Há nela também três opções: "**minimizar/maximizar**",  "**esconder**" e "**fechar**".

Na opção "minimizar" é alterado a propriedade **display** do **CSS** da parte do conteúdo para **none**. Voltando para **block** com "maximizar".

O "esconder" além de aproveitar a função para "minimizar" também altera o **display** da **statusbar** para **none**. E seta a **posição** da janela para a **origem** da tela (**left**:0 e **top**: 0).

E o "fechar" por sua vez altera a propriedade do **visibility** do CSS da  janela toda para **hidden**. E no palco tem uma opção para (re)**abrir** a janela, que altera o **visibility** para **visible**.

O porquê de usar visibility para "fechar" a janela é porque não queremos mudar o comportamento da janela, como ela é vista, e sim só sumir, torná-la invisível. O mesmo não funcionaria muito bem com o conteúdo porque fazendo ele só sumir ainda ficaria o seu "espaço guardado" fazendo apenas o conteúdo ficar invisível ao invéz da janela realmente minimizar.

Ao arrastar a janela também é **alterado** o **cursor**, mudando para **move**. O que caracteriza melhor a janela sendo arrastada.

Qualquer dúvida é só deixar no comentário.

[Exemplo: Draggable Window ](http://dev.rogeriolino.com/exemplos/javascript/drag/index.html)

[Source: Draggable Window](http://dev.rogeriolino.com/exemplos/javascript/drag/script/drag.js)
