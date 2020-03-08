Title: OSX - Deixando o seu terminal colorido e com suporte ao Git
Date: 2016-04-18 20:57
Author: paulo
Category: Mac - OSX
Tags: branch, color, colorido, git, mac, terminal
Slug: osx-deixando-o-seu-terminal-colorido-e-com-suporte-ao-git
Status: published

Olá pessoal,

Esta dica é bem simples e talvez ajude bastante no dia-a-dia em seu desenvolvimento, caso utilize o terminal do OSX.

Realizando estes processos seu terminal ficará colorido, facilitando e leitura e ainda aparecerá o nome da branch em que você está, caso utilize o Git.

Siga os passos:

1 - Edite o arquivo .bash\_profile digitando no terminal:

``` {.EnlighterJSRAW enlighter-language="null"}
nano ~/.bash_profile
```

2 - Adicione as linhas:

``` {.EnlighterJSRAW enlighter-language="shell"}
export CLICOLOR=1
export LSCOLORS=ExFxBxDxCxegedabagacad
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$(parse_git_branch) $ "

parse_git_branch() {
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
```

3 - Salve o arquivo com **CONTROL + O**

4 - Feche o terminal e abra-o novamente ou caso queira manter a sessão com as modificações, execute:

``` {.EnlighterJSRAW enlighter-language="shell"}
source ~/.bash_profile
```

Obs: Esta dica funciona também com o iTerm2.

 

Bom, espero ter ajudado com esta dica.

Obrigado e até o próximo post pessoal.
