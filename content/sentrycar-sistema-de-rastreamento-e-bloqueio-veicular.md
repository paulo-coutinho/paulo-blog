Title: SentryCar - Sistema de rastreamento e bloqueio veicular
Date: 2017-08-11 22:20
Author: paulo
Category: Sem categoria
Tags: gps, monitorar, rastreamento, sentrycar
Slug: sentrycar-sistema-de-rastreamento-e-bloqueio-veicular
Status: published

[![](http://pcoutinho.com/wp-content/uploads/2017/08/Logo.png){.wp-image-354 .aligncenter width="209" height="172"}](http://pcoutinho.com/wp-content/uploads/2017/08/Logo.png)

Olá,

Recentemente desenvolvi todo um sistema de rastreamento e bloqueio de veículos, chamado de SentryCar.

O projeto consiste em uma aplicação mobile ou web que pode ser acessada por um cliente/usuário para rastrear um ou vários veículos, monitorar sua localização e velocidade, além de bloquear e desbloquear o carro, cortando a fonte de combustível quando ele atinge 20Km/H ou menos.

O sistema é dividido em 6 partes:

-   **Apps** (iOS e Android).
-   **Web** (mesmo sistema acessado pelos apps e pagamento da mensalidade).
-   **Servidor** (servidor desenvolvido em Go para receber conexões TCP/IP dos rastreadores e coletar os dados necessários).
-   **Banco de dados** MySql.
-   **Rastreadores** importados do AliExpress e interpretação do protocolo definido pelo fabricante.
-   **API** que permite qualquer device via HTTP/TCP enviar sua posição, desde que esteja cadastrado no sistema. Tanto os aplicativos, como o sistema web e o rastreador, utilizam a mesma API.

 

Eu precisei fazer uns vídeos para que a Apple aprovasse meu app, então fiz alguns vídeos demos e coloquei em minha conta do Youtube:

-   https://www.youtube.com/watch?v=pKCQLeSOvdg
-   https://www.youtube.com/watch?v=0RsqSgQETRc

 

URL para demonstração:

-   http://sentrycar.prsolucoes.com

 

Caso alguém precise desenvolver algo do tipo, podemos fazer uma parceria.

 

Obrigado e até o próximo post pessoal.
