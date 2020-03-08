Title: C++ - Separando ou explodindo uma String
Date: 2014-09-19 16:21
Author: paulo
Category: C++
Tags: c++, explode, explodir, string, texto
Slug: c-separando-ou-explodindo-uma-string
Status: published

Olá pessoal,

Vejo muitas pessoas com dúvida em relação a como fazer um split ou explodir uma string em partes usando um delimitador.

Vou então mostrar algumas técnicas possíveis de executar isso.

Vamos usar uma frase de exemplo:

>     O rato roeu a roupa do rei de roma.

Nossa intenção é separar cada palavra contida na frase usando o caracter \[espaço\] como delimitador e com isso ter uma lista em memória com todas as palavras encontradas.

Vou mostrar agora 3 métodos de fazer isto em C++ de forma prática e fácil.

1 - Se você usa a biblioteca Boost, use o código abaixo para em 3 linhas obter um vetor de strings com as palavras:

    #include <boost/algorithm/string.hpp>
    int main()
    {
        vector<string> results;
        boost::split(results, line, boost::is_any_of(";"));
    }

2 - Usando agora uma função antiga para saber o ponteiro na string de onde começa cada palavra:

    #include
    #include 

    int main() {
        char s[] = "one, two,, four , five,"; /* mutable! */ const char* p;
        for (p = strtok( s, "," ); p; p = strtok( NULL, "," )) {
            printf( "\"%s\"\n", p );
        }
        return 0;
    }

3 - E por último, uma função simples que funciona basicamente como o método \#1:

    #include 
    #include 

    void split(string str, string separator, vector* results)
    {
        int found;
        found = str.find_first_of(separator);

        while(found != string::npos)
        {
            if(found > 0)
            {
                results->push_back(str.substr(0,found));
            }
            
            str = str.substr(found+1);
            found = str.find_first_of(separator);
        }

        if(str.length() > 0)
        {
            results->push_back(str);
        }
    }

    int main()
    {
        vector results;
        split("O rato roeu a roupa do rei de roma", " ", &results);
    }

É isso ai. Espero que com estes códigos um pouco simples, ajudem a todos.
