Title: Git - Como fazer push na mesma branch em que estou trabalhando?
Date: 2014-09-19 16:16
Author: paulo
Category: Git
Tags: branch, git, push
Slug: git-como-fazer-push-na-mesma-branch-em-que-estou-trabalhando
Status: published

Olá pessoal,

Vejo muita gente irritada com o Git pelo fato de ter que passar o nome da **"branch"** toda vez que vamos fazer um **" push"**.

Hoje vou mostrar como é simples mudar o comportamento local do Git em relação a isso, e para isso vamos usar o utilitário de configuração interno do Git chamado "git config".

Existem vários comportamentos de como o Git faz o push, segue a lista dos possíveis comportamentos que podemos usar:

-   **nothing** - não faz nenhum push
-   **matching** - faz push de todas as branchs que tenham o mesmo nome local e remotamente
-   **upstream** - faz o push da branch atual para a sua branch remota correspondente (mesmo nome)
-   **simple** - parecido com a "upstream", porém se a branch remota tiver um nome diferente, nenhum push é feito
-   **current** - talvez seja a opção para a maioria, envia o branch local para o branch de mesmo nome no servidor remoto

Agora que você já sabe o que cada opção representa, basta configurar o Git para usar a opção que melhor se encaixa no seu caso com o comando (exemplo):

    git config push.default current

Para usar qualquer outra opção, substitua o **"current"** no comando, pela opção desejada dentre as opções da lista acima.

Agora que você configurou o comportamento padrão de como o Git faz o **"push"**, basta usar **"git push"** e ser feliz.

Um abraço. Que o Senhor vos abençoe!
