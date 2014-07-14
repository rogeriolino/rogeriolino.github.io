---
author: rogeriolino
comments: true
date: 2006-07-11 12:47:21+00:00
layout: post
slug: escrevendo-o-primeiro-xhtml
title: Escrevendo o Primeiro XHTML
wordpress_id: 12
categories:
- CSS
- Semântica
- Tableless
- XHTML
tags:
- CSS
- Semântica
- strict
- Tableless
- XHTML
---

Mãos à obra, vamos agora escrever nosso primeiro código **XHTML**. Abaixo o código já pronto e comentado:

    
    
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="pt" lang="pt">
    <head>
        <title> Título </title>
        <meta name="Generator" content="" />
        <meta name="Author" content="" />
        <meta name="Keywords" content="" />
        <meta name="Description" content="" />
        <meta name="language" content="pt-br" />
        <!-- Favicon -->
        <link rel="shortcut icon" href="favicon.ico" />
        <!-- Style -->
        <link rel="stylesheet" href="style.css" type="text/css"/></em>
    </head>
    <body>
    </body>
    </html>
    



Antes de iniciar a tag html é declarado o tipo da página, o Doctype, se você não sabe o que é: [leia aqui](http://rogeriolino.com/2006/07/03/xhtml-o-que-e/) e/ou [aqui](http://www.revolucao.etc.br/archives/doctype-dtd-document-type-definition/).

Nesse caso foi definido como Strict, caso você ainda não esteje preparado pode utilizar como Transitional.


<blockquote>_<!DOCTYPE HTML PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">_</blockquote>


Você deve estar se perguntando: Por que aquele "xmlns" dentro da tag html ?

É chamado de namespace e serve para mostrar para o browser quais elementos pertencem a qual linguagem no documento. [Dúvida?](http://www.maujor.com/w3c/xhtml10_2ed.html#docconf) [Mais?](http://www.maujor.com/w3c/xhtml10_2ed.html#ref-xmlns) [Mais!](http://www.imasters.com.br/artigo/3956/xhtml/faq_completo_sobre_xhtml)

As tags **meta** servem para colocar informações adicionais, tais como, autor, idioma, palavras-chave e etc. - essas tags são utilizadas por mecanismos de buscas, como o Google por exemplo, para localizar os sites. Um site bem estruturado e definido tem chance maior de aparecer primeiro na busca.

Logo abaixo aparece a tag **link** referenciando um arquivo externo, ícone. Chamado Favicon - ícone do favoritos - que é nada mais nada menos do que aquele íconezinho que fica aparecendo no browser ao lado do endereço do seu site e nos favoritos também é claro. Caso ainda tenha dúvida [veja aqui](http://www.google.com.br/search?q=favicon&start=0&ie=utf-8&oe=utf-8&client=firefox-a&rls=org.mozilla:pt-BR:official).

Depois como já vimos aparece novamente a tag **link** para "puxar" o arquivo de estilo da página - CSS.

Fecha-se a tag **head**, abre e fecha a **body** e fecha a **html**, e pronto. O seu XHTML já está pronto.

Na próxima veremos o um layout já pronto com o CSS.
