---
author: rogeriolino
comments: true
date: 2006-09-04 18:54:42+00:00
layout: post
slug: navbar-com-imagem-de-fundo-1
title: 'NavBar com imagem de fundo #1'
wordpress_id: 19
categories:
- CSS
- Tableless
- XHTML
tags:
- barra
- CSS
- fundo
- image-replacement
- imagem
- navbar
- navegacao
- Tableless
- XHTML
---

Esse post será voltado para ensinar fazer um menu estilo navbar. Para ser mais específico será esse o menu.

Vejamos as principais características do menu: imagem de fundo, inline e efeito over.

Primeiramente vamos desenhar os botôes do menu, feito isso vamos exportar como gif, para que o fundo fique transparente.

Você deve estar se perguntando por que exportar numa única imagem, sendo que os botões irão estar separados e ter links diferentes. Logo você irá entender o porquê disso.

Depois de desenhado e exportado vamos à linguagem de marcação para estrutura-lo:

    
    
    <ul id="nav">
    	<li id="home"><a href="index.html">home</a></li>
    	<li id="sobre"><a href="sobre.html">sobre</a></li>
    	<li id="contato"><a href="contato.html">contato</a></li>
    </ul>
    



Escrevemos uma lista não ordenada simples, com os links. Para cada item da lista definimos um nome de identificação, o que vai fazer que cada um receba sua respectiva imagem.

Para "economizar" uma **div** identificamos também a lista toda - **nav** - para formatá-la.

A parte da marcação pronta, vamos então ao CSS. Para realmente dar vida ao menu:

    
    
    ul#nav {
    	width: 324px;
    	height: 35px;
    	_padding-right: 1px;
    	list-style-type: none;
    	float: right;
    }
    
    ul#nav li {
    	display: inline;
    }
    
    ul#nav li a {
    	width: 98px;
    	height: 35px;
    	margin-left: 5px;
    	margin-right: 5px;
    	background: url(imgs/nav.gif) no-repeat;
    	float: left;
    	text-indent: -5000px;
    	overflow: hidden;
    }
    
    ul#nav li#home a { background-position: 0px 5px; }
    ul#nav li#sobre a { background-position: -99px 5px; }
    ul#nav li#contato a { background-position: -198px 5px; }
    
    ul#nav li#home a:hover { background-position: 0px 0px; }
    ul#nav li#sobre a:hover { background-position: -99px 0px; }
    ul#nav li#contato a:hover { background-position: -198px 0px; }
    



Defindo primeiro o tamanho da lista - **ul** -, removendo as marcações da lista - **list-style-type** - e flutuando para a direita, o que não irá interfirir no resultado. Já que foi usado exclusivamente para o site.

Antes tem um CSS hack - **_padding-right** - devido ao nosso amigo Internet Explorer.

Colocando os itens da lista inline - ul#nav li { display: inline; }.

Agora na tag **a** vamos definir o tamanho de cada botão, altura, espaçamento e a imagem de fundo. Repare que todos os links do menu irão receber aquela imagem de fundo que foi exportada.

Para a tag **a** ficar com o tamanho especificado - aceitar essas propriedades - deve-se coloca-la para flutuar, de preferência para a esquerda, senão irá inverter a ordem da lista.

Faça o teste, vendo o menu sem o **float**.

O **identamento negativo** juntamente com o **overflow** setado para **hidden** é justamente para fazer sumir o texto do botão colocado no HTML. Essa técnica chama-se [image-replacement](http://www.maujor.com/tutorial/image-replacement.php).

Agora que vem a parte legal, definir a posição da imagem de fundo para cada botão. Aproveitando o **id** de cada **li** mudamos a posição da tag **a** do respectivo item.

Como a largura do botão é de 99px, essa será a diferença de cada **x**, sendo decrementado, já que para cada botão que passa a imagem tem que ser "rolada" para trás.

No **y**  foi coloca **5px** para dar a impressão que o botão fica maior - sobe - ao passar o mouse sobre. Começando com 5px o botão ficará mais baixo.
Usando a [pseudo-classe](http://www.w3schools.com/css/css_reference.asp#pseudoclasses) **hover** vamos setar o **y** da posição da imagem para **0px** para fazer o efeito descrito anteriormente. Repare que o **x** permanece o mesmo.

Agora é só salvar e testar o menu.

**ps:** A utilização de uma única imagem de fundo não quer dizer que todos os demais exemplos serão assim. Como esse exemplo só tem três botões prefiri fazer assim. Para que ao carregar a imagem todos os menus aparecerão ao mesmo tempo.

**mais sobre:**

[Maujor - Barra de Navegação](http://www.maujor.com/tutorial/barNavCSS.php)
**
