---
author: rogeriolino
comments: true
date: 2012-05-16 19:48:48+00:00
layout: post
slug: html5-websocket
title: 'HTML5: Websocket'
wordpress_id: 563
categories:
- HTML5
- Javascript
- PHP
tags:
- demo
- example
- html5
- hybi
- Javascript
- PHP
- rfc6455
- socket
- websocket
---


[The Websocket Protocol](http://www.rfc-editor.org/rfc/rfc6455.txt)
```
The WebSocket Protocol enables two-way communication between a client running untrusted code in a controlled environment to a remote host that has opted-in to communications from that code. The security model used for this is the origin-based security model commonly used by web browsers. The protocol consists of an opening handshake followed by basic message framing, layered over TCP.  The goal of this technology is to provide a mechanism for browser-based applications that need two-way communication with servers that does not rely on opening multiple HTTP connections (e.g., using XMLHttpRequest or <iframe>s and long polling).
```

Aproveitando um post sobre [PHP Sockets](http://rogeriolino.com/2010/04/22/php-socket-class/) que tinha escrito unindo o estudo sobre Websocket, eu criei um [projeto no Github](https://github.com/rogeriolino/phpsocket) para facilitar o uso de sockets com PHP fornecendo suporte ao Websocket também.

E para visualizar o [exemplo](https://github.com/rogeriolino/phpsocket/tree/master/demo/websocket) basta fazer checkout do projeto, executar o arquivo server.php: 

    
```bash
$ php server.php
```   

E abrir a página chat.html pelo browser. O funcionamento do exemplo vai depender, além obviamente do suporte à Websocket, do tipo da versão da implementação do browser. Por enquanto a suportada pelo projeto é a HyBi (descrita na [RFC 6455](http://www.rfc-editor.org/rfc/rfc6455.txt)).
