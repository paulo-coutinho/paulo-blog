Title: Frameworks PHP - Yii, Laravel, Phalcon e afins
Date: 2015-11-28 15:29
Author: paulo
Category: PHP
Tags: framework, laravel, phalcon, php, yii, zend
Slug: frameworks-php-yii-laravel-phalcon-e-afins
Status: published

Olá pessoal,

Recentemente estava dando uma olhada nos últimos frameworks para PHP e analisando as últimas novidades de cada um.

Após pesquisar bastante, vi que a maioria esmagadora, como eu, que usa Yii2 continua no Yii2 por ser um framework full-stack, enterprise e consolidado no mercado a mais de 2 anos bem estável. A única coisa que vi algumas pessoas falando é que para micro-framework talvez o Laravel seja melhor por permitir rotas no estilo Go ou NodeJS.

Mas de modo geral cada um acaba usando um ou outro dependendo do caso, então se você quer uma aplicação de porte menor ou um microframework, use o Laravel e se você quer uma aplicação de médio ou grande porte use o Yii2. O Yii2 segue a mesma idéia do ZendFramework, ser um framework enterprise para PHP Full-Stack. Tem até alguns usuários que transformaram o Yii2 em micro-framework, mas não é o seu objetivo ([REF](https://github.com/Nebo15/micro-yii)).

Porém um framework que acompanhei no passado sobreviveu até hoje e recebi a notícia de que estava em sua versão 2.0 e bem estável e este sim, talvez seja uma boa opção se alguém precisa de um pouco mais de performance, o [Phalcon](https://phalconphp.com/en/) ([Tutorial](https://docs.phalconphp.com/en/latest/reference/tutorial.html)). A diferença dele para qualquer outro framework para PHP é que ele é feito em C e não em PHP, o que garante uma performance muito melhor, pois suas classes são expostas para o PHP e todo o processamento até chegar no método que atende a requisição é feito em C mesmo. Aqui tem uma lista dos diversos tópicos que ajudam a entender cada pedaço dele ([Tutorial 2](https://docs.phalconphp.com/en/latest/index.html)).

 

Obrigado e até o próximo post pessoal.
