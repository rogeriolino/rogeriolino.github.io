---
author: rogeriolino
comments: true
date: 2010-05-06 19:04:35+00:00
layout: post
slug: javascript-game-engine-for-html5-canvas
title: Javascript Game Engine for HTML5 Canvas
wordpress_id: 292
categories:
- HTML5
- Javascript
- Jogos
tags:
- canvas
- engine
- games
- html5
- Javascript
- Jogos
- scenegraph
---

Comecei escrever um pequeno projeto para facilitar a criação de jogos em Javascript utilizando HTML5 Canvas para isso. Baseado em [scenegraph](http://en.wikipedia.org/wiki/Scene_graph) podendo criar nós dependentes, relativos ao nó pai. Por enquanto a estrutura da engine é composta por:



**Canvas:** para encapsular a tag canvas, pegando automaticamente o context e fornecendo algumas funções a mais.

**Game:** o jogo em sí, possui uma ou muitas cenas (Scene). Contém o loop principal para atualizações do canvas. Necessita de uma instância do Canvas.

**Scene:** deve ser estendida para criar cenas customizadas, deve implementar o método update(interval).

**CanvasNode:** um nó do grafo, possui as coordenadas e ângulo de rotação do elemento no canvas.

**CanvasNodeGroup:** um grupo de nós. Estende CanvasNode.

**Graphics:** um nó "printável", quem for estendê-lo deve implementar o método draw(). Possui como subclasses: Rectangle, Triangle, Circle, Text, Image2d e Line.

**GraphicsGroup:** estende CanvasNodeGroup, possui um grupo de graphics. Scene é um GraphicsGroup.


Os próximos passos serão a implementação de TileMap, Scene Intro, Menu e botões. Agora é só aguardar até o próximo exemplo.

**[update 2010-05-06]**
Added mouse and button support.
See example above.
**[/update]**

**[update 2010-05-06]**
Examples in [http://mangame.rogeriolino.com/](http://mangame.rogeriolino.com/)
**[/update]**

**[update 2011-11-11]**
Source now available in [GitHub](https://github.com/rogeriolino/mangame)!
**[/update]**
