Title: Instalando drivers não assinados (unsigned) no Mac/OSX
Date: 2016-10-20 14:30
Author: paulo
Category: Mac - OSX
Tags: driver, kext, lan7500, mac, unsigned
Slug: instalando-drivers-nao-assinados-unsigned-no-macosx
Status: published

Olá,

Recentemente precisamos instalar o driver de um adaptador de Rede Ethernet RJ45 no Mac (**Plugable USB 3.0 to 10/100/1000 Gigabit Ethernet LAN Network Adapte - Chiptset LAN7500**) e o adaptador não ligava e não funcionava de jeito algum.

Porém ao tentar carregar o driver via terminal aparecia a mensagem:

> /System/Library/Extensions/LAN7500.kext failed to load - (libkern/kext) not loadable (reason unspecified); check the system/kernel logs for errors or try kextutil(8).

O problema está na verdade não com o driver, mas com o sistema que é o Sierra. Parece que depois de alguma versão El Captain ou Yosemite a Apple passou a aplicar um sistema de segurança nos drivers que só pode ser desabilitado em modo de recuperação.

Então para fazer o driver funcionar e verificar se você possui o mesmo problema, faça o seguinte:

> sudo kextload /System/Library/Extensions/LAN7500.kext

Substitua "**LAN7500.kext**" pelo nome do seu driver. Se ao executar você receber a mensagem abaixo, então você está com o mesmo problema:

> /System/Library/Extensions/LAN7500.kext failed to load - (libkern/kext) not loadable (reason unspecified); check the system/kernel logs for errors or try kextutil(8).

Agora reinicie seu Mac segurando as teclas CMD + R. O sistema iniciará em modo de recuperação. Acesse o menu **"Utilitários \> Terminal"** e digite:

> csrutil disable

Ele vai informar que você precisa reiniciar, então digite agora:

> reboot

Ao reiniciar seu Mac, o driver já será carregado e tudo funcionará.

 

[![Adaptador rede Mac OSX](http://pcoutinho.com/wp-content/uploads/2016/10/adaptador-rede-macosx.jpg){.alignnone .wp-image-319 width="259" height="429"}](http://pcoutinho.com/wp-content/uploads/2016/10/adaptador-rede-macosx.jpg)

 

Espero ter ajudado com este artigo.

Obrigado e até o próximo post pessoal.
