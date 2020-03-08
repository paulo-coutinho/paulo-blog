Title: Javascript - Usando o sistema de notificações do WebKit com o Chrome
Date: 2014-09-23 13:16
Author: paulo
Category: Javascript
Tags: browser, notificação, notification, web, webkit
Slug: javascript-usando-o-sistema-de-notificacoes-do-webkit-com-o-chrome
Status: published

Olá pessoal,

Não sei se já perceberam, mas no Gmail existe um recurso de notificações, que só funciona no Google Chrome.

Essas notificações aparecem quando você recebe um novo email, por exemplo.

Estas notificações não foram inventadas exclusivamente para o Google Chrome, na verdade é um padrão W3C que está sendo implementado aos poucos nos navegadores, mas somente no Chrome já está funcionando.

Referência: <http://dev.w3.org/2006/webapi/WebNotifications/publish/Notifications.html>

Mas como podemos usufruir deste recurso em nossos websites?

É bem simples, usando obviamente os novos recursos do Javascript, temos acesso a todas essas APIs. Os passos básicos para implementar são:

> 1 - Verificar se o navegador tem suporte
>
> 2 - Pedir permissão para exibir notificações
>
> 3 - Exibir as notificações

Vamos ao que interessa, o código:

    function verificarSuporte()
    {
        var c = ( window.webkitNotifications !== undefined );
    if (!c)
    {
        alert("Seu navegador não suporta notificações desktop. Por favor, use o Google Chrome!");
    }
        return c;
    }

Esta função é a que verifica se o seu navegador tem suporte a notificações desktop ou não. Se o navegador não suportar, a função exibe um alert.

``` {#_mcePaste}
function verificarPermissao()
{
    if ( !verificarSuporte() ) return;

    switch ( webkitNotifications.checkPermission() )
    {
        case 0: // PERMITIDO
        alert( "Permitido" );
        break;
        
        case 1: // NÃO PERMITIDO
        alert("Não permitido");
        break;

        case 2: // PERMISSÃO NEGADA
        alert( "Permissão negada" );
        break;
    }
}
```

Esta função é a que verifica a permissão de exibir as notificações que seu navegador definiu para a sua página. Para cada caso de permissão, é exibido um alert com a descrição.

    function solicitarPermissao()
    {
        if (!verificarSuporte()) return;
        webkitNotifications.requestPermission();
    }

Esta função que solicita ao navegador a permissão de exibir as notificações. Assim que ela é chamada, o navegador exibe uma caixa de confirmação.

    function testeDeNotificacao()
    {
        if ( !verificarSuporte() ) return;
        if ( webkitNotifications.checkPermission() == 0 )
        {
            var icone = "http://www.prsolucoes.com/downloads/logo_notificacao.png";
            var titulo = "Mensagem de PRSoluções";
            var subTitulo = "Eu irei desaparecer em 10 segundos!";
            var notificacao = webkitNotifications.createNotification( icone, titulo, subTitulo );
            
            notificacao.show();
            
            setTimeout( function() { notificacao.cancel() }, 10000 );
        }
        else
        {
            alert( "Por favor, solicite permissão primeiro." );
        }
    }

Esta função exibe a notificação em si. É bem simples, basta passar a url do icone, o título e o subtítulo.

Obrigado pessoal e até o próximo post.
