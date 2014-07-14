---
author: rogeriolino
comments: true
date: 2013-12-27 12:06:51+00:00
layout: post
slug: php-slim-framework-action-based
title: 'PHP: Slim Framework action based'
wordpress_id: 831
categories:
- PHP
- Quickpost
- Tutorial
tags:
- actionbased
- composer
- crud
- framework
- github
- PHP
- skeleton
- slimapp
- slimframework
- tutorial
---

Há algum tempo utilizo o [Slim Framework](http://www.slimframework.com/) como base de meus projetos. E o motivo é sua simplicidade, velocidade e facilidade.

E para criar CRUD, eu utilizo um trecho de código para trabalhar rotas semelhante aos frameworks action based. Seguindo a convenção **/controlador/método**.

**Exemplo:**



<blockquote>Para a URI **/clients/add** terei uma classe controladora **ClientsController** com um método público (a ação) **add**. E o script tentará renderizar a página **add.php** dentro do diretório **clients**. E para a URI **/clients/view/1** será necessário ter o método **view** que recebe um parâmetro (nesse caso "1").
</blockquote>



Abaixo segue o trecho semelhante ao que está disponível no meu repositório no Github (porém nesse repositório utilizo o Twig como template engine): [rogeriolino/slimapp-skeleton](https://github.com/rogeriolino/slimapp-skeleton).


    
    
    
    $app->any('/:controller(/)(:action(/)(:params+))', function($controller, $action = 'index', $params = array()) use ($app) {
        // transforma o parâmetro :controller no nome da classe controladora (com namespace)
        $class = "MeuNamespace\\" . ucfirst($controller) . "Controller";
        try {
            if (!class_exists($class)) {
                throw new \Exception('Controlador não encontrado');
            }
            $ctrl = new $class($app);
            $methodName = preg_replace('/[^A-z0-9]/', '_', $action);
            $ref = new \ReflectionMethod($class, $methodName);
            if (!$ref->isPublic()) {
                throw new \Exception('O método do controlador não é público.');
            }
            $view = $methodName;
            $rs = $ref->invokeArgs($ctrl, $params);
            if ($rs) {
                $view = $rs;
            }
            $app->render("{$controller}/{$view}.php");
        } catch (\Exception $e) {
            $app->notFound();
        }
    });
    
    



Para utilizar o [slimapp-skeleton](https://github.com/rogeriolino/slimapp-skeleton) basta clonar o repositório e depois fazer a instalação das dependências via [Composer](http://getcomposer.org/).
