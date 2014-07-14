---
author: rogeriolino
comments: true
date: 2006-07-03 19:17:28+00:00
layout: post
slug: xhtml-o-que-e
title: XHTML - O que é?
wordpress_id: 8
categories:
- Semântica
- Tableless
- XHTML
tags:
- certo
- doctype
- errado
- frameset
- html
- o que e
- Semântica
- strict
- Tableless
- tag
- transitional
- w3c
- XHTML
---

XHTML (**Extensible Hypertext Markup Language**) é uma linguagem de marcação baseada em XML escrita para substituir o HTML.

No XML podemos criar nossas próprias tags, e o XHTML já vem com as tags pré-definidas baseadas nas tags já conhecidas do HTML. Utilizando as regras do XML.

_Já que o XHTML usa as tags do HTML para que utilizá-lo?_

Imagine que para cada página da internet que você fosse ver um código diferente. E que cada pessoa fosse definir o seu padrão. Seria muito difícil verificar se aquele código estaria dentre os padrões. É aí que entra o XHTML.

Para construir uma página em XHTML você deverá seguir os padrões da W3C, padronizando os códigos e tornando mais fácil sua validação e a legibilidade.

Por exemplo: todas as tags e seus atributos devem ser escritos em letra minúscula, todo valor dos atributos devem estar entre "" (alt="Olá"), e as tags simples devem ser fechadas com "/>" (<img  src="foto.gif" alt="eu" />).

**Alguns exemplos:**

Tags e atributos:


<blockquote>**errado:** <IMG src="foto.gif" ALT="eu">

**certo:** <img src="foto.gif" alt="eu"></blockquote>


Aninhamento das tags:


<blockquote>**errado:** <p>parágrafo <em> negrito </p></em>

**certo:** <p>parágrafo <em> negrito </em></p></blockquote>


**O XHTML é dividido em três tipos (DOCTYPE):**


<blockquote>**Strict:** o mais rigoroso, exige que seja seguido por completamente os padrões.
**Transitional:** transição da forma antiga de marcação para uma nova forma. Utilizado por quem ainda está preso à alguma forma antiga em seu site. Sendo um pouco menos rigoroso que o Strict.
**Frameset:** usado quando se utiliza frames no site.</blockquote>


**Principais diferenças entre XHTML e HTML **

Além das tags escritas em letra minúscula, o fechamento obrigatório das tags, e as aspas. Também a sintaxe dos atributos devem ser escritas por completo ( <dl compact> para <dl compact="compact"> ). E a "troca" do atributo name para o atributo id.

Logo  veremos mais a fundo o que são DOCTYPE e como funcionam e a declaração de um XHTML.

**mais sobre:**
[Maujor.com - Tutorial XHTML](http://www.maujor.com/tutorial/xhtml.php)
[W3.org - O que é XHTML?](http://www.w3.org/TR/xhtml1/#xhtml)
[W3schools - XHTML validation](http://www.w3schools.com/xhtml/xhtml_validate.asp)
[W3Schools - Diferença entre XHTML e HTML](http://www.w3schools.com/xhtml/xhtml_html.asp)
[Revolução.ect.br - O que é XHTML?](http://www.revolucao.etc.br/archives/o-que-e-xhtml/)
[Revolução.etc.br - Doctype](http://www.revolucao.etc.br/archives/doctype-dtd-document-type-definition/)
[Linha de Código - Tutorial XHTML](http://www.linhadecodigo.com.br/artigos.asp?id_ac=88)
[Linha de Código - Escrevendo um XHTML válido](http://www.linhadecodigo.com.br/artigos.asp?id_ac=88)
