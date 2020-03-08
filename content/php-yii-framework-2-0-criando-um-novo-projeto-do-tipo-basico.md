Title: PHP - Yii Framework 2.0 - Criando um novo projeto do tipo básico
Date: 2014-10-14 07:11
Author: paulo
Category: PHP
Tags: basic, composer, framework, php, yii
Slug: php-yii-framework-2-0-criando-um-novo-projeto-do-tipo-basico
Status: published

Olá pessoal,

Resolvi escrever um tutorial de como usar o [**composer**](https://getcomposer.org/ "PHP Composer") para criar um projeto simples com o Yii Framework 2.0. Depois de muito quebrar a cabeça consegui achar os comandos corretos para instalar e criar uma aplicação básica com o Yii Framework 2.0, pois tem muito material das versões betas e RC e fica um pouco confuso saber como proceder na versão final que saiu.

De forma resumida precisamos instalar o composer, adicionar o repositório no composer e criar uma aplicação Yii com o composer.

1 - Instalando o composer (ao instalar o **composer**, um arquivo **composer.phar** será baixado para a pasta aonde você está executando o comando, portanto, execute o comando abaixo em uma pasta que servirá como repositório deste arquivo, pois em todos os comandos que irão usar o **composer** você precisará **passar o caminho deste arquivo como parâmetro**):

    curl -sS https://getcomposer.org/installer | php

Se o comando acima falhar, use o comando abaixo:

    php -r "readfile('https://getcomposer.org/installer');" | php

2 - Adicionando o repositório das dependências do projeto:

``` {.p1}
php composer.phar global require "fxp/composer-asset-plugin:~1.1.1"
```

3 - Criando a aplicação básica com o composer(execute este comando na **raiz do seu servidor web**, pois ele criará uma pasta chamada **"meu-projeto"** com os arquivos dentro):

``` {.p1}
php composer.phar create-project yiisoft/yii2-app-basic meu-projeto
```

4 - Se você usa Apache, adicione na raiz do seu projeto o arquivo "**.htaccess" (meu-projeto/.htaccess)** com o conteúdo:

    Options -Indexes
    <IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteCond %{REQUEST_URI} !^public
    RewriteRule ^(.*)$ web/$1 [L]
    </IfModule>

    # Deny accessing below extensions
    <Files ~ "(.json|.lock|.git)">
    Order allow,deny
    Deny from all
    </Files>

    # Deny accessing dot files
    RewriteRule (^\.|/\.) - [F]

5 - Adicione na pasta **"web"** do seu projeto outro arquivo **".htaccess"** **(meu-projeto/web/.htaccess)** com o conteúdo:

    RewriteEngine on
    RewriteCond %{REQUEST_FILENAME} !-f
    RewriteCond %{REQUEST_FILENAME} !-d
    RewriteRule . index.php

Acesse no seu navegador: **http://localhost/meu-projeto**

Obs: Eu coloquei o comando php seguido do **composer.phar**, mas você deve colocar o caminho aonde o seu **composer.phar** se encontra em seu servidor. Ex: **php /home/user/php/composer.phar \[comando\]**

Obrigado e até o próximo post pessoal.
