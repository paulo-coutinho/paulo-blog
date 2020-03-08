Title: Xcode - Corrigindo o erro "This certificate has an invalid issuer"
Date: 2016-02-18 16:45
Author: paulo
Category: Xcode
Tags: apple, certificate, expired, wwdrc, xcode
Slug: xcode-corrigindo-o-erro-this-certificate-has-an-invalid-issuer
Status: published

Olá,

A Apple possui um certificado "pai" ao qual sem este certificado ou com este certificado expirado, todos os outros se tornam inválidos.

O certificado "pai" conhecido como "WWDR Certificate" pode ser baixado gratuitamente e ao executá-lo, ele já deve ser instalado em seu KeyChain automaticamente.

Recentemente todo mundo começou a receber a mensagem de que o seu certificado estava inválido com a mensagem "This certificate has an invalid issuer" simplesmente "do nada".

Mas na verdade o que aconteceu é que o "WWDR Certificate" expirou e agora há a necessidade de baixarmos o novo certificado com uma nova expiração. Neste novo certificado a expiração ocorrerá em 2023.

Para baixar acesse o link:

<https://developer.apple.com/certificationauthority/AppleWWDRCA.cer>

Basta executá-lo e o problema será resolvido.

Obrigado Vinícius ([\@vibrito](https://twitter.com/vibrito)) pela dica.

Obrigado e até o próximo post pessoal.
