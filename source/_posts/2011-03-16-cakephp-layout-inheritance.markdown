---
author: rogeriolino
comments: true
date: 2011-03-16 18:37:26+00:00
layout: post
slug: cakephp-layout-inheritance
title: 'CakePHP: Layout Inheritance'
wordpress_id: 356
categories:
- PHP
- Tutorial
tags:
- cakephp
- dica
- framework
- inheritance
- layout
- PHP
- template
- tip
- tutorial
---

Para quem está utilizando o CakePHP ou já utilizou e também sentiu falta de herança nos layouts. Segue abaixo uma dica para ajudar na criações de templates utilizando o CakePHP.


    
    
    &lt;?php
    // sublayout.ctp
    
    ob_start();
    
    ?&gt;
     <!-- html content -->
     &lt;?php eco $content_for_layout; ?&gt;
     <!-- html content -->
    &lt;?php
    
    $content = ob_get_contents();
    ob_end_clean();
    
    echo $this->renderLayout(
            $content, 
            'default' // parent layout
    );
    




    
    
    &lt;?php
    // controller class
    class MyController extends AppController {
    
        function test() {
            $this->layout = 'sublayout';
        }
    
    }
    



