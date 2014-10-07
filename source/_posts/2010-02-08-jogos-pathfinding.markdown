---
author: rogeriolino
comments: true
date: 2010-02-08 19:15:33+00:00
layout: post
slug: jogos-pathfinding
title: 'Jogos: Pathfinding'
wordpress_id: 166
categories:
- Jogos
- Tutorial
tags:
- a*
- ai
- algorithm
- algoritmo
- bots
- bug
- caminho
- dijkstra
- games
- ia
- Jogos
- meshes
- navigation
- pathfinding
- tutorial
- waypoint
---

É inevitável o estudo e a aplicação de [IA ](http://pt.wikipedia.org/wiki/Intelig%C3%AAncia_artificial)_(Inteligência Artificial) _em jogos nos quais possuem inimigos (personagens) não controlados pelo jogador (humano). E o problema mais comum é encontrar uma maneira eficaz de delimitar áreas no cenário aonde o personagem pode se locomover sem aparentar ser um robô seguindo um rastro, ou seja, mais próximo possível da realidade.

Normalmente visualizamos o problema como um grafo e nas arestas distribuimos valores que medem o custo entre um nó e outro. E para saber qual o melhor caminho (de menor custo) utilizamos de algum algoritmo de [caminho mínimo](http://pt.wikipedia.org/wiki/Problema_do_caminho_m%C3%ADnimo). Dentre os algoritmos existentes, os mais famosos são: [A*](http://pt.wikipedia.org/wiki/Algoritmo_A*) (A Estrela), [Algoritmo de Dijkstra](http://pt.wikipedia.org/wiki/Algoritmo_de_Dijkstra), [Branch-and-Bound](http://en.wikipedia.org/wiki/Branch_and_bound) e [etc](http://en.wikipedia.org/wiki/Category:Search_algorithms).


[![](http://rogeriolino.com/uploads/2010/02/AstarExample.gif)](http://rogeriolino.com/uploads/2010/02/AstarExample.gif)


Não vou analisar a efeciência do algoritmo utilizado, já que o objetivo é mostrar o problema ao utilizar grafos e uma possível solução (já aplicada em vários jogos).

Esse grafo delimitando a trajetória que pode ser percorrida pelo cenário é denominado _**waypoint graphs**_. O termo _waypoint_ ficou bastante conhecido no mod [Counter-Strike](http://pt.wikipedia.org/wiki/Counter-Strike), no qual para poder adicionar bots aos mapas para jogar "sozinho" era necessário antes percorrer todo o mapa criando marcaçöes (waypoints) que seriam utilizadas pelos bots para se locomoverem. Abaixo segue um vídeo mostrando alguns bugs envolvendo caminhos em jogos famosos:




## Evitando o problema


Uma forma de evitar esse problema é utilizando polígonos para delimitar aonde os personagens podem andar. Venha as imagens abaixo:

[caption id="attachment_171" align="alignnone" width="399" caption="Cenário marcado com waypoints"][![Cenário marcado com waypoints](http://rogeriolino.com/uploads/2010/02/Stormwind_waypoints.jpg)](http://rogeriolino.com/uploads/2010/02/Stormwind_waypoints.jpg)[/caption]

[caption id="attachment_172" align="alignnone" width="399" caption="Cenário marcado com Navegation Mesh"][![Cenário marcado com Navegation Mesh](http://rogeriolino.com/uploads/2010/02/Stormwind-NavMesh.jpg)](http://rogeriolino.com/uploads/2010/02/Stormwind-NavMesh.jpg)[/caption]

O [Navegation Mesh](http://en.wikipedia.org/wiki/Navigation_mesh) nada mais é que um grafo aonde cada nó é representado por um polígono, e ao invés de buscar por um ponto no cenário que se pode andar, verifica se o ponto do jogador está contido no polígono. Levando em consideração que os mesmos algoritmos utilizados com os waypoints podem ser utilizados para o navegation mesh efetuando pequenas modificações. Obviamente dessa forma será um pouco mais custosa ([custo do algoritmo](http://www.google.com.br/search?q=custo+algoritmo&ie=utf-8&oe=utf-8&aq=t&rls=org.mozilla:pt-BR:official&client=firefox-a)), em contrapartida, pode conseguir economizar uma quantidade enorme de waypoints.

[caption id="attachment_176" align="alignnone" width="538" caption="Waypoints: Saindo do ponto A para o ponto B"][![Waypoints: Saindo do ponto A para o ponto B](http://rogeriolino.com/uploads/2010/02/Halaa_waypoints2_AB.jpg)](http://rogeriolino.com/uploads/2010/02/Halaa_waypoints2_AB.jpg)[/caption]

[caption id="attachment_175" align="alignnone" width="538" caption="NavMesh: Saindo do ponto A para o ponto B"][![NavMesh: Saindo do ponto A para o ponto B](http://rogeriolino.com/uploads/2010/02/Halaa_navmesh2_AB.jpg)](http://rogeriolino.com/uploads/2010/02/Halaa_navmesh2_AB.jpg)[/caption]

Também nem sempre essa solução será a melhor para todos os tipos de jogos, é preciso antes de qualquer coisa, analisar com calma quais são as necessidades para não ter que utilizar um canhão para matar uma mosca.


## Alguns jogos que utilizam navigation meshes





	
  * [Halo 2](http://www.gamerankings.com/htmlpages2/562116.asp)

	
  * [Halo 3](http://www.gamerankings.com/htmlpages2/926632.asp)

	
  * [First Encounter Assault Recon (F.E.A.R.)](http://www.gamerankings.com/htmlpages2/920744.asp)

	
  * [Counter-Strike: Source](http://developer.valvesoftware.com/wiki/Navigation_Meshes)

	
  * [Metroid Prime](http://www.gamerankings.com/htmlpages2/447244.asp)

	
  * [Metroid Prime 2: Echoes](http://www.gamerankings.com/htmlpages2/589573.asp)

	
  * [Metroid Prime 3: Corruption](http://www.gamerankings.com/htmlpages2/928517.asp)

	
  * [Jak and Daxter: The Precursor Legacy](http://www.gamerankings.com/htmlpages2/516509.asp)

	
  * [Jak II](http://www.gamerankings.com/htmlpages2/914535.asp)

	
  * [Jak 3](http://www.gamerankings.com/htmlpages2/919901.asp)

	
  * [Uncharted: Drake's Fortune](http://www.gamerankings.com/htmlpages2/932984.asp)

	
  * [Scarface: The World is Yours](http://www.gamerankings.com/htmlpages2/922228.asp)


Algumas parte desse texto e imagens foram retirados do artigo publicado no site [ai-blog](http://www.ai-blog.net/archives/000152.html) e nesse mesmo blog há outra solução e um conteúdo muito mais robusto.
