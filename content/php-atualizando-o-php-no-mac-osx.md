Title: PHP - Atualizando o PHP no Mac - OSX
Date: 2014-10-14 16:03
Author: paulo
Category: PHP
Tags: 5.4, 5.5, 5.6, 7.0, 7.1, atualizar, mac, osx, php, update
Slug: php-atualizando-o-php-no-mac-osx
Status: published

Olá pessoal,

Se você possui um Mac e deseja atualizar a versão do PHP que vem nele, existem comandos simples que você pode executar no terminal para realizar esta façanha de forma simples.

Segue abaixo uma lista com os comandos para cada versão (basta copiar e colar no terminal que o script faz todo o restante para você):

**PHP 7.0 (Versão estável):**

    curl -s http://php-osx.liip.ch/install.sh | bash -s 7.0

**PHP 5.6:**

    curl -s http://php-osx.liip.ch/install.sh | bash -s 5.6

**PHP 5.5:**

    curl -s http://php-osx.liip.ch/install.sh | bash -s 5.5

**PHP 5.4 **(Esta versão já não é mais utilizada):****

    curl -s http://php-osx.liip.ch/install.sh | bash -s 5.4

**PHP 5.3 (Esta versão já não é mais utilizada):**

    curl -s http://php-osx.liip.ch/install.sh | bash -s 5.3

Lembrando que este script não modifica ou apaga a versão do PHP que vem nativamente com o OSX, por isso ele instala em uma pasta diferente. Para você sobrescrever o comando **"php" do OSX** para apontar para a sua nova versão instalada, faça o seguinte:

1 - Edite o arquivo **".bash\_profile"**:

    nano ~/.bash_profile

2 - Adicione as linhas e salve o arquivo:

    export PATH=/usr/local/php5/bin:$PATH

3 - Atualize os comandos no terminal:

    source ~/.bash_profile

 

Para verificar a versão do PHP e saber se tudo deu certo, basta executar:

    /usr/local/php5/bin/php -v

Por padrão o script **"packager"** é instalado em **"/usr/local/packer"** e o **PHP** é instalado em **"/usr/local/php5"**. Ao longo da instalação o script pedirá sua senha de usuário, mas fique tranquilo, pois ele pede para copiar os arquivos para as pastas internas do sistema.

Caso você queira saber mais sobre como executar o **"pecl"**, alterar o **"php.ini"**, **"memcached"**, acesse o site oficial: <http://php-osx.liip.ch/> e neste mesmo site você fica sabendo de todas as versões PHP suportadas.

Obrigado e até o próximo post pessoal.
