Title: Mac OSX - Desabilitando o ganho automático do microfone no Skype
Date: 2015-11-23 18:34
Author: paulo
Category: Mac - OSX
Tags: auto, gain, mac, microfone, volume
Slug: mac-osx-desabilitando-o-ganho-automatico-do-microfone-no-skype
Status: published

Olá pessoal,

Este pequeno artigo é para ajudar a todos os que possuem um "problema" comum no Skype para mac/osx que é o "auto ganho" do microfone.

Este recurso que eu chamei de problema é bem incômodo, pois toda vez que entramos em uma call no Skype numa sala com barulhos externos, o ganho vai aumentando cada vez mais e as pessoas do outro lado da ligação acabam ouvindo todo o barulho externo, tornando a ligação impossível e confusa.

A solução é bem simples, basta adicionar-mos uma tag no XML de configuração do Skype e o problema é resolvido.

Siga os passos:

    1 - Abra o aplicativo Terminal no seu mac/osx

    2 - Digite:
    open -a /Applications/TextEdit.app ~/Library/Application\ Support/Skype/shared.xml

``` {.p1}
3 - Procure pela tag "<VoiceEng>".  Abaixo/dentro dela adicione a tag: <AGC>0</AGC>. Ficando +/- assim:
<VoiceEng>
    <AGC>0</AGC>
    ...
</VoiceEng>
```

    4 - Salve com COMMAND+S, feche o editor e pronto.

 

Obrigado e até o próximo post pessoal.
