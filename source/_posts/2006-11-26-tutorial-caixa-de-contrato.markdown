---
author: rogeriolino
comments: true
date: 2006-11-26 01:50:06+00:00
layout: post
slug: tutorial-caixa-de-contrato
title: Tutorial Caixa de Contrato
wordpress_id: 56
categories:
- CSS
- Javascript
- Tableless
- XHTML
tags:
- caixa
- contrato
- CSS
- css3
- div
- Javascript
- license
- Tableless
- XHTML
---

<del>Esses dias no Fórum do Flashmasters perguntaram como poderia fazer um campo de texto que não pudesse ser alterado, modificado. Mas que tivesse uma barra de rolagem. A minha sugestão foi que ao invez de usar um textArea como ele queria, usa-se uma div mesmo, com overflow auto.</del>

**[UPDATE date="2012-11-08"]**
Atualizando em 08/11/2012, exemplo funcional utilizando textarea. No qual o seu conteúdo pode ser importado de um arquivo txt. Foi utilizado javascript apenas para habilitar e desabilitar o botão "Next".

[Clique aqui para ver a nova versão](http://dev.rogeriolino.com/exemplos/css/license/index.html)
**[/UPDATE]**

**Exemplo:**

** CSS**

    
    
      #license-box {
        font-family: Verdana, Arial, Sans-Serif;
        width: 600px;
        padding: 20px 30px;
        border-radius: 5px;
        box-shadow: 1px 1px 10px #999;
        margin: auto;
        
        background: #ffffff; /* Old browsers */
        background: -moz-linear-gradient(top,  #ffffff 0%, #f3f3f3 50%, #ededed 51%, #ffffff 100%); /* FF3.6+ */
        background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#ffffff), color-stop(50%,#f3f3f3), color-stop(51%,#ededed), color-stop(100%,#ffffff)); /* Chrome,Safari4+ */
        background: -webkit-linear-gradient(top,  #ffffff 0%,#f3f3f3 50%,#ededed 51%,#ffffff 100%); /* Chrome10+,Safari5.1+ */
        background: -o-linear-gradient(top,  #ffffff 0%,#f3f3f3 50%,#ededed 51%,#ffffff 100%); /* Opera 11.10+ */
        background: -ms-linear-gradient(top,  #ffffff 0%,#f3f3f3 50%,#ededed 51%,#ffffff 100%); /* IE10+ */
        background: linear-gradient(to bottom,  #ffffff 0%,#f3f3f3 50%,#ededed 51%,#ffffff 100%); /* W3C */
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ffffff', endColorstr='#ffffff',GradientType=0 ); /* IE6-9 */
      }
    
      #license-box h1 {
        font-size: 20px;
        color: #333333;
        text-transform: uppercase;
        text-align: center;
      }
    
      #license-box .text textarea {
        width: 100%;
        height: 400px;
        border-color: #f1f1f1;
        background-color: #fff;
      }
    
      #license-box .next {
        padding: 15px 0 0 0;
        float: right;
      }
    
      #license-box .next input {
        padding: 5px 20px;
        color: #fff;
        font-weight: bold;
        border-width: 0;
        border-radius: 5px;
        box-shadow: 1px 1px 5px #666;
        cursor: pointer;
        background: #b4e391; /* Old browsers */
        background: -moz-linear-gradient(top,  #b4e391 0%, #61c419 50%, #b4e391 100%); /* FF3.6+ */
        background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#b4e391), color-stop(50%,#61c419), color-stop(100%,#b4e391)); /* Chrome,Safari4+ */
        background: -webkit-linear-gradient(top,  #b4e391 0%,#61c419 50%,#b4e391 100%); /* Chrome10+,Safari5.1+ */
        background: -o-linear-gradient(top,  #b4e391 0%,#61c419 50%,#b4e391 100%); /* Opera 11.10+ */
        background: -ms-linear-gradient(top,  #b4e391 0%,#61c419 50%,#b4e391 100%); /* IE10+ */
        background: linear-gradient(to bottom,  #b4e391 0%,#61c419 50%,#b4e391 100%); /* W3C */
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#b4e391', endColorstr='#b4e391',GradientType=0 ); /* IE6-9 */
      }
    
      #license-box .next input:disabled {
        background: #e2e2e2; /* Old browsers */
        background: -moz-linear-gradient(top,  #e2e2e2 0%, #dbdbdb 50%, #d1d1d1 51%, #fefefe 100%); /* FF3.6+ */
        background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#e2e2e2), color-stop(50%,#dbdbdb), color-stop(51%,#d1d1d1), color-stop(100%,#fefefe)); /* Chrome,Safari4+ */
        background: -webkit-linear-gradient(top,  #e2e2e2 0%,#dbdbdb 50%,#d1d1d1 51%,#fefefe 100%); /* Chrome10+,Safari5.1+ */
        background: -o-linear-gradient(top,  #e2e2e2 0%,#dbdbdb 50%,#d1d1d1 51%,#fefefe 100%); /* Opera 11.10+ */
        background: -ms-linear-gradient(top,  #e2e2e2 0%,#dbdbdb 50%,#d1d1d1 51%,#fefefe 100%); /* IE10+ */
        background: linear-gradient(to bottom,  #e2e2e2 0%,#dbdbdb 50%,#d1d1d1 51%,#fefefe 100%); /* W3C */
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#e2e2e2', endColorstr='#fefefe',GradientType=0 ); /* IE6-9 */
      }
    
      #license-box .checkbox {
        padding: 20px 0;
      }
    
      #license-box .checkbox input {
        margin-right: 5px;
      }
      
      #license-box .checkbox label {
        font-size: 12px;
        font-weight: bold;
      }
    



Você pode alterar o estilo da borda: [estilos de borda css](http://www.w3schools.com/css/tryit.asp?filename=trycss_border-style).

**HTML**

    
    
        <div id="license-box">
            <h1>Terms and Conditions</h1>
            <div class="text">
                <textarea disabled="true">
                        {{{ LICENSE HERE }}}
                </textarea>
            </div>
            <div>
                <div class="next">
                    <input id="btn-next" class="btn" type="submit" value="Next" disabled="true" />
                </div>
                <div class="checkbox">
                    <input id="license-check" type="checkbox" value="" onclick="setTimeout(function() { document.getElementById('btn-next').disabled = !document.getElementById('license-check').checked; }, 100)" />
                    <label for="license-check">I accept</label>
                </div>
            </div>
        </div>
    



<del>Uma encheção de lingüiça aí. E com apenas algumas linhas no CSS você tem sua caixa de contrato personalizada.</del>

[Clique aqui](http://dev.rogeriolino.com/exemplos/css/license/index.html) para ver o exemplo.
