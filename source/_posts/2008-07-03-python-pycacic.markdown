---
author: rogeriolino
comments: true
date: 2008-07-03 18:31:11+00:00
layout: post
slug: python-pycacic
title: 'Python: PyCACIC'
wordpress_id: 113
categories:
- Programas
- Python
tags:
- agente linux
- cacic
- pycacic
- Python
- software publico
---

<blockquote>
![Cacic](http://rogeriolino.files.wordpress.com/2008/07/logo.png)**CACIC:** "Primeiro Software Público do Governo Federal, resultado do Consórcio de
Cooperação entre a SLTI - Secretaria de Logística Tecnologia da Informação, do
Ministério do Planejamento, Orçamento e Gestão - MPOG e a DATAPREV - Empresa de
Tecnologia e Informações da Previdência Social, desenvolvido pelo Escritório
Regional da DATAPREV no Espírito Santo.

O Cacic é capaz de fornecer um diagnóstico preciso do parque computacional e
disponibilizar informações como o número de equipamentos e sua distribuição nos mais
diversos órgãos, os tipos de softwares utilizados e licenciados, configurações de
hardware, entre outras. Também pode fornecer informações patrimoniais e a localização
física dos equipamentos, ampliando o controle do parque computacional e a segurança
na rede."

**fonte:** [http://www.softwarepublico.gov.br/ver-comunidade?community_id=3585](http://www.softwarepublico.gov.br/ver-comunidade?community_id=3585)
</blockquote>


**PyCacic**

Há bastante tempo existe a versão do **Agente Cacic** para Windows, versão bastante difundida não só no Brasil quanto no mundo, mas ainda não existia uma versão para **GNU/Linux**. O que para a comunidade de software livre era uma pena, diante da grande utilidade e compentência do Cacic.

E para felicidade geral foi lançada nesta segunda-feira (30/06/08) a versão rc1 (release candidate 1) do agente para **GNU/Linux** escrita em **Python**, no qual tive o prazer de ser um dos principais desenvolvedores junto com toda - excelente - equipe de desenvolvimento da **Dataprev** (**URES** - Unidade Regional Espírito Santo).

Esta versão conta com a praticidade de um gerador de pacotes preconfigurados (deb, rpm ou tgz genérico) para facilitar a instação nas estações. Coleta informações de software, hardware, variáveis de ambiente, informações de rede e patrimoniais, partições e unidades de disco.

O código fonte e pacotes podem ser baixados no próprio site da comunidade no [Software Público Brasileiro](http://www.softwarepublico.gov.br/).
