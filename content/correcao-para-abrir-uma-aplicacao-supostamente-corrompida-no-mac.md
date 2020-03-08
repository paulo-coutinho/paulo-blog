Title: Correção para abrir uma aplicação supostamente corrompida no Mac
Date: 2017-12-16 03:27
Author: paulo
Category: Mac - OSX
Tags: corrompido, damaged, dmg, mac
Slug: correcao-para-abrir-uma-aplicacao-supostamente-corrompida-no-mac
Status: published

Olá,

As vezes ao baixar alguma aplicação fora da App Store no Mac/OSX você recebe uma mensagem de aplicação corrompida, que na verdade é uma proteção do sistema operacional para não executar aplicações que não sejam "seguras" para o usuário, ou aplicações que não foram baixadas de uma fonte segura.

Existe uma forma de burlar isso bem fácil. Abra o terminal e digite:

``` {.EnlighterJSRAW enlighter-language="shell"}
sudo spctl --master-disable
```

Isso desabilitará a proteção. Então agora basta você executar a mesma aplicação e ela funcionará. Após rodar a aplicação, habilite novamente a proteção com o comando no seu terminal:

``` {.EnlighterJSRAW enlighter-language="shell"}
sudo spctl --master-enable
```

Obs: Lembre-se que você só deve fazer isso se realmente tiver certeza de que a aplicação é confiável, caso contrário não faça.

Obrigado e até o próximo post pessoal.

 
