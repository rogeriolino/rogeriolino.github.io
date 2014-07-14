---
author: rogeriolino
comments: true
date: 2006-06-30 17:43:44+00:00
layout: post
slug: tags-o-que-sao-2
title: Tags - O que são?
wordpress_id: 6
categories:
- Semântica
- Tableless
- XHTML
tags:
- atributos
- CSS
- html
- Javascript
- o que sao
- propriedades
- Semântica
- tags
- XHTML
---

São as estruturas que formam o **HTML**, podem conter atributos ou não. Uma tag é constituída por um sinal de "<" no começo seguido de seu nome mais o sinal de ">". Os atributos da tag são especificados dentro dela.

**exemplo:**

<hr align="center" width="50%">
resultado:



* * *

note que todos os valores dos atributos estão entre "", mesmo não sendo necessárias para o HTML, mas é bom acostumar para que quando começar a trabalhar com o XHTML (veremos) - para que seja validado pela W3C. O mesmo serve para a "/", que é insirida no final das tags simples, como é o caso da tag hr.** Abaixo as principais tags e seus atributos:****html** - a tag princiapal da página aonde ficará todas as outras tags.**head** - dentro da tag head ficam o titulo (title), os scripts (javascript)  e o estilo (CSS), além de outras tags como meta e link.**title** - define o título da página.

**body** - o corpo da página, o que vai aparecer para o visitante.

**hn** - varia de h1 até h6, vem com predefinições para o texto, utilizada para títulos.

**p** - para iniciar um parágrafo.

**blockquote** - serve para definir uma citação do texto.

**hr** - horizontal rule, inseri uma linha horizontal. Pode ser controlada pelos seguintes atributos:



<blockquote>width: tamanho da linha, medida em pixel ou porcentagem;
size: largura da linha, medida em pixel;
align: define como será alinhada a linha (left, center, right);
noshade: retira a sombra da linha;</blockquote>


**font** - para formatar a fonte da página.



<blockquote>size: tamanho da fonte, vai de 1 até 7;
color: cor da fonte em hexadecimal;
face: o tipo da fonte, pode-se escolher mais de uma fonte separando por vírgula no qual o browser vai procurar qual o visitante tem da esquerda para a direita - usa-se como default "Sans-Serif";
ex: <font size="3" color="#000000" face="Verdana, Arial, Sans-Serif">Texto</font></blockquote>


**a** - defini um link na página.


<blockquote>href: destino do link, pra onde o usuário vai.
title: a descrição que irá aparecer ao repousar o mouse em cima.</blockquote>


**img** - adiciona uma imagem à página. Tag simples, então termina com "/".



<blockquote>src: destino da imagem.
alt: descrição da imagem (ao posicionar o mouse em cima). Opcional, mas para ser validado tem que pelo menos conter. ex: alt="".
width: largura.
height: altura.
ex: <img src="imagens/avatar.gif" width="100" height="75"/></blockquote>



**i** - adiciona itálico ao texto;

**b** - adiciona negrito ao texto (bold);

**center** - centraliza o conteúdo contido nele na página.

Algumas dessas tags - como por exemplo i, b e center e os atributos da tag font - quase não são usadas e seus atributos também, sendo substituídos por classes ou ids definidas no CSS (Cascade Style Sheet). Mas é bom vermos para termos uma boa base sobre como funcionam as tags.

Toda tag pode receber uma **id** e/ou **class** para ser identificada e formatada no CSS.

Dica: tente testar as tags alterando os atributos e ver os resultados para melhor fixar e compreender.

**mais sobre:**

[http://pt.wikipedia.org/wiki/Tag](http://pt.wikipedia.org/wiki/Tag)
