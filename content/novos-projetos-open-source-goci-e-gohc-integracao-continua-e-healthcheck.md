Title: Novos projetos open-source: GoCI e GoHC (integração contínua e healthcheck)
Date: 2016-05-21 20:42
Author: paulo
Category: Golang
Tags: continuous, go, goci, gohc, golang, healthcheck, integration
Slug: novos-projetos-open-source-goci-e-gohc-integracao-continua-e-healthcheck
Status: published

Olá pessoal,

Gostaria de compartilhar com vocês os meus dois novos projetos open-source em Go (golang).

**1 - GoCI**

O GoCI é um projeto para integração contínua de fácil instalação, manutenção e configuração.

Com ele você pode criar suas tarefas de integração através de execuções em CLI ou através de arquivos Javascript.

A inicialização do projeto é feita por dois arquivos principais, o **config.ini** e o arquivo do seu projeto em **JSON**, que podem ser vários na verdade.

O GoCI exporta algumas variáveis pro Javascript, a fim de que você possa implementar sua lógica de teste, deploy ou qualquer outra tarefa e ainda controlar cada um destes objetos. Ao manipular estes objetos você acompanha todos os resultados em tempo real através da interface web do GoCI, como os outputs, a barra de progresso, a duração da execução, etc.

Cada tarefa pode mostrar resultados em diversas abas, a aba principal é a Console, onde o output geral aparece ali, além do output normal, você tem output de erro, sucesso, alerta, etc.

Cada tarefa do seu projeto pode ter vários passos (steps), sendo cada passo baseado em um plugin, que como falamos, podem ser **"cli"** ou **"js"**.

Porém o projeto não se limita somente a desenvolvimento ou testes e deploy de uma aplicação. Você pode fazer o que quiser dentro dele. Você pode criar mais plugins, caso queira. Eu tenho algumas tarefas por exemplo, que enviam push pro meu device de teste, tenho outra que baixa os arquivos de linguagens atualizados da ferramenta de localização e coloca dentro do projeto.

O projeto vem com uma pasta "extras/sample" com os arquivos de exemplo, embora sejam bem simples.

Toda a interface foi pensada para funcionar perfeitamente em smartphones, tablets ou PCs.

Segue algumas imagens:

\[gallery order="DESC" ids="283,282,281,280,279"\]

Link para o projeto:

[https://github.com/prsolucoes/goci ](https://github.com/prsolucoes/goci)

 

**2 - GoHC**

O GoHC é um sistema **passivo** de healthcheck com suporte a notificações quando entra em modo warning ou error. Ele é passivo por não ser de sua responsabilidade realizar a operação de validação, pois criaria um limite e o propósito do projeto é poder criar healthcheck para qualquer coisa que possa entrar em contato com o servidor onde estiver rodando.

Exemplos do que você pode fazer com ele:

1.  Validar se uma URL/servidor/IP está ativo.
2.  Medir tempo de determinadas operações, como o intervalo de tempo de processamento do pagamento do cliente com o seu gateway de pagamento. Você pega este intervalo em sua aplicação e envia pro healthcheck validar se ele está dentro do range de sucesso, alerta ou crítico/erro/falha.
3.  Validar de a quantidade de memória/cpu/disco/network está dentro de um range.
4.  Validar se a quantidade de humidade de uma planta está dentro de um range e emitir um alerta se estiver em nível crítico.

Com este sistema de healthcheck você possui 3 formas de validar a "saúde" do que você precisa monitor e esta validação pode ser automática dentro dos 3 ranges possíveis (sucesso, alerta, erro/falha) ou manual, onde você diz qual é o status manualmente.

1.  Ping - é o tipo mais simples, você chama o healthcheck e ele de acordo com o último ping enviado e o atual verifica em qual das áreas do range você está e envia alertas ou não - mas é você quem diz o tempo do ping para cada range.
2.  Range - é o tipo mais específico, onde você especifica as áreas dos ranges e ao receber um range qualquer, ele valida em qual dos ranges você está baseado no range enviado.
3.  Manual - é o tipo onde você diz o status diretamente, não tem informação de ping ou range neste tipo, o status que você enviar é o que ele vai assumir e pode enviar alertas também caso você especifique.

Tudo isso pode ser acompanhado através de uma interface web bem amigável e que foi pensada para funcionar perfeitamente em smartphones, tablets ou PCs.

Existe na interface hoje o modo lista de healthchecks e o modo dashboard, dependendo de como você quer ver os healthchecks você pode optar por um ou por outro. Se você quer deixar numa televisão, sugiro o modo dashboard.

Os alertas são baseados em plugins. Hoje eu criei apenas alguns, mas essenciais.

1.  CLI - executa algo no servidor no CLI
2.  SendGrid - envia um email usando o sendgrid
3.  PushBullet - envia um push usando o pushbullet
4.  Http Get - faz requisição HTTP GET em uma URL
5.  Slack - envia via webhook uma mensagem para o serviço Slack

A inicialização do projeto é feita por dois arquivos principais, o **config.ini** e um arquivo **JSON** chamado **healthchecks.json** com a lista de seus healthchecks e plugins de alerta.

O projeto vem com uma pasta "extras/sample" com os arquivos de exemplo, embora sejam bem simples.

No arquivo **config.ini**, você pode especificar uma propriedade chamada **warmTime**, que define um tempo após a inicialização para o sistema começar a processar os healthchecks.

Segue algumas imagens:

\[gallery order="DESC" ids="276,278,277"\]

Segue o link do projeto:

<https://github.com/prsolucoes/gohc>

 

É isso pessoal, espero ter ajudado alguém com estes projetos.

Obrigado e até o próximo post pessoal.
