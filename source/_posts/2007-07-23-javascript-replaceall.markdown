---
author: rogeriolino
comments: true
date: 2007-07-23 21:20:57+00:00
layout: post
slug: javascript-replaceall
title: 'Javascript: replaceAll()'
wordpress_id: 88
categories:
- Javascript
tags:
- all
- Javascript
- replace
- substituir
- tudo
---

<blockquote>**UPDATE**: Ao invés de usar a função abaixo, utilize **split + join**. Conforme mostrado no post [http://rogeriolino.com/2009/01/07/javascript-benchmark-replaceall/](http://rogeriolino.com/2009/01/07/javascript-benchmark-replaceall/)</blockquote>




Creio que algumas pessoas já se depararam com a situação de ter que substituir um caracter ou uma string num texto. Tudo resolveria casa o replace() não substituisse só o primeiro token encontrado.

Por isso temos que criar nossa própria função para sair buscando os resultados repitidos. Abaixo segue uma simples função que realiza tal instrução:


    
    
    function replaceAll(string, token, newtoken) {
    	while (string.indexOf(token) != -1) {
     		string = string.replace(token, newtoken);
    	}
    	return string;
    }
    



Com a ajuda do indexOf() - que retorna a posição da string que queira achar ou -1 caso não encontre - podemos em poucas linhas resolver isso.

Enquanto ainda existir a string que queira substituir (indexOf != -1) substitua (replace).

Uso:


    
    
    str = "Phasellus commodo gravida ligula. Vivamus libero eros, dignissim sit amet, imperdiet quis, condimentum ut, enim.";
    window.alert(replaceAll(str, "a", "[A]"));
    
