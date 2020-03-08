Title: Mac - OSX - Conectando via SSH e mantendo a conexão aberta (KeepAlive)
Date: 2014-10-20 05:19
Author: paulo
Category: Mac - OSX
Tags: connection, keepalive, mac, openssh, osx, ssh, terminal, timeout
Slug: mac-osx-conectando-via-ssh-e-mantendo-a-conexao-aberta-keepalive
Status: published

Olá pessoal,

Esta dica é bem importante e resolve o problema de muita gente que ao conectar via **SSH** em uma máquina, percebe que depois de algum tempo a conexão é encerrada, necessitando criar uma nova.

Isso ocorre devido ao cliente **OpenSSH** que vem no **Mac (OSX)** não enviar o comando de **Keep Alive (manter vivo)**, que como o nome já diz, mantém a conexão **"viva"**.

Para fazer isso siga os passos abaixo executando os comandos direto no terminal:

1 - Abra o terminal

2 - Crie a pasta **"\~/.ssh/"** (caso já não exista) com o comando:

    mkdir ~/.ssh/

3 - Edite o arquivo **"config"** com o programa "nano" (caso ele não exista, o próprio **"nano"** criará):

    nano ~/.ssh/config

4 - Adicione as linhas:

    Host *
        ServerAliveInterval 60

5 - Salve o arquivo com **CONTROL + O**

6 - Feche o editor com **CONTROL + X**

7 - Reinicie o terminal para que as mudanças tenham efeito.

 

Existe uma forma de fazer diretamente na execução do comando SSH, assim:

    ssh -o ServerAliveInterval=60 servidor.com

 

Obs: Você pode experimentar diferentes intervalos de tempo do envio da informação do keep alive.

 

Obrigado e até o próximo post pessoal.
