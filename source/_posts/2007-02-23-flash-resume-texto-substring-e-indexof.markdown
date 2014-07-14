---
author: rogeriolino
comments: true
date: 2007-02-23 22:51:51+00:00
layout: post
slug: flash-resume-texto-substring-e-indexof
title: 'Flash: Resume Texto (substring e indexOf)'
wordpress_id: 75
categories:
- ActionScript
- Flash
tags:
- Flash
- flashmasters
- forum
- indexof
- prototype
- resumo
- substring
- texto
---

Esses dias no[ Forum FlashMasters](http://www.flashmasters.net/forum) um amigo meu deixou a seguinte dúvida:

Ele queria saber como fazer uma função para resumir um texto (uma String) por palavras. E não por caracteres. O que poderia ser feito apenas usando uma função **substring()** do próprio Flash.

Então fiz uma bem simples depois dei uma implementada nela (utilizando prototype) e estou postando aqui porque acho que poderá ser útil:


    
     
    String.prototype.resume = function(q) {
        var aux:String = "";
        for (var i = 0; i < q; i++) {
            aux += this.substring(0, this.indexOf(" ")) + " ";
            this = this.substring(this.indexOf(" ") + 1);
        }
        return (aux += "...");
    }
    



Na função é passado por parâmetro a quantidade de espaços (palavras) no qual o texto será resumido.


<blockquote>**substring()** : Retorna um pedaço da **String**. Método sobrecarregado você pode passar dois ou um parâmetro (**Integer**). Passando dois o primeiro é o ponto inicial e o segundo final. Com um parâmetro ela retorna da posição escolhida em diante.

**indexOf() :** Retorna a posição (**Integer**) no texto (**String**)  da **Char/String** passado como parâmetro, ou -1 quando não achar.</blockquote>


E para utilizar:

    
    
    var texto = "Putz, o carnaval acabou comigo.";
    trace(texto.resume(3)); // "Putz, o carnaval ..."
    



**Mais sobre essas funções e outras:**

[Livedocs.Adobe.com - Flash 8](http://livedocs.adobe.com/flash/8/main/wwhelp/wwhimpl/js/html/wwhelp.htm?href=Part4_ASLR2.html)

**[update date="24/02/2007" ] **

Adicionei condições para ver se o texto não é uma única palavra ou a quantidade de palavras no texto é menor do que a quantidade que quer resumir.


    
    
    String.prototype.resume = function(q) {
        var aux:String = "";
        var menor:Boolean = (this.indexOf(" ") == -1) ? false : true;
        for (var i= 0; i < q; i++) {
            if (!menor) {
                return this;
            } else if (this.indexOf(" ") != -1) {
                aux += this.substring(0, this.indexOf(" ")) + " ";
                this = this.substring(this.indexOf(" ") + 1);
            } else {
                return aux + this;
            }
        }
        return aux + "...";
    }
    


** [/update]**
