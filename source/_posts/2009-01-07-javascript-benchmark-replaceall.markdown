---
author: rogeriolino
comments: true
date: 2009-01-07 17:06:39+00:00
layout: post
slug: javascript-benchmark-replaceall
title: 'Javascript Benchmark: replaceAll'
wordpress_id: 127
categories:
- Benchmark
- Javascript
tags:
- Benchmark
- Javascript
- join
- regexp
- replace
- replaceAll
- split
---

Há algum tempo [escrevi um post contendo](http://rogeriolino.com/2007/07/23/javascript-replaceall/) um exemplo de método para fazer replace em toda String. No caso o método que escrevi usava **while** e realmente é muito menos eficiente do que as alternativas apresentadas nos comentários, a primeira usando **Expressão Regular** (sugerida pelo [Almir Mendes](http://www.almirmendes.net/)) e a segunda utilizando **split** e **join** (sugerida pelo [Lucas Ferreira](http://blog.lucasferreira.com/)).  Então resolvi (depois de muito tempo) fazer um benchmark utilizando os três métodos para poder chegar a uma conclusão sobre qual seria melhor.

Fiquei muito surpreso com os testes, não porque o método utilizando while foi de longe o pior entre os três, mas sim pelo fato do método que consiste em dividir a String em um vetor e depois junta-la novamente (**split+join**) ter sido mais rápido do que o próprio método de replace do javascript utilizando Expressão Regular (já que o split também utiliza ER).

Outro fato interessante é que tanto utilizando **ER** quanto **split-join** os métodos se mostraram bastante escaláveis, enquanto o com **while** piora consideravelmente conforme o número de ocorrência aumenta.

Lembrando que fiz os testes através [desta página](http://dev.rogeriolino.com/benchmark/javascript/replace_all/index.html) que criei utilizando como browser o [Firefox 3.0.5](http://pt-br.www.mozilla.com/pt-BR/firefox/). Caso alguém faça os testes e obtenha resultados diferente gostaria de receber feedbacks.
