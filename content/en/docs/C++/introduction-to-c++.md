---
title: "Introdução ao C++"
description: "Aprenda C++ do básico ao avançado."
lead: "Aprenda C++ do básico ao avançado."
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "C++"
weight: 100
toc: true
---

## Uma história básica

C++ is one of the most popular languages and it has been used for the development of many widely used applications. Although it is one of the older programming languages, C++ is steadily ranked among the most widely used and most powerful programming languages. C++ is not specialized for a specific application field; on the contrary, it is used for an impressive range of applications. For example, C++ is widely used to develop gaming applications, web applications, operating systems, networking applications, financial, browsers, compilers, embedded systems, and many more. A great number of popular applications that we all use in our daily life are written in C++. Also, it is more effective than many other languages for developing applications across a different range of computing systems and environments, such as personal computers, workstations, tablets, and mobile phones.

C++ originally derives from C, which was developed at Bell Labs in the early 1970s by Dennis Richie and others. The rapid expansion of the C language and its increased popularity led many companies to develop their own C compilers. However, due to the absence of an official standard, features that were not clearly described could be implemented in different ways. As a result, the same program could be compiled with one C compiler and not with another. In parallel, the C language continued to evolve with the addition of new features and the replacement or obsolescence of existing ones. The need for the standardization of C language became apparent. In 1983, the American National Standard Institute (ANSI) began the development of the C standard that was completed and formally approved, in 1989, as ANSI C or Standard C. The ANSI C standard also defines a library that every ANSI C implementation must support. C++ also supports that library.

The design and development of C++ began at Bell Labs in the early 1980s by Bjarne Stroustrup as an extension of the C language. Stroustrup had several reasons to base C++ on C, such as C’s brevity, high performance, portability, and widespread popularity. In fact, the name C++ comes from the C increment operator ++, which increments the value of a variable by one. According to Stroustrup, the name signifies the evolutionary nature of the changes from C.

## Nosso primeiro programa em C++

___

Nosso primeiro programa será uma versão "rock" do programa que a maioria dos programadores começam. Ao invés da clássica mensagem *hello world*, nosso primeiro programa exibe na tela o clássico som dos *Ramones*: *Hey Ho, Let's Go*.  

```c++
#include<iostream>
int main()
{
  std::cout << "Hey Ho, Let's Go\n";
  return 0;
}
```

Antes de explicarmos as linhas do programa, vamos discutir brevemente a biblioteca padrão.

### Biblioteca Padrão

A palavra *biblioteca* refere-se a uma coleção de recursos de software (por exemplo, funções), geralmente escritos por outros, que podemos usar em nossos programas. A biblioteca padrão ocupa grande parte do C++ standard e fornece uma grande coleção de componentes que facilitam o trabalho do programador. Por exemplo, a classe *string* é um desses componentes e torna mais fácil para o programador gerencia-lás. Todo compilador C++ deve suportar a biblioteca padrão.

A biblioteca padrão é definida em um namespace separado, que se chama *std*. Falaremos sobre namespaces em breve. Os serviços da biblioteca padrão (por exemplo, exibir dados na tela) são fornecidos por meio de arquivos especiais, esses arquivos são normalmente chamados de arquivos de cabeçalho (*header files*) e são fornecidos com o compilador. Um deles é o *iostream*; Como dissemos, a biblioteca C++ inclui a biblioteca C, para cada arquivo de cabeçalho *X.h* da biblioteca C existe o cabeçalho *cX* correspondente na biblioteca C++. A letra c indica que o arquivo de cabeçalho faz parte da biblioteca C. Por exemplo, o arquivo correspondente de *stdio.h* é o arquivo *cstdio*. Embora seu conteúdo possa ser o mesmo, o formato *cX* é mais adequado para programas C++. Em particular, a inclusão do arquivo *cX* coloca os nomes definidos neste arquivo no namespace *std*. Observe que você pode ler programas que incluem o arquivo *iostream.h* em vez de *iostream. iostream.h* que é uma versão mais antiga do *iostream* e não é mais compatível com o padrão C++.

### A Diretiva #include

C++ usa um programa de software chamado pré-processador. O pré-processador normalmente faz parte do compilador e sua função é processar o programa antes de ser compilado. O pré-processador comunica-se com o compilador por meio de diretivas. Uma diretiva de pré-processador instrui o compilador a agir de acordo. Por exemplo, com a diretiva __#include__, o pré-processador instrui o compilador a incluir o conteúdo do arquivo *iostream* no programa antes de ser compilado. Com relação à sintaxe, as diretivas sempre começam com o caractere # e não terminam com ponto e vírgula (;) ou algum outro marcador especial. Veremos mais diretivas de pré-processador no Capítulo 15.

O arquivo *iostream* onde a letra __i__ corresponde ao *input* e __o__ ao *output*, contém informações sobre classes e funções necessárias para ler e exibir dados. Se não incluirmos este arquivo, o compilador não reconhecerá o *cout* e a compilação falhará. Para incluir um arquivo da biblioteca padrão  como *iostream*, colocamos o nome do arquivo entre colchetes <>. Um arquivo incluído também pode conter diretivas __#include__ e incluir outros arquivos. Em geral, quando estamos usando componentes da biblioteca padrão em nosso programa, devemos incluir os arquivos de cabeçalho correspondentes. Por exemplo, se estivermos usando a classe *string*, precisamos incluir o arquivo *string*. A ordem em que os arquivos são incluídos não importa; A prática comum é colocar as diretivas __#include__ no início do arquivo.

Quando você se familiarizar com o C++, você pode editar seus próprios arquivos de cabeçalho e incluí-los em seus programas. Para incluir seu próprio arquivo de cabeçalho, coloque seu nome entre aspas duplas ("").

Quando o programa é compilado, o compilador procura os arquivos incluídos. As regras de busca dependem da implementação. Normalmente, se o nome do arquivo estiver entre <>, o compilador pesquisa em diretórios predefinidos que contêm os cabeçalhos da biblioteca padrão. Se estiver entre aspas duplas (""), o compilador geralmente começa com o diretório que contém o arquivo de origem e, em seguida, pesquisa os diretórios predefinidos. Se o arquivo não for encontrado, o compilador produzirá uma mensagem de erro e a compilação falhará. O nome do arquivo pode incluir informações relativas ou completas do caminho. Por exemplo:

```c++
#include "d:\projects\serial.h" // DOS/Windows path.
#include "/usr/include/serial.h" // Linux/Unix path.
#include "..\projects\test.h" // Relative path.
```
No entanto, seria melhor evitar incluir informações de path ou drive, pois se seu programa for transferido para outro sistema, sua compilação poderá falhar.

Depois de se familiarizar com o C++, você pode abrir os arquivos incluídos (por exemplo, iostream) e lê-los. Não confie neles apenas como fonte de algum conhecimento místico que esconde segredos invisíveis. São arquivos de texto que existem em seu computador. Encontre-os e veja seu conteúdo. É uma excelente fonte de conhecimento e informação extra.


### A Função main()

Cada programa em C++ deve conter uma função chamada *main()*. A palavra *main()* deve ser escrita em caracteres minúsculos. O código do programa, ou então o corpo da função, deve estar entre chaves ({}). Um statement é um comando que será executado quando o programa for executado. Os statements são normalmente escritas em linhas separadas e, quase sempre, cada statement termina com um ponto e vírgula. Embora o compilador não se importe com o layout do programa, a indentação e o espaçamento adequados tornam seu programa mais fácil de ler. Braces(chaves) são usadas para agrupar declarações e instruções em um bloco ou então uma instrução composta que o compilador trata como uma. Além das funções, usaremos chaves em instruções de controle e loops.

O *main()*, como o próprio nome indica, é a função principal de qualquer programa. Falaremos sobre funções no Capítulo 11. Simplificando, uma função é uma série de declarações e comandos que foram agrupados e receberam um nome (por exemplo, main()). Uma função é chamada pelo seu nome para realizar uma tarefa específica e pode, opcionalmente, retornar um valor. A função *main()* é chamada automaticamente pelo sistema operacional quando o programa é executado. A execução do programa começa com a primeira instrução de *main()* e termina quando a última instrução de *main()* é executada, a menos que uma instrução de saída (por exemplo, __return__) seja chamada anteriormente. Obviamente, se ocorrer um erro grave durante a execução do programa, como uma divisão por 0, o programa terminará de forma anormal. A palavra-chave __int__ indica que *main()* deve retornar um integer ao sistema operacional quando terminar. Esse valor é retornado com a instrução __return__; o valor 0 indica terminação normal, enquanto valores diferentes de zero indicam algum tipo de falha. Esta declaração de *main()* é bastante comum. No entanto, você pode ver outras declarações, como:

```c++
void main
```

Como veremos no Capítulo 11, a palavra-chave __void__ indica que *main()* não retorna nenhum valor. Embora um compilador C++ possa aceitar essa declaração, ela não está em conformidade com o padrão porque *main()* deve retornar um valor. Outra declaração comum é:

```c++
int main(void)
```

A palavra __void__ afirma explicitamente que *main()* não aceita parâmetros; no entanto, seu uso é desnecessário porque os parênteses vazios () indicam o mesmo. No Capítulo 11, veremos outra declaração de *main()*, no qual *main()* recebe parâmetros. Observe que a instrução __return__ pode ser omitida. Se for omitida, o programa retornará automaticamente o valor 0. Embora o resultado seja o mesmo, minha preferência é usar a instrução __return__ para que seja claramente mostrada.

_cout_ é um objeto que é declarado no namespace *std* e está associado à saída padrão predefinida (por exemplo, tela). *cout* sabe como exibir uma variedade de dados, incluindo strings, números e caracteres individuais. Em C++, uma série de caracteres entre "" é chamada de *string literal*. A notação ≪ indica que a string é enviada para *cout*. Como veremos no Capítulo 3, o caractere de nova linha *\n* move o cursor para o início da próxima linha. A principal razão pela qual eu adiciono *\n* no final da string é que mensagens como Pressione qualquer tecla para continuar, que podem ser exibidas por alguns compiladores após o término do programa, aparecem na próxima linha.

### Estilos de Escrita

Em relação à sintaxe do programa, as chaves {} não precisam ser colocadas em linhas separadas. Por exemplo, podemos adicionar o {next to *main()* e escrever *main()*{ or the} próximo à instrução __return__. Além disso, não é necessário recuar o código. Como você pode imaginar, há muitas maneiras de escrever o programa. Por exemplo, poderíamos escrever *main()*{ e colocar o código em uma única linha grande; no entanto, essa opção tornaria nosso programa ilegível. Uma linha pode conter várias instruções. Por exemplo, é legal escrever:

```c++
std::cout << "Hey Ho, Let's Go\n"; return 0;
```

Além das preferências que qualquer um possa ter, o que realmente importa é que um programa seja escrito de tal forma que seja fácil de ler não só por quem o escreveu, mas também por outros que vão lê-lo. Para melhor legibilidade, o estilo de escrita que prefiro é sempre colocar o {} em linhas separadas, cada instrução em uma linha e recuar o código.

### Namespaces 

Vamos fazer uma breve introdução aos namespaces. C++ permite o agrupamento de dados (por exemplo, classes, funções, variáveis, …) em um namespace comum. Assim, o namespace é uma parte do programa, no qual determinados nomes (por exemplo, variáveis) são declarados. Esses nomes não são conhecidos fora desta área. Por exemplo, todos os nomes da biblioteca padrão são definidos em um namespace chamado *std*. Como veremos no Capítulo 25, para acessar um elemento do namespace, devemos escrever o namespace seguido do operador de resolução de escopo __::__. Por exemplo, quando escrevemos *std::cout*, acessamos o objeto *cout* que está declarado no namespace *std*. Se quisermos disponibilizar todos os nomes do namespace *std*, escrevemos:

```c++
 using namespace std;
```

Agora, não precisamos adicionar o prefixo *std::* antes dos nomes que usamos, ou seja, podemos escrever:

```c++
cout << "Hey Ho, Let's Go\n";
```

Alternativamente, podemos disponibilizar apenas os nomes que usamos. Isso é obtido usando declarações __using__ correspondentes. Por exemplo:

```c++
 using std::cout;
```

Agora, não precisamos adicionar o prefixo *std::* quando usamos o *cout*, enquanto temos que adicioná-lo ao usar outros nomes de *std*. A convenção que costumo seguir é colocar declarações __using__ separadas para os nomes que uso ou, se esses nomes não aparecerem muitas vezes no programa, use o prefixo, como fiz no primeiro programa com *std::*. A razão pela qual eu prefiro usar declarações __using__ separadas em vez de todo o namespace é deixar claro quais elementos eu uso desse namespace. Ocasionalmente, se os nomes utilizados forem muitos, para maior facilidade de escrita e leitura do código, disponibilizarei todo o namespace. Se em alguns programas eu declaro o std inteiro, embora os nomes não sejam muitos, é para formatar as páginas deste livro para salvar algumas linhas. Falaremos mais sobre namespaces no Capítulo 25. Por enquanto, basta saber que com os namespaces C++ permite que espaços diferentes contenham elementos (por exemplo, variáveis) com os mesmos nomes, que podem ser usados ​​no programa sem criar um conflito entre eles.

### Adcionando Comentários 

