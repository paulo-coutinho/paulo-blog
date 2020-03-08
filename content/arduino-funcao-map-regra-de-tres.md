Title: Arduino - Função MAP - Regra de três
Date: 2014-09-23 13:00
Author: paulo
Category: Arduino
Tags: arduino, função, map, regra, trÊs
Slug: arduino-funcao-map-regra-de-tres
Status: published

Olá pessoal,  
A um tempo atrás achei uma função bem útil no Arduino, chamada: **map**

Ela basicamente faz uma regra de 3 e te retorna o valor de X (na regra de três). Vou mostrar um exemplo:

    // lê os dados qualquer da porta 0
    int valor = analogRead(0);

    // faz o mapeamento da faixa inicial e faixa final do valor 1 com a faixa inicial e faixa final do valor 2, através do valor passado no primeiro parâmetro
    valor = map(valor, 0, 1023, 0, 255);

    // escreve na porta 9 o valor gerado
    analogWrite(9, valor);

 

Explicação detalhada:

**Parâmetro 1:**  
É o valor que temos em mão, e que queremos que o mapeamento use como referência

**Parâmetro 2:**  
Faixa inicial do "parâmetro 1", ou seja, o menor valor possível para ele

**Parâmetro 3:**  
Faixa final do "parâmetro 1", ou seja, o maior valor possível para ele

**Parâmetro 4:**  
Faixa inicial do valor a ser retornado em relação ao "parâmetro 2", ou seja, o menor valor possível em relação ao "parâmetro 2"

**Parâmetro 5:**  
Faixa final do valor a ser retornado em relação ao "parâmetro 3", ou seja, o maior valor possível em relação ao "parâmetro 3"

Resumindo: O resultado desta função é um valor entre os **"parâmetros 4 e 5" em relação aos parâmetros "2 e 3"**.

Obrigado e até o próximo post pessoal.
