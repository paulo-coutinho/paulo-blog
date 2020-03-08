Title: PHP - Composer - Facilitando a vida de quem usa
Date: 2014-10-14 15:56
Author: paulo
Category: PHP
Tags: alias, comando, composer, php, terminal
Slug: php-composer-facilitando-a-vida-de-quem-usa
Status: published

Olá pessoal,

Para quem usa o composer, o gerenciador de dependências para PHP (<http://www.getcomposer.org>) sabe o quanto é tediante ficar escrevendo o comando completo, ex:

    php /Users/usuario/Developer/php/composer.phar install

Porém, para usuários de Mac e Linux, existe uma solução bastante simples e útil que vai facilitar a vida de todo mundo, que é a criação de um **ALIAS** para o comando completo. Abra o arquivo "**.bash\_profile"** do seu usuário e adicione o **ALIAS** para o comando completo do **composer**. Exemplo:

Edite o seu bash\_profile:

    nano ~/.bash_profile

Adicione a linha abaixo e salve o arquivo:

    alias composer="php [pasta aonde se encontrar o composer]/composer.phar"

Atualize a sessão do terminal com os novos comandos:

    source ~/.bash_profile

Agora basta você executar no terminal:

    composer install

 

Obrigado e até o próximo post pessoal.
