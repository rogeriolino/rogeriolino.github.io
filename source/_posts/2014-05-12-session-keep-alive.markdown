---
author: rogeriolino
comments: true
date: 2014-05-12 16:14:14+00:00
layout: post
slug: session-keep-alive
title: Session Keep Alive
wordpress_id: 907
categories:
- Javascript
- PHP
- Tutorial
tags:
- idle
- Javascript
- keepalive
- PHP
- session
- timeout
---

Uma maneira fácil de manter a sessão ativa no lado do servidor sem sobrecarregá-lo com longos tempos de timeout, é usar um script que redireciona o usuário para a tela de login após um determinado período de inatividade (teclado e mouse ociosos), e fazer requisições assíncronas ao servidor para manter a sessão ativa durante a atividade.

<!-- more -->

Resumindo, enquanto usuário está utilizando a aplicação (digitando ou movendo o cursor) uma requisição assíncrona é disparada a cada X minutos (ping), e quando o usuário ficar ocioso começa a contar o tempo para redirecioná-lo para a tela de login. É importante que esse tempo para redirecionar para o login seja menor do que o timeout do servidor.

Para implementar essa ideia, vou utilizar um plugin jQuery que monitora a atividade do usuário (teclado e mouse): https://github.com/rogeriolino/jquery-idletimer.

Abaixo o trecho javascript para disparar o ping e fazer o logout após 10 minutos de ociosidade.


    
    // session keep alive
    ;(function($) {
        "use strict";
        
        var pingTime = 60; // ping a cada 60 segundos
        var count = pingTime;
        $.idleTimer({
            time: 10 * 60, // 10 minutos para timeout
            start: function() {
                count = pingTime;
            },
            change: function(it) {
                count--;
                console.log(count);
                if (count <= 0) {
                    count = pingTime;
                    $.ajax({ url: '/ping.php' });
                }
            },
            end: function() {
                window.location.href = '/logout.php';
            }
        });
    })(jQuery);



Arquivo PHP para receber as requisições e abrir a sessão mantendo-a ativa:


    
    <?php
    
    session_start();
    



