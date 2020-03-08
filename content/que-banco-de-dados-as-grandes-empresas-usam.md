Title: Que banco de dados as grandes empresas usam?
Date: 2015-11-28 02:24
Author: paulo
Category: Sem categoria
Tags: arquitetura, banco, dados, empresas, estrutura, grandes, infra
Slug: que-banco-de-dados-as-grandes-empresas-usam
Status: published

Olá pessoal,

Recentemente analisando alguns sites de busca fiquei me perguntando sobre qual banco de dados esses sites com milhões de acesso utilizam hoje. Digo hoje porque temos uma enorme variedade de opções, seja banco relacional ou NoSQL.

Após uma boa pesquisa cheguei a alguns resultados bem interessantes:

    Facebook: MySQL, Cassandra, Memcached
    REF1, REF2, REF3 e REF4

    Google: BitTable, MySQL, MegaStore
    REF1, REF2 e REF3

    TripAdvisor: MySQL, SQL Server
    REF1

    FourSquare: MongoDB
    REF1

    Twitter: MySQL, FlockDB, Memcache, Cassandra, Gizzard, Lucene, HBase/Hadoop, Redis
    REF1 e REF2

    Quora: MySQL
    REF1

    OpenStreetMaps: MySQL(no passado, mas migrou) PostgreSQL(de 19 de abril 2009 para cá)
    REF1 e REF2

    Dropbox: MySQL, Memcached
    REF1 e REF2

    Wikipedia: MySQL(no passado), MariaDB(hoje), Memcached
    REF1 e REF2

 

Como ficou bem claro, o MySQL ainda está na maioria dos lugares. As empresas com engenheiros mais fortes acabam criando um fork do MySQL para torná-lo mais eficiente com os seus requisitos.

 

Obrigado e até o próximo post pessoal.
