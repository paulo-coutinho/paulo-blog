Title: Google Apps Scripts - Ferramenta do Google para integração entre seus apps, automatização de tarefas e aplicações na loja do Google Chrome
Date: 2016-03-04 07:06
Author: paulo
Category: Google
Tags: apps, chrome, google, javascript, script, web, web store
Slug: google-apps-scripts-ferramenta-do-google-para-integracao-entre-seus-apps-automatizacao-de-tarefas-e-aplicacoes-na-loja-do-google-chrome
Status: published

Olá pessoal,

O Google sempre surpreendendo e melhorando cada vez mais, lançou uma ferramenta chamada Google Apps Script.

Se eu pudesse comparar com algum produto, iria selecionar o VBScript da Microsoft integrado ao Office para este fim, porém o GAS (Google Apps Script) vai bem mais além, pois você pode automatizar qualquer coisa nas ferramentas do Google (docs, sheets, calendar, etc), acessando todas as ferramentas cloud do Google e usando JavaScript para tal.

Será difícil colocar aqui todos os detalhes, mas vou destacar aqueles que me chamaram a atenção:

1.  Editor de códigos JavaScript do Google com Auto Complete (online)
2.  Integração com todos os produtos do Google (docs, sheet, drive, calendar, etc)
3.  Integração com cloud (ex: banco de dados key-value)
4.  Editor visual de formulários (RAD)
5.  Reaproveitamento do script em todas as ferramentas (em qualquer ferramenta você pode chamar o script se houver esta opção, eles não são exclusivos de uma ferramenta, mas ficam gravados em sua conta)
6.  Publicação da aplicação na loja do Google Chrome ([Google Chrome Web Store](https://chrome.google.com/webstore))

 

Fazendo alguns testes foi bem simples, por exemplo, exibir uma mensagem em um novo menu que criei no Google Spreadsheet:

\[gallery order="DESC" ids="245,248,247,246"\]

O seu script pode se tornar um código para diversos tipos de aplicação no ambiente do Google, como pode ser visto na imagem abaixo:

[![](http://pcoutinho.com/wp-content/uploads/2016/03/Screenshot-2016-03-04-04.00.04.png){.alignnone .wp-image-250 .size-full width="980" height="526"}](http://pcoutinho.com/wp-content/uploads/2016/03/Screenshot-2016-03-04-04.00.04.png)

É claro que este teste foi bem simples, mas você pode estudar toda a documentação e fazer seus testes, coletando dados de outras aplicações e montando aquilo que vai te ajudar no dia-a-dia ou automatizar o seu trabalho. Acesse o link da documentação completa em:

<https://developers.google.com/apps-script/>

Vou deixar também o código do teste que fiz:

``` {.EnlighterJSRAW enlighter-language="js"}
function menuMostraMsg() {
  Browser.msgBox("Até funciona!")
}

function menuSobre() {
  Browser.msgBox("Visite: pcoutinho.com")
}

function createMenu() {
  var menuEntries = [
    { name : "Clique Aqui!", functionName : "menuMostraMsg" },
    null,
    { name : "Sobre", functionName : "menuSobre" }
   ];
  
   SpreadsheetApp.getActiveSpreadsheet().addMenu("Meu Menu", menuEntries );
}

function onOpen(e) {
  // quando todo os script é carregado
  createMenu(); 
}

function onInstall(e) {
  // quando alguém instala o add-on
  onOpen(e); 
}

function onEdit(e) {
  // quando alguém edita algum dado
}
```

 

Bom, espero ter ajudado com estas dicas.

Obrigado e até o próximo post pessoal.
