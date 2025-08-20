---
title: Python som miniräknare
weight: 30
---

Du skall nu får lära dig mer om Python Console (REPL) genom att använda det som en
miniräknare.

## Starta Spyder

Starta [Spyder](../spyder) om du inte redan gjort det. 

## Python Console och prompten

Nere till höger i Spyder hittar du **Python Console** vilket är ett Python REPL. 

![](/images/python/spyder/python-console.png)

## Förenklad prompt 

I alla kommande exempel kommer den förenklade prompten `>>>` användas och
resultatprefixet kommer utelämnas. Följande exempel i Python Console:

``` text
In [1]: 1+1
Out[1]: 2

In [2]: 
```

, kommer i alla kommande exempel att se ut så här: 

``` text
>>> 1+1
2
>>> 
```

Den första raden: 

``` text
>>> 1+1
```

, betyder inte att du skall skriva skriva in `>>> 1+1` i Python Console. Det
betyder att du skall skriva in `1+1` efter prompten i Python Console. 

En rad med endast `>>>`: 

``` text 
>>>
```` 

, betyder att en ny prompt kommer visas här i Python Console. 

## Addition

Skriv in `1+1` efter prompten och tryck enter. 

``` text
>>> 1 + 1
```

Svaret på denna beräknings skriv nu ut på en egen rad följt av en ny prompt.

```text 
>>> 1 + 1
2
>>>
```

Notera att du kan använda godtyckligt många mellanslag runt plustecknet. Alla
dessa varianter är likvärdiga.

```text
1+1
1 +1
1+ 1
1    +1
1+    1
1  +  1
```

Men, du kan inte börja med ett eller flera mellanslag. 

```text 
>>>  1 + 1
  File "<stdin>", line 1
    1+1
IndentationError: unexpected indent
>>>
```

Om du böjar med ett eller flera mellanslag klagar Python och ger felmeddelandet `IndentationError: unexpected indent`.

## Testa fler räknesätt

Nedan ser du exempel på addition, multiplikation och division. 
``` text
>>> 1 + 3
4
>>> 3*7
21
>>> 1 / 3
0.3333333333333333
>>> 1 + 2*1/3
1.6666666666666665
>>> 
```

Parenteser kan användas för att gruppera. 

```text
>>> 10 - 5 / 2
7.5
>>> (10 - 5) / 2
2.5
>>>
```

## Operatorprioritet 

[Operatorprioritet][operatorprioritet] eller prioriteringsregler för operatorer
är ett begrepp inom bland annat matematik och programmering. Operatorprioriteten används för att
avgöra i vilken ordning operationer (räknesätt) utförs. Behovet kommer från att
vissa uttryck, exempelvis `1 + 2 * 3` har olika värden beroende på om man först
adderar `1 + 2` (då uttrycket har värdet `9`) eller först multiplicerar `2 * 3` (då
uttrycket har värdet `7`).

[operatorprioritet]: https://sv.wikipedia.org/wiki/Operatorprioritet

De prioriteringsregler som används i matematik kan sammanfattas med följande:

- Först beräknas parenteser.
- Sedan potenser.
- Därefter utförs multiplikation och division i valfri ordning. 
- Sist utförs addition och subtraktion i valfri ordning.

Reglerna ovan kan leda till tvetydighet. Därför är ordningen för addition och
subtraktion liksom för multiplikation och division att operationerna i allmänhet
utförs från vänster till höger. 

Hur beräknas `5 - 2 + 3`? Reglerna innebär att subtraktionen `5 - 2` skall utföras först.

``` text 
5 - 2 + 3 = (5 - 2) + 3 =  3 + 3 = 6
````

Enligt reglerna är det fel att beräkna additionen `2 + 3` först.

``` text
5 - 2 + 3 = 5 - (2 + 3) = 5 - 5 = 0
```

Vi testar och ser hur Python beräknar `5 - 2 + 3`.

``` text
>>> 5-2+3
6
```

Python följer reglerna och utför subraktionen `5 - 2` först. 

Hur beräknas `3 + 2 * 6`? Enligt reglerna gäller att multiplikationen `2 * 6` skall
utföras först. 

``` text
3 + 2 * 6 = 3 + (2 * 6) = 3 + 12 = 15
```

Enligt reglerna är det fel att beräkna additionen `3 + 2` först. 

``` text
3 + 2 * 6 = (3 + 2) * 6 = 5 * 6 = 30
```

Vi testar och ser hur Python beräknar `3 + 2 * 6`.

``` text
>>> 3+2*6
15
```

Python följer reglerna och multiplikationen `2 * 6` utförs först. 

Python följer de vanliga reglerna för operatorprioritet från matematiken. Är du
osäker på hur något kommer beräknas kan du alltid lägga till parenteser för att
göra det tydligare. 

``` text
>>> 3+(2*6)
15
```

## Variabler

Värdet av en beräkning kan lagras i en variabel. I exemplet nedan lagras värdet
`5` i variabeln `a` och värdet `2` i variabeln `b`. Variablerna `a` och `b` kan
sedan användas i nya beräkningar. 

``` text
>>> a = 5
>>> b = 2
>>> (a + b) / 2
3.5
>>>
``` 

## Testa på egen hand

Testa att utföra olika beräkningar med hjälp av `+`, `-`, `*` och `/` på egen
hand. Testa även att använda dig av parenteser `(` och `)` för att gruppera. 

## Klurighet

I Python är symbolerna `+`, `-`, `*` och `/` exempel på binära aritmetiska
operatorer. Kan du lista ut vad den binära aritmetiska operatorn `%` beräknar
för något?

Låt oss testa några exempel.

``` text
>>> 1 % 3
1
>>> 2 % 3
2
>>> 3 % 3
0
>>> 4 % 3
1
>>> 5 % 3
2
>>> 6 % 3
0
>>> 7 % 3
1
>>> 
```

Några exempel till. 

``` text
>>> 1 % 2
1
>>> 2 % 2
0
>>> 3 % 2
1
>>> 4 % 2
0
>>> 
```

Kan du klura ut vad som beräknas med hjälp av operatorn `%`? 

## Mer matematik

För att få tillgång till mer avancerade matematiska funktioner behöver du importera
biblioteket `math`.

``` text
>>> import math
```

## Talet π

Efter import av biblioteket `math` finns talet `π` nu tillgängligt som `math.pi`.

``` text
>>> math.pi
3.141592653589793
```

Datorer kan inte representera decimaltal med oändligt många decimaler. I detta
fall får vi nöja oss med att `π` approximeras till `3.141592653589793`. 

## Sinus

I intervallet `0` till `2π` ser sinusfunktionen ut så här.

![](/images/python/numpy/sinus.png?width=600px)

Efter import av biblioteket `math` finns funktionen sinus tillgänglig som
`math.sin`. Testa att beräkna `sin(0)`.

``` text
>>> math.sin(0)
0.0
```

Testa att beräkna `sin(π/4)`.

``` text
>>> math.sin(math.pi/4)
0.7071067811865475
```

Testa att beräkna `sin(π/2)`.

``` text
>>> math.sin(math.pi/2)
1.0
```

Testa att beräkna `sin(3π/4)`.

``` text
>>> math.sin(3*math.pi/4)
0.7071067811865476
```

Testa att beräkna `sin(π)`.

``` text
>>> math.sin(math.pi)
1.2246467991473532e-16
```

Notera att `sin(π)` inte blir exakt `0` utan att det
beräknas till `1.2246467991473532e-16` vilket är mycket, mycket nära `0`. Detta
beror på att datorer inte kan representera decimaltal, till exempel `π`,  med oändligt många
decimaler.

## Cosinus

I intervallet `0` till `2π` ser cosinusfunktionen ut så här.

![](/images/python/numpy/cosinus.png?width=600px)

Efter import av biblioteket `math` finns funktionen sinus tillgänglig som
`math.cos`. Testa att beräkna `cos(0)`.

``` text
>>> math.cos(0)
1.0
```

Pröva att på egen hand beräkna cosinus för `π/4`, `π/2`, `3π/4` och `π`.

## Den naturliga logaritmen

Talet `e` utgör basen för den naturliga logaritmen. Efter import att biblioteket
`math` finns talet `e` tillgängligt som `math.e`.

``` text
>>> math.e
2.718281828459045
```

Funktionen för det naturliga logaritmen `ln` finns tillgänglig som `math.log`.
Vi beräknar `ln(7)`.

``` text
>>> math.log(7)
1.9459101490553132
```

För att beräkna  e<sup>x</sup> används `math.exp(x)`. Vi prövar att beräkna e<sup>2</sup>.

``` text
>>> math.exp(2)
7.38905609893065
```

Per definition skall e<sup>ln(x)</sup> = x. Vi testar om det stämmer. 

``` text
>>> math.exp(math.log(7))
6.999999999999999
```

I detta fall blir resultat inte exakt `7` utan
`6.999999999999999`. Detta beror återigen på att datorer inte kan representera
decimaltal, till exempel talet `e`, med oändligt många decimaler. 

##  Lär dig mer

Om du vill kan lära dig med om vilka konstanter och funktioner som finns
tillgängliga i biblioteket `math` [här][math].

[math]: https://www.w3schools.com/python/module_math.asp

