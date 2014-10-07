---
author: rogeriolino
comments: true
date: 2012-10-01 15:47:04+00:00
layout: post
slug: php-5-4-new-features
title: 'PHP: 5.4 new features'
wordpress_id: 625
categories:
- PHP
tags:
- features
- PHP
- php5.4
---

Segue abaixo algumas das novas funcionalidades da versão 5.4 do PHP. Para ver mais informações, siga os links no final do post.



### Trait


Trait (ou mixin em outras linguagens) é um mecanismo que permite que as classes reutilizem métodos de outras classes sem a necessidade de estende-la.


``` php
    trait Singleton {
        public static function getInstance() { ... }
    }
    
    class A {
        use Singleton;
        // ...
    }
    
    class B extends ArrayObject {
        use Singleton;
        // ...
    }
    
    // Singleton method is now available for both classes
    A::getInstance();
    B::getInstance();
```

### Sintaxe curta para definição de Array


Agora é possível instanciar um array de maneira semelhante à outras linguagens de script, como por exemplo, Javascript.


``` php
$a = [1, 2, 3];
$b = ['foo' => 'orange', 'bar' => 'apple'];
```



### Referência direta ao retorno das funções/métodos


Também é possível fazer fazer chamada direta ao retorno das funções, sem que haja necessidade de atribuir o valor a uma variável e só depois fazer a chamada.


``` php
function fruits() {
    return ['apple', 'banana', 'orange'];
}
echo fruits()[0]; // Outputs: apple
```
    

O mesmo serve para chamadas através de novas **instâncias**:


    
``` php
class Person {
    private $name;
    public function setName($name) {
        $this->name = $name;
    }
    public function getName() {
        return $this->name;
    }
}
function createPerson() {
    $p = new Person();
    $p->setName('Rogerio');
    return $p;
}

echo (new Person)->setName('Rogerio')->getName(); // Outputs: Rogerio
```


### Método mágico __invoke


Permite chamar um objeto como se fosse uma função


``` php
class MoneyObject {
    private $value;
    function __construct($val) {
        $this->value = $val;
    }
    function __invoke() {
        return sprintf('$%.2f',$this->value); 
    }
}
$Money = new MoneyObject(11.02/5*13);
echo $Money(); // Outputs: $28.65
```


### Built-in Web Server (CLI)


CLI server é uma pequena implementação de um Web server que você pode executar via linha de comando.

``` sh
% php -S localhost:8000
``` 


Obviamente, não é para ser usado em produção.


### Native Session Handler Interface


Ao invés de definir várias funções, você pode criar uma handler para a sua sessão, e apenas informá-lo no session_set_save_handler.


``` php
SessionHandler implements SessionHandlerInterface {
    public int close ( void )
    public int destroy ( string $sessionid )
    public int gc ( int $maxlifetime )
    public int open ( string $save_path , string $sessionid )
    public string read ( string $sessionid )
    public int write ( string $sessionid , string $sessiondata )
}

session_set_save_handler(new MySessionHandler);
```
    

### JsonSerialize Interface


Semelhante ao __tostring ao tentar imprimir um objeto, você pode pre-definir o objeto que será serializado para o formato json, através do uso da função **json_encode**.


``` php    
class Foo implements JsonSerializable {

    private $data = 'Bar';

    public function jsonSerialize() {
        return array('data'=>$this->data);
    }
}

echo json_encode(new Foo); // Outputs: {"data":"Bar"}
```    

Para visualizar as alterações entre as versão 5.3 e 5.4, [clique aqui](http://www.php.net/manual/en/migration54.php).

**Fontes:**
[http://php.net/manual/en/migration54.new-features.php](http://php.net/manual/en/migration54.new-features.php)
[http://css.dzone.com/polls/what-new-feature-php-54](http://css.dzone.com/polls/what-new-feature-php-54)
[http://www.oracle.com/technetwork/articles/dsl/lerdorf-php54-1564639.html](http://www.oracle.com/technetwork/articles/dsl/lerdorf-php54-1564639.html)
