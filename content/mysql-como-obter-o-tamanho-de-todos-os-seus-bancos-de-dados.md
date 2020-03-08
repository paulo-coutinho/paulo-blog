Title: MySQL - Como obter o tamanho de todos os seus bancos de dados?
Date: 2014-09-25 04:10
Author: paulo
Category: MySQL
Tags: database, mega, mysql, size, tamanho
Slug: mysql-como-obter-o-tamanho-de-todos-os-seus-bancos-de-dados
Status: published

Olá pessoal,

Hoje vou mostrar como é simples e fácil agente obter o tamanho de todos os nossos bancos de dados em MegaBytes.

Para isso, basta conectar no seu servidor do **MySQL** e executar a query:

    SELECT table_schema "Banco de dados", 
    ROUND(sum( data_length + index_length ) / 1024 / 
    1024) "Tamanho em MB", 
    ROUND(sum( data_free )/ 1024 / 1024) "Espaço livre em MB" 
    FROM information_schema.TABLES 
    GROUP BY table_schema;

Obs: Você pode remover a função **ROUND** e ver o tamanho em um formato mais preciso, sem arredondamento.

Obrigado e até o próximo post pessoal.
