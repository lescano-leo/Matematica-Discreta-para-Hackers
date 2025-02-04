---
layout: post
title: "Capítulo 8 Estruturas Algébricas"
subtitle: "Matemática Discreta para Hackers"
author:  Mellean
tags:   python
category:  python
visualworkflow: false
---

<!-- Start Writing Below in Markdown -->

Capítulo 8:  Estruturas Algébricas
=====

## Semi-grupos

Quer a adição quer a multiplicação em $\mathbb{N}$, são operações que a cada par de números fazem corresponder um número natural. Diz-se, por tal facto, que a adição e a multiplicação são operações internas ou leis de composição interna em $\mathbb{N}$.

### Lei de composição interna

A operação $\oplus$ é uma lei de composição interna ou operador binário no conjunto $A$, se e só se faz corresponder a cada par ordenado $(a,b)$ em $A\times A$, um único elemento pertencente a $A$,
$$
\oplus:A\times A \rightarrow A
$$

Assim, não estamos em presença de uma operação interna sempre que para dois elementos dados, o resultado da operação não pertença ao mesmo conjunto.

### Definição:
Se $\oplus$ é uma operação interna em $A$, diz-se que $A$ é fechado relativamente a $A$.

São as leis de composição interna que conferem aos conjuntos o que habitualmente chamamos de estruturas. Assim podemos desde já definir a mais simples das estruturas, o grupóide.

### Definição:
Um conjunto $A$ diz-se um **grupóide** relativamente à operação $\oplus$, ou que a estrutura $(A,\oplus)$ define um grupóide, se e só se $\oplus$ é uma lei de composição interna em $A$.

### Exemplos:
$$
(\mathbb{Z},+), (\mathbb{Z},-),\text{ e }(\mathbb{R},\times)
$$
são exemplos de grupóides. $(\mathbb{Z},+)$ é grupóide porque a adição está definida para números inteiros e a soma de dois inteiros é um inteiro. De forma idêntica,  $(\mathbb{Z},-)$ é um grupóide já que a diferença está definida para todo o par de inteiros, e o resultado é um único inteiro. $(\mathbb{R},\times)$ é um grupóide porque o produto está definido para todo o par de reais e o resultado é um real.

### Exercícios:
Justifique que são grupóides:

1. $(\mathbb{N},+)$
+ $(\mathbb{R},\times)$
+ $(P(A),\cap)$, em que $P(A)$ é o conjunto das partes de $A$.


### Exercícios:

Justifique que não são grupóides:
1. $(\mathbb{N},-)$
+ $(\mathbb{R},:)$, onde $:$ é a operação de divisão de reais
+ $(B,\oplus)$, em que $B=\{0,1\}$ e a operação $\oplus$ está definida pela tabela

$\oplus$ | 0 | 1 
---------|---|---
**0** | 0 | 1 
**1** | 1 | 2 



Numa estrutura $(A,\oplus)$ diz-se que a operação $\oplus$ é **associativa** se e só se
$$
\forall a,b,c\in A:\;(a\oplus b)\oplus c = a\oplus (b\oplus c).
$$
E diz-se que é **comutativo** se e só se
$$
\forall a,b\in A:\;a\oplus b = b\oplus a.
$$
Recorde que a adição quer a multiplicação são operações associativas e comutativas em $\mathbb{N}$.

### Exemplo:
Em $\mathbb{Z}$ defina-se a operação $\oplus$ por
$$
a\oplus b =3a-ab.
$$
Calculemos por exemplo,
$$
(1\oplus 2)\oplus3=(3-2)\oplus 3=1\oplus3=3-3=0
$$
e, em seguida
$$
1\oplus(2\oplus 3)=1\oplus(6-6)=1\oplus0=3-0=3.
$$
Assim, $1,2,3\in \mathbb{Z}$, e $(1\oplus 2)\oplus3\neq1\oplus(2\oplus 3)$.

Então, a operação $\oplus$ não é associativa, pois,
$$
\exists a,b,c\in \mathbb{Z}:\;(a\oplus b)\oplus c\neq a\oplus(b\oplus c).
$$

Calculando agora
$$
1\oplus 2 = 3-2=1
$$
e
$$
2\oplus 1 =6-2 =4.
$$
Então
$$
\exists a,b\in \mathbb{Z}:\;a\oplus b\neq b\oplus a
$$
e a operação $\oplus$ também não é comutativa.

### Exemplo:
Em $A=\{1,2,3\}$, defina-se agora o operador interno $\oplus$ pela tabela

$\oplus$ | 1 | 2 | 3
---------|---|---|---
**1** | 2 | 1 | 3
**2** | 1 | 3 | 1
**3** | 3 | 1 | 1

Para averiguar se a operação $\oplus$ é associativa temos de verificar se, para todos os elementos de $A$, se verifica
$
(a\oplus b)\oplus c = a\oplus (b\oplus c).
$
Temos de examinar 27 possibilidades. No entanto, se se encontrar um termo em que não se verifique, podemos logo concluir que $\oplus$ não é associativa. Por exemplo:
$
(1\oplus 2)\oplus 3 = 1\oplus 3 = 3
$
e
$
1\oplus (2\oplus 3 )= 1\oplus 1 = 2.
$
Logo, $\oplus$ não é associativa.

Para investigar se a operação é comutativa basta ver se existe simetria em relação à diagonal principal da tabela. Neste caso existe simetria, logo a operação $\oplus$ é comutativa.

Se num conjunto $A$, está definida uma operação binária associativa, diz-se que $(E,\oplus)$ é um semi-grupo.


### Definição: Semi-grupo
Seja $A$ um conjunto e $\oplus$  uma operação. $(A,\oplus)$ é um **semi-grupo** se $\oplus$ é uma lei de composição interna em $A$ e $\oplus$ é associativa. Caso num semi-grupo o operador seja comutativo, é usual designá-lo de **semi-grupo comutativo** ou **semi-grupo abeliano**.

### Exemplos:
As estruturas algébricas
$$
(\mathbb{N},+), (\mathbb{N},\times),\text{ e }(P(A),\cap)
$$
são **semi-grupos**.

No semi-grupo comutativo $(\mathbb{Z},+)$, o número 0 tem a seguinte propriedade:
$$
\forall a\in\mathbb{Z}:\; a+0=0+a=a.
$$
Por esta razão se diz que zero é o elemento neutro para a adição em $\mathbb{Z}$.

### Definição:
No semi-grupo $(A,\oplus)$ diz-se que $e$ é **elemento neutro** para a operação $\oplus$, se e só se
$$
\forall a\in A:\; a+e=e+a=a.
$$


Com base nesta definição podemos mostrar que:

### Teorema:
Se o semi-grupo $(A,\oplus)$ tem elemento neutro, este é único.

### Exemplo:
No semi-grupo $(\{0,1,2\},\oplus)$, a operação $\oplus$ está definida pela tabela:

$\oplus$ | 0 | 1 | 2 
---------|---|---|---
**0** | 2 | 0 | 1 
**1** | 0 | 1 | 2 
**2** | 1 | 2 | 0 

O elemento neutro será o elemento a que corresponde uma linha e uma coluna iguais e pela mesma ordem dos elementos de suporte $A$. Logo o elemento neutro é 1.

### Exercício:
Verifique que $\emptyset$ (conjunto vazio) é elemento neutro do semi-grupo $(P(A),\cup)$, que tem por suporte o conjunto das partes de $A$.

### Exercício:
Qual é o elemento neutro do semi-grupo $(P(A),\cap)$? Justifique.

### Exercício:
O semi-grupo $(\mathbb{Z},-)$ tem elemento neutro? Justifique.

### Exercício:
Indique os elementos neutros, se existem, das operações definidas pelas tabelas:

$\oplus$ | 1 | 2 | 3 
---------|---|---|---
**1** | 2 | 3 | 1 
**2** | 3 | 1 | 2 
**3** | 1 | 2 | 3 
         

$\oplus$ | 1 | 2 | 3 | 4
---------|---|---|---|---
**1** | 2 | 3 | 1 | 4 
**2** | 4 | 1 | 2 | 3 
**3** | 1 | 2 | 3 | 4 
**4** | 1 | 4 | 4 | 2 

### Definição: Monóide
A estrutura $(A,\oplus,e)$ diz-se um **monóide** se

1. $(A,\oplus)$ é um semi-grupo e
+ $e$ é elemento neutro da operação $\oplus$.


### Exercício:
1. $(\mathbb{N},+)$ não tem elemento neutro.
+ $(\mathbb{Z},+,0)$ é um monóide porque $(\mathbb{Z},+)$ é um semi-grupo e a adição tem por elemento neutro 0.
+ $(\mathbb{Z},\times,1)$ é um monóide porque $(\mathbb{Z},\times)$ é um semi-grupo e a multiplicação tem por elemento neutro 1.

## Alfabetos e Linguagens


### Definição: Alfabeto
Um alfabeto é um conjunto finito e não-vazio de símbolos.

Em geral usamos a letra grega $\Sigma$ (Sigma) para designar um alfabeto. Por exemplo consideramos $\Sigma=\{0,1\}$ como sendo o alfabeto binário.

### Definição: Palavra
Uma palavra sobre um **alfabeto** $Sigma$ é uma sequência finita de símbolos de $\Sigma$. O comprimento de uma palavra $w$ em $\Sigma$ é o número de ocorrências de símbolos em $w$, denotado por $|w|$. Em particular a **palavra vazia**, denotada de $\lambda$ (lambda), é a palavra com zero ocorrências de símbolos.

Por exemplo, **11011011** é uma palavra, de comprimento 8, sobre o alfabeto binário $\Sigma=\{0,1\}$ e da mesma forma **python** é uma palavra, de comprimento 6, no alfabeto $\Sigma=\{h,n,o,p,t,y\}$.

O conjunto das palavras de comprimento $k$ sobre $\Sigma$ é dado por
$$
\Sigma^k=\{a_1\ldots a_k:\;a_i\in\Sigma,\text{ para }i=1,\ldots,n\}
$$
Em particular $\Sigma^0=\{\lambda\}$. Por exemplo, se tomarmos $\Sigma=\{0,1\}$, tem-se $\Sigma^0=\{\lambda\}$, $\Sigma^1=\{0,1\}$,$\Sigma^2=\{00,10,01,11\}$,
$\Sigma^3=\{000,010,001,011,100,110,101,111\}$, $\ldots$

Como uma palavra não tem comprimento fixo, o conjunto das palavras sobre $\Sigma$, denotado por $\Sigma^\ast$, é o conjunto definido por:
$$
\Sigma^\ast=\bigcup_{k=0}^{\infty}\Sigma^k=\Sigma^0\cup\Sigma^1\cup\Sigma^2\cup\ldots
$$

Em geral recorremos à notação $w^k$, para $k\in \mathbb{N}$ e $w\in \Sigma^\ast$, para designar a palavra
$$
w^k=\underbrace{ww\ldots w}_{k \text{ vezes}}
$$
Por exemplo, $0^3=000$ e $(10)^3=101010$. Onde se assume que $w^0=\lambda$, por exemplo, $(101)^0=\lambda$.

### Definição: Concatenação
Dadas duas palavras $w_1=a_1a_2\ldots a_n$ e $w_2=b_1b_2\ldots b_m$ sobre $\Sigma$, definimos a sua concatenação $w_1\cdot w_2$ (também representada simplesmente por $w_1w_2$) como sendo a palavra
$
a_1a_2\ldots a_nb_1b_2\ldots b_m
$
onde os símbolos de $w_2$ aparecem após os símbolos de $w_1$ e pela mesma ordem.

Para as palavras sobre o alfabeto binário $\Sigma=\{0,1\}$, temos por exemplo, para $w_1=100101$ e $w_2=0001001$, que $w_1w_2=1001010001001$ e $w_2w_1=0001001100101$ (note que a operação não é comutativa). Neste caso $w_1\lambda=100101$ e $\lambda w_1=100101$. Genericamente para toda a palavra $w_1,w_2\in\Sigma^\ast$, temos
1. $|w_1w_2|=|w_1|+|w_2|$, e
+ $\lambda w=w\lambda=\lambda$.

Neste sentido a palavra vazia é o elemento neuro para a concatenação de palavras. Garantido isto que, quando algebrizamos o conjunto das palavras com a concatenação a estrutura algébrica
$
(\Sigma^\ast,\cdot,\lambda),
$
define um monóide, já que para todo o alfabeto $\Sigma$ e qualquer uma das suas palavras $w_1,w_2,w_3\in \Sigma^\ast$, é válida a associatividade:
$
w_1(w_2w_3)=(w_1w_2)w_3.
$

### Definição: Linguagem
Uma linguagem sobre um alfabeto $\Sigma$ é um subconjunto $L$ de $\Sigma^\ast$.


Por exemplo, $L=\{1,11,111\}$ é uma linguagem sobre $\{0,1\}^\ast$, são exemplos de linguagens no mesmo alfabeto $$\emptyset\text{ ou }\{w\in \{0,1\}^\ast:\; \text{ que tem o mesmo número de 1's e 0's} \}.$$

### Exemplos:
São exemplos de linguagens no alfabeto $\Sigma=\{a,b,c\}$:
1. $\emptyset$ o conjunto vazio
+ $L_1=\{a^n:\;n\geq 0\}$
+ $L_2=\{a^n:\;n> 0\}$
+ $L_3=\{a,b,c\}$
+ $L_4=\{aab,cab\}$

### Definição:
Sejam $L_1$ e $L_2$ linguagens sobre o alfabeto $\Sigma$. Definimos as seguintes operações cujo resultado são também linguagens sobre $\Sigma$.
1. **União**: $L_1\cup L_2=\{w\in\Sigma^\ast:\;w\in L_1 \vee w\in L_2\}$
+ **Concatenação**: $L_1\cdot L_2=\{w_1w_2\in\Sigma^\ast:\;w_1\in L_1 \wedge w_2\in L_2\}$
+ **Operador potência**: $L_1^k=\{w_1w_2\ldots w_k\in\Sigma^\ast:\;w_i\in L_1\}$
+ **Operador de fecho**: $L_1^\ast=\{w_1w_2\ldots w_k\in\Sigma^\ast:\;k\geq 0 \wedge w_i\in L_1\}$

Note que, $L_1^\ast$ é o conjunto de todas as palavras que podem ser obtidas concatenando palavras de $L_1$, tantas vezes quanto se queira. Por $L_1^+$ denotamos o conjunto das palavras que podem ser obtidas concatenando palavras de $L_1$, excepto a palavra vazia.
$
L_1^+=\{w_1w_2\ldots w_k\in\Sigma^\ast:\;k> 0 \wedge w_i\in L_1\}
$

Por exemplo, para $L_1=\{10,11\}$ e $L_2=\{0,111\}$,tem-se:

1. $L_1\cup L_2=\{0,10,11,111\}$
+ $L_1\cdot L_2=\{100,10111,110,11111\}$
+ $L_1^0=\{\lambda\}$
+ $L_1^1=\{10,11\}$
+ $L_1^2=\{1010,1011,1110,1111\}$
+ $L_1^\ast=\{\lambda,10,11,1011,1110,1111,101010,101011,\ldots\}$
+ $L_1^+=\{10,11,1011,1110,1111,101010,101011,\ldots\}$

(concatenando zero palavras de $L_1$, obtém-se a palavra vazia. Concatenando uma palavra de $L_1$, obtém-se as palavras 10 e 11. Concatenando-se duas palavras de  $L_1$, obtém-se 1010, 1011, 1110 e 1111. Concatenando três palavras de $L_1$, obtém-se $\ldots$).

Se o conjunto $\Sigma$ estiver parcialmente ordenado, pode definir-se a ordem lexicográfica em $\Sigma^\ast$ como sendo a mesma que é utilizada num dicionário, excepto que palavras mais curtas precedem palavras mais longas. Por exemplo, para a ordem usual $0\leq 1$ em $\{0,1\}$, é dada por:
$
\lambda\leq0\leq1\leq00\leq01\leq10\leq11\leq000\leq\cdots
$
Formalmente diz-se que $u\leq v$, para $u,v\in \Sigma^\ast$, se:
1. $|u|<|v|$, ou
+ se $|u|=|v|$, então existe $k$ tal que $u_i=v_i$, para $i=1,\ldots,k-1$ e $u_k<v_k$.

## Expressões regulares

As expressões regulares são uma forma de caracterizar a sintaxe de linguagens.
Com base num alfabeto, definimos indutivamente o que se entende por uma expressão regular.

### Definição: Expressão regular
Uma expressão regular sobre um alfabeto $\Sigma$ é uma expressão à qual associamos uma linguagem sobre $\Sigma$. Uma expressão regular pode somente ser obtida pelas seguintes regras:
1. Se $a\in \Sigma$, então $a$ é uma expressão regular associada à linguagem $\{a\}$,
+ $\lambda$ e $\emptyset$ são expressões regulares associadas às linguagens $\{\lambda\}$ e $\emptyset$, respectivamente,
+ Se $r_1$ e $r_2$ são expressões regulares associadas a linguagens $L_1$ e $L_2$, respectivamente, então também são expressões regulares,
    1. $(r_1|r_2)$ associada à linguagem $L_1\cup L_2$,
    + $(r_1\cdot r_2)$ associada à linguagem $L_1\cdot L_2$,
    + $(r_1^\ast)$ associada à linguagem $L_1^*$, e
    + $(r_1^+)$ associada à linguagem $L_1^+$.
+ Nada mais é uma expressão regular.

Para simplificar a notação, vamos utilizar as seguintes convenções quando escrevemos uma expressão regular:
1. sempre que estamos a concatenar duas expressões regulares, omitimos o símbolo $\cdot$;
+ os operadores de fecho ($^*$ e $^+$) tem precedência sobre os restantes operadores;
+ o operador de concatenação tem precedência sobre o operador de união.

Utilizando estas precedências, podemos eliminar muitos dos parêntesis. Por exemplo, para $\Sigma=\{0,1\}$, a expressão:
$
001^\ast0|01
$
corresponde à expressão regular
$
((0\cdot0\cdot(1^\ast)\cdot0)|(0\cdot1))
$
são exemplo de palavras associadas a esta expressão regular por exemplo,
$
01,000,0010\text{ e }00110.
$
A linguagem associada a $001^\ast0|01$ é dada por
$
\{w\in\{0,1\}^\ast:\;w=01\vee w=001^k0\text{ para algum }k\in \mathbb{N}\}.
$


### Definição: Linguagens Regulares
As linguagens associadas a expressões regulares dizem-se linguagens regulares.

### Exemplos:
São exemplos de linguagens regulares no alfabeto $\Sigma=\{a,b,c\}$:
1. $L_1=\{a^n:\;n\geq 0\}$ associada à expressão regular $a^\ast$;
+ $L_2=\{a^n:\;n> 0\}$ associada à expressão regular $a^+$;
+ $L_3=\{a,b,c\}$ associada à expressão regular $a|b|c$;
+ $L_4=\{aab,cab\}$ associada à expressão regular $aab|cab$;
+ $L_5=\{a^nb^mc^p:\;n> 0,m\geq 0,p> 0,\}$ associada à expressão regular $a^+b^\ast c^+$;
+ $L_6=\{ab^mac^pa:\;n> 0,m\geq 0,p> 0,\}$ associada à expressão regular $ab^\ast a c^+a$;

### Exercício:
Determine exemplos de palavras que satisfazem a expressão regular:
$
(a|b|c)^+d^\ast(a|c)(a|d)(a|b)
$


Notemos que nem todas as linguagens podem ser descritas por expressões regulares. Exemplo disso são as linguagens
1. $L=\{0^k1^k:\;k\geq 0\}$, ou
+ $L=\{0^k1^k0^k:\;k\geq 0\}$.

Nestes casos, a igualdade entre sequências de 0's e 1's, inviabiliza a sua representação através de uma expressão regular.

### Exercício:
Para cada uma das seguintes expressões regulares, indique duas palavras que pertençam à linguagem que lhe está associada e duas palavras que não pertençam a esta linguagem. O alfabeto é $\Sigma=\{a,b\}$.
1. $a^\ast b^\ast$
+ $a^+ b^\ast a^\ast$
+ $a(ba)^\ast b$
+ $a(ba)^+ b^+$
+ $a^\ast|b^\ast$
+ $(aaa)^\ast$
+ $(a|b)^\ast a(a|b)^\ast b$
+ $aba|bab$
+ $(\lambda|a)b$
+ $(\lambda|a)b^+$
+ $(a|ba|bb)(a|b)^\ast$

### Exercício
Apresente um exemplo de uma palavra. de comprimento mínimo, pertencente a cada uma das linguagens associadas às expressões regulares do exercício anterior.

Sejam $r_1$, $r_2$ e $r_3$ expressões regulares. Então é válido afirmar:
1. $(r_1|r_2)|r_3=r_1|(r_2|r_3)$, a operação $|$ é associativa,
+ $r_1|r_2 = r_2|r_1$, a operação $|$ é comutativa,
+ $r_1|r_1 = r_1$, a operação $|$ é idempotente,
+ $(r_1\cdot r_2)\cdot r_3=r_1\cdot(r_2\cdot r_3)$, a concatenação é associativa,
+ $r_1\cdot \lambda = \lambda \cdot r_1 = r_1$, a palavra vazia é elemento neutro para a concatenação,
+ $r_1\cdot(r_2|r_3)=r_1\cdot r_2|r_1\cdot r_3$, a concatenação é distributiva à esquerda relativamente à operação $|$,
+ $(r_1|r_2)\cdot r_3=r_1\cdot r_3|r_2\cdot r_3$, a concatenação é distributiva à direita relativamente à operação $|$,
+ $r_1^+=r_1\cdot r_1^\ast=r_1^\ast\cdot r_1$
+ $r_1^\ast=\lambda | a^+$
+ $(r_1|\lambda)^+=(r_1|\lambda)^\ast=r_1^\ast$

## Gramáticas

Por gramáticas entende-se um mecanismo que permite definir indutivamene as palavras duma linguagem.

### Definição: Gramática
Uma gramática é um tuplo
$$
G=(\Sigma,V,P,S)
$$
onde:
1. $\Sigma$ é um alfabeto, cujos elementos designamos de conjunto de símbolos terminais;
+ $V$ é um conjunto finito de símbolos não-terminais ou variáveis, diferentes de $\Sigma$, tal que $\Sigma\cap V= \emptyset$;
+ $P$ é um conjunto finito de regras do tipo
$$
w_1\rightarrow w_2,
$$
designadas de regras de produção, onde a primeira componente $w_1$ é uma palavra de $(\Sigma\cup V)^\ast$, e a segunda componente $w_2$ é uma palavra de $(\Sigma\cup V)^\ast$;
+ $S$ é um símbolo não terminal, elemento de $V$, denominado símbolo inicial.

Os símbolos não terminais em $\Sigma$ são aqueles que aparecem nas palavras geradas pela gramática. Os símbolos de $V$ são usados como variáveis auxiliares na geração de palavras. As produções definem as condições de geração de palavras. A aplicação de uma produção é denominada derivação. Uma regra $w_1\rightarrow w_2$ indica que $w_1$ pode ser substituída por $w_2$ sempre que ocorre $w_1$. Enquanto houver símbolos não-terminais numa palavra, o processo de derivação deve continuar. O símbolo inicial é o símbolo usado para iniciar os processos de derivação. O processo termina quando deixar de existir símbolos não-terminais.

Vamos usar as produções para a derivação de novas palavras à custa de palavras dadas. Assim substitui-se a parte igual ao lado esquerdo da regra pela do lado direito da mesma.

### Exemplo:
Seja $G=(\{a,b\},\{S,A,B\},P,S)$ uma gramática onde o conjunto de regras de produção $P$ é dado por:
1. $S\rightarrow AB$
+ $A\rightarrow a$
+ $B\rightarrow b$

Esta gramática permite gerar a linguagem com uma única palavra:
$$
L=\{ab\}
$$
que aparece associada às únicas  duas cadeias de derivações:
$$
S\Rightarrow_{1} AB\Rightarrow_{2} aB\Rightarrow_{3} ab
$$
$$
S\Rightarrow_{1} AB\Rightarrow_{3} Ab\Rightarrow_{2} ab
$$

Onde por $\Rightarrow_{1}$ denotamos a aplicação da primeira produção, por $\Rightarrow_{2}$ e $\Rightarrow_{3}$ referenciamos a aplicação das produções 2 e 3. Neste caso chamamos a $S$, $AB$, $Ab$ e $aB$ palavras não terminais e a $ab$ de palavra terminal.

### Exemplo
Seja $G=(\{a,b,c\},\{A,B\},P,A)$ uma gramática onde o conjunto de regras de produção $P$ é dado por:
1. $A\rightarrow aB$
+ $B\rightarrow bB$
+ $B\rightarrow c$
}
Neste caso a gramática tem por símbolo inicial $A$, e é uma sequência de derivações válidas:
$$
A\Rightarrow_{1} aB\Rightarrow_{2} abB\Rightarrow_{2} abbB \Rightarrow_{3} abbc
$$
Se aplicarmos a primeira produção $n$ vezes, a segunda e uma vez a terceira, tem-se
$$
A\Rightarrow_{1} aB\Rightarrow_{2} abB\Rightarrow_{2} abbB \Rightarrow_{2}\cdots \Rightarrow_{2} ab^nB\Rightarrow_{3}ab^nc
$$
Podemos assim dizer que a linguagem gerada contém todas as palavras do tipo $ab^nc$, onde $n\geq 0$. A linguagem gerada pela gramática está assim associada à expressão regular $ab^\ast c$.

### Exemplo:
Seja $G=(\{a,b\},\{S\},P,S)$ uma gramática onde o conjunto de regras de produção $P$ é dado por:
1. $S\rightarrow aSb$
+ $S\rightarrow ab$

Assim $S$ é símbolo inicial e a única variável, $a$ e $b$ são símbolos terminais.

É nosso objectivo determinar a linguagem gerada pela gramática $G$, $L(G)$.
1. Ao aplicarmos a primeira produção $(n-1)$-vezes, seguida por uma aplicação da segunda produção tem-se
$$
S\Rightarrow_{1} aSb\Rightarrow_{1} aaSbb\Rightarrow_{1} \cdots \Rightarrow_{1} a^{n-1}Sb^{n-1}\Rightarrow_{1}a^nb^n.
$$
+ Reparemos agora que sempre que se faz uso da primeira produção, o número de $S$'s se mantém igual a 1. Na utilização da segunda produção o número de $S$'s decresce de uma unidade. Logo a utilização da segunda produção elimina os $S$'s da sequência. Como ambas as produções têm um único $S$ à esquerda, a ordem pela qual as produções podem ser aplicadas é $S\rightarrow aSb$ um certo número de vezes, seguido de uma aplicação de $S\rightarrow ab$.

Logo $L(G)=\{a^nb^n:\;n\geq 1\}$.

Neste exemplo, foi simples determinar as palavras que se podem derivar de $S$. Em geral pode ser difícil determinar a linguagem gerada por uma gramática dada.

### Exemplo:
Consideremos a gramática $G=(\{a,b,c\},\{S,A,B\},P,S)$ onde o conjunto de regras de produção $P$ é dado por:
1. $S\rightarrow ABc$
+ $A\rightarrow aB$
+ $A\rightarrow Bc$
+ $B\rightarrow aAc$
+ $B\rightarrow bc$

A seguinte derivação em $G$
$$
S\Rightarrow_{1} ABc\Rightarrow_{4} AaAcc\Rightarrow_{3} BcaAcc\Rightarrow_{5}bccaAcc\Rightarrow_{3}bccaBccc\Rightarrow_{5}bccabcccc
$$
pode ser representada pela seguinte **árvore de derivação**.

<img src="derivationTree.gif" width = 200/>

### Exercício:
Considere uma gramática, de símbolo inicial $S$, com as seguintes produções:
1. $S\rightarrow aAb$
+ $A\rightarrow aA$
+ $A\rightarrow bA$
+ $A\rightarrow \lambda$
Construa árvores de derivação das palavras terminais $abab$ e $aabb$.

### Definição:
Dada uma gramática $G=(\Sigma,V,P,S)$ e duas palavras $w_0,w_1\in (\Sigma\cup V)^\ast$, diz-se que $w_1$ deriva de $w_0$ por uma derivação, se existe uma produção $p\in P$ tal que, quando aplicada a $w_0$, a transforma em $w_1$, neste caso escrevemos
$$
w_0\Rightarrow_p w_1.
$$
Caso exista uma sequência de produções $p_1,p_2,\ldots,p_n$ tal que
$$
w_0\Rightarrow_{p_1} w_1\Rightarrow_{p_2} w_2\Rightarrow_{p_3}\ldots\Rightarrow_{p_n} w_n
$$
escrevemos
$$
w_0\Rightarrow^* w_n
$$

### Exemplo:
Assim do exemplo anterior escrevemos
$$
 S\Rightarrow^\ast bccabcccc,
$$
 para indicar que do símbolo $S$ se pode derivar $bccabcccc$, mediante a aplicação de uma sequência de produções.

### Definição:
A linguagem $L(G)$ gerada pela gramática $G=(\Sigma,V,P,S)$ contém todas as palavras terminais geradas a partir do símbolo inicial $S$,
$$
L(G)=\{w\in\Sigma^\ast:\;S\Rightarrow^\ast w\}.
$$

Definimos uma linguagem regular, como uma linguagem que pode ser descrita por uma expressão regular. Outra forma de caracterizar a sintaxe de linguagens regulares é através de gramáticas regulares.


### Definição: [Gramáticas regulares]
Uma gramática $G=(\Sigma,V,P,S)$ diz-se regular (mais precisamente regular à direita) quanto todas as produções são da forma:
1. $A\rightarrow w$ ou
+ $A\rightarrow wB$,

em que $A,B\in V$ (símbolos não terminais) e $w\in \Sigma^\ast$ (uma palavra terminal). Isto é, todas as produções têm do lado direito, no máximo um símbolo não terminal (e este é o último símbolo do lado direito).

### Exercício:
Determine as produções em $P$ de uma gramática regular (à direita) $G=(\Sigma,V,P,S)$, onde $\Sigma=\{a,b,c\}$ e $V=\{S,A,B,C,D\}$ tais que a linguagem gerada $L(G)$ seja descrita pelas expressões regulares abaixo:
1. $a^\ast b^\ast$
+ $(a|b)^\ast(a^\ast|c)$
+ $aba^+c$
+ $ab^\ast$
+ $ab^\ast aba^+c$
+ $(ab^*)^*a$

Genericamente, pode mostrar-se que:

### Teorema:
Qualquer linguagem regular é gerada por uma gramática regular (no nosso caso, uma gramática regular à direita).


```python

```
