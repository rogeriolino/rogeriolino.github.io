---
author: rogeriolino
comments: true
date: 2013-07-17 21:23:11+00:00
layout: post
slug: php-5-5-new-features
title: 'PHP: 5.5 new features'
wordpress_id: 788
categories:
- PHP
tags:
- class
- features
- finally
- generators
- iterator
- novidades
- php.net
- php5
- php5.5
- versão
- version
---

A versão 5.5 do PHP foi lançada no mês passado, e trouxe algumas funcionalidades relevantes. Entre elas, seguem abaixo as mais interessantes (pelo menos para mim):



### Generators



Com o [Generators](http://br1.php.net/manual/en/language.generators.overview.php) você pode iterar com um dado dentro de uma função sem a necessidade de criar um array para ser retornado.


    
    
    function numerosInteiros($minimo, $maximo) {
        for ($i = $minimo; $i <= $maximo; $i++) {
            // a keyword yield "libera" a variável $i para a iteração (sem sair/retornar da/a função)
            yield $i;
        }
    }
    
    for (numerosInteiros(1, 10) as $numero) {
        echo "$numero ";
    }
    



Ou um exemplo do próprio site php.net


    
    
    function xrange($start, $limit, $step = 1) {
        if ($start < $limit) {
            if ($step <= 0) {
                throw new LogicException('Step must be +ve');
            }
    
            for ($i = $start; $i <= $limit; $i += $step) {
                yield $i;
            }
        } else {
            if ($step >= 0) {
                throw new LogicException('Step must be -ve');
            }
    
            for ($i = $start; $i >= $limit; $i += $step) {
                yield $i;
            }
        }
    }
    
    /*
     * Note that both range() and xrange() result in the same
     * output below.
     */
    
    echo 'Single digit odd numbers from range():  ';
    foreach (range(1, 9, 2) as $number) {
        echo "$number ";
    }
    



Repare que não há necessidade de criar um array, populá-lo, retorná-lo, e só depois iterá-lo para imprimir os valores.



### Finally



Mesmo já possuindo a bastante tempo o bloco try/catch, só agora a partir da versão 5.5 foi introduzida a keyword **finally**. No qual você define um bloco para ser executado de qualquer maneira (mesmo que caia no catch).


    
    
    function divide($a, $b) {
        if ($b === 0) {
            throw new Exception('Divisão por zero');
        }
        return $a / $b;
    }
    
    try {
        echo '10 / 2 = ' . divide(10, 2);
        echo '2 / 0 = ' . divide(2, 0);
    } catch (Exception $e) {
        echo $e->getMessage();
    } finally {
        echo 'Término das operações';
    }
    





### ::class



Agora é possível resolver o nome da classe apenas através de [MinhaClass::class](http://br1.php.net/oop5.basic#language.oop5.basic.class.class).


    
    
    <?php
    namespace NS {
        class ClassName {
        }  
        echo ClassName::class;
    }
    ?>
    





### empty()



Agora é possível passar expressões para a função [empty()](http://br2.php.net/migration55.new-features#migration55.new-features.empty) e não mais apenas variáveis.


    
    
    <?php
    function always_false() {
        return false;
    }
    
    if (empty(always_false())) {
        echo "This will be printed.\n";
    }
    
    if (empty(true)) {
        echo "This will not be printed.\n";
    }
    ?>
    





### Veja mais



Para saber mais sobre a nova versão acesse os links abaixo:

[http://www.php.net/releases/5_5_0.php](http://www.php.net/releases/5_5_0.php)
[http://br2.php.net/manual/en/migration55.php](http://br2.php.net/manual/en/migration55.php)

E o **php.net** também lançou sua versão nova (ainda em beta). [Clique aqui para abrir a versão beta](http://php.net/?setbeta=1&beta=1).
