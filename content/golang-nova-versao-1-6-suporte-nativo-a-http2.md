Title: Golang - Nova versão 1.6 (suporte nativo a HTTP2)
Date: 2016-02-24 02:04
Author: paulo
Category: Golang
Tags: 1.6, golang, nova, versão
Slug: golang-nova-versao-1-6-suporte-nativo-a-http2
Status: published

Olá pessoal,

No dia 17 de fevereiro saiu a versão 1.6 da linguagem Go (Golang).

Em termos de velocidade o Google se empenhou na versão 1.5.1 em deixar ela o mais rápido possível e o garbage collector o mais otimizado também, então com relação a isso, não mudou tanto.

Os destaques desta nova versão ficam por conta dos itens:

-   Suporte ao protocolo HTTP2, habilitado por padrão
-   Suporte ao recurso "vendor", que era experimental até então, para as bibliotecas
-   Em aplicações onde há um maior consumo de memória, a versão 1.6 está mais rápida
-   O algoritmo de ordenação da função "sort.Sort" está 10x mais rápido, porém pode causar alguma incompatibilidade, pois os itens não ficam na mesma ordem (use "sort.Stable" para manter a ordem original)
-   Algumas melhorias também ocorreram na parte de templates do Go

A lista completa você pode conferir aqui:

<https://golang.org/doc/go1.6>

 

Obrigado e até o próximo post pessoal.

 

 
