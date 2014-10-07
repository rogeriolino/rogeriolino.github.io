---
author: rogeriolino
comments: true
date: 2010-03-26 13:21:12+00:00
layout: post
slug: php-annotations
title: 'PHP: Annotations'
wordpress_id: 249
categories:
- PHP
tags:
- addendum
- annotations
- doctrine
- java
- jpa
- persistence
- PHP
- reflection
---

É indiscutível a agilidade e facilidade de configuração que as annotations provêm no [Java](http://java.sun.com/), e com o objetivo de trazer tal comodidade ao [PHP](http://php.net) surgiu o projeto [Addendum](http://code.google.com/p/addendum/) - escrito por [Jan Suchal](http://jsmf.net/) - que permite via [Reflection](http://en.wikipedia.org/wiki/Reflection_(computer_science)) acessar as annotations das classes.

As annotations devem ser escritas em blocos de comentários, uma vez que o [@](http://thesmithfam.org/blog/2006/05/07/php-the-operator/) (caracter que inicia uma annotation) é um caractere reservado no PHP. Elas podem ser mono ou multi valoradas de acordo com os exemplos abaixo.
   
    
``` php
// Custom annotation
class Persistent extends Annotation {}

// Custom annotation
class Table extends Annotation {}

// Multi valued annotation
class Secured extends Annotation {
   public $role;
   public $level;
}

/** 
 * @Persistent 
 * @Table("people")
 * @Secured(role = "admin", level = 2)
 */
class Person {
   // some code
}

// getting the annotation by class name
$reflection = new ReflectionAnnotatedClass('Person');

// getting the annotation by instance
$person = new Person();
$reflection = new ReflectionAnnotatedClass($person);

// true
$reflection->hasAnnotation('Persistent'); 

// contains string "people"
$reflection->getAnnotation('Table')->value; 
```

E seguindo na mesma onda da [JPA](http://java.sun.com/javaee/technologies/persistence.jsp), a [versão 2.0 do projeto Doctrine](http://www.doctrine-project.org/blog/php-5-3-and-doctrine-2-0-teaser) implementou também a mesma funcionalidade e agora possui suas próprias annotations facilitando a configuração das classes de persistência e seus relacionamentos.


``` php
/**
 * @DoctrineEntity(tableName="cms_articles")
 */
class CmsArticle {

  /**
  * @DoctrineId
  * @DoctrineColumn(type="integer")
  * @DoctrineIdGenerator("auto")
  */
  public $id;

  /**
  * @DoctrineColumn(type="varchar", length=255)
  */
  public $topic;

  /**
  * @DoctrineColumn(type="varchar")
  */
  public $text;

  /**
  * @DoctrineManyToOne(targetEntity="CmsUser", joinColumns={"user_id" = "id"})
  */
  public $user;

  /**
  * @DoctrineOneToMany(targetEntity="CmsComment", mappedBy="article")
  */
  public $comments;
}
```
