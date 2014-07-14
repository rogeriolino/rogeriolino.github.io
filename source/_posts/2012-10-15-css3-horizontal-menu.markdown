---
author: rogeriolino
comments: true
date: 2012-10-15 14:34:32+00:00
layout: post
slug: css3-horizontal-menu
title: 'CSS3: Horizontal Menu'
wordpress_id: 638
categories:
- CSS
- HTML5
tags:
- CSS
- css3
- example
- gradient
- horizontal
- html5
- menu
- navbar
- transition
---

Exemplo de um menu dropdown horizontal, utilizando gradient e transition apenas com CSS3.



### CSS



    
    
    .hmenu {
        height: 40px;
        position: relative;
    }
    
    .hmenu, .hmenu ul { 
        border-radius: 3px;
    }
    
    .hmenu, .hmenu * {
        margin: 0;
        padding: 0;
    }
    
    .hmenu li {
        list-style: none;
        position: relative;
        display: inline;
    }
    
    .hmenu li {
        list-style: none;
        position: relative;
        float: left;
    }
    
    /* all links style */
    .hmenu a {
        font-weight: bold;
        font-family: Arial, Verdana, sans-serif;
        font-size: 12px;
        text-decoration: none;
    }
    
    /* main link style */
    .hmenu>li>a {
        padding: 13px 20px;
        float: left;
    }
    
    .hmenu li ul {
        width: 150px;
        position: absolute;
        visibility: hidden;
        opacity: 0;
        /* fading transition */
        transition: opacity .5s ease-in-out;
       -moz-transition: opacity .5s ease-in-out;
       -webkit-transition: opacity .5s ease-in-out;
    }
    
    /* first submenu */
    .hmenu>li>ul {
        top: 40px;
        left: 0;
        border-top-left-radius: 0;
        border-top-right-radius: 0;
    }
    
    .hmenu li:hover>ul {
        visibility: visible;
        opacity: 1;
    }
    
    .hmenu li ul ul {
        top: 0px;
        left: 150px;
        border-top-left-radius: 0;
        border-bottom-left-radius: 0;
    }
    
    .hmenu li ul li {
        width: 150px;
        display: block;
    }
    
    /* submenu link style */
    .hmenu ul a {
        margin: 3px 2px;
        padding: 8px 15px;
        border-radius: 5px;
        display: block;
    }
    
    /* theming */
    .hmenu {
        box-shadow: 0px 1px 5px #ccc;
        background: #ffffff; /* Old browsers */
        background: -moz-linear-gradient(top,  #ffffff 0%, #e5e5e5 100%); /* FF3.6+ */
        background: -webkit-gradient(linear, left top, left bottom, color-stop(0%,#ffffff), color-stop(100%,#e5e5e5)); /* Chrome,Safari4+ */
        background: -webkit-linear-gradient(top,  #ffffff 0%,#e5e5e5 100%); /* Chrome10+,Safari5.1+ */
        background: -o-linear-gradient(top,  #ffffff 0%,#e5e5e5 100%); /* Opera 11.10+ */
        background: -ms-linear-gradient(top,  #ffffff 0%,#e5e5e5 100%); /* IE10+ */
        background: linear-gradient(to bottom,  #ffffff 0%,#e5e5e5 100%); /* W3C */
        filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#ffffff', endColorstr='#e5e5e5',GradientType=0 ); /* IE6-9 */
    }
    
    .hmenu a {
        color: #999;
    }
    
    .hmenu a:hover {
    }
    
    .hmenu li:hover>a {
        color: #000;
        text-shadow: 1px 1px 2px #ccc;
    }
    
    .hmenu ul {
        background-color: #f1f1f1;
        box-shadow: 0px 1px 5px #bbb;
    }
    
    .hmenu ul a:hover {
        background-color: #e1e1e1;
    }
    
    .hmenu>li>ul {
        border-top: 2px solid #999;
    }
    
    .hmenu li ul ul {
        border-left: 2px solid #999;
    }
    





### HTML



    
    
    <ul class="hmenu">
        <li><a href="#">Home</a></li>
        <li>
            <a href="#">Services</a>
            <ul>
                <li><a href="#">Service 1</a></li>
                <li>
                    <a href="#">Service 2</a>
                    <ul>
                        <li><a href="#">Subservice 1</a></li>
                        <li><a href="#">Subservice 2</a></li>
                        <li><a href="#">Subservice 3</a></li>
                    </ul>
                </li>
                <li><a href="#">Service 3</a></li>
                <li><a href="#">Service 4</a></li>
                <li><a href="#">Service 5</a></li>
            </ul>
        </li>
        <li>
            <a href="#">About</a>
            <ul>
                <li><a href="#">Company</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </li>
    </ul>
    



[Visualizar o menu funcionando](http://dev.rogeriolino.com/exemplos/css/hmenu.html)
