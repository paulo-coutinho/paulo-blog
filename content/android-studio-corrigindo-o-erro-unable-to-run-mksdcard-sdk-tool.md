Title: Android Studio - Corrigindo o erro "Unable to run mksdcard SDK tool."
Date: 2016-05-10 17:20
Author: paulo
Category: Android
Tags: android, erro, mksdcard, sdk, studio, tool
Slug: android-studio-corrigindo-o-erro-unable-to-run-mksdcard-sdk-tool
Status: published

Olá pessoal,

Para aqueles que como eu, estão tendo problemas na hora de usar o Android Studio no Ubuntu ocorrendo o erro [**"Unable to run mksdcard SDK tool."**]{style="color: #ff0000;"}, segue uma dica bem simples. Instale as dependências seguintes e magicamente tudo estará resolvido.

> sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6

Em alguns casos, ocorrerá um erro ao instalar a dependência **lib32bz2-1.0**. Basta executar o mesmo comando sem esta dependência:

> sudo apt-get install lib32z1 lib32ncurses5 lib32stdc++6

 

Bom, espero ter ajudado com esta dica.

Obrigado e até o próximo post pessoal.
