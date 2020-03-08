Title: PHP - Configurando o PHPStorm 7/8 para reconhecer o YiiFramework
Date: 2014-09-23 18:34
Author: paulo
Category: PHP
Tags: auto, complete, php, phpstorm, yii, yiiframework
Slug: php-configurando-o-phpstorm-7-8-para-reconhecer-o-yiiframework
Status: published

Olá pessoal,

Tenho visto que algumas pessoas que usam o **PHPStorm 7/8** não estão conseguindo acessar recursos dinâmicos e interno do **framework Yii** ([www.yiiframework.com](http://www.yiiframework.com)) em seus projetos. Vou usar como exemplo para este post o projeto open-source que disponibilizei no **GitHub** e que também usa o **Yii Framework**:  <https://github.com/prsolucoes/PHPDefaultProject/>.

Para resolver este problema, a solução é simples e só demanda configuração diretamente pela IDE, porém de forma resumida precisamos **"dizer"** a IDE aonde está a pasta raiz do nosso projeto e excluir o arquivo **"yiilite.php"** da **indexação** do PHP.

Para isso acesse as **configurações/settings** do seu projeto e procure pelo menu **"PHP \> Framework Integration"**. Marque a caixa **"Enable framework integration"** e ao lado selecione na lista a opção **"Yii"**.

Abaixo disso você terá uma treeview contendo as pastas e arquivos do seu projeto. Procure pela pasta **"protected"** e ao lado do nome da pasta(na coluna da direita da treeview) se você clicar aparecerá uma série de opções possíveis para você dizer à IDE o que esta pasta representa na integração com o **YiiFramework**, marque a opção **"application base directory"**.

Agora do **lado esquerdo**, procure pelo menu **"File Types \> PHP files (PHP)"**. Na parte inferior do **lado direito** terá uma caixa de texto com a informação **"Ignore files and folders"**. Edite indo até o final dos arquivos já ignorados, acrescente um **ponto e vírgula** (caso já não tenha) e adicione o texto **"yiilite.php;"** (sem as aspas, claro).

Clique em OK na parte inferior da IDE e espere o índice do PHP ser refeito.

Faça um teste com o código de exemplo:

    Yii::app()->db->create[aperte control+espaço ou command+espaço se for mac e verifique se aparece os possíveis comandos do Yii]

Segue algumas imagens do processo:

\[gallery columns="2" ids="47,48"\]

 

Um abraço e até o próximo post pessoal.
