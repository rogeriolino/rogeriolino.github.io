---
author: rogeriolino
comments: true
date: 2010-03-11 19:17:36+00:00
layout: post
slug: html5-database
title: 'HTML5: Database'
wordpress_id: 207
categories:
- HTML5
- Javascript
- Tutorial
tags:
- cookie
- database
- db
- firefox
- html5
- Javascript
- safari
- sql
- sqlite
- tutorial
- webkit
---

Uma das funcionalidades mais robustas presentes nessa nova versão do HTML é exatamente o suporte ao armazenamento local, sem ser por [Cookie](http://pt.wikipedia.org/wiki/Cookie) mas sim pelo banco de dados presente no browser. Tal funcionalidade já está presente no [Webkit](http://webkit.org) que fornece uma aplicação de exemplo: [http://webkit.org/demos/sticky-notes/](http://webkit.org/demos/sticky-notes/).

No Webkit as informações são armazenadas utilizando [SQLite](http://www.sqlite.org/), e acredito que o Firefox irá pelo mesmo caminho, já que ele também utiliza o SQLite para armazenar os "Favoritos".

Para abrir a conexão com a banco de dados (**openDatabase**) deve-se informar o nome do banco (_database name_), a versão (_database version_), o nome de exibição (_display name_) e o tamanho estimado em bytes (_estimated size_) que será armazenado.


    
    
    var db;
    try {
        if (window.openDatabase) {
            db = openDatabase("MyDB", "1.0", "HTML5 Database Example", 200000);
            if (!db) {
                alert("Failed to open the database.");
            }
        } else {
            alert("Couldn't open the database.");
        }
    } catch(err) { }
    
    



Uma vez estabelecida a conexão a interação passa ser efetuada através de comandos [SQL](http://pt.wikipedia.org/wiki/SQL).


    
    
    db.transaction(function(tx) {
    tx.executeSql("CREATE TABLE myTable (id REAL UNIQUE, name TEXT, description TEXT, timestamp REAL");
    });
    
    db.transaction(function (tx) {
    tx.executeSql("INSERT INTO myTable (id, name, description, timestamp) VALUES (?, ?, ?, ?)", [id, name, description, timestamp]);
    });
    
    db.transaction(function(tx) {
    tx.executeSql("DELETE FROM myTable WHERE id = ?", [id]);
    });
    
    db.transaction(function(tx) {
        tx.executeSql(
            "SELECT * FROM myTable WHERE id = ?", 
             [id], 
             function(tx, result) {
                 // success
                 if (result.rows.length > 0) {
                       alert("My name is: " + result.rows.item(0)['name']);
                 } else {
                      alert("Sorry, no result for this id");
                  }
             }, 
             function(tx, error) {
                 // error
                 alert("Error when try retrieve data: " + error.message);
             }
        );
    });
    
    



O método **executeSql** pode receber 4 parâmetros, sendo eles:



	
  * O SQL a ser executado

	
  * Os valores parametrizados para serem utilizados na consulta (array)

	
  * Função callback para ser executada caso haja sucesso (onSuccess)

	
  * Função callback para ser executada caso haja falha (onError)



Sinceramente eu achei muito legal conceder mais esse poder ao Javascript no HTML5, porém _"com grandes poderes vêm grandes responsabilidades"_.

