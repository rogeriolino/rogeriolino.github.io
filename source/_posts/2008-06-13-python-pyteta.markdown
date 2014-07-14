---
author: rogeriolino
comments: true
date: 2008-06-13 20:19:58+00:00
layout: post
slug: python-pyteta
title: 'Python: PyTETA'
wordpress_id: 110
categories:
- Python
tags:
- chat
- code
- google
- pateta
- projeto
- pyteta
- Python
- socket
---

![Pateta](http://rogeriolino.files.wordpress.com/2008/06/pateta.png)Incentivado por um trabalho de faculdade, no qual teria que fazer um simples sistema de chat (contando com um cliente e um servidor, também cliente) usando socket. Eu e Ulysses resolvemos então criar um protocolo para transferência de mensagem e utilizá-lo em nossos trabalhos para que posteriormente ambos consigam se comunicar. Surgiu então o protocolo P.A.T.E.T.A (Protocolo Aberto de Transferência Especialmente para Trabalhos Acadêmicos).

E tão bobo quanto o nome do protocolo surgiu o [PyTETA ](http://code.google.com/p/pyteta/)versão feita em Python do comunicador baseado no protocolo PATETA. Imitando descaradamente o mIRC (só que infinitamente mais humilde), o sistema conta com envios de mensagens privadas (pvt), públicas e notificações de status dos outros usuários (mudança de nick, entrada, saída - exibindo a frase personalizada do usuário).

Para poder utilizar (caso tenha curiosidade) necessita ter além do Python 2.4, o GTK+, pygtk e pyglade. Estes últimos exclusivos da interface gráfica. O servidor pode tanto ser executado no prompt, quando pela interface gráfica.

Para quem é curioso em programação, vale a pena conferir o código. E se interessar, convido a participar lá no [Google Code](http://code.google.com/p/pyteta/) comigo.
