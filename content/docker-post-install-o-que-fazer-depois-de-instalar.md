Title: Docker - Post Install - O que fazer depois de instalar?
Date: 2017-10-16 19:22
Author: paulo
Category: Docker
Tags: clean, clear, docker, install, logs, post
Slug: docker-post-install-o-que-fazer-depois-de-instalar
Status: published

Olá,

Recentemente tive alguns problemas com o **Docker** relacionados não com ele, mas com os logs gerados por ele e o espaço em disco disponível que eu tinha em uma instância na AWS.

Após muito varrer o disco em busca dos dados que mais ocupavam espaço, vi que os logs estavam crescendo exponencialmente e decidi usar o **logrotate**, um utilitário pro Linux para rotacionar os logs quando estes atingem as regras que você define em um arquivo de configuração.

Para instalar o **logrotate**, execute:

``` {.EnlighterJSRAW enlighter-language="shell"}
sudo apt-get update
sudo apt-get install logrotate
```

Após instalar execute **"logrotate"** para saber se está instalado corretamente.

Após instalar, precisamos configurar uma regra no **logrotate** para os **logs do Docker**. Então execute:

``` {.EnlighterJSRAW enlighter-language="shell"}
nano /etc/logrotate.d/docker-container
```

Obs: Eu usei o "nano", mas você pode usar o "vi" ou "vim" se preferir. Dentro do editor, cole a seguinte regra para o logrotate:

``` {.EnlighterJSRAW enlighter-language="null"}
/var/lib/docker/containers/*/*.log {
  rotate 7
  daily
  compress
  size=1M
  missingok
  delaycompress
  copytruncate
}
```

Salve o arquivo, feche o editor e pronto, **logrotate** configurado.

No meu caso, eu deixei os arquivos de log com no máximo 1M de tamanho, mas você poderá aumentar para quanto quiser.

Caso você queria **testar o logrotate** e ver o que ele vai fazer, execute o comando:

``` {.EnlighterJSRAW enlighter-language="shell"}
logrotate -df /etc/logrotate.d/docker-container
```

 

Obs: Além disso, mesmo configurando, havia um arquivo que parece ter corrompido e depois de muito pesquisar eu acabei tendo que apagar este arquivo, pois estava impedindo o **logrotate** de executar, já que ele parece usar este arquivo como referência para alguma coisa. Então, caso aconteça contigo, apague o arquivo **"status" na pasta do logrotate** com o comando:

``` {.EnlighterJSRAW enlighter-language="null"}
rm /var/lib/logrotate/status
```

 

Bom, é isso pessoal. Espero que isso ajude a economizar espaço com os logs gerados pelo Docker. É claro que isto não se aplica só ao Docker, você pode criar regras para qualquer arquivo, basta especificar o pattern para os arquivos e colocar as regras.

Ah, e no meu caso o espaço utilizado foi de 76% para 34% do disco, ou seja, 42% do disco era log do Docker.

Obrigado e até o próximo post pessoal.
