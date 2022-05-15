# Dicas para resolver os exercícios do https://run.codes/

Nas monitorias da disciplina de COM112 - Algoritmos e Estruturas de Dados II (UNIFEI), tenho visto algumas práticas que ao meu ver dificultam a resolução dos exercícios como também o aprendizado. Então eu resolvi fazer esse texto na intenção de compartilhar o que eu já falo sempre para os colegas quando presencio essas práticas. O objetivo aqui não é ter um livro de regras que devem ser seguidas cegamente e sim mostrar alternativas que acredito fazer o processo de resolução do exercício mais produtivo. Ele ficará aqui no GitHub justamente pra ser modificado futuramente, inclusive você pode contribuir se quiser.

## Contextualizando o run.codes
O professor passa uma matéria, e depois lança um exercício no run.codes. Cada exercício é um código que você tem que fazer e que será corrigido automáticamente. Normalmente os exercícios são compostos de:
1. <b>Enunciado:</b> É o texto que explica o que é pra fazer, ele pode estar no próprio run.codes ou em um arquivo que o professor postou no sigaa.
2. <b>Casos de testes</b>: São arquivos de textos que podem ser baixados na página do exercício no run.codes. Alguns podem estar com as extensões `.in` ou `.out` pra identificar respectivamente os arquivos de entrada e de saída. Mas independente da extensão que ele estiver eles são apenas arquivos de textos que podem ser abertos com qualquer editor de texto. Os arquivos de entrada conterá os dados de entrada que será lido pelo seu programa. <b>Mas não confunda!</b> O seu programa irá ler os dados como se alguém estivesse digitando (conhecido como <b>entrada padrão</b>), você irá ler esses dados na linguagem C usando funções como `scanf` por exemplo. Em alguns exercícios será necessário ler algum arquivo com funções de leitura de arquivo, mas isso será explícito de alguma forma no <b>enunciado</b> ou no <b>código</b> fornecido pelo professor (na maioria das vezes a parte de leitura escrita já vem implementada).
3. <b>Código</b>: Pode ser um ou mais arquivos que irá compor o programa. Nesse código normalmente o professor implementa a leitura e escrita dos dados e define os locais aonde ele quer que você escreva o seu código.
   
## Dicas iniciais
Agora que já está tudo contextualizado, algumas dicas já podem ser ditas, e embora eu não quero parecer um ditador, são ações obrigatórias, que se você não fizer vai perder muito tempo pra terminar o exercício (e só vai consegir terminar se tiver muita sorte). Abaixo eu listei o que você deve fazer obrigatoriamente antes mesmo de digitar um caractere no programa:
1. Leia todo o <b>enunciado</b>.
2. Baixe os casos de teste.
3. Baixe o <b>código</b> fornecido pelo professor.
4. Coloque o arquivos dos <b>casos de teste</b> e o <b>código</b> na mesma pasta na sua máquina.
5. Leia o <b>código</b> do professor.
6. Leia alguns arquivos dos <b>casos de teste</b>.
7. Entenda o que cada dado significa nos arquivos de entrada e saída dos <b>casos de teste</b>.
8. Entenda o que as funções já implementadas no <b>código</b> do professor fazem.
9. Entenda o que significa os `structs` do <b>código</b> do professor.
10. Entenda o que a `main` está fazendo.
11. Compile o <b>código</b> fornecido.
12. Rode o programa.

## Ainda não é hora de começar
É esperado que o código tenha compilado sem nehum erro. Caso haja algum erro na compilação avise o professor, pois o código dele está errado. Também é esperado que você consiga executar o programa sem nenhum problema. Existem várias de executar o programa na sua máquina, que podem variar de acordo com o seu ambiente:
1. Você pode copiar o texto do arquivo de entrada de um <b>caso de teste</b> e colar no "terminal" que você está rodando.
2. Ou pode rodar no terminal fazendo o programa ler a entrada automaticamente.
    No terminal do linux rodamos assim:
    ~~~bash
    ./executavel < arquivo-de-entrada
    ~~~
    Na minha opinião essa é a maneira mais produtiva, pois como o terminal "grava" os comandos na memória, você não precisa digitar ele toda hora. Basta teclar a seta pra cima e teclar <i>enter</i> e o programa será executado lendo a entrada sem a necessidade de digitar ou copiar e colar.

Agora você sabe que o seu ambiente está funcionando e o <b>código</b> do professor não está com erro, porém você tem que ter certeza que você sabe o que o código do professor faz:

1. Crie um outro um novo programa com uma `main` em branco e cole no programa as funções e `struct` do professor (obviamente fora da `main`).
2. Agora brinque com essas funções nessa `main`. Se for preciso crie variáveis, crie instâncias do `struct` ou até leia arquivos de entrada se for preciso e imprima as saídas das funções. Vá compilando e rodando o programa. Veja se as saídas dessas funções fazem sentido pra você. Algumas funções só vão poder ser chamadas depois de outras, e se você conseguir usar essas funções de maneira diferente da `main` do professor, e se as saídas estão fazendo sentido pra você é por que você entendeu o <b>código</b> do professor.

## Entendendo a lógica
Agora você precisa entender os algoritmos da função que você vai implementar:
1. Faça desenhos, e explique para o seu amigo imaginário o que o algoritmo faz.
2. Faça testes de mesa escrevendo, desenhando, apagando, etc. Fazendo uma simulação do comportamento do algoritmo.
3. Resista a tentação de olhar o código do seu colega, pois isso causa dependência, e você não desenvolve o seu raciocínio. Eu já vi uns dez que só fazia isso, mas já deixaram o curso, por que chega num ponto que fica insustentável, e o amigo não está lá com você na entrevista de estágio.
4. Converse em alto nível com o seu colega, falando o que o algoritmo faz.

## É hora de programar
Quando é mais de uma função que você precisa implementar, na minha opinião, o ideal é você ir implementando e testando uma por uma, usando aquela `main` em branco que eu falei anteriormente.
### "Converse" com o editor
A maioria dos editores mostram onde tem um erro de sintaxe antes mesmo de compilar. Descubra o porque desse erro e tente corrigir antes de compilar.
### "Converse" com o compilador
Se ainda houver um erro de sintaxe, o compilador irá informar o número da linha onde está o erro e mostrará uma mensagem sobre o erro. Se não entendeu a mensagem por estar em ingês, copie e cole a mensagem no google tradutor. Se ainda não entendeu o significado do erro, copie e cole no google. Se apareceu um resultado do Stack Overflow, provavelmente a primeira resposta já vai te ajudar entender o seu erro.
### Foque em um erro de cada vez
Quando aparecer vários erros na compilação, tente corrigir apenas o primeiro de cima pra baixo. Depois que corrigir, compile de novo e veja os novos erros. As vezes os demais são consequência do primeiro erro, por isso não perca tempo tentando corrigir tudo de uma vez.
### O compilador só mostra erro de sintaxe
Quando aparece um ou mais erros na compilação, não siginifica que a sua lógica está errada. Significa que você não está usando a linguagem da maneira correta. Erro de sintaxe você descobre olhando para as mensagens de erro do compilador, já erro de lógica você encontra olhando saídas funções e do programa inteiro.
### Erro de segmentação
Você compilou e não apareceu nenhum erro, mas quando rodou apareceu um `segmentation fault (core dumped)`. Esse erro acontece quando o programa tenta acessar uma memória que não foi declara ou alocada. Na maioria das vezes esse erro acontece no `for` mas existe exceções. Como esse erro só aparece na hora da execução, você terá que procurar ele dentro do código.
Se você tentar alterar o código sem ter certeza de onde está o erro de segmentação, você vai destruir seu programa inteiro. Então se não tem ideia de onde esteja esse erro use a função `exit(0);`. Essa linha irá interromper a execução do programa. Coloque essa linha abaixo das linhas que você acha que o erro está. Compile e rode. Se não aparecer a mensagem `segmentation fault (core dumped)` novamente, significa que o erro não está nas linhas acima de `exit(0);` e está abaixo. Então coloque a linha mais abaixo e repita o processo até encontrar a linha em que se `exit(0);` estiver acima dela a mensagem não aparece e se estiver abaixo a mensagem aparece. Se essa linha for uma função, você deve entrar dentro da função e fazer a mesma coisa até encontrar o trecho que causou esse erro.
### Erro de lógica
Você fez tudo recomendado até aqui, compilou e executou o programa contendo o código do professor e as funções que você implementou. Compilou e rodou sem nenhum erro. Porém a saída está diferente do arquivo de saída.
Você não precisa enviar o código no run.codes para ver isso, basta rodar o programa na sua máquina e olhar a saída e comparar com o arquivo de saída. Se estiver diferente, isso significa que seu programa não está funcionando como deveria. O erro aqui não é de código, o erro está na lógica, você imaginou uma lógica para resolver o problema e ela está equivocada. Obviamente você deve rever os materiais da disciplina, ou voltar no enunciado pra ver se não entendeu errado o exercício.
E se não conseguir resolver  <b>AQUI É A HORA IDEAL DE PROCURAR O MONITOR</b>.

### Enviando o código no run.codes
Assumindo que agora o seu programa está rodando sem nenhum erro e a saída do programa está exatamente igual ao arquivo de saída, então <b>É AQUI A HORA DE ENVIAR O CÓDIGO NO RUN CODES</b>. Ainda assim alguns erros podem aparecer no run.codes, mas se você seguiu as recomendações até aqui, serão erros simples de resolver.
## Dicas finais
1. Como você já deve ter percebido, os exercícios no run.codes nem sempre poderão ser resolvidos em alguns minutos, na maioria das vez vão ser horas. Então tente chegar na fase do <b>erro de lógica</b> numa data que ainda dê tempo de procurar a monitoria, pois em menos de duas horas da monitoria não dá tempo de fazer o exercício do começo se estiver com dificuldades.
2. Você não precisa esperar o professor passar um exercício ou trabalho valendo nota para ir na monitoria. Faça qualquer exercício da lista e tendo qualquer dúvidas leve na monitoria.
3. Se suas dúvidas são coisas básicas da linguagem C, use o site beecrowd.com.br para treinar. Lá tem desafios básicos e avançados e a correção é automática igual ao run.codes. Você pode fazer isso no horário da monitoria também, se tiver dúvidas o monitor te ajuda.
4. Toda vez que for escrever um código que alguém vai ler, use <b>identação</b>, esse alguém pode ser você no futuro. Deixei uma dicas especial de identação ali embaixo.
## Identação
Não existe consenso em qual dessas duas formas é a correta:
~~~c
if(a == 0){
    printf("'a' é igual a zero\n");
}
~~~
~~~c
if(a == 0)
{
    printf("'a' é igual a zero\n");
}
~~~
Porém você tem que seguir umas regrinhas:
* *Toda vez que uma chave `{`é aberta, as demais linhas recebem mais uma `tab` do que a linha que iniciou o bloco.*
* *Deixe a chave que fecha um bloco `}` alinhado horizontalmente com palavra que iniciou o bloco.* 
* Isso serve para `if`, `switch`, `for`, `while`, a função `main` e qualquer delcaração de função.

## É hora de dar tchal
Acredito que essas dicas são úteis não só para passar em uma disciplina, mas sim pra uma carreira toda. Desejo muito sucesso a todos.


Tiago Rafael Amaral Reis
tiagoamral23@gmail.com