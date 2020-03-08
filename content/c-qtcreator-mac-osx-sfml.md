Title: C++ - QtCreator + Mac OSX + SFML
Date: 2014-09-19 16:23
Author: paulo
Category: C++
Tags: c++, qt, qtcreator, sfml
Slug: c-qtcreator-mac-osx-sfml
Status: published

Olá,

Recentemente criei um projeto no github onde irá facilitar a vida de muita gente.

Quem desenvolve jogos, sabe que é chato ficar configurando a IDE e também as bibliotecas e pensando nisso, criei um repositório onde quem usa a biblioteca Qt poderá facilmente fazer um clone desse repositório e sair usando a SFML independente da plataforma, seja Mac, Linux ou Windows.

 

Mas no que isso irá me ajudar?

Se você desenvolve em C++ e usa a SFML, basta você baixar o QtCreator (http://qt.nokia.com/downloads) que é gratuito e logo após instalar o QtCreator, faça um clone do projeto (https://github.com/prsolucoes/sfml-project) em uma pasta qualquer, abra o arquivo .pro e clique em "Run" no QtCreator e o projeto já estará configurado e funcionando.

 

O que foi implementado?

1 - Configuração independente de plataforma (windows, linux e mac)  
2 - Código básico de teste de uma aplicação com SFML  
3 - Todos os arquivos de include e lib para cada plataforma  
4 - Ícone padrão para seu aplicativo - basta mudar o arquivo na pasta "resources" e recompilar  
5 - Nome do binário gerado também é configurável  
6 - As configurações do projeto são definidas em um único arquivo "sfml-project.pro"

Para baixar o projeto, acesse:  
<https://github.com/prsolucoes/sfml-project>

Espero poder facilitar a vida de todos assim.

Obrigado!
