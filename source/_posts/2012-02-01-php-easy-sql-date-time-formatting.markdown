---
author: rogeriolino
comments: true
date: 2012-02-01 18:26:03+00:00
layout: post
slug: php-easy-sql-date-time-formatting
title: 'PHP: Easy SQL date time formatting'
wordpress_id: 478
categories:
- PHP
- Tutorial
tags:
- array
- array_reverse
- data
- date
- datetime
- easy
- explode
- format
- formatação
- hora
- implode
- join
- PHP
- sql
- strtotime
- time
- timestamp
- tutorial
---

**SQL to Human:**

    
    
    /* 
     * date
     */
    $format = 'm/d/Y'; // en-US
    // $format = 'd/m/Y'; // pt-BR
    $date = '2012-02-01';
    echo date($format, strtotime($date));
    
    
    /* 
     * datetime
     */
    $format .= ' H:i:s';
    $datetime = '2012-02-01 11:33:59';
    echo date($format, strtotime($datetime));
    



**Human to SQL:**

    
    
    /* 
     * date
     */
    $sqlFormat = 'Y-m-d';
    $date = '02/01/2012';
    
    // en-US
    echo date($sqlFormat, strtotime($date));
    // pt-BR
    echo join('-', array_reverse(explode('/', $date)));
    
    
    /* 
     * datetime
     */
    $sqlFormat = 'Y-m-d H:i:s';
    
    // en-US
    $datetime = '02/01/2012 11:33:59';  
    echo date($sqlFormat, strtotime($datetime));
    
    // pt-BR
    $datetime = '01/02/2012 11:33:59';
    $datetime = explode(' ', $datetime);
    $date = join('-', array_reverse(explode('/', $datetime[0])));
    echo $date . ' ' . $datetime[1];
    
    



**Reference:**

[strtotime](http://php.net/strtotime)
The function expects to be given a string containing an English date format and will try to parse that format into a Unix timestamp (the number of seconds since January 1 1970 00:00:00 UTC), relative to the timestamp given in now, or the current time if now is not supplied.

[date](http://php.net/date)
Returns a string formatted according to the given format string using the given integer timestamp or the current time if no timestamp is given. In other words, timestamp is optional and defaults to the value of [time()](http://php.net/time).

[explode](http://php.net/explode)
Returns an array of strings, each of which is a substring of string formed by splitting it on boundaries formed by the string delimiter.

[array_reverse](http://php.net/array_reverse)
Takes an input array and returns a new array with the order of the elements reversed.

[join / implode](http://php.net/join)
Join array elements with a glue string.
