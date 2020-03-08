Title: PHP - Yii Framework 2.0
Date: 2014-10-14 05:06
Author: paulo
Category: PHP
Tags: composer, framework, php, web, yii, yii framework
Slug: php-yii-framework-2-0
Status: published

Olá pessoal,

Acabou de ser lançado o Yii Framework 2.0.

Framework que eu particularmente utilizo devido a sua robustez, arquitetura, segurança e ao mesmo tempo simplicidade para fazer uma aplicação enterprise.

Algumas coisas que se destacaram nesta versão que vale a pena citar aqui:

-   O gerador de códigos conhecido como Gii agora possui um gerador via web e via console.
-   Framework com foco em testes.
-   Utiliza frameworks conhecidos no mercado e especificações PSR.
-   Debugger integrado (não precisamos mais de plugins para visualizar o que acontece na aplicação).
-   A parte de segurança foi feia com a ajuda de 2 especialistas em segurança com PHP, que revisaram e rescreveram esta parte.
-   O Yii 1 já era um dos frameworks top em performance, e a versão 2 foi reformulada pra ter um desempenho ainda melhor, inclusive na parte relacionada ao banco de dados (ActiveRecord).
-   Uma coisa que me incomodava no Yii 1 era o fato de você alterar um único campo no modelo e ao dar o "save/update" ele alterava todos os campos (montava um update com todos os campos) da tabela. Agora na versão 2 ele controla isso internamente e monta a query de "update" somente com os campos que você modificou.
-   O Yii Framework 2 vem com suporte nativo a RESTful, possibilitando nativamente escrever API RESTful de forma simplificada.
-   A parte de autenticação agora possui suporte a autenticação externa, vindo com suporte nativo a OAuth1, OAuth2 e OpenID, ou seja, você já pode integrar com autenticação via Google e Facebook por exemplo de forma simples. Veja o exemplo no site oficial para entender a simplicidade do negócio.
-   Todos os widgets vem com suporte ao Bootstrap.
-   Vários helpers adicionados para trabalhar com elementos html, gerar links e todas aquelas coisas comuns em que as vezes criávamos funções estáticas para ter o mesmo resultado.
-   Criação de modelo para trabalhar com formulários simplificado.
-   Criação de regras para as classes ActiveRecord e Model (antigo CFormModel), simplificados.
-   Uso de namespace em todo o framework.
-   A arquitetura de pastas foi reformulada e proporcionou ainda mais a separação com o código do projeto, pois ele foi ainda mais projetado nesta versão para ser extensível e modular.
-   O componente de envio de e-mail padrão é o Swift com suporte a engine de templates do Yii.

Com todos esses recursos, potência, segurança e cuidado que os engenheiros do Yii possuem ao fazer o framework, que outro framework vai conseguir bater de frente com ele?

Fica aqui o meu parabéns a equipe de engenheiros que desde de sua versão 1 que eu uso até hoje, fizeram um excelente trabalho.

O link da notícia no site oficial é:  
<http://www.yiiframework.com/news/81/yii-2-0-0-is-released/>

Obrigado e até o próximo post pessoal.
