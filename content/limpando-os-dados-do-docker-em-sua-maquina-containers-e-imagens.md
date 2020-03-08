Title: Limpando os dados do Docker em sua máquina (containers e imagens)
Date: 2016-12-16 19:27
Author: paulo
Category: Docker
Tags: container, docker, image, limpar, remove, space, trash
Slug: limpando-os-dados-do-docker-em-sua-maquina-containers-e-imagens
Status: published

Olá,

Quem utiliza Docker no dia-a-dia sabe que ele deixa muitos lixos na máquina em que está rodando, principalmente se você fica criando containers de teste como eu.

Quando você sai do container o Docker não apaga eles automaticamente, o que vai enchendo o disco e você acaba recebendo o erro: **No space left on device**.

Como eu passo por isso sempre, resolvi fazer uma sequência de comandos para copiar e colar no terminal, a fim de que o ambiente fique limpo denovo.

``` {.EnlighterJSRAW enlighter-language="shell"}
docker rm -v $(docker ps -a -q -f status=exited)
docker rmi $(docker images -f "dangling=true" -q)
docker volume rm $(docker volume ls -qf dangling=true)
```

 

Espero ter ajudado com este artigo.

Obrigado e até o próximo post pessoal.

 
