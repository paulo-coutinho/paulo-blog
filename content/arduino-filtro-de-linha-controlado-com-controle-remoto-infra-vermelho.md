Title: Arduino - Filtro de linha controlado com controle remoto infra-vermelho
Date: 2015-04-19 05:23
Author: paulo
Category: Arduino
Tags: 12V, 5V, arduino, controle, filtro, infra, infra-vermelho, linha, remoto, vermelho
Slug: arduino-filtro-de-linha-controlado-com-controle-remoto-infra-vermelho
Status: published

Olá pessoal,

Recentemente precisei desenvolver para a casa de minha mãe um projeto que foi na verdade um desafio bem interessante.

O problema era o seguinte: Ela possuía quatro equipamentos que precisavam ser acionados via controle remoto, de forma que com um único controle eu pudesse controlar tudo e que houvesse a possibilidade de remover um dos quatros dispositivos e colocar  outro no lugar (luz de led da estante, 5 barras de LED do armário da sala e outros).

Pensando neste problema, eu tentei inicialmente criar um filtro de linha próprio(ou régua), mas não achei o socket fêmea que eu queria, que era o socket fêmea no padrão brasileiro com abas parafusáveis, parecido com a imagem abaixo:

\[gallery ids="121"\]

Por não encontrar esse socket e não dar certo com outros sockets, eu comprei um filtro de linha e modifiquei ele pra ficar do jeito que eu queria. Escolhi um modelo que já tinha um fusível de proteção, cabos resistentes com tomada dentro do padrão e sockets dentro do padrão de tomadas brasileiro e ficou bem legal, dêem uma olhada nas imagens abaixo:

\[gallery ids="124,130,129,128,127,126,125,123"\]

 

\[embed\]https://www.youtube.com/watch?v=q09QiujExD4\[/embed\]

Depois de bastante trabalho para modificar o filtro de linha e ligar no meu projeto com o arduino, tive outro problema, ao ligar os 4 canais simultaneamente do módulo de relé o arduino resetava, pois a corrente era bem maior do que a corrente limite da porta 5V do arduino. Acabei colocando um conversor DC-DC (12V -\> 5V 3A) e coloquei tanto o receptor de infra-vermelho quanto o módulo com 4 relés para ser alimentado pelos 5V deste conversor.

O código do projeto ficou bacana e o produto "filtro de linha com controle remoto" ficou muito bom.

Caso alguém tenha alguma dúvida ou queira alguma ajuda, basta entrar em contato.

Obrigado e até o próximo post pessoal.
