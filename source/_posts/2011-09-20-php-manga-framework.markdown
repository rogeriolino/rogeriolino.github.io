---
author: rogeriolino
comments: true
date: 2011-09-20 18:35:56+00:00
layout: post
slug: php-manga-framework
title: 'PHP: Manga Framework'
wordpress_id: 364
categories:
- PHP
tags:
- engine
- facelets
- framework
- git
- github
- ioc
- java
- jsf
- lithium
- manga
- opensource
- PHP
- playframework
- rails
- rest
- ror
- router
- ruby
- symfony
- template
- vraptor
- yii
---

Criado o projeto para o framework [Manga, no Github](https://github.com/rogeriolino/manga-framework) (PHP 5.3+).

Entre algumas funcionalidades, destaca-se o seu template engine baseado no [Facelets](http://facelets.java.net/).

Os arquivos de configuração poderão ser escritos em mais de um formato, inicialmente suporte a XML e YAML. Annotations são utilizadas para enxugar esses arquivos de configuração, deixando o código mais intuitivo.

O próximo passo é implementar suporte à [IoC](http://en.wikipedia.org/wiki/Inversion_of_control), que inicialmente pode ser simulado pelo arquivo de configuração de rotas (com suporte [REST](http://en.wikipedia.org/wiki/Representational_state_transfer)).

A intenção não é desenvolver um framework revolucionário, e sim adaptar as ideias e metodologias já utilizadas por outros em um único framework afim de aumentar a produtividade. Servem como inspiração os seguintes frameworks:

**Ruby**

   
  * [RoR](http://rubyonrails.org/)


**Java**

    
  * [JSF2](http://javaserverfaces.java.net/)
    
  * [Spring 3](http://www.springsource.org/)
    
  * [VRaptor](http://vraptor.caelum.com.br/)
    
  * [Play Framework](www.playframework.org)



**PHP**

    
  * [Lithium](http://lithify.me/)
    
  * [Symfony](http://symfony.com/)
    
  * [Yii](http://www.yiiframework.com/)

