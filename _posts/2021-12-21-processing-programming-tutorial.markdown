---
layout: post
title:  "Estrelas no céu"
date:   2021-12-21
categories: Processing
excerpt_separator: <!--more-->
---

Tutorial sobre programação basica no processing.
<!--more-->

# Tutorial Estrelas no céu
## Requisitos

* Setup
* Geração de números aleatórios
* Desenhar pontos
* Percorrer espaço em duas dimensões

## Setup

​	Para começar o tutorial, é necessário o download do software processing. O software processing é um programa para experimentação com programação visual, que gera resultados gráficos. É um software construído em cima da linguagem java e permite que os usuários utilizem comandos de alto nível para desenhar primitivas em uma janela.

Link para download: https://processing.org/download

## Geração de números aleatórios (random)

​	Para desenhar estrelas no céu, é necessário que consigamos gerar números aleatórios. Precisamos disso para que as estrelas sejam colocadas em posições diferentes quando o programa rodar. É possível desenhar estrelas sem geração aleatória, porém será perceptível um padrão no desenho. Vamos abordar essa técnica e comparar os resultados. Antes, vamos aprender a gerar números aleatórios.

Para gerar números randômicos (ou aleatórios) chamamos a função random:
`random(1,10);`

Essa função recebe dois parâmetros: o mínimo e o máximo, e ela retorna um número aleatório entre esses dos valores (de 1 incluindo 1, até 10 excluindo o 10). 

Exemplo de código:

```java
void setup()
{ 
int numero = random(1,10);
 println(numero);
}
```

Quando você rodar esse código, o número gerado será impresso no console do processing:

![img](https://lh4.googleusercontent.com/h7I8A8hQ8lc2GUAy_KdBoyx-4Qqur1zb-048fQBhst21Bj-oI00Ztwn-Hv-cGLfGbCTiUhzBDEiEFJYwfJzABvl0OakKLXRCOuLwkoVddsJNDDajMpK01hqjgVg3ce12sotMlD1Q)

​	Para gerar estrelas, vamos usar números aleatórios para decidir em cada parte da tela, se vamos ou não desenhar uma estrela. Assim, as estrelas serão desenhadas de forma mais natural sem muito padrão. Para tal, temos que usar um número aleatório para decidir a cada ponto se uma estrela deverá ser desenhada. 

## Usando números aleatórios para decisão

​	Para decidir se algo deve acontecer aleatoriamente, usamos números aleatórios e ifs (condicionais -> o nome do if em português é ’condicional’ pois ele representa um código que executa apenas dada uma condição).

​	Vamos ver um exemplo:

```java
void setup()
{
    int numero = random(0,100);
    if(numero > 50)
    {
        println("ola");
    }
    else
    {
        println("hello");
    }
}
```


​	Esse código gera um número aleatório entre 0 e 100, em seguida, ele compara o número para saber se ele é maior que 50. Caso positivo, escreve ‘ola’ na tela, caso contrário (else), escreve ‘hello’ na tela. Ou seja, em outras palavras, o código decide aleatoriamente se vai escrever ola ou hello na tela, com 50% de chance de escrever cada opção.

​	Podemos testar ainda mais esse código transformando ele em uma função e rodando ele multiplas vezes (observando os resultados diferentes):

```java 
void setup()
{ 
    dizerOi(); 
    dizerOi();
    dizerOi();
}

void dizerOi()
{ 
    if(random(0,100) > 50)
    {	
        println("ola"); 
    }
    else
    {	
        println("hello");
    }
}
```

Vemos o seguinte resultado:

![img](https://lh5.googleusercontent.com/uOOH_X1HqDgta3E078HgOof_fz3sqZeP3syhEtvEWeAmfn49p9mXMff7VMJ7nb_P3faFiCMu5XrzxV5DxmF3xHZixI13koqjNX2WYFc-VcHZgcNV02qtqhHszFHUhIptCKWs9vwX)

## Desenhando pontos

​	Agora que já sabemos tomar decisões e sabemos gerar números aleatórios, precisamos aprender a desenhar pontos. Os pontos serão nossas estrelas.

​	Para desenhar um ponto basta utilizar a seguinte função:
​	`point(10, 10);`

Essa função desenha um ponto na posição x = 10 e y = 10. Vamos ver como fica:

![img](https://lh6.googleusercontent.com/lToH6oMKwZ3WHI2-H-tsT96pDhTvRz1YaeRSWrIQd3JQ6L9R7Y9hG1gcyv7ilP_7QGj8vNiuQy-HMcykuVSPQOIueXXaICVC5hI2hw-TKq00X0SfJyQiI8qlJOyXCmKGjGbnTNDS)

​	Quase não dá para ver né? Mas está ali no cantinho! À 10 de distância da esquerda da janela, e à 10 de distância do topo da janela. A distância da esquerda da janela é a coordenada que chamamos de x, e a distância do topo da janela é a coordenada que chamamos de y.	

​	É interessante saber que ambas as coordenadas estão em pixels, então se alterarmos o tamanho da janela, ganhamos mais espaço para desenhar. 

Vamos fazer isso:

```java
void setup()
{ 
    size(500, 500); 
    point(10,10);
}
```

​	Esse código muda o tamanho da janela (operação que só pode ser feita dentro da função setup e apenas uma vez), e pinta o ponto na posição 10,10:

![img](https://lh6.googleusercontent.com/-DHL2A3sbHwPhytjzT5WNGh4cAqhfV13YwEHdvaW2og4jUJHy0synt8VWB1lFleY0EKcJLf2aaM4sxT2qF6Izs0lEMslDg-WtTqqGi0OA2MYr8bXIwSDWWbjtdMHJdB9frWJgnrj)



​	Agora o ponto sumiu de vez! Mas vamos em frente. Uma coisa que precisamos fazer é mudar a cor das nossas estrelas e do fundo do nosso céu. Para pintar o fundo, vamos chamar a função background e para mudar a cor das coisas que pintamos (no caso pontos) vamos chamar a função stroke:

```java
void setup()
{ 
    size(500, 500); //Muda o tamanho da janela para 500px x 500px
    background(0); //Pinta o fundo todo de preto
    stroke(255); //Deixa o pincel na cor branca rgb(255,255,255) = branco
    point(10,10); //Pinta ponto da cor branca (cor do pincel)
}
```


​	A função background funciona assim: 

* Você passa para ela três valores (chamados de parâmetros), R para vermelho, G para verde e B para azul. Os valores são passados em ordem e devem ser números inteiros de 0 a 255.
* Se os três números forem iguais para a cor desejada (como preto 0,0,0), você pode chamar a função com apenas um valor. Isso quer dizer que background(0) é o mesmo que background(0,0,0) e é o fundo preto. O mesmo vale para o stroke(255) que é o branco do ponto para a estrela. 

O resultado fica assim:

![img](https://lh4.googleusercontent.com/KTdIif0whovom4rvjPw6ZJfQr-mlf6TCBhn1QhRckYBRNQKKhpc7H52IM0gMj4spL17t9yzZ2JbsA1iRv8g4ZpTEz5rFt4RwleukHG68UGNPnfMLNCb0GLXI-9Fb37rlePDEK7BT)

## Percorrendo o espaço em 2D
​	Agora que desenhamos um ponto, aprendemos a decidir onde desenhar ou não, e sabemos pintar corretamente a tela, vamos aprender a desenhar vários pontos em 2D (duas dimensões).	Para desenhar vários pontos sabemos que devemos usar um loop. Loops são estruturas de código que repetem instruções várias vezes. Conhecemos dois loops, o *for* e o *while*. Para esse caso, o *for* é o melhor loop pois queremos desenhar um número finito conhecido de estrelas.

Vamos primeiro ver um exemplo para entender melhor como o *for* pode nos ajudar:

```java
void setup()
{ 
    size(500, 500);
    background(0); 
    stroke(255); 
    for(int x=0;x<10;x++)
    {
        point(x,10);
    }
}
```

​	Esse código é o mesmo que antes porém desenhamos o ponto várias vezes usando um *for*. Vemos no *for* que criamos uma variável de contagem que começa em 0 e chama x. Vemos que utilizamos a comparação x<10 para parar o *for*, ou seja, ele deverá rodar 10 vezes parando quando x for igual a 9 (lembre-se que a contagem começa em 0!). A função point foi modificada para utilizar a variável de contagem X como parâmetro da posição x do ponto, ao invés de um valor fixo.

Isso quer dizer que quando o for estiver rodando a primeira vez, x será 0 e a função point será chamada assim:
`point(0,10);`

A segunda, será chamada assim: 
`point(1,10);`

E assim por diante, até que x seja 9 e o loop se encerre. 

O resultado desse código é o seguinte:

![img](https://lh4.googleusercontent.com/nEHsKwDLJgYtQDAQp84VPcsmmEZsOP36jfYvFos7eO5ErqrNbGqKm7IgjpqHL2yMsNh0gB4MHfbQL0Z0856p0LA3rXlWNAmak25zRPo_p64MUiyIjISIgaTb2dHkCoLn8n-MZVIy)

​	Vemos uma pequena linha como resultado! Interessante! Isso acontece porque desenhamos pontos de pixel em pixel para todas as posiçoes de 0 até 10 onde y era igual a 10! Soa complicado mas basta testarmos com outros valores de y na função point, ou brincarmos com os valores de x no *for* para vermos o que está acontecendo:

```java
void setup()
{ 
    size(500, 500); 
    background(0); 
    stroke(255);  
    for(int x=200;x<300;x++)
    {	
        point(x,100);
    }
}
```


![img](https://lh5.googleusercontent.com/3zYZYN1c3kYSmIIbS7Xm1JmBiJeImXfymihqrfaDslVgT0AIaLhFa5I8hooy4m-BwFSwAxR9CFcV6cQTonOE9PCYdYK5TvBR7ULNON7nxBOHF8ey0kRQyPHn2fOZWLH6bAu2pvs8)

​	Legal! Agora só nos resta transformar isso em estrelas! Mas como? Primeiro precisamos desenhar uma linha com estrelas e não totalmente preenchida. Para isso, vamos usar uma decisão aleatória dentro do nosso loop de forma que não vamos desenhar o ponto todas as vezes, mas sim só algumas. Além disso, vamos mudar o código para que a linha vá de um lado da tela até o outro, ou seja, de 0 até 500 (em x):

```java
	void setup()
    { 
        size(500, 500);
        background(0);
        stroke(255);
        for(int x=0;x<500;x++)
        {
            if(random(0,100) < 10)
            { 	  
                point(x,100);
            } 
        }
    }
```


​	Esse código faz o mesmo que o código da linha anterior, porém cada vez que ele roda, ele gera um número aleatório entre 0 e 100 e testa se ele é menor do que 10 (10% de chance). Quando ele é menor do que 10, um a função point é chamada e um ponto é desenhado:

![img](https://lh5.googleusercontent.com/FlfL6tL6evFpXM1V5JKZPkgKSKDAeYMRwep3ghK7ATAmHLmXhJRu-viQ7wUuGg7Kv_riZdklTNjsdfuWEteAHzZbn9IFzmltt3Co9f2cgNxqMiKuS9-WKcp26A6MIfuUTELS-ujV)

​	Ficou muito legal e interessante! Agora já temos uma linha de estrelas! Basta desenhar essa linha várias vezes na direção y! Vamos fazer isso com outro loop. Podemos pegar o nosso loop atual e colocar dentro de outro, assim o cada vez que o loop de dentro desenha, ele desenha uma linha, e cada vez que o loop de fora roda uma vez ele desce o y em 1 pixel. 

Vamos fazer isso:

```java
void setup()
{ 
    size(500, 500);
    background(0);
    stroke(255);
    for(int y=0;y<500;y++)
    {	
        for(int x=0;x<500;x++)
        { 
            if(random(0,100) < 10)
            {  		
                point(x,y); 	
            }	
        } 
    }
}
```


​	Vemos agora que temos um loop de fora, que possui a variável y e que faz ela ir de 0 até 500 (tamanho vertical da nossa janela), e um loop de dentro que faz a mesma coisa com a variável x (mas no tamanho horizontal da janela, que por sorte é igual). O loop de dentro, desenha o ponto 500 vezes, movendo o x 1 por 1 e sempre começando do 0. Quando ele acaba, o loop de fora incrementa o y em 1, e roda o loop de dentro novamente, até que o y chegue em 500. Assim, uma linha será desenhada em cada pixel da janela, partindo do topo na esquerda e terminando no fundo à direita. 

Vamos ver o resultado:

![img](https://lh4.googleusercontent.com/HORWT-p2rD3XBJD52V6BxZM7DOkeUQxNcUCdAOYeQfteHYynEpPtVz9nQF0PPTmDSjKaxy7FaA2uMKDCBzOfp2mPNXoaWH0t5riCzmlXQHplTL4UgBUDtvk07VpFqAK77K6CtlrN)

​	Uau! Um céu estrelado!! Muito legal! Conseguimos! Agora, não pare por aqui, programação é onde temos total controle dos nossos universos e devemos brincar e explorar as possibilidades. Agora que temos um código que desenha o céu, podemos mexer nas variáveis e brincar com os valores para ter resultados diferentes. Um exemplo é mexer na chance do nosso if de decisão. Mudando a chance para um valor maior como 20, aumenta o número de estrelas, e para um menor, diminui.

​	Além disso, podemos usar o comando stroke que aprendemos antes, e usar o random, para criar cores aleatórias cada vez que vamos desenhar um ponto:

```java
void setup()
{ 
    size(500, 500);
    background(0);
    for(int y=0;y<500;y++)
    {	
        for(int x=0;x<500;x++)
        { 	
            if(random(0,100) < 0.4)
            {  	
                int verdeverm = (int)random(150, 250); 
                stroke(verdeverm, verdeverm, random(200, 255));
                point(x,y); 
            }	
        } 
    }
}
```


![img](https://lh4.googleusercontent.com/HW1uPxVY1ksJvX5JYcLD93L4PNoK6ezKej1WwW-wvcMe-zcc7pGKGKhRXbTWxIhN08Vr6xlGlyN5Jm0VOb7HhFoOTYFkHfAWGCIUYHMqUCSmbzLpbfGgG9j15MrycRVgjMCgt4Lr)

​	Muito legal! E se ao invés de usar a função point, utilizássemos uma função nossa que desenha triângulos? Ou se trocássemos point pela função ellipse que desenha círculos e elipses?

```java
void setup()
{ 
    size(500, 500);
    background(0);
    for(int y=0;y<500;y++)
    {	
        for(int x=0;x<500;x++)
        { 	
            if(random(0,100) < 0.4)
            {  
                float tamanho = random(20,40);
                stroke(random(0, 255), random(0, 255), random(0, 255));
                ellipse(x,y, tamanho, tamanho);
            }	
        } 
    }
}
```


As possibilidades são ilimitadas! Brinque e divirta-se! Foi incrível poder trocar esse conhecimento com você! Um grande abraço e happy coding!