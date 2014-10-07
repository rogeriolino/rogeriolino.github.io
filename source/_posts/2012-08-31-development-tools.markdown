---
author: rogeriolino
comments: true
date: 2012-08-31 20:02:57+00:00
layout: post
slug: development-tools
title: Development Tools
wordpress_id: 594
categories:
- CSS
- HTML5
- Javascript
- PHP
- Quickpost
tags:
- base64
- browser
- cnpj
- converter
- cpf
- crypt
- css3
- decode
- dev
- encode
- geolocation
- gerador
- html5
- Javascript
- jquery
- json
- lipsum
- md5
- modernizr
- PHP
- random
- sha1
- tools
- whois
---

[![](http://rogeriolino.com/uploads/2012/08/dev-tools.png)](http://dev.rogeriolino.com/tools/crypt)

Iniciei e publiquei um pequeno projeto que reune algumas funcionalidades para auxiliar durante o desenvolvimento. Segue abaixo as funcionalidades que estão disponíveis por enquanto:





  * **Crypt**: algorítimos de hash como sha1 e md5, e base64 encode/decode


  * **Random:** geração de senhas (com opções de configuração), CPF e CNPJ, e Lorem Ipsum


  * **Converter**: conversor de unidades de medida


  * **Network**: exibe o IP do cliente, geo localização (coordenadas e mapa), e consulta de domínios (whois server)


  * **Browser**: informações sobre versão, user-agent, resolução e viewport, e as principais funcionalidades do HTML5 e CSS3 que o browser suporta.


  * **Javascript**: code minifier and optimizer



Como toda a execução é feita no lado do servidor, você pode fazer uma execução ajax do seu site/aplicação para o dev-tools e pegar no response o resultado, sem que haja necessidade de importar novos recursos:



<blockquote>GET
>     /ajax/<package>/<method>/?<params>
>     /ajax/crypt/sha1?data=test
>     
>     JSON RESPONSE
>     {"success":true,"data":"a94a8fe5ccb19ba61c4c0873d391e987982fbbd3"}
>     
> 
> </blockquote>



Conforme eu vá sentindo necessidade de mais funcionalidade ou alguém dê uma sugestão, irei incrementando. Depois criarei um projeto no Github e atualizarei o post com o link.


