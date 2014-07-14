---
author: rogeriolino
comments: true
date: 2006-10-05 18:48:48+00:00
layout: post
slug: paradigma-orientado-a-objetos
title: Paradigma Orientado a Objetos
wordpress_id: 55
categories:
- Paradigmas
tags:
- clas
- herança
- java
- objetos
- oo
- orientado
- paradigma
- PHP
- polimorfismo
- poo
---

A Programação Orientada a Objetos (POO) tem grande vantagem diantes as demais, como por exemplo o reuso de código, organização lógica dos programas e estruturação do código produzido.

Abaixo alguns conceitos de POO.

**Classe**
É na classe que definimos as propriedades e os métodos dos objetos.

**Objeto:**
É a instância de uma classe, é o elemento criado a partir da classe, segundo o molde definido nela.

**Herança:**
É a característica da Orientação a Objetos que permite derivar uma classe de outra já existente. Herdando seus métodos e tudo que contém nela.

**Polimorfismo:**
É a alteração da funcionalidade de um método em diferentes níveis de classe, sem alterar o formato do mesmo. Permite a Classe derivada alterar a funcionalidade de algo feito pela mãe, aproveitando ou não o que a mãe fazia. Ou seja, é o fato de objetos diferentes responderem a uma mesma chamada de método de maneiras diferentes.

Exemplo (Java):

    
    
    
    class FormaGeometrica {
    
        public void introduz() {
            System.out.println("Sou uma forma geométrica");</p>
        }
    
    }
    
    class Retangulo extends FormaGeometrica {
     
        public void introduz() {
            System.out.println("Sou um retângulo");
        }
    
    }
    
    class Circulo extends FormaGeometrica {
    
        public void introduz() {
            System.out.println("Sou um círculo");
        }
    
    }
    
    public class Uso {
    
        public static void main (String[] args) {
            FormaGeometrica g1, g2, g3;
            g1 =  new FormaGeometrica();
            g2 = new Retangulo();
            g3 = new Circulo();
            g1.introduz(); // Sou uma forma geométrica
            g2.introduz(); // Sou um retângulo
            g3.introduz(); // Sou um círculo
        }
    
    }
    



**mais sobre:**

http://pt.wikipedia.org/wiki/Orientado_a_objeto
http://www.vivaolinux.com.br/artigos/verArtigo.php?codigo=2365
