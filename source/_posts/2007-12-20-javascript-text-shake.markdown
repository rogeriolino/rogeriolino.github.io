---
author: rogeriolino
comments: true
date: 2007-12-20 19:52:58+00:00
layout: post
slug: javascript-text-shake
title: 'Javascript: Text Shake'
wordpress_id: 104
categories:
- CSS
- Javascript
tags:
- CSS
- DOM
- embaralhar
- Javascript
- jquery
- mistura
- settimeout
- shake
- text
- twister
---

![shake.jpg](http://rogeriolino.com/wp-content/uploads/2007/12/shake.jpg)


Mais um exemplo em Javascript, agora uma função, creio que conhecida por muitos já, que tem a finalidade de embaralhar o texto contido em uma tag qualquer (embaralhar o texto após passar o mouse por cima).

Há duas maneiras de usá-la, uma aplicando em apenas uma tag o evento, e a outra, aplicando o evento a todas os elementos de mesmo _"tag name"._

Ex:

    
    
    shakeAll('h2');
    




    
    
    <h3 onmouseover="shake(this)"></h3>
    



**[update]**
_Codigo portado para jQuery_

    
    
    /**
     * textShake
     * @author rogeriolino http://rogeriolino.com
     */
    (function($) {
        
        $.fn.textShake = function(options) {
            
            var defaults = {
                timeIn: 20,
                timeOut: 50
            };
            
            var opts = $.extend({}, defaults, options);
            
            return this.each(function() {
                
                var self = $(this);
                self.running = false;
                
                self.mouseover(function() {
                    if (!self.running) {
                        self.running = true;
                        self.content = self.text();
                        self.len = self.content.length;
                        self.init(self.i);
                    }
                });
                
                self.init = function(i) {
                    self.i = 0;
                    setTimeout(
                        function() {
                            self.text(self.shakeChar(i));
                            if (i <= self.len) {
                                self.init(++i);
                            } else {
                                self.undo(0);
                            }
                        }
                        , 
                        opts.timeIn
                    );
                }
    	        
                self.shakeChar = function(i) {
                    return self.text().substring(0, i - 1) + randomChar() + self.text().substring(i);
                }
    	        
                self.undo = function(i) {
                    setTimeout(
                        function() {
                            if (i <= self.len) {
                                self.text(self.content.substring(0, i) + self.text().substring(i));
                                self.undo(++i);
                            } else {
                                self.text(self.content);
                                self.running = false;
                            }
                        }, 
                        opts.timeOut
                    );
                }
    	        
            });
            
            function range(ini, fin) {
                var j = 0;
                var a = new Array(fin - ini);
                for (var i = ini; i < fin; i++) {
                    a[j++] = i;
                }
                return a;
            }
    
            function randomChar() {
                var arr = new Array();
                arr = arr.concat(range(48, 57), range(65, 90), range(97, 122)); // numbers, uppers, lowers 
                var c = arr[Math.floor(Math.random() * arr.length)];
                return String.fromCharCode(c);
            }
       
        }
        
    })(jQuery);
    


**[/update]**

[clique aqui para visualizar](http://dev.rogeriolino.com/exemplos/javascript/shake/index.html)
