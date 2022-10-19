# Lab5

## Objetivos de aprendizagem

Com este guião, exercitaremos:

1. a leitura da consola, vários valores por linha e até ao fim dos dados
1. escrita formatada
1. a utilização de listas

## Enunciado

Submeta cada uma das tarefas no problema correspondente do concurso IP_L5.


### Tarefa A

Pretende-se a ordenação crescente de sequências de números. Não sabemos quantas sequências temos nem quantos elementos por sequência. Para cada linha lida, ordenamos os elementos e apresentamos a sequência ordenada.

Vamos então preparar um programa que receba da consola, até ao fim dos dados, linhas com sequências de inteiros e, para cada linha, apresente a sequência por ordem crescente, com cada elemento separado por um espaço. 

Porque queremos um programa "completo", começamos pelas linhas que indicam ao Python que deve começar pela função de teste, ou seja

```
test_ordem_crescente()
```

Em seguida, sabemos que precisaremos da função de  *test_ordem_crescente*, responsável pela leitura, da função *ordem_crescente* e de uma função para apresentação dos resultados, seja *mostra_sequência_separada_por_espaços*. 
Mantemos as funções vazias (*pass* para indicar que não há nada a fazer).


O esboço do nosso programa fica assim:

```
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

"""Resolução guiada
L4 - A
Programa que recebe da consola, até ao fim dos dados, 
linhas com sequências de inteiros e, 
para cada linha, apresenta a sequência por ordem crescente, 
com cada elemento separado por um espaço.

"""


def ordem_crescente():
    """Ordena uma sequência de números inteiros"""
    pass

def mostra_sequência_separada_por_espaços():
    """Apresenta os números inteiros separados por espaço"""
    pass

def test_ordem_crescente():
    """Lê várias linhas e, para cada linha lida, manda ordenar e mostrar."""
    pass  

test_ordem_crescente()
```

Usamos a abordagem apresentada para a {ref}`Leitura`.
Começamos por passar cada linha para uma lista e, para verificar, usamos uma primeira versão da função *mostra_sequência_separada_por_espaços*, que apresenta a lista ainda não formatada.

Usamos também algo que nos ajuda quando as funções começam a ser muitas: identificamos os tipos de dados, para que fique claro como estamos a organizar as atividades do programa. E depois a ajuda em linha também apresenta essa informação. Isto é opcional e apenas indicativo, o Python não vai verificar se os argumentos usados na chamada da função são ou não do tipo sugerido.


O nosso programa ficaria então assim:

```
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

"""Resolução guiada
L4 - A
Programa que recebe da consola, até ao fim dos dados, 
linhas com sequências de inteiros e, 
para cada linha, apresenta a sequência por ordem crescente, 
com cada elemento separado por um espaço.

"""
import sys

def ordem_crescente(a: list) -> list:
    """Ordena uma sequência de números inteiros"""
    pass

def mostra_sequência_separada_por_espaços(a: list) -> None:
    """
    Função que apresenta uma lista, cada elemento separado por espaço.
    """
    print(a)

def test_ordem_crescente():
    """Lê várias linhas e, para cada linha lida, manda ordenar e mostrar."""
    while True:
        try:
            linha = input().split()
        except (EOFError, KeyboardInterrupt):
            sys.exit(0)
        if linha:
            mostra_sequência_separada_por_espaços(linha)
        else:
            sys.exit(0)

    

test_ordem_crescente()

```


Com o nosso código num ficheiro chamado *ordenar_lista.py*, experimentamos.

```
python ordenar_lista.py 
1 4 7 3 6 2
['1', '4', '7', '3', '6', '2']
```

O resultado ainda não é exatamente o que pretendíamos.

Em primeiro lugar, a lista devia ser de inteiros. Há que converter! Podemos conseguir isso alterando o bloco do *try* para

```
            linha = input().split()
            lista = [int(x) for x in linha]
```

e, claro, revendo as utilizações da lista *linha*.


Em segundo lugar, era pedido que entre cada dois elementos existisse um espaço.
Aliás, deve haver um espaço entre cada dois elementos, mas não pode haver um espaço antes do primeiro elemento nem um espaço depois do último.

A nossa função *mostra_sequência_separada_por_espaços* poderia ficar assim, criando a string de saída e depois apresentando-a.

```
def mostra_sequência_separada_por_espaços(a: list) -> None:
    """
    Função que apresenta uma lista, cada elemento separado por espaços.
    """
    resultado = ''
    for i in a: 
        if len(resultado) == 0:
            resultado = str(i)
        else:
            resultado = resultado + ' ' + str(i)
    print(resultado)
```

Experimentemos outra vez. Deveremos ver o que introduzimos.

Ora o que falta agora é a ordenação da lista. O Python tem essa função mas há que ter cuidado pois essa função altera a lista original. Complete agora a função *ordem_crescente* para a ordenação crescente dos elementos inteiros de uma lista, inclua a chamada na função *test_ordem_crescente* e teste.


#### Casos de teste 

**Input 1**

```
2 9 1 8 6

```

**Output 1**

```
1 2 6 8 9
```

**Input 2**

```
1 4 7 3 6 2
34 27 39 6 2 100
5 -5 10 -10 -50 250


```

**Output 2**

```
1 2 3 4 6 7
2 6 27 34 39 100
-50 -10 -5 5 10 250
```

Submeta no problema A.
