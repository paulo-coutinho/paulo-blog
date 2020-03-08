Title: Golang - Ferramenta para upload do arquivo DSYM para o Fabric/Crashlytics
Date: 2016-02-26 13:13
Author: paulo
Category: Golang
Tags: crashlytics, dsym, fabric, ios, iphone, manual, osx, upload
Slug: golang-ferramenta-para-upload-do-arquivo-dsym-para-o-fabriccrashlytics
Status: published

Olá pessoal,

Lancei uma ferramenta para enviar o arquivo DSYM (arquivo contendo os "debugs symbols" gerado ao compilar uma aplicação para OSX ou iOS) para o Fabric/Crashlytics manualmente, via linha de comando.

Você pode integrar esta ferramenta em seu processo de deploy ou integração contínua, usando o Jenkins ou Fastlane por exemplo.

Uma dica para quem vai usar com o Fastlane é usar o comando abaixo para executar a ferramenta:

``` {.EnlighterJSRAW enlighter-language="shell"}
sh "cd .. && fabric-upload-dsym --bundleid=[YOUR-APP-BUNDLE] --fabricapikey=[YOUR-FABRIC-API-KEY] --file=[ZIPPED-DSYM-FILE]"
```

 

Obrigado e até o próximo post pessoal.
