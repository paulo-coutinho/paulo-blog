Title: Golang - WebRemoteLog - Um serviço feito com a linguagem Go para log remoto
Date: 2015-07-02 04:43
Author: paulo
Category: Golang
Tags: go, golang, log, logger, web remote
Slug: golang-webremotelog-um-servico-feito-com-a-linguagem-go-para-log-remoto
Status: published

Olá,

Tenho visto o frequente uso da linguagem Go em diversas empresas. Existem diversos artigos e eventos que participo em que algumas empresas citam seu caso de uso.

Passei então a estudar até conseguir compreender os conceitos e decidi fazer um projeto que estava em minha lista a um bom tempo, porém ao invés de fazer em PHP com Yii2 decidi fazer com Go + MongoDB.

O projeto WebRemoteLog consiste em um gerenciador de log remoto. Sua aplicação faz o log enviando os dados através de uma chamada ao serviço da aplicação e este log fica gravado em uma coleção do MongoDB. A interface web serve para visualizar os logs em tempo real, como no console da IDE, além de permitir que você possa filtrar as mensagens.

Com este simples projeto, eu usei três recursos da linguagem e seus pacotes: http(rotas, rest, get, post), MongoDB, json.

O resultado ficou muito bom e eficiente. O código fonte do projeto está no github:

<https://github.com/prsolucoes/WebRemoteLog-Go>

Imagens:

\[gallery columns="2" ids="143,169,168"\]

Você pode baixar, modificar e colaborar livremente.

Obrigado e até o próximo post pessoal.
