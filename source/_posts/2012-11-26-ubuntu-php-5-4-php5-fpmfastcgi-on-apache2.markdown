---
author: rogeriolino
comments: true
date: 2012-11-26 16:55:46+00:00
layout: post
slug: ubuntu-php-5-4-php5-fpmfastcgi-on-apache2
title: 'Ubuntu: PHP 5.4 + PHP5-FPM/FastCgi on Apache2'
wordpress_id: 706
categories:
- Linux
- PHP
- Tutorial
tags:
- apache
- fastcgi
- PHP
- php-fpm
- php5.4
- tutorial
- ubuntu
---

Os comandos abaixo que devem ser executados como **root**.



### Passo 1 - Verificando a versão do PHP no repositório




    
    
    apt-cache show php5 | grep Version
    



Caso a versão mais nova já esteja na 5.4 ou superior, então pule para o próximo passo. Senão execute os comandos abaixo para adicionar o repositório com a versão 5.4.


    
    
    apt-get install python-software-properties
    add-apt-repository ppa:ondrej/php5
    apt-get update
    






### Passo 2 - Instalando os pacotes



Execute o commando abaixo para instalar de uma só vez o Apache2 como Worker, o módulo FastCgi e o PHP 5.4 com PHP-FPM.

    
    
    apt-get install apache2-mpm-worker libapache2-mod-fastcgi php5-fpm php5
    



Habilitando os módulos de requeridos para o próximo passo:


    
    
    a2enmod actions fastcgi alias
    





### Passo 3 - Configurando o Apache2


Editar o arquivo de configuração do módulo fastcgi


    
    
    vim /etc/apache2/mods-enabled/fastcgi.conf
    



Caso já tenha algumas entradas, comente (adicionando # no início da linha ou simplesmente remova) e adicione as seguintes linhas:


    
    
    AddHandler php5-fcgi .php
    Action php5-fcgi /php5-fcgi
    Alias /php5-fcgi /usr/lib/cgi-bin/php5-fcgi
    FastCgiExternalServer /usr/lib/cgi-bin/php5-fcgi -socket /var/run/php5-fpm.sock -pass-header Authorization
    



obs: O arquivo /usr/lib/cgi-bin/php5-fcgi realmente não existe, será apenas uma ponte para o PHP-FPM




### Passo 4 - Configurando o PHP-FPM



Abra o arquivo de configuração do PHP-FPM


    
    
    vim /etc/php5/fpm/pool.d/www.conf
    



E procure pela opção listen. Se não estiver como socket, altere conforme abaixo:


    
    
    listen = /var/run/php5-fpm.sock
    



Essa opção serve para evitar overhead no TCP (caso o socket não esteja configurado)

obs: Repare que tem que ser o mesmo caminho especificado no fastcgi.conf



### Passo 5 - Reiniciando e testando



Reiniciando os serviços:


    
    
    /etc/init.d/apache2 restart
    /etc/init.d/php5-fpm restart
    



Criando arquivo de teste:


    
    
    cd /var/www
    echo '<?php phpinfo();' | tee info.php
    



Depois acesse o arquivo criado via browser: http://nome_servidor/info.php

Confira a **versão do PHP descrita no cabeçalho** e se o valor do **Server API** está como **FPM/FastCGI**.

![](http://rogeriolino.com/wp-content/uploads/2012/11/phpinfo.png)
