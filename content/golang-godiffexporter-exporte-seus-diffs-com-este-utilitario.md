Title: Golang - GoDiffExporter - Exporte seus DIFFs com este utilitário
Date: 2016-07-31 00:57
Author: paulo
Category: Golang
Tags: diff, exporter, golang, pdf
Slug: golang-godiffexporter-exporte-seus-diffs-com-este-utilitario
Status: published

Olá,

Recentemente precisei compartilhar o resultado de um DIFF (git diff) para uma outra pessoa fazer a conferência e com isso eu precisava passar o acesso ao bitbucket e o link do commit específico para a conferência.

Isso me gerava um certo trabalho que eu não gostaria de ter toda vez que precisasse fazer isso, foi ai que pensei então no GoDiffExporter, um exportador em PDF de um arquivo DIFF qualquer.

Basicamente o parser do DIFF é feito e depois eu itero nas diferenças e crio o PDF, usando a lib GoFPDF, que inclusive colaborei recentemente adicionando o suporte a fontes embarcadas através de um array de bytes que vai dentro da sua própria aplicação, removendo a necessidade de distribuir as fontes em si (<https://github.com/jung-kurt/gofpdf/pull/79>).

O resultado do GoDiffExplorer é um PDF como este:

\[gallery order="DESC" ids="307,309,308"\]

 

O projeto e as instruções de como instalar e usar estão na página do projeto:

<https://github.com/prsolucoes/godiffexporter>

 

Espero ter ajudado com este artigo.

Obrigado e até o próximo post pessoal.
