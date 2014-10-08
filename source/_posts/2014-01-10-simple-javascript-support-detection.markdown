---
author: rogeriolino
comments: true
date: 2014-01-10 23:57:26+00:00
layout: post
slug: simple-javascript-support-detection
title: Simple javascript support detection
wordpress_id: 880
categories:
- CSS
- Javascript
- Quickpost
- Sem categoria
- Tutorial
tags:
- browser
- CSS
- detection
- example
- Javascript
- simple
- tutorial
---

Partindo do princípio que o seu navegador não suporta javascript e depois contrariando via o próprio javascript, é possível fazer uma simples verificação se o navegador do usuário está com javascript habilitado ou não.


```html
<!DOCTYPE html> 
<html class="no-js" lang="pt-BR">
<head>
    <title>JS detection</title>
    <script>document.documentElement.className = document.documentElement.className.replace("no-js","js");</script>

    <style>
        .js .alert-danger { display: none; }
        .no-js .alert-success { display: none; }
    </style>
</head>
<body>

    <div class="alert alert-danger">O seu navegador não possui suporte à <b>Javascript</b></div>

    <div class="alert alert-success">O suporte à <b>Javascript</b> está ativado</div>

</body>
</html>
```

Visualizar [demo online](http://dev.rogeriolino.com/exemplos/javascript/js-detection/).
