Title: Golandy - Game multiplayer open-source em HTML5 com Phaser + Golang e WebSocket - Versão para desktop, browser, android e iOS
Date: 2016-05-28 04:07
Author: paulo
Category: Game, Golang
Tags: game, golandy, golang, html5, opensource, phaser
Slug: golandy-game-multiplayer-open-source-em-html5-com-phaser-golang-e-websocket-versao-para-desktop-browser-android-e-ios
Status: published

Olá pessoal,

A um tempinho atrás fiz um game bem simples, usando HTML5 + Phaser e Go + WebSocket.

Fiz também os arquivos necessários para rodar o projeto tanto em desktop, web, android e iOS usando o Apache Cordova.

O link do game rodando é:

<http://golandy.prsolucoes.com>

Os links para baixar se encontram no meu Github, segue:

Cliente: <https://github.com/prsolucoes/golandy-web>

Servidor: <https://github.com/prsolucoes/golandy-server>

 

Sobre o jogo, ele é um tipo de clone do clássico bomberman. É multiplayer em tempo real. Fiz usando a engine Phaser e o servidor em Go. Toda a comunicação usa WebSocket e a versão nativa do Google, pois o desempenho da versão Gorilla é horrível.

Os mapas podem ser editados usando o MapEditor/Tiled (padrão tmx).

O game funciona no navegador, no desktop, no android, no iOS e onde mais o Apache Cordova suportar, pois como é em HTML5, qualquer browser roda ele. Em casa por exemplo, minha filha joga na TV.

É claro que o jogo não é perfeito e a comunidade da engine não ajuda muito.

Segue imagem:

[![Golandy Game Screenshot](http://pcoutinho.com/wp-content/uploads/2016/05/Screenshot-2016-05-28-01.04.19.png){.alignnone .size-full .wp-image-291 width="2540" height="1432"}](http://pcoutinho.com/wp-content/uploads/2016/05/Screenshot-2016-05-28-01.04.19.png)

 

Espero com este projeto, que a idéia e a arquitetura possam servir de inspiração para outros projetos e trabalhos.

Obrigado e até o próximo post pessoal.

 
