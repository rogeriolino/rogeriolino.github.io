---
author: rogeriolino
comments: true
date: 2010-09-09 21:22:29+00:00
layout: post
slug: php-template-engines
title: 'PHP: Template Engines'
wordpress_id: 315
categories:
- PHP
tags:
- django
- dwoo
- engine
- facelets
- flexy
- framework
- fxl
- h2o
- inheritance
- java
- jinja
- jsf
- mvc
- pear
- PHP
- Python
- quickskin
- smarty
- template
- tinybutstrong
- vemplator
- vlib
- xtemplate
---

Todo mundo que programa em PHP sente falta de uma boa alternativa para separar o código PHP do visual (HTML). Nessas horas vale a pena estudar algumas template engines para PHP disponíveis para saber qual que melhor se adapta à suas necessidades e projeto. Alguns frameworks MVC possuem sua própria engine, outros tentam.

[Smarty](http://www.smarty.net/)

O mais famoso e usado como inspiração por muitos outros projetos. Robusto (possuindo blocos condicionais/loops e várias funções próprias) e rápido ("compilando" suas páginas para arquivos PHP).

    
``` html
    <ul>
    {foreach from=$myArray item=foo}
        <li>{$foo}</li>
    {/foreach}
    </ul>
```

    
``` php
$smarty = new Smarty;
$arr = array(1000, 1001, 1002);
$smarty->assign ('myArray', $arr);
$smarty->display ('HelloWorld.tpl');
```


[vlibtemplate](http://vlib.clausvb.de/vlibtemplate.php)

Com esta engine saímos de um problema e entramos em outro, é necessário aprender (lembrar) algumas palavras reservadas para sinalizar variáveis, além do uso dos limitadores das expressões.


    
``` html
<html>
    <head>
        <title>{tmpl_var name='title_text'}</title>
        <meta http-equiv="content-type" content="text/html; charset=iso-8859-1" />
    </head>
    <body>
        <p>{tmpl_var name='body_text'}</p>
    </body>
</html>
```


``` php
$tmpl = new vlibTemplate('tmpl/basic.htm');
$tmpl->setvar('title_text', 'TITLE: This is the vLIB basic example ...');
$tmpl->setvar('body_text', 'BODY: This is the message set using setvar()');
$tmpl->pparse();
``` 

 
[FXL Template](http://www.feverxl.org/template/)

Muito pouco usual, o FXL faz uso dos blocos de comentário HTML para definir os loops. Outros semelhantes e nada melhores são: [QuickSkin](http://quickskin.worxware.com/) e [XTemplate](http://xtemplate.sourceforge.net/).


``` html    
 <table>
     <!-- START row -->
         <tr>
             <!-- START cell --> 
             <td >{td_value} </td> 
             <!-- END cell -->
         </tr>
     <!-- END row -->
 </table>
``` 


``` php
$fxlt = new fxl_template('example.tpl');
$fxlt_row = $fxlt->get_block('row');
$fxlt_cell = $fxlt_row->get_block('cell');
for ($tr = 1; $tr <= 3; $tr++) {
    for ($td = 1; $td <= 3; $td++) {
        $fxlt_cell->assign('td_value', $tr.':'.$td);
        $fxlt_row->assign('cell', $fxlt_cell);
        $fxlt_cell->clear();
    }
    $fxlt->assign('row', $fxlt_row);
    $fxlt_row->clear();
}
$fxlt->display();
```


[Vemplator](http://www.greaterscope.net/projects/Vemplator)

Mais do mesmo, mas com alterações de sintaxe.

``` html    
<h1>{if:logged} Welcome {username} {else:} User not logged {end:} </h1>
<ul>
    {foreach:rows,row}
        <li>
        {row['name']} 
        </li>
    {end:} 
</ul>
```


``` php
$t = new vemplator();
// if/else
$t->assign('logged', true);
$t->assign('username', 'Rogerio');
// loop
$items = array(
	array('name' => 'Laptop'),
	array('name' => 'Memory Stick')
);
$t->assign('rows', $rows);
echo $t->output('example.template.html');
``` 



[TinyButStrong](http://www.tinybutstrong.com/)

Uma alternativa ao estilo Smarty de muitos, porém é mais confuso e segue um padrão de nomenclatura bem particular.


``` html    
<table>
    <tr><td>[blk.val;block=tr]</td></tr>
</table>
```


``` php 
$TBS =& new clsTinyButStrong ;
$TBS->LoadTemplate('template.htm') ;
$list = array('X','Y','Z') ;
$TBS->MergeBlock('blk',$list) ;
$TBS->Show();
```



[Dwoo](http://dwoo.org/)

Possui como diferencial um [Template Inheritance](http://wiki.dwoo.org/index.php/TemplateInheritance), o que facilita muito a vida na construção de templates.


    
``` html
<html>
    <head>
        <title>{block "title"}My site name{/block} </title>
    </head>
    <body>
        <h1>{block "page-title"}Default page title{/block} </h1>
        <div id="content">
        {block "content"}
            Welcome to my amazing homepage
        {/block}
        </div>
    </body>
</html>
```
    
``` html 
{extends "base.html"}

{block "title"}
    Gallery
{/block}

{foreach $images img}
    <img src="{$img.url}" alt="{$img.description}"></img>
{/foreach}
```


``` php    
$dwoo = Dwoo();
$images = array(
    array('url' => 'img1.jpg', 'description' => 'Ferrari'),
    array('url' => 'img2.jpg', 'description' => 'BMW')
);
$params = array();
$params['images'] = $images;
echo $dwoo->get("gallery.tpl", $params);
``` 


[h2o](http://www.h2o-template.org/)

Baseado no Smarty, [Django Templates](http://www.djangoproject.com/) e [Jinja](http://jinja.pocoo.org/) (os dois últimos para Python).


    
``` html    
<html>
    <head>
        <title>{{ page.title }}</title>
    </head>
    <body>
        {{ page.content }}
    </body>
</html>
```


``` php 
$h2o = new h2o('index.html');
$page = array(
  'title' => 'title of a page',
  'body' => 'Hello world'
);
echo $h2o->render(compact('page'));
```


[PEAR Flexy](http://pear.php.net/package/HTML_Template_Flexy/)

Entre os projetos disponíveis no PEAR ([PHPLIB](http://pear.php.net/package/HTML_Template_PHPLIB/), [Sigma](http://pear.php.net/package/HTML_Template_Sigma/) e [IT](http://pear.php.net/package/HTML_Template_IT/)) esse é o melhor. 

Tem como desvantagem o fato de ter que definir as propriedades da sua classe como public (pelo menos dá para trabalhar com classes), linhas de includes e configurações exageradas (não presentes no exemplo abaixo), e algumas automações que precisam ser bem explicadas senão o programador (usuário) fica doido. Além de ter que codificar muito mais linhas se compararmos com os demais exemplos. 


    
``` html
<html>
    <head>
        <title>{title}</title>
    </head>
    <body>
        <!-- o valor do input será adicionado em $element['input'] -->
        Input Box: <input name="input" />
        <ul>
            <!-- isso é o mesmo que foreach ($numbers as $number => $string) -->
            <li flexy:foreach="numbers,number,string" >
                <a href="mypage.html?id={number}">{string}</a>
            </li>
        </ul>
        <!-- chamando o método da classe -->
        {someMethod()}
    </body>
</html>
```

    
``` php
class controller_test  {

    var $title;
    var $numbers = array();
    var $elements = array();

    function controller_test() {
        $this->start();
        $this->output();
    }

    function start() {
        $this->title = "Hello World";
        // create an HTML Element for the form element.
        $this->elements['input'] = new HTML_Template_Flexy_Element;
        $this->elements['input']->setValue('Hello');

        for ($i = 1;$i< 5;$i++) {
            $this->numbers[$i] = "Number $i";
        }
    }

    function output() {
        $output = new HTML_Template_Flexy();
        $output->compile("home.html");
        $output->outputObject($this,$this->elements);
    }

    function someMethod() {
        return "Hello From A Method";
    }

}
new controller_test();
```


_Todos os exemplos a cima foram retirados dos próprios sites dos projetos, sofrendo alterações afim de minimizar as linhas e focar em suas caracterísicas, vantagens e desvantagens._

Em meados do ano passado comecei escrever uma engine baseada no [JSF](https://javaserverfaces.dev.java.net/)+[Facelets](https://facelets.dev.java.net/) (Java) e nesse mês voltei a trabalhar nela e espero que no próximo ano (2011) já tenha uma versão liberada (farei um post sobre).
