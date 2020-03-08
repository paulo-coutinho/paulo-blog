Title: Shell - Matando processos por pattern
Date: 2015-11-06 13:46
Author: paulo
Category: Shell Script
Tags: kill, matar, process, processos, shell
Slug: shell-matando-processos-por-pattern
Status: published

Olá,

Existem algumas formas de matar um processo se você souber o **PID** dele ou até mesmo o nome do processo. Geralmente o procedimento é abrir o **TOP**, pegar o **PID** e executar: **kill -9 \[PID\]**.

Além de ser trabalhoso, quando você quer fazer um script que mate um processo seu conhecido para executá-lo denovo, como foi o meu caso, torna-se trabalhoso fazer isso, além da preocupação de achar o PID correto, então procurei formas mais práticas de fazer isso e pelo nome do meu arquivo binário, já que não teria nenhum outro processo com o nome do nome ou com um nome parecido.

Eu encontrei duas formas, uma usando o **PKILL** e outra usando um loop no resultado do commando **PS** com **GREP**. Abaixo vou colocar as duas soluções, que podem ficar em uma única linha do seu script ou arquivo **Makefile**:

    ps -ef | grep nome-do-processo | grep -v grep | awk '{print $2}' | xargs kill -9

<div>

</div>

<div>

ou

</div>

<div>

</div>

<div>

</div>

    pkill -f nome-do-processo

 

O único cuidado mesmo é com relação ao nome do processo, não pode ser algo genérico, como "a". Senão ele matará todos os processos com o pattern "a".

Obrigado e até o próximo post pessoal.
