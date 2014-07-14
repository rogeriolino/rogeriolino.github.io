---
author: rogeriolino
comments: true
date: 2007-01-12 22:45:37+00:00
layout: post
slug: flash-as2-hello-world
title: 'Flash: AS2 "Hello World!"'
wordpress_id: 65
categories:
- ActionScript
- Flash
tags:
- ActionScript
- as2
- Flash
- hello world
- textfield
- textformat
---

Vamos nos familiarizar com a ActionScript 2, nesse exemplo veremos como exibir uma mensagem no meio do palco sem usar a ferramenta de texto, apenas por AS.

Após abrir o Flash (na versão 6 ou superior) escolha novo arquivo (_New/Novo > Flash Document_) .

Clique no primeiro frame da Timeline e aperte F9 (atalho para abrir a janela das Actions).

Criando então o campo de texto aonde aparecerá a mensagem.


    
    
    this.createTextField("meuCampo", _root.getNextHighestDepth(), 0, 0, 0, 0);
    meuCampo.autoSize = true;
    meuCampo.html = true;
    meuCampo.text = "Hello World!";
    



É passado como parâmetro no método **createTextField()** o nome de instância do campo de texto (text field), a profundidade (o que define o que fica em cima do que - nesse caso usamos um método para retornar um valor para seu objeto ficar por cima de todos), o valor da posição em **x**, em **y**, largura e altura.

Não precisa se preocupar porque todos valores estão zerados, que como pode ver logo embaixo definimos que o nosso campo de texto pode auto ajustar o seu tamanho (autoSize). Logo aumentará de acordo com o tamanho do texto.

Mais abaixo pertimimos o campo de texto aceitar tags, ele aceita html.

E por fim o nosso texto, a mensagem que queremos que apareça - "Hello World!". Como nosso campo de texto tá definido como html poderiamos passar o texto assim:

    
    
    meuCampo.htmlText = "Hello World!";
    



Assim o campo de texto irá tratar as tags e mostrará só o texto. Isso é muito bom porque você pode passar um texto todo e ele ficará já pré-definido pelas tags. E também nos possibilita utilizar CSS para formatar o texto, mas isso não veremos agora.

Se você executar agora o arquivo verá a mensagem aparecer na parte superior esquerda, e com a formatação padrão.

Vamos então criar o objeto que formatará o nosso texto (**textFormat**).


    
    
    var style:TextFormat = new TextFormat();
    style.align = "center";
    style.bold = true;
    style.italic = true;
    style.color = 0x000099;
    style.font = "Verdana";
    style.size = 30;
    style.url = "http://rogeriolino.com"
    



Para poder conhecer  melhor as propriedades vamos deixar o texto bem "emperequetado". Alinhamento central (pode escolher: "justify", "center", "left", "right"), negrito (bold), italico (italic), a cor é representada de uma forma diferente do CSS ao invéz da "#" na frente usa-se "0x" (zero e xis) mais o código hexadecimal, a font (poderia ser "Arial" por exemplo), o tamanho (size) e por graça um link (url) passando o destino dele. Para este último funcionar tem que definir o campo como **html**.

Agora só falta adicionar esse estilo ao campo:


    
    
    meuCampo.setTextFormat(style);
    



E colocar o ele centralizado no palco:

    
    
    meuCampo._x = (Stage.width-meuCampo._width)/2;
    meuCampo._y = (Stage.height-meuCampo._height)/2;
    



Posição x recebe a largura do palco menos a largura do texto dividido por 2;
Posição y recebe a altura do palco menos a altura do texto dividido por 2;

Para funcionar corretamente temos que alinhar por último já que o tamanho do campo de texto irá mudar ao aplicar o estilo.

Agora é só executar. Abaixo o código completo:


    
    
    this.createTextField("meuCampo", _root.getNextHighestDepth(), 0, 0, 0, 0);
    meuCampo.autoSize = true;
    meuCampo.html = true;
    meuCampo.text = "Hello World!";
    
    var style:TextFormat = new TextFormat();
    style.align = "center";
    style.bold = true;
    style.italic = true;
    style.color = 0x000099;
    style.font = "Verdana";
    style.size = 30;
    style.url = "http://rogeriolino.com";
    
    meuCampo.setTextFormat(style);
    meuCampo._x = (Stage.width-meuCampo._width)/2;
    meuCampo._y = (Stage.height-meuCampo._height)/2;
    
