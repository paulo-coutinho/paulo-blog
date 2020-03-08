Title: Usando o auto-update do Fastlane
Date: 2016-11-14 15:05
Author: paulo
Category: Integração, iOS
Tags: auto, fastlane, ios, update, upgrade
Slug: usando-o-auto-update-do-fastlane
Status: published

Olá pessoal,

Recentemente tivemos um necessidade de fazer com que o Fastlane (ferramenta para deploy contínuo - http://fastlane.io/) fizesse a atualização de suas dependências automaticamente, isso inclui todos esses caras:

> cert, credentials\_manager, deliver, fastlane, fastlane\_core, frameit, gym, match, pem, pilot, produce, scan, screengrab, sigh, snapshot, spaceship, supply

Toda vez que vamos usar o Fastlane para subir as aplicações tem atualizações novas de suas dependências e que muitas das vezes gera algum erro no envio e não conseguimos subir os aplicativos até que atualizemos manualmente as dependências necessárias com o comando "gem update ..." e depois começamos o processo novamente de deploy.

Isso é bem chato, então a primeira coisa que pensei foi em adicionar o "gem update" em nossa ferramenta de integração contínua, GoCI ([http://github.com/prsolucoes/goci](https://github.com/prsolucoes/goci)), antes de fazer as chamadas ao Fastlane.

A segunda opção era buscar na documentação para saber se existe alguma coisa pronta para este problema, e foi ai que achei o comando "update\_fastlane". Após olhar a documentação e realizar alguns testes, resolvi escrever o passo-a-passo para implementar isso. Vamos à prática:

1.  Adicione no início do seu arquivo Fastfile, antes de qualquer coisa, esta linha:  

    > update\_fastlane

2.  Adicione as seguintes linhas ao seu arquivo ".bash\_profile" ou ".bashrc", que fica na pasta do seu usuário, ex (nano \~/.bash\_profile):  

    > export GEM\_HOME=\~/.gems  
   > export GEM\_SPEC\_CACHE=\$GEM\_HOME/specs  
   > export PATH=\$PATH:\~/.gems/bin

3.  Execute o arquivo modificado com o comando "source", ex:  

    > source \~/.bash\_profile

4.  Atualize o rubygems e o gem:  

    > gem install rubygems-update  
   > sudo gem update --system

5.  Instale suas gems novamente, as que você usa. No meu caso era o fastlane e cocoapods, então fiz assim:  

    > gem install cocoapods fastlane --no-ri --no-rdoc

Com tudo isso feito, você já preparou o seu ambiente e atualizou tudo o que é necessário para que o auto-update do fastlane funcione. Agora basta você executar suas tarefas do fastlane que ele vai executar o auto-update antes de tudo.

Obs: Nós definimos uma novo diretório para as "gems" do ruby porque sem isso o fastlane irá reclamar que a pasta de "gems" é do usuário root (sendo necessário fazer um sudo + comand) e não sua.

 

Espero ter ajudado com este artigo.

Obrigado e até o próximo post pessoal.
