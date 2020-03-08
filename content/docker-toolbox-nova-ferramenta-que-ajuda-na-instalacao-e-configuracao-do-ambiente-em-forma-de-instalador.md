Title: Docker Toolbox - Nova ferramenta que ajuda na instalação e configuração do ambiente em forma de instalador
Date: 2016-02-29 01:19
Author: paulo
Category: Docker
Tags: ambiente, docker, instalação, quickstart, toolbox
Slug: docker-toolbox-nova-ferramenta-que-ajuda-na-instalacao-e-configuracao-do-ambiente-em-forma-de-instalador
Status: published

Olá pessoal,

O Docker vem ganhando espaço em todo o mundo com a novo método de criação de ambiente que usa um recurso do link chamado "container". [Veja aqui](https://en.wikipedia.org/wiki/LXC). É uma virtualização no nível do sistema operacional que torna capaz rodar múltiplos e isolados sistemas Linux (containers) em um único host com Linux.

Por ser um recurso exclusivo do Linux, sistemas como OSX e Windows precisam de uma máquina virtual com Linux por trás dos panos para que através desta máquina o Docker funcione.

Até ai nenhum problema, senão fosse pelos passos que precisam ser dados no OSX e Windows para que todo o ambiente funcione perfeitamente. Não é nada difícil, mas é um trabalho braçal. Pensando em facilitar a adoção do Docker e também em ajudar os usuários a montar este ambiente de forma mais rápida e prática, foi lançada a ferramenta "Docker Toolbox". É uma ferramenta visual para OSX e Windows que já instala e configura o ambiente para você.

Ela pode ser baixada gratuitamente através do link:

<https://www.docker.com/products/docker-toolbox>

[![docker-toolbox-instalador](http://pcoutinho.com/wp-content/uploads/2016/02/docker-toolbox-instalador.png){.alignnone .size-full .wp-image-239 width="1236" height="868"}](http://pcoutinho.com/wp-content/uploads/2016/02/docker-toolbox-instalador.png)

Eu instalei em meu Mac e após seguir os passos do instalador (next, next, finish), já estava tudo funcionando, bastava abrir o programa "Docker Quickstart Terminal" que vem no pacote que ele já montava tudo e já podia começar a usar.

Dependendo do seu container e da sua necessidade, pode ser que já exista um pronto no Docker Hub:

<https://hub.docker.com/>

 

Bom, espero ter ajudado com estas dicas.

 

Obrigado e até o próximo post pessoal.
