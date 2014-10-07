---
author: rogeriolino
comments: true
date: 2007-09-04 14:20:22+00:00
layout: post
slug: javascript-password-generator
title: 'Javascript: Password Generator'
wordpress_id: 92
categories:
- Javascript
tags:
- ascii
- DOM
- ftp
- generator
- gerador
- Javascript
- password
- script
- senha
---

Hoje me deparei com o fato de ter que alterar a senha do FTP, e há algum tempo queria fazer um gerador de senhas.

Então não teve momento mais oportuno, com um simples **script** que **transforma** um **números aleatórios** em **char **e pronto. Está resulvido o meu problema.


    
    
    var Password = function() {
        this.pass = "";
        this.generate = function(chars) {
            for (var i= 0; i<chars; i++) {
                this.pass += this.getRandomChar();
            }
            return this.pass;
        }
    
        this.getRandomChar = function() {
            /*
             * matriz contendo em cada linha indices (inicial e final) da tabela ASCII para retornar alguns caracteres.
             *  [48, 57] = numeros;
             *  [64, 90] = "@" mais letras maiusculas;
             *  [97, 122] = letras minusculas;
             */
            var ascii = [[48, 57],[64,90],[97,122]];
            var i = Math.floor(Math.random()*ascii.length);
            return String.fromCharCode(Math.floor(Math.random()*(ascii[i][1]-ascii[i][0]))+ascii[i][0]);
        }
    }
    



O que tem de novo nesse script em relação ao conteúdo do blog está na funcão **getRandomChar. **Primeiro temos um **vetor bidimensional** (matriz) que guardamos em cada linha dois valores (duas colunas).

Guardamos esses dois valores porque estamos utilizando a tabela [ASCII](http://equipe.nce.ufrj.br/adriano/c/apostila/tabascii.htm) para converter número em caracter. Portanto para não termos caracteres do tipo "*", ".", ";" (etc) em nossa senha, temos que delimitar quais caracteres podem ser gerados. Logo o primeiro valor guarda a primeiro caracter que pode ser exibido e o segundo o último, e entre eles todos podem ser exibidos.

E para converter o valor no tão "pelejado"  caracter utilizamos a função própria do Javascript da classe String ( **String.fromCharCode()** ), que obviamente é passado um inteiro como parâmetro e retornado um char.

Enfim o script é capaz de gerar senhas de tamanho 0 até 9999 (restringido devido que senhas muito grandes são mais demoradas para serem geradas, e pode levar a travamento do browser) contendo letras minúsculas (a até z), letras maiúsculas (A até Z), números (0 até 9) e "@" (arroba).


[![Password Generator](http://rogeriolino.com/uploads/2007/09/password_generator.jpg)](http://dev.rogeriolino.com/exemplos/javascript/gerador_senhas/index.html)


Espero que seja de bom aproveito.
