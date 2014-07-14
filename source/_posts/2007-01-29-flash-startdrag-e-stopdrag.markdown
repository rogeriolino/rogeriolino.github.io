---
author: rogeriolino
comments: true
date: 2007-01-29 17:34:33+00:00
layout: post
slug: flash-startdrag-e-stopdrag
title: 'Flash: startDrag() e stopDrag()'
wordpress_id: 70
categories:
- ActionScript
- Flash
tags:
- ActionScript
- arrastavel
- draggable
- Flash
- flutuante
- janela
- movieclip
- startdrag
- stopdrag
- swf
- window
---

Aproveitando o post anterior sobre uma div arrastável usando Javascript. Vamos ver agora como seria feito uma janela também arrastável só que no Flash.

Primeiro de tudo é desenharmos nossa janela, ela será divida da seguinte maneira:



<blockquote>**janela** (MovieClip Principal)
|-- **barra**;
|-- **minimax**;
|-- **fechar**;
\-- **conteudo**.</blockquote>



Use as ferramentas de desenho para construir a janela, mas deixe os desenhos separados como mostrado acima. Se você ainda não está familiarizado[ leia este post primeiro](http://rogeriolino.com/2006/09/06/flash-8-para-quem-esta-comecando-1/).

A minha janela ficou assim:

![Desenho da Janela](http://rogeriolino.files.wordpress.com/2007/01/janela.gif)

Aonde cada parte (desenho) é um MovieClip diferente, para **transformar** o seu **desenho** em **MovieClip** selecione ele aperte **F8** coloque o nome do MC e verifique se o **radiobutton MovieClip** realmente está marcado.

Após criado o Movie devemos instanciâ-lo, para isso clique nele e vá na aba **Propriedades** (**CTRL+F3**), preencha o campo instância (siga os nomes definidos acima).

Com os quatros MovieClips prontos (**barra**, **minimax**, **fechar** e **conteudo**) selecione-os e aperte novamente **F8** para transformá-los no nosso **MC janela**.

Caso você queira editar algum movie ou apenas posicionar melhor, dê um duplo clique nele e poderá navegar através dos demais que estão contidos nele.

Agora com os MCs criados e instanciados, vamos às **actions**:

Clique no **frame principal** (o primeiro frame da timeline) e aperte **F9**. Cole o código abaixo:

    
    
    this.janela.barra.onPress = function() {
        this._parent.startDrag();
    }
    
    this.janela.barra.onRelease = function() {
        this._parent.stopDrag();
    }
    
    this.janela.fechar.onRelease = function() {
        this._parent._visible = false;
    }
    
    this.abrir.onRelease = function() {
        this._parent.janela._visible = true;
    }
    
    this.janela.minimax.onRelease = function() {
        this._parent.conteudo._visible = !this._parent.conteudo._visible;
    }
    



Ao contrário do Javascript e das versões bem mais antigas (até a 5) do Flash não é necessário um método para pegar um alvo. Você mostra o caminha para se chegar nele a partir do palco (_root sempre para raiz, ou this este filme - isso ficará mais claro quando aprendermos sobre carregar filme externo).

Por exemplo o movie** fechar** está no dentro do MC** janela** que por sua vez está no palco, então: **this.janela.fechar**. E se você estiver em um MC (fehcar por exemplo) e queira acessar o seu pai (janela), fica assim: **this._parent**.

Repare no código que a lógica é a mesma, porém no Flash tem um método nativo para realiza esse arrastar (**startDrag()**) e um para parar esse arrastar (**stopDrag()**). O que no HTML temos que fazer na mão mesmo.

O que reduz e muito o código final. Agora é só testar (CTRL+ENTER).

Para ver o [exemplo clique aqui](http://dev.rogeriolino.com/exemplos/flash/drag/index.html).
