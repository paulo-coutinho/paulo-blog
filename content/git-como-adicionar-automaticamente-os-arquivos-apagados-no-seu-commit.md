Title: Git - Como adicionar automaticamente os arquivos apagados no seu commit
Date: 2014-09-15 14:54
Author: paulo
Category: Git
Tags: apagar, commit, git
Slug: git-como-adicionar-automaticamente-os-arquivos-apagados-no-seu-commit
Status: published

Olá a todos,

Um problema comum entre os usuários do Git, se deve ao fato de que toda vez que você apaga um arquivo do seu projeto, você precisa executar o comando de remoção do Git e só depois de remover todos eles, é que você pode efetuar o commit, ex:

    git rm arquivo.txt
    git rm arquivo2.txt
    git rm arquivo3.txt arquivo4.txt
    git commit -m "remocao de arquivo"

 

Porém existe dois meios fáceis e rápidos de fazer o Git adicionar a remoção desses arquivos automaticamente. O primeiro é:

    git add -u .

 

E o segundo é:

    git add -A .

 

Ao executar este comando último comando **"-A ."**, você está na verdade executando:

    git add .
    git add -u .

 

O comando com parâmetro **"-u ."**, adiciona os arquivos que você apagou do seu projeto no **stage**, ou seja, é como se você estivesse executando um  **"git rm \[arquivo\]"** automaticamente para cada arquivo apagado.

Então ao invés de usar o **"git rm \[aquivo\]"**, use apenas os comandos:

    git add -A .
    git commit -m "meu novo commit"

 

Agora, para quem quiser algo mais rápido e mais prático, caso você vá fazer um commit direto, tem um outro atalho, que é o comando:

    git commit -a -m "meu mais novo commit"

 

O parâmetro **"-a"** do commit, executa vários comandos comuns antes de fazer o commit efetivamente, e uma das coisas é executar o **"git add -u"**.

 

[Obs: A única coisa que estes comandos não fazem é adicionar um novo arquivo ao stage, isso tudo só funciona para arquivos que já são do stage.]{style="color: #ff0000;"}

 

Espero ter ajudado pessoal.
