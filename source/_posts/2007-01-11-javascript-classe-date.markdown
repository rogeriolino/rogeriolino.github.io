---
author: rogeriolino
comments: true
date: 2007-01-11 20:55:17+00:00
layout: post
slug: javascript-classe-date
title: 'Javascript: Classe Date()'
wordpress_id: 64
categories:
- Javascript
tags:
- classe
- data
- date
- horas
- hours
- Javascript
- mensagem
- minutes
- minutos
- seconds
- segundos
---

Uma classe muito funcional do Javascript e em muitas outras linguagens é a Date().

Definindo um objeto como Date podemos pegar a hora, minutos, segundos, dia, mês, ..., local ou do horário universal.

Usando:

    
    
    var minhaData = new Date();
    var hora = minhaData.getHours();
    window.alert( hora);
    



Será mostrado na janela de aviso a hora local.

Podemos então aproveitar isso para mostrar uma mensagem (bom dia, boa tarde ou boa noite) para o usuário.


    
    
    var minhaData = new Date();
    var hora = minhaData.getHours();
    var msg = "Boa noite";
    if ((hora >= 6) && (hora < 12)) {
        msg = "Bom dia";
    } else if ((hora >= 12) && (hora < 18)) {
        msg = "Boa tarde";
    }
    window.alert(msg);
    



Define uma variável como Date(), e pegamos a hora local. O porquê da variavél msg receber "Boa noite" já vai dar para entender.

Perguntamos então se o valor de hora é maior ou igual a 6 e menor que 12 (6 a 11), então ainda é dia. Caso contrário pode ser noite ou tarde, por isso perguntamos se esse valor é maior igual a 12 ou menor que 18 (12 a 17), então é tarde.

Se não estiver entre os valores acima então é noite. Por isso já setamos a variável como "Boa noite", só para economizar um else. =]

Brincando um pouco mais com a Classe Date fiz um simples relógio, e mostrar a data formatada no site (na página também há um link para explicação de cada função da classe). Para conferir segue o link: [Classe Date()](http://dev.rogeriolino.com/exemplos/javascript/date/index.html).

**Mais sobre:**

[http://www.w3schools.com/jsref/jsref_obj_date.asp](http://www.w3schools.com/jsref/jsref_obj_date.asp)
