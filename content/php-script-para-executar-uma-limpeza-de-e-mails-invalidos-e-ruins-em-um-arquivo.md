Title: PHP - Script para executar uma limpeza de e-mails inválidos e ruins em um arquivo
Date: 2015-09-22 17:33
Author: paulo
Category: PHP
Tags: email, limpar, php, script
Slug: php-script-para-executar-uma-limpeza-de-e-mails-invalidos-e-ruins-em-um-arquivo
Status: published

Olá,

Por muitas vezes precisamos exportar uma base de e-mails para ferramentas de e-mail marketing e ao importar a base de dados nessas ferramentas por diversas vezes são importados e-mail inválidos, escritos de forma incorreta, faltando um ponto e ao enviar uma campanha a ferramenta detecta esses problemas e o IP do sender do e-mail marketing é bloqueado.

Para resolver estes problemas, resolvi criar um script para remover os e-mails que são considerados como inválidos (ex.: aqueles domínios de e-mails temporários, que um usuário usa só pra se cadastrar no seu site e que no final você é prejudicado por enviar um e-mail para estes domínios) e para consertar os domínios mais comuns escritos de forma errada.

Analisei uma base real de 300mil registros e detectei que apenas 1/3 da base continha e-mail escritos de forma correta e com domínios válidos através de um script que fiz para saber quantos e-mail estavam escritos errados e quantos continham domínios inválidos antes de realmente corrigir. De toda a base, apenas 5 e-mails tinham domínio inválido e mais de 200mil usuários escreveram o domínio do e-mail de forma incorreta, ex: Ao invés de \@gmail.com colocavam \@gmai.com ou \@gmailcom.

Após o término do script o processo removeu apenas 5 dos 300mil e pude ainda usar os outros 299995 como base limpa.

Agora você imagina o quanto de melhora em relação aos resultados do e-mail marketing pôde ser obtido com este simples script.

 

Baixe o script gratuitamente no repositório:

<https://github.com/prsolucoes/clean-emails>

 

Não é obrigatório, só peço que as novas regras que forem úteis e puderem ser compartilhada, que você faça um pull-request para que cada vez mais o script fique melhor.
