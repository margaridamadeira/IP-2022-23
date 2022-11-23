# Lab6


Note bem:

+ Cotação deste guião: 2 pontos
+ Submeta cada uma das tarefas no problema correspondente do concurso IP_L6.
+ Prazo limite de submissão: 23h59m de 29 de novembro
+ Prazo limite de validação das submissões aceites: 5 de dezembro, horário de atendimento de segunda-feira (9h às 11h).

## Objetivos de aprendizagem

Com este guião, exercitaremos:

1. o desenvolvimento de uma solução completa
1. o uso de string e listas 
1. a técnica *count-while* 


## Pluviosidade


```{figure} ./figures/chuva-pexels-pixabay-459451.jpg
---
height: 300px
name: chuva
---
[Chuva](https://www.pexels.com/photo/rain-drops-459451/), de Pixabay em [Pexels](https://www.pexels.com/), CC0.
```


Temos tido alguma chuva ultimamente, mas pouco chove no Algarve. O [Sistema Nacional de Informação de Recursos Hídricos](https://snirh.apambiente.pt/) disponibiliza, entre outros dados, os valores diários da precipitação.

Vamos querer alguns valores estatísticos pelo que, para testar o programa, fomos buscar os valores de precipitação diária de uma estação meteorológica desde o início do ano. Retirámos a informação que não precisávamos e ficámos apenas com os valores da precipitação: em cada dia, numa linha, um valor real. 

Queremos saber qual o valor da precipitação acumulada, qual o maior valor de precipitação diária e em quantos dias choveu.

### Tarefa A

Prepare um programa em Python que leia da consola, até ao fim do input, uma sequência de números e apresente a soma dos valores lidos, o maior valor e o número de dias em que choveu (ou seja, o valor da precipitação é maior que zero).

O programa lerá tantas linhas quantos os dias contidos no registo. Em cada linha haverá um número (inteiro ou real) correspondente à precipitação num dia. Quando não choveu, o valor da precipitação é 0 (zero).
Ao terminar a leitura, o programa escreverá na mesma linha três valores separados por espaços. Os primeiros dois valores, em notação científica, correspondem à soma dos valores lidos e ao maior valor registado; o terceiro valor é um número inteiro que indica quantos dias choveu. 

*Requisito técnico*: deve ler os valores para uma lista.

**Casos de teste**

**Input 1**

```
0.1
0.6
1.8
2.7
1.5
6.4
0
0
```

**Output 1**

```
1.310000e+01 6.400000e+00 6
```

**Input 2**

```
0
0
0
0
0
0
0.1
0
0
0
0
0
0
```

**Output 2**

```
1.000000e-01 1.000000e-01 1
```

**Input 3**

```
0
0
0
0
0
0
0.6
1.8
2.7
1.5
6.4
0
0
0.2
0.4
0.5
20.2
4.9
0.3
```

**Output 3**

```
3.950000e+01 2.020000e+01 11
```

Submeta na tarefa A.

<div style="page-break-after: always"></div>

## Temperatura


```{figure} ./figures/subida-temperatura.jpeg
---
height: 300px
name: Subida de temperatura
---
```
Porque a definição dos valores de referência no ar condicionado tem impacto no uso de energia passámos a recolher a temperatura de hora a hora.
Houve alturas em que se verificou uma sequência crescente, ou seja, um conjunto de medidas T em que $t_n < t_{n+1}$.
Para analisarmos a evolução das temperaturas, queremos identificar a maior amplitude das sequências crescentes de temperatura.

### Tarefa B

Dada uma série de medidas de temperatura, pretende-se identificar qual a maior amplitude das sequências crescentes de temperatura. 

O seu programa deve ler, da consola, uma única linha contendo números reais separados por espaços.

O programa deve apresentar um número real com 4 casas decimais que corresponde à maior amplitude das sequências crescentes.


#### Exemplo

**Input 1**

```
26.79 26.76 26.62 26.12 25.47 30.12 30.18 30.65 32.07 32.13 33.17 32.83 32.89 35.47 35.91 37.34 37.62 36.89
```

**Output 1**

```
7.7000
```

**Input 2**

```
0

```

**Output 2**

```
0.0000
```

**Input 3**

```
0.0 27.0
```

**Output 3**

```
27.0000
```

**Input 4**

```
27.0 0.0
```

**Output 4**

```
0.0000
```

**Input 5**

```
12 -5 -4 -3 -2 -1 22 27 0 5 6 7
```

**Output 5**

```
32.0000
```

**Input 6**

```
12 5 6 7 -5 -4 -3 -2 -1 22 27 0
```

**Output 6**

```
32.0000
```

Submeta na tarefa B.

<div style="page-break-after: always"></div>

## Química à toa

```{figure} ./figures/tp-ualg.jpeg
---
height: 300px
name: Tabela Periódica
---
[Exposição “Desafios da Tabela Periódica”, na Biblioteca da UAlg](https://ualg.pt/pt/content/exposicao-desafios-da-tabela-periodica-pode-ser-visitada-na-biblioteca-da-ualg)
```

Fonte: [Problema C do ToPAS 2016](https://eventos.fct.unl.pt/sites/default/files/topas-lx/files/problemas_topaslx_2016.pdf)

Quando o Rui estava a estudar Química, escrevendo fórmulas
de compostos no caderno (como $CaCO_3$ , $Na_2CO_3$ e $H_ 2SO_4$ ),
apareceu a irmã mais nova, que ficou fascinada com aquelas
sequências de letras e algarismos. O pior é que ela não se calava,
exigindo que ele lhe explicasse como dividia uma sequência
grande em pedacinhos. Desesperado, o Rui enunciou as regras:

* Cada sequência de letras que começa com uma letra
grande (a irmã não conhecia a palavra “maiúscula”) representa um elemento;

* Se houver algum número a seguir ao elemento, esse é o número de átomos do elemento;
se não houver, o número de átomos do elemento é 1.


Depois, exemplificou com a fórmula do carbonato de cálcio, $CaCO_3$ , que tem um átomo de
cálcio (Ca), um átomo de carbono (C) e três átomos de oxigénio (O).
A irmã ficou muito contente e queria aprender mais Química. Mas ele convenceu-a a praticar.
Para poder regressar ao estudo rapidamente, decidiu escrever “fórmulas químicas” à toa e
até inventou símbolos químicos com 1, 2, 3, 4 e 5 letras. Por exemplo, deu-lhe a fórmula
$Ai_{19}Xpto_5Uus$ (que tem tamanho 12) para decompor.

### Tarefa C

Escreva um programa que, dada uma fórmula química inventada pelo Rui e terminada por
“.”, apresenta os elementos que ocorrem na fórmula e o número de átomos de cada um.


**Input**

Uma linha com uma fórmula química (inventada pelo Rui) terminada por “.”. A fórmula é
uma sequência de $n$ letras e algarismos, que começa com uma letra maiúscula e que não tem o
algarismo zero imediatamente a seguir a uma letra, nem uma letra minúscula imediatamente
a seguir a um algarismo. Nenhum elemento tem mais de cinco letras, nem ocorre mais do que
uma vez na fórmula. O número de algarismos seguidos não excede $n − 1$.


**Output**

O output tem uma linha por cada elemento que ocorre na fórmula. Cada linha tem um
elemento, um espaço, o número de átomos desse elemento e uma mudança de linha. Os
elementos têm de aparecer pela ordem em que ocorrem na fórmula.


**Casos de teste**

**Input 1**

```
CaCO3.
```

**Output 1**

```
Ca 1
C 1
O 3
```

**Input 2**

```
Ai19Xpto5Uus.
```

**Output 2**

```
Ai 19
Xpto 5
Uus 1
```

Submeta na tarefa C.
