Title: OSX - Removendo todos os arquivos .DS_Store
Date: 2016-05-13 18:11
Author: paulo
Category: Mac - OSX
Tags: clean, delete, ds_store, mac, osx, remove, remover
Slug: osx-removendo-todos-os-arquivos-ds_store
Status: published

Olá pessoal,

Um problema muito comum em meio aos usuários de MAC/OSX, principalmente para quem desenvolve, são os famosos arquivos .DS\_Store.

Para remove-los completamente de uma pasta específica basta uma linha de comando.

Abra o seu Terminal, entre na pasta raiz do seu projeto ou na pasta raiz que você deseja limpar e execute:

``` {.EnlighterJSRAW enlighter-language="shell"}
find ./ -name ".DS_Store" -depth -exec rm {} \;
```

Caso você queira remover de todo o seu computador, use com o sudo e insira a senha do seu usuário, se solicitado:

``` {.EnlighterJSRAW enlighter-language="shell"}
sudo find / -name ".DS_Store" -depth -exec rm {} \;
```

Bom, espero ter ajudado com esta dica.

Obrigado e até o próximo post pessoal.
