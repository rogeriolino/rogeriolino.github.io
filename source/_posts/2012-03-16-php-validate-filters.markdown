---
author: rogeriolino
comments: true
date: 2012-03-16 17:46:43+00:00
layout: post
slug: php-validate-filters
title: 'PHP: Validate Filters'
wordpress_id: 529
categories:
- PHP
- Tutorial
tags:
- class
- classe
- email
- filter
- filters
- filter_var
- ip
- oo
- PHP
- regex
- tutorial
- url
- validate
- validation
- validator
---

A partir do PHP 5.2 foi introduzida a função [filter_var](http://php.net/filter_var). Que serve justamente para filtrar uma variável a partir de um filtro especificado.



<blockquote>

>     
>     
>     mixed filter_var ( mixed $variable [, int $filter = FILTER_DEFAULT [, mixed $options ]] )
>     // Returns the filtered data, or FALSE if the filter fails.
>     
> 
> 
</blockquote>



Filtros pré-definidos:


    
    
    // email filtering
    echo filter_var('email@domain.com', FILTER_VALIDATE_EMAIL); // email@domain.com
    echo filter_var('domain.com', FILTER_VALIDATE_EMAIL); // false
    
    // url filtering
    echo filter_var('http://rogeriolino.com', FILTER_VALIDATE_URL); // http://rogeriolino.com
    echo filter_var('rogeriolino.com', FILTER_VALIDATE_URL); // false
    
    // ip filtering
    echo filter_var('127.0.0.1', FILTER_VALIDATE_IP); // 127.0.0.1
    echo filter_var('127.0.1', FILTER_VALIDATE_IP); // false
    



Como a função pode retornar **FALSE** (caso o filtro falhe) ou o valor filtrado. Podemos utilizar o **Not identical operator** (!==) para verificar se retorno é realmente FALSE, ou seja, o valor testado não passou pelo filtro.

Colocando em prática a função mais orientação à objetos para criar algumas classes validadoras:


    
    
    
    /**
     * Interface Validator 
     */
    interface Validator {
    
        public function isValid($value);
    
    }
    
    /**
     * Abstract class Simple Validator
     */
    abstract class SimpleValidator implements Validator {
        
        protected abstract function defaultFilter();
    
        public function isValid($value) {
            return filter_var($value, $this->defaultFilter()) !== false;
        }
    
    }
    
    /**
     * Simple Email validator 
     */
    class EmailValidator extends SimpleValidator {
    
        protected function defaultFilter() {
            return FILTER_VALIDATE_EMAIL;
        }
    
    }
    
    /**
     * Simple URL validator 
     */
    class UrlValidator extends SimpleValidator {
    
        protected function defaultFilter() {
            return FILTER_VALIDATE_URL;
        }
    
    }
    
    /**
     * Simple IP Validator 
     */
    class IpValidator extends SimpleValidator {
    
        protected function defaultFilter() {
            return FILTER_VALIDATE_IP;
        }
    
    }
    



Testando


    
    
    // email validating
    $validator = new EmailValidator();
    echo $validator->isValid('rogeriolino@com'); // false
    echo $validator->isValid('contact@rogeriolino.com'); // true
    echo $validator->isValid('contact+spam@rogeriolino.com'); // true
    
    // URL validating
    $validator = new UrlValidator();
    echo $validator->isValid('http://rogeriolino.com'); // true
    echo $validator->isValid('http://rogeriolino.com/contact'); // true
    echo $validator->isValid('rogeriolino.com/contact'); // false
    echo $validator->isValid('https://rogeriolino'); // true
    echo $validator->isValid('ftp://rogeriolino.com'); // true
    
    // URL validating
    $validator = new IpValidator();
    echo $validator->isValid('127.0.0.1'); // true
    echo $validator->isValid('127.0.0'); // false
    echo $validator->isValid('1050:0000:0000:0000:0005:0600:300c:326b'); // true
    echo $validator->isValid('1050:0000:0000:0000:0005:0600'); // false
    



Para ver outros filtros:
[http://php.net/manual/filter.filters.validate.php](http://php.net/manual/filter.filters.validate.php)
