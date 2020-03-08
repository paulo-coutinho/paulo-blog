Title: PHP - Usar aspas simples ou duplas para criar uma String?
Date: 2014-09-15 14:26
Author: paulo
Category: PHP
Tags: aspas, dupla, php, simples, stirng, web
Slug: php-usar-aspas-simples-ou-duplas-para-criar-uma-string
Status: published

Olá pessoal,

A um tempo atrás estava pesquisando sobre performance e um dos pontos levantados foi o fato de usar aspas duplas, pois para o interpretador do PHP custa muito mais processamento exibir uma frase do tipo:

    "Nome: $nome"

Do que:

    'Nome: ' . $nome

E para comprovar isso, usei o codepad.org para executar e medir o tempo de processamento de um script bem simples que realiza o teste nestes dois cenários.

O primeiro script que usa no teste aspas duplas está aqui:

<https://gist.github.com/prsolucoes/bbb047c320f9e50e875f>

O segundo script que usa no teste aspas simples está aqui:

<https://gist.github.com/prsolucoes/7677b60d600feb6b091c>

 

Resultado (média de tempo em MS para 3 execuções):

[Com aspas duplas: 76ms]{style="color: #ff0000;"}

[Com aspas simples: 60ms]{style="color: #ff0000;"}

[ ]{style="color: #ff0000;"}

São 16ms acrescentados no tempo de execução do script, simplesmente por suar aspas duplas. Imagina isso multiplicado por N em um sistema cheio de códigos utilizando aspas duplas por todo lado.

Espero que tenha ajudado.
