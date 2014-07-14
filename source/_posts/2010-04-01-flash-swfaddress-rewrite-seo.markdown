---
author: rogeriolino
comments: true
date: 2010-04-01 14:44:53+00:00
layout: post
slug: flash-swfaddress-rewrite-seo
title: 'Flash: SWFAddress + ReWrite = SEO'
wordpress_id: 262
categories:
- ActionScript
- Flash
- Javascript
- SEO
tags:
- adobe
- ancora
- apache
- asual
- Flash
- html
- opensouce
- rewrite
- sample
- SEO
- swf
- swfaddress
- url
---

[![](http://rogeriolino.com/wp-content/uploads/2010/03/asual-swfaddress.jpg)](http://www.asual.com/swfaddress)


<blockquote>[SWFAddress](http://www.asual.com/swfaddress) é uma pequena mas poderosa biblioteca que provê [deep linking](http://en.wikipedia.org/wiki/Deep_linking) para Flash e Ajax. É uma ferramenta de desenvolvimento, permitindo a criação de URLs unicas e virtuais que podem apontar para uma seção do site ou aplicação. SWFAddress habilita algumas de importantes capacidades que faltam hoje em dia nas tecnologias [RIA](http://pt.wikipedia.org/wiki/RIA), incluindo:

> 
> 
	
>   * Adicionar ao Favoritos de um navegador ou site social
> 
	
>   * Enviar links via email ou mensageiros instantâneos
> 
	
>   * Procurar por um conteúdo específico através dos sites de buscas
> 
	
>   * Utilizar o histórico do navegador e o botão de recarregar
> 

</blockquote>



O [Flash](http://www.adobe.com/br/products/flash/) está para o [SEO](http://en.wikipedia.org/wiki/Search_engine_optimization) assim como o [Coringa está para o Batman](http://cinemaeafins.com/files/2008/11/batmancoringa.jpg). Mas nem tudo está perdido quando se trata de otimizar a indexação do site em SWF nos mecanismos de busca. Com SWFAddress você pode interagir com a página via javascript alterando a URL e o próprio conteúdo do filme, possibilidade do o uso dos botões voltar e avançar do browser, adicionar ao Favoritos e alterar a animação do seu filme de acordo com a URL que está sendo requisitada.

Caso sua página seja acessada através da URL **http://siteemflash.com/#contato**, você poderá pular na timeline indo direto para o frame do contato. Para evitar o reload da página toda interação é feita através de âncoras html (#). E as alterações da URL utilizando âncoras são desprezadas pelos buscadores, uma vez que a âncora só serve para movimentar o foco na mesma página, logo o seu conteúdo permanece inalterado.

É aí que entra o [módulo ReWrite do Apache](http://httpd.apache.org/docs/1.3/mod/mod_rewrite.html), com o mod_rewrite podemos escrever condições para tratar as requisições, redirecionando-as ou não. Então voltando ao exemplo anterior, teríamos uma condição que quando for requisitada a página **http://siteemflash.com/contato** (ou qualquer outra URL) redireciona para a página inicial (index) adicionando a âncora para contato (#contato) e imprime na página o conteúdo referente à mesma. Esse conteúdo impresso não será visível, apenas para indexação. O [sitemap](http://pt.wikipedia.org/wiki/Sitemap) ou a estrutura básica do site, também deve estar contido no bloco de código html invisível, juntamente com todas outras informações relevantes.

Resumindo, você acaba tendo um trabalho dobrado ao desenvolver o site, mas evita transtornos de indexação. É muito útil para quem não abre mão do site feito com o uso da ferramenta da Adobe.

No próprio site da Asual tem um [exemplo de uso do SWFAddress para SEO](http://www.asual.com/swfaddress/samples/seo/) (o exemplo pode ser baixado pelo site). Abaixo segue alguns sites que fizeram uso da biblioteca, no qual o primeiro eu participei do desenvolvimento:




	
  * [Óticas Paris](http://www.oticasparis.com.br/)

	
  * [Salinas Rio -inverno2010](http://www.salinas-rio.com.br/inverno2010/)

	
  * [Umbro](http://www.umbro.com/)

	
  * [Mis Architecture](http://www.mis-architecture.co.uk/)

	
  * [Kraftfoods - Food and Family](http://www.kraftfoods.com/foodandfamily)

	
  * [BBH](http://www.bartleboglehegarty.com/)




