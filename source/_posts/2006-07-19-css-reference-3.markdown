---
author: rogeriolino
comments: true
date: 2006-07-19 00:17:26+00:00
layout: post
slug: css-reference-3
title: 'CSS Reference #3'
wordpress_id: 16
categories:
- CSS
tags:
- CSS
- font
- reference
- referencia
---

Terceira referência de CSS agora mostrando a propriedade Font.


**FONT**

**font-style:** define o estilo da font.

* _nomal: não muda nada, a font fica na vertical._

* _italic: deixa a font em itálico, inclinada._

* _oblic: converte a font oblíqua. _</blockquote>


**font-variant:** mostra o texto com todas as letras em maiúsculo mas mantendo o tamanho diferente entre maiúsculas e minúsculas.

* _normal: não altera a font._

* _small-caps: transforma em maiúscula de menor altura. _</blockquote>


**font-weight: **define o quanto a font é mais pesada, mais escura.

* _normal: não altera._

* _bold: negrito. _

* _bolder: um pouco mais escuro que bold._

* _lighter: um pouco mais claro que bold._

_Ou pode setar uma centena para definir o valor: 100, 200, 300, 400, 500, 600, 700, 800, 900. _


**font-size : **tamanho da font, altura. Pode tanto definir um valor numa medida aceita pelo CSS (px, em, pt, cm...), porcentagem, ou um tamanho pré-definido abaixo, do menor para o maior:

_xx-small, x-small, smaller, small, medium, large, larger, x-large, xx-large_


**font-family: **o tipo da font (o nome), podendo definir uma lista de maior prioridade dos tipo mais à esquerda separando por vírgula. Caso o usuário não tenha determinada font passa à próxima, assim sucessivamente. Para nomes complexo adicionar aspas dupla.

_ex: Verdana, Arial, Tahoma, "Comic Sans MS", Sans-Serif;_


**color:** aplica uma cor desejada à font (Hexadecimal, RGB ou nome em inglês).

* _ ex: #FF0000;_

* _ ex: red;_

* _ex: rgb(255, 0, 0);_


**font:** jeito simplificado de escrever tudo. Ficando nessa seguinte ordem os valores: _[style] [variant] [weight] [size] [line-height] [family]._

Sendo os valores** size** e **family** obrigatórios os demais assumem o valor padrão.

_ex: font: italic small-caps bold 12px Arial, Tahoma, Sans-Serif; _

_ex: font: 12px Arial, Tahoma, Sans-Serif; _


**mais sobre:**

[Maujor - A Propriedade Font](http://www.maujor.com/tutorial/fonttut.php)

[W3Schools - CSS Reference](http://www.w3schools.com/css/css_reference.asp#font)
