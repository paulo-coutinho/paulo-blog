Title: Trocando a versão do Python no macOS
Date: 2018-01-24 01:34
Author: paulo
Category: Mac - OSX
Tags: change, default, mac, osx, padrão, python, trocar
Slug: trocando-a-versao-do-python-no-macos
Status: published

Olá,

Ao instalar o **macOS** ele traz diversas linguagens e seus interpretadores já pré-instalados. Ele traz o **Python**, o PHP, o Ruby, entre outros.

Mas talvez você tenha tido o mesmo problema que eu. Eu precisava fazer com que os comandos que eu tenho que chamam o Python, passassem a chamar uma outra versão do Python, sem que eu tivesse que mudar todos os meus scripts. Seria fácil fazer um alias ou mudar os scripts para **python2** ou **python3**, mas essa com certeza não era pra mim a melhor solução.

A primeira coisa que fiz foi instalar as versões que eu queria. Então usei o [Brew](https://brew.sh/) para me ajudar com isso. Instalei rapidamente o Python 2 e 3 atualizados com os comandos no Terminal:

``` {.EnlighterJSRAW enlighter-language="null"}
brew install python
brew install python3
```

Caso você queira saber se está funcionando digite:

``` {.EnlighterJSRAW enlighter-language="null"}
python2 --version
python3 --version
```

O Terminal deverá exibir as versões após a execução das linhas acima.

Após isso ainda não fizemos nada, apenas deixamos instaladas as versões que queremos.

É totalmente desaconselhável remover a versão que já vem no macOS, isso deve quebrar algumas coisas que dependem disso.

A primeira coisa a se fazer é definir a ordem de como o sistema irá procurar o comando **"python"** no macOS. Para isso edite o arquivo com o nano, assim:

``` {.EnlighterJSRAW enlighter-language="null"}
sudo nano /etc/paths
```

E verifique se a primeira linha do arquivo está como:

> [/usr/local/bin]{.s1}

Caso não esteja, remova ela de onde estiver e coloque na primeira linha do arquivo.

Isso fará com que os "**binários**" sejam procurados primeiramente na pasta "**/usr/local/bin**", dando preferência aos "**binários**" e links simbólicos dentro desta pasta.

Agora tudo o que precisamos fazer é criar um link simbólico dentro de "**/usr/local/bin**" que tenha o nome "**python**" e aponte para a nossa versão do Python que queremos (2 ou 3, depende da sua necessidade).

Para isso execute a seguinte linha para o Python 2:

``` {.EnlighterJSRAW enlighter-language="null"}
ln -s /usr/local/bin/python2 /usr/local/bin/python
```

E para o Python 3 digite no terminal:

``` {.EnlighterJSRAW enlighter-language="null"}
ln -s /usr/local/bin/python3 /usr/local/bin/python
```

Caso você já tenha criado anteriormente algum link simbólico e deseja trocar, apague o link simbólico atual com a seguinte linha:

``` {.EnlighterJSRAW enlighter-language="null"}
rm -f /usr/local/bin/python
```

Não precisa executar estas linhas como root/sudo, pois seu usuário já tem acesso a ela.

Caso você queira atualizar o Python, basta executar o Brew com o parâmetro **upgrade**, assim:

``` {.EnlighterJSRAW enlighter-language="null"}
brew upgrade python
brew upgrade python3
```

Ao terminar tudo, reinicie seu terminal para que as alterações façam efeito.

 

Obrigado e até o próximo post pessoal.
