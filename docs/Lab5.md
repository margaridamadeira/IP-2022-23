# Lab5

Note bem:

+ Cotação deste guião: 2 pontos
+ Submeta cada uma das tarefas no problema correspondente do concurso IP_L5.
+ Prazo limite de submissão: 23h59m de 15 de novembro
+ Prazo limite de validação das submissões aceites: 21 de novembro, horário de atendimento de segunda-feira (9h às 11h).

## Objetivos de aprendizagem

Com este guião, exercitaremos:

1. o desenvolvimento de uma solução completa
1. o uso de condições lógicas na implementação de soluções computacionais
1. o uso dos métodos intrínsecos dos tipos de dados.

## IMI

(baseado num exercício do Prof. Doutor Tiago Candeias, IP (MAEG))

O IMI é o imposto sobre o património imobiliário. Todos os proprietários de imóveis têm que pagar este imposto anualmente. Este imposto incide sobre o valor do imóvel e a taxa mínima é de 0.3%. Por exemplo, um apartamento cujo valor seja 100000 euros pagará 300 euros.

Pretende-se determinar o montante a pagar caso se adote uma política que atribua um desconto no IMI, para beneficiar as famílias com filhos. O desconto seria de 10% no caso de um filho, 15% no caso de 2 filhos e 20% no caso de 3 filhos ou mais. No entanto, o desconto nunca seria superior a 80 euros.

### Tarefa A

Programe uma função `desconto_imi` com dois argumentos, o primeiro de tipo float, representando o valor do imóvel, e o segundo, de tipo int, representando o número de filhos; essa função calculará o valor do imi a pagar.

Prepare um programa em Python completo, incluindo uma função de teste, que leia da consola uma linha com o valor do imóvel e o número de filhos e apresente o valor a pagar.

**Casos de teste**

**Input 1**

```
100000 0
```

**Output 1**

```
300.0
```

**Input 2**

```
100000 1
```

**Output 2**

```
270.0
```

**Input 3**

```
500000 0
```

**Output 3**

```
1500.0
```

**Input 4**

```
500000 1
```

**Output 4**

```
1420.0
```

Submeta na tarefa A.

<div style="page-break-after: always"></div>

## Gerar senhas


```{figure} ./figures/codigos.png
---
height: 200px
name: p4assw0rd
---

Password secreta
```

Isto de inventar senhas, todas diferentes, tem muito que se lhe diga. Vou passar a criar uma senha a partir de uma frase, idealmente associada ao serviço onde me quero autenticar.

Vou passar a adotar uma estratégia que passa por aplicar sequencialmente cada uma das seguintes três transformações: em cada palavra (ou sequência separada por espaços), se o primeiro carater for uma letra, converto-a para maiúscula e converto as demais letras para minúsculas; substituo todas as ocorrências de 'a', 'e', 'i' e 'o' por '4', '3', '1' e '0', respetivamente; como muitas vezes são pedidos sinais de pontuação, então se a soma dos digitos numéricos for par, junto um ponto final ('.') e se for ímpar, junto um ponto de exclamação ('!).

Agora só preciso de um programa para converter as frases para quando precisar das senhas.

### Tarefa B

Prepare um programa em Python que leia da consola uma frase e apresente a frase original e a senha correspondente de acordo com a estratégia apresentada.

O input é uma única linha contendo uma string.
O output é uma única linha contendo a string lida e a string resultante da codificação, separadas pela sequência espaço, dois pontos, espaço (ou seja, " : " (sem as aspas)).

**Casos de teste**

**Input 1**

```
segredo meu e MUITO meu
```

**Output 1**

```
segredo meu e MUITO meu : S3gr3d0 M3u E Mu1t0 M3u!
```

**Input 2**

```
o carteiro toca sempre duas vezes
```

**Output 2**

```
o carteiro toca sempre duas vezes : O C4rt31r0 T0c4 S3mpr3 Du4s V3z3s.
```

**Input 3**

```
conta da Univ do Algarve
```

**Output 3**

```
conta da Univ do Algarve : C0nt4 D4 Un1v D0 Alg4rv3.
```

Submeta na tarefa B.
