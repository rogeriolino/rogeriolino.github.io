---
author: rogeriolino
comments: true
date: 2007-10-11 19:08:52+00:00
layout: post
slug: javascript-datagrid
title: 'Javascript: DataGrid'
wordpress_id: 95
categories:
- CSS
- Javascript
tags:
- CSS
- DataGrid
- DOM
- Javascript
- XHTML
---

![](http://rogeriolino.com/uploads/2007/10/datagrid.jpg)

Há algum tempo queria fazer algo parecido e então tirei um tempo para desenvolver, ou pelo menos tentar, uma espécie de data grid.

Este é composto por uma tabela de quantas linhas e colunas desejar, e em cada célula (**<td>**) contém um **<div>** e um **<input>**, no qual se alternam. Para uma hora poder alterar o seu conteúdo (mostra o **<input>**) e outra apenas exibi-lo (**<div>**).

Ao clicar duas vezes (**ondbclick**) na célula o atributo **type** do **<input>** é alterado,
se é **text** altera para **hidden** e seu valor é colocado dentro da **<div>** (**innerHTML**), caso contrário se é **hidden** altera-se para **text** e o seu valor recebe o conteúdo da **<div>** (limpando-a: div.**innerHTML** = "";).

Nessa primeira versão tem uma quantidade razoável de funções, possibilitando uma boa customização. Mas nada impede de utilizar **CSS** para conseguir um resultado mais desejado.

Para utilizar o DataGrid é bastante simples, precisa apenas informar a quantidade de linhas e colunas e aonde deseja adicioná-la.


    
    
    var datagrid = new DataGrid(10, 25);
    datagrid.setCelSize(10,10);
    datagrid.pack("container2");
    



** new DataGrid(linhas, colunas) **: cria um novo DataGrid, com a quantidade de linhas e colunas desejada;

**setCelSize(largura, altura) :** seta uma largura e altura para as células (em pixels);

**pack(alvo) :**  inclui (append) o DataGrid no alvo desejado, passando como parâmetro o **id **do alvo.

Para visualiza-lo funcionando clique no link a seguir:

[http://dev.rogeriolino.com/exemplos/javascript/datagrid/index.html](http://dev.rogeriolino.com/exemplos/javascript/datagrid/index.html)

**ps:** Para reportar algum bug, dúvida ou sugestões basta deixar um comentário. Caso vá usá-lo recomendo que leia o código primeiro para poder aproveitá-lo melhor.
