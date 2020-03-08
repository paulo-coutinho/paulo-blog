Title: Golang - Novo projeto opensource chamado Gonotin
Date: 2015-10-14 13:03
Author: paulo
Category: Golang
Tags: benchmark, comparar, dados, golang, gonotin, performance, script
Slug: golang-novo-projeto-opensource-chamado-gonotin
Status: published

Olá,

Recentemente necessitamos fazer uma comparação de arquivos para saber se os números de telefone de uma base existiam em outra e depois de várias tentativas para achar a quantidade correta de registros, eu desenvolvi alguns scripts para fazer essa comparação independente da ordem dos dados e realizando a comparação um a um.

Inicialmente fiz em PHP, porém usando a função IN\_ARRAY, notei que a performance estava péssima. Com um arquivo de 200mil (2.5mb) registros esperei quase 45 minutos e ainda não tinha finalizado, por fim desisti e resolvi reescrever usando o Go.

Ao reescrever o código em Go o processamento foi quase que imediato usando a abordagem do MAP. Você cria um map com a chave a valor sendo o texto que você tem e verifica se os itens existem no MAP ou não.

Após esta abordagem funcionar muito bem no Go, escrevi diversas formas no PHP de processar os mesmos arquivos para fazer um benchmark de performance e a melhor performance alcançada foi usando a função ISSET.

Depois decidi também criar um gerador de arquivos com números aleatórios para fazer listas com dados para os meus testes e validar possíveis erros e melhorar os scripts.

Todo o código está disponível no Github de forma gratuita e pode ser acessado em:

<https://github.com/prsolucoes/gonotin>

 

Dá pra fazer a mesma usando a função DIFF do linux/osx, porém os dados precisam estar ordenados nas duas listas.

Espero com este script poder ajudar a todos que precisam resolver este problema de forma prática.

Obrigado e até o próximo post pessoal.
