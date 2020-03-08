Title: Corrigindo o problema de permissão no Wordpress com Docker
Date: 2019-09-14 01:15
Author: paulo
Category: Docker
Tags: docker, permissão, wordpress
Slug: corrigindo-o-problema-de-permissao-no-wordpress-com-docker
Status: published

<!-- wp:paragraph -->

Olá,

Quem já migrou seu blog Wordpress para o container docker a fim de facilitar e organizar as coisas deve ter se deparado com o problema de permissão na pasta ***wp-content***.

A solução é simples e precisa ser executada dentro do container, então para entrar no container e solicitar o shell para executar comandos dentro dele, digite:

<!-- /wp:paragraph -->

<!-- wp:enlighter/codeblock -->

``` {.EnlighterJSRAW enlighter-language="generic" enlighter-theme="" enlighter-highlight="" enlighter-linenumbers="" enlighter-lineoffset="" enlighter-title="" enlighter-group=""}
docker exec -it [nome-do-container] bash
```

<!-- /wp:enlighter/codeblock -->

<!-- wp:paragraph -->

Logo depois mude o dono das pastas para ***www-data*** com o seguinte comando:

<!-- /wp:paragraph -->

<!-- wp:enlighter/codeblock -->

``` {.EnlighterJSRAW enlighter-language="generic" enlighter-theme="" enlighter-highlight="" enlighter-linenumbers="" enlighter-lineoffset="" enlighter-title="" enlighter-group=""}
chown -R www-data:www-data /var/www/html/wp-content
```

<!-- /wp:enlighter/codeblock -->

<!-- wp:paragraph -->

Agora basta sair do container (exit) e instalar o que você não conseguia instalar ou fazer o que não conseguia fazer.

Obrigado e até o próximo post pessoal.

<!-- /wp:paragraph -->
