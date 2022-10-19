# Lab4

Note bem:

+ Cotação deste guião: 2 pontos
+ Submeta cada uma das tarefas no problema correspondente do concurso IP_L4.
+ Prazo limite de submissão: 23h59m de 25 de outubro
+ Prazo limite de validação das submissões aceites: **31 de outubro**, horário de atendimento de segunda-feira (11h às 12h).

## Objetivos de aprendizagem

Com este guião, exercitaremos:

1. a leitura da consola, vários valores por linha e até ao fim dos dados
1. escrita formatada


## Enunciado

Submeta cada uma das tarefas no problema correspondente do concurso IP_L4.


### Tarefa A

Num centro de atendimento ao cliente a duração das diferentes chamadas é cronometrada de forma automática, em segundos. Para saber se a capacidade de atendimento de cada turno está prestes a esgotar-se, queremos saber a duração total de cada turno em horas, minutos e segundos.

Prepare um programa em Python que leia uma sequência de números, um por linha e, para cada número lido, apresente esse valor no formato HH:MM:SS.

#### Casos de teste 

**Input 1**

```
7505
```

**Output 1**

```
02:05:05
```

**Input 2**

```
44135
```

**Output 2**

```
12:15:35
```


**Input 3**

```
7505
44135
```

**Output 3**

```
02:05:05
12:15:35
```

Submeta no problema A.

### Tarefa B

Atualizamos os equipamentos e agora os tempos de cada turno são apresentados em horas, minutos e segundos. Queremos saber o tempo total gasto nos turnos, em dias, horas, minutos e segundos.

Podíamos converter os tempos para segundos e depois de termos um total, converter então para o formato desejado. Mas a nossa conversão não considerava a possibilidade de traduzir valores de horas superiores a 24 em dias e horas. Assim, vamos lendo a duração das experiências e atualizando o tempo total.

Prepare um programa que leia os tempos da consola, um por linha, até ao fim dos dados e apresente, para cada linha lida, o tempo acumulado em dias, horas, minutos e segundos. Cada linha contém uma string com o formato *HH:MM:SS* em que *HH* corresponde às horas, *MM* corresponde aos minutos e *SS* aos segundos. O tempo total, que deve ser apresentado num única linha, deverá respeitar o formato "DD:HH:MM:SS" (sem as aspas), em que *DD*, *HH*, *MM* e *SS* correspondem ao valores de dias, horas, minutos e segundos, respetivamente. Note que deve usar dois dígitos para cada valor.



#### Casos de teste 

**Input 1**

```
02:05:05
```

**Output 1**

```
00:02:05:05
```

**Input 2**

```
02:05:05
12:15:35
24:00:00
12:45:20
```

**Output 2**

```
00:02:05:05
00:14:20:40
01:14:20:40
02:03:06:00
```

Submeta no problema B.

### Tarefa C

Estamos a registar o trabalho e verificámos que muitas vezes há erros na introdução das datas. É preciso então validar as datas introduzidas. 

Usamos o [formato padrão](https://pt.wikipedia.org/wiki/ISO_8601), *YYYY-MM-DD* em que *YYYY* representa o ano, *MM* representa o mês e *DD* o dia. Para simplificar, vamos considerar o [calendário gregoriano](https://pt.wikipedia.org/wiki/Ano_bissexto), ou seja, que temos datas a partir de 1582.

Relembremos agora as regras para as datas. Os meses são 12, isso é simples. Os dias variam, como sabemos do ditado popular: "Trinta dias tem novembro, abril, junho e setembro, vinte e oito terá um e os mais têm trinta e um". Fevereiro terá 28 dias, ou, num ano bissexto, 29. Um ano bissexto é divisível por quatro mas, se for um ano secular só será bissexto se for divisível por 400. E um ano secular é um ano divisível por 100.

Prepare um programa que leia as datas da consola, uma por linha, até ao fim dos dados. Por cada linha lida, o seu programa deve repetir a data lida, indicando se é válida ou não. Cada linha do input conterá *YYYY-MM-DD* em que *YYYY*, *MM* e *DD* são inteiros maiores que zero e representam ano, mês e dia, respetivamente. 
Cada linha do output repetirá o input acrescentando " -> Válida" (sem as aspas) ou " -> Inválida" (sem as aspas), se a data for válida ou não, respetivamente. 

#### Casos de teste

**Input 1**

```
2020-03-31
2020-03-45
2020-04-30
2020-04-31
2020-04-45
2019-02-28
2019-02-29
1600-02-29
1700-02-29
1800-02-29
1900-02-29
2000-02-29
2019-02-29
2020-02-29
2020-02-30
```

**Output 1**

```
2020:03:31 -> Válida
2020:03:45 -> Inválida
2020:04:30 -> Válida
2020:04:31 -> Inválida
2020:04:45 -> Inválida
2019:02:28 -> Válida
2019:02:29 -> Inválida
1600:02:29 -> Válida
1700:02:29 -> Inválida
1800:02:29 -> Inválida
1900:02:29 -> Inválida
2000:02:29 -> Válida
2019:02:29 -> Inválida
2020:02:29 -> Válida
2020:02:30 -> Inválida
```


Submeta no problema C.
