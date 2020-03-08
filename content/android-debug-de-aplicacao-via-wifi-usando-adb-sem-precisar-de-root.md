Title: Android - Debug de aplicação via WiFi usando ADB sem precisar de root
Date: 2016-07-22 15:53
Author: paulo
Category: Android
Tags: adb, android, debug, terminal, wifi
Slug: android-debug-de-aplicacao-via-wifi-usando-adb-sem-precisar-de-root
Status: published

Olá,

Recentemente tive a necessidade de rodar a aplicação pelo Android Studio sem usar cabo, por questões de comodidade mesmo, e após pesquisar e fazer vários testes, preparei um tutorial sem simples.

1.  Desconectar o seu dispositivo do computador, caso esteja.
2.  Conectar o seu computador de desenvolvimento e o seu dispositivo Android na mesma rede WiFi.
3.  Habilitar o modo desenvolvedor em seu dispositivo (Configurações \> Sobre \> Apertar 7 vezes em Número da versão).
4.  Habilitar a depuração USB (Configurações \> Programador \> Depuração USB).
5.  Obtenha o IP do seu dispositivo em Configurações \> Sobre \> Status \> Endereço IP.
6.  Abrir o terminal e executar (troque o IP abaixo pelo IP do seu dispositivo):

    ``` {.EnlighterJSRAW enlighter-language="shell"}
    adb tcpip 5555
    adb connect 192.168.0.103:5555
    ```

7.  Rodar a aplicação no Android Studio normalmente e se tudo deu certo seu dispositivo aparecerá na lista de devices como se estivesse conectado via cabo.

 

Espero ter ajudado com este artigo.

Obrigado e até o próximo post pessoal.
