Title: Xcode - Resolvendo o problema "[MT] PluginLoading: Required plug-in compatibility"
Date: 2015-12-10 17:13
Author: paulo
Category: Xcode
Tags: error, plugin, problema, uuid, xcode
Slug: xcode-resolvendo-o-problema-mt-pluginloading-required-plug-in-compatibility
Status: published

Olá,

Aqui vai uma dica para quem atualizou o Xcode e começou a receber o seguinte erro ao executar alguma coisa via linha de comando no terminal:

    [MT] PluginLoading: Required plug-in compatibility UUID XYZ for plug-in at path XYZ

Basta seguir os passos:

1 - Abra o Terminal

2 - Execute:

    XCODEUUID=`defaults read /Applications/Xcode.app/Contents/Info DVTPlugInCompatibilityUUID`

3 - Execute:

    for f in ~/Library/Application\ Support/Developer/Shared/Xcode/Plug-ins/*; do defaults write "$f/Contents/Info" DVTPlugInCompatibilityUUIDs -array-add $XCODEUUID; done

 

Obrigado e até o próximo post pessoal.

 
