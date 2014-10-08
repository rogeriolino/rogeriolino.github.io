---
author: rogeriolino
comments: true
date: 2014-06-09 17:44:23+00:00
layout: post
slug: php-jsonserializable
title: 'PHP: JsonSerializable'
wordpress_id: 916
categories:
- PHP
tags:
- ajax
- api
- json
- PHP
- php5
- php5.4
- restful
- serializable
---

Desde a **versão 5.4** do PHP ficou mais fácil transformar entidades em **JSON** através da função _json_encode()_. Basta implementar a interface [JsonSerializable](http://www.php.net/manual/class.jsonserializable.php), no qual o único método que precisa ser implementado pela subclasse é o _jsonSerialize_.

<!-- more -->


```php
class User implements \JsonSerializable {

    private $username;
    private $firstName;
    private $lastName;

    ...

    public function jsonSerialize() {
        return array(
            'username' => $this->username,
            'firstName' => $this->firstName,
            'lastName' => $this->lastName,
            'fullName' => "{$this->firstName} {$this->lastName}"
        );
    }

}
```

Serializando:

```php
$user = new User();
$user->setUsername("rogeriolino");
$user->setFirstName("Rogério");
$user->setLastName("Lino");
echo json_encode($user);
```

Resultado:

    
```json    
{
    "username": "rogeriolino",
    "firstName": "Rogério",
    "lastName": "Lino",
    "fullName": "Rogério Lino",
}
```  

Essa implementação se torna muito útil para desenvolvimento de APIs **RESTful** e **ajax responses** (json response).
