Title: Mobile - Como as redes de anúncios (Ad Networks) realizam o tracking de campanhas
Date: 2016-06-02 20:45
Author: paulo
Category: Mobile
Tags: ads, analytics, campaign, campanha, install, referrer, tracking
Slug: mobile-como-as-redes-de-anuncios-ad-networks-realizam-o-tracking-de-campanhas
Status: published

Olá pessoal,

Uma dúvida muito comum e também uma informação muito importante, é saber como fazer o tracking (ou rastreamento) de um usuário que fez o download e instalou um determinado aplicativo através de um link, banner ou uma campanha em geral.

É importante entender que não existe um jeito fácil, simples e universal para que isso aconteça e pode ser que alguma informação se perca no meio do caminho dependendo das ações dos usuários. Cada plataforma resolveu este problema de um jeito diferente.

### No caso da Apple funciona assim:

Um usuário utiliza uma ferramenta de anúncios que irá exibir um banner, link ou algo do tipo no dispositivo do usuário. O link contido neste banner é um link que contém uma informação especial chamada pela Apple de IDFA, que consiste em um token específico para anúncios e é único por device. A Apple não permite o uso desse token outro fim além de usá-lo para tracking de anúncios e qualquer tentativa fora esta terá o app rejeitado, como está em sua documentação ([Link 1](https://developer.apple.com/library/ios/documentation/LanguagesUtilities/Conceptual/iTunesConnect_Guide/Chapters/SubmittingTheApp.html#//apple_ref/doc/uid/TP40011225-CH33-SW8), [Link 2](https://support.appsflyer.com/hc/en-us/articles/207032086-New-Apple-IDFA-Guidelines-How-To-Submit-Your-iOS-App-With-IDFA), [Link 3](https://developers.facebook.com/docs/app-ads/targeting/mobile-advertiser-ids)).

Vou usar o exemplo do Google Analytics para explicar como ele consegue através do IDFA fazer o tracking de suas campanhas.

Um anúncio exibido pelo Google em suas redes de anúncio teria um link com uma estrutura parecida com esta:

> http://click.google-analytics.com/redirect?  
> tid=UA-1234-1 **// Google Analytics Tracking ID.**  
> &idfa=BBA44F63-E469-42BA-833A-2AC550310CB3 **// Identifier for Advertising (IDFA)**  
> &aid=com.bundle.myapp **// App ID.**  
> &cs=network **// Campaign source.**  
> &cm=cpc **// Campaign medium.**  
> &cn=campaign\_name **// Campaign name.**  
> &url=https%3A//itunes.apple.com/us/app/myApp/id123%3Fmt%3D8 **// Redirect URL to iTunes.**

Esse link do anúncio do Google vai registrar no servidor deles que você clicou nele e vai gravar as informações que ele deseja para depois juntar as peças e cruzar as informações. Após gravar o que ele precisa, ele vai redirecionar você para a loja da Apple, indo direto para o aplicativo desejado quando você clicou no anúncio.

Quando você instalar o aplicativo desejado, o SDK do Google contido dentro do seu aplicativo vai obter o IDFA do seu aparelho e enviar para o servidor deles. Seria algo assim:

> Ah, então você é o IDFA "ABC123456" que clicou na campanha "C123", estou adicionando +1 no contador de instalação, bem como todas as informações do seu dispositivo. Obrigado.

Na documentação do Google, tem mais detalhes, mas a regra é esta.

[https://developers.google.com/analytics/solutions/ios-install-tracking\#redirect ](https://developers.google.com/analytics/solutions/ios-install-tracking#redirect)

Segue uma imagem que o Google fez para exemplificar seu fluxo:

[![ios-install-tracking-redirect](http://pcoutinho.com/wp-content/uploads/2016/06/ios-install-tracking-redirect.png){.alignnone .size-full .wp-image-294 width="825" height="438"}](http://pcoutinho.com/wp-content/uploads/2016/06/ios-install-tracking-redirect.png)

A segunda solução do Google Analytics é fazer com que a rede de anúncios envie assincronamente um "ping" para a URL:

> click.google-analytics.com/ping?param1=value1&param2=value2

E com isso poderá ser feita a contabilidade também server-side posteriormente pelas ferramentas.

 

### No caso do Google funciona assim:

O Google criou uma classe que atua como um Broadcast Receiver, que receberá estes dados assincronamente quando um usuário instalar o aplicativo através de uma campanha.

Basicamente o Google Play vai fazer um broadcast com a informação somente quando o aplicativo for instalado pela loja e os dados da campanha estiverem disponíveis, ou seja, se ele veio com os parâmetros de campanha definidos quando ocorreu a instalação.

Estes dados serão consumidos pelo seu broadcast que irá submeter os dados para sua plataforma de anúncios. Se você usa o SDK do Google Analytics e definiu que ele será o "recebedor" destas informações, ele será o responsável por jogar estas informações de campanha para o servidor do Google, ou então você captura e repassa isso para diversas ferramentas manualmente, pois uma limitação do Android é que só pode existir um Broadcast Receiver para Install Referrer.

O AppsFlyer fez um Broadcast Receiver especial que consegue receber estes dados e depois repassar para todos os outros Broadcast Receivers que você tiver, automaticamente ([Link de como usar](https://support.appsflyer.com/hc/en-us/articles/207032146-How-Can-I-Get-the-Install-Referrer-URL-from-my-Android-App-Context-)), permitindo então você possuir diversos Broadcast Receivers.

Documentação:

<https://developers.google.com/android/reference/com/google/android/gms/tagmanager/InstallReferrerReceiver>

<https://developers.google.com/android/reference/com/google/android/gms/analytics/CampaignTrackingReceiver>

 

Basicamente o link no padrão para o Google Play seria assim:

> https://play.google.com/store/apps/details?id=com.example.application&**referrer=utm\_source%3Dgoogle%26utm\_medium%3Dcpc%26utm\_term%3Drunning%252Bshoes%26utm\_content%3Dlogolink%26utm\_campaign%3Dspring\_sale**

É importante entender que a informação que você terá é o texto dentro do parâmetro "referrer", que deverá estar no padrão URL Encoded, ou seja, sem os símbolos "%, &, =, etc".

É importante também usar o gerador de URL para o Google Play para criar a URL dentro do padrão esperado ([Link 1](https://developers.google.com/analytics/devguides/collection/android/v4/campaigns#google-play-url-builder), [Link 2](https://developers.google.com/analytics/devguides/collection/android/v4/campaigns#google-play-url-builder)):

Se você deseja simular isso no Android, sem ter que instalar o aplicativo pela loja, afim de testar o funcionamento, execute os comandos abaixo trocando os parâmetros ([Link](http://stackoverflow.com/questions/5890914/how-to-test-android-referral-tracking/6966718#6966718)):

``` {.EnlighterJSRAW enlighter-language="shell"}
adb shell 
am broadcast -a com.android.vending.INSTALL_REFERRER -n <your.package>/.<path.up.until.your.BroadcastReceiver> --es "referrer" "utm_source=test_source\&utm_medium=test_medium\&utm_term=test_term\&utm_content=test_content\&utm_campaign=test_name"
```

E caso você queira criar seu Broadcast Receiver crie uma classe com o conteúdo:

``` {.EnlighterJSRAW enlighter-language="java"}
public class InstallReferrerReceiver extends BroadcastReceiver {
    @Override
    public void onReceive(Context context, Intent intent) {
        String referrer = intent.getStringExtra("referrer");

        //Use the referrer
    }
}
```

E no seu AndroidManifest.xml adicione:

``` {.EnlighterJSRAW enlighter-language="xml"}
<receiver
    android:name="com.example.android.InstallReferrerReceiver"
    android:exported="true">
    <intent-filter>
        <action android:name="com.android.vending.INSTALL_REFERRER" />
    </intent-filter>
</receiver>
```

 

 

### Como funciona no caso do AppsFlyer:

Agora que você já entendeu como as plataformas se utilizam desses recursos, veja como o AppsFlyer mostrou esse funcionamento na rede deles:

Links:

<https://support.appsflyer.com/hc/en-us/articles/207032096-Accessing-AppsFlyer-Attribution-Conversion-Data-from-the-SDK-Deferred-Deeplinking->

<https://support.appsflyer.com/hc/en-us/articles/207032146-How-Can-I-Get-the-Install-Referrer-URL-from-my-Android-App-Context->

Imagem:

[![appsflyer-attribution-data](http://pcoutinho.com/wp-content/uploads/2016/06/appsflyer-attribution-data.jpg){.alignnone .size-full .wp-image-295 width="1237" height="780"}](http://pcoutinho.com/wp-content/uploads/2016/06/appsflyer-attribution-data.jpg)

 

No caso do Google, basicamente o usuário vai clicar em um link como este:

> app.appsflyer.com/angry-birds-android?pid=tapjoy\_int&clickid=1020fe4c7e875&c=Ad1&af\_siteid=2684

E quando o Broadcast Receiver for notificado, irá receber algo como:

> af\_tranid=3M69WKEKDHFPRXPG&pid=tapjoy\_int&clickid=1020fe4c7e875&c=Ad1&af\_siteid=2684

O AppsFlyer também possui uma aplicação para testar as campanhas antes de enviar o aplicativo para a loja:

Para Android:

<https://support.appsflyer.com/hc/en-us/articles/207032136-Testing-AppsFlyer-Android-SDK-Integration-Before-After-Submitting-to-Google-Play>

Para iOS:

<https://support.appsflyer.com/hc/en-us/articles/207032046-Testing-AppsFlyer-iOS-SDK-Integration-Before-Submitting-to-the-App-Store->

 

### Funcionamento geral:

Há diversas formas de fazer este tracking, como por exemplo, por IP. Mas usuários que usam WIFI ou estão dentro de redes específicas podem ter o mesmo IP de saída e esta regra acaba falhando.

O IDFA, no caso da Apple, ajuda neste sentido, pois você sabe quem é o usuário pois o mesmo IDFA clicado é o mesmo que gerou o evento após o aplicativo ser aberto.

É claro que as informações podem se perder, o usuário podem nem mesmo abrir o aplicativo, um problema de conexão pode impedir o envio dos dados, ou ele pode simplesmente desinstalar, enfim, como regra geral essas técnicas funcionam bem e fica fácil entender como este processo funciona agora.

 

Espero ter ajudado com este artigo.

Obrigado e até o próximo post pessoal.
