---
title: NumPy
weight: 50
---

[NumPy][numpy] (Numerical Python) är ett bibliotek till Python specialiserat på numeriska
beräkningar. 

[numpy]: https://numpy.org/

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

## Importera NumPy

För att använda dig av NumPy behöver du först importera NumPy. Skriv in följande
vid prompten i Python Console och tryck enter. 


``` python
import numpy as np
```

Alla funktioner i NumPy finns nu tillgängliga under det kortare namnet `np`. 

## Array

En grundläggande datatyp i NumPy är array. Arrayer kan vara 1-dimensionella
eller 2-dimensionella. Ett annat namn på 1-dimensionella arrayer i matematiken
är vektor och ett annat namn på 2-dimensionella arrayer i matematiken är matris.

I denna korta introduktion kommer vi endast kika på 1-dimensionella arrayer
(vektorer).I fortsättningen kommer vi kort och gått kalla en 1-dimensionell array (vektor)
för array. 

Skriv in följande i Python Console för att skapa en array med elementen `1`, `3`
och `7`. Glöm inte att avsluta med enter. 

``` python
np.array([1, 3, 7])
```

När du trycker på enter skapas arrayen och visas på nästa rad och sedan skrivs
en ny prompt ut. 

``` python
>>> np.array([1, 3, 7])
array([1, 3, 7])
>>>
```

Det går att lagra arrayer i variabler. 

``` python
>>> a = np.array([1, 3, 7])
```

Denna gång visas inte arrayen efter att den skapats. För att visa arrayen
skriver du `a` och trycket på enter. 

``` python
>>> a
array([1, 3, 7])
>>> 
```

## Multiplicera tal med array 

Det går att multiplicera ett tal med en array. Detta gör så att alla värden i
arrayen multipliceras med talet. I följande exempel multipliceras arrayen `a`
med talet `3`.

```python
>>> a = np.array([1, 3, 7])
>>> 3*a
array([ 3,  9, 21])
>>>
```

I följande exempel multipliceras arrayen `a`
med talet `100`.

``` python
>>> 100*a
array([100, 300, 700])
>>> 
```

## Addera arrayer

Arrayer kan adderas med varandra. 

``` python
>>> a = np.array([1, 3, 7])
>>> a + a
array([ 2,  6, 14])
>>> 
```

Det går att kombinera multiplikation och addition. 

``` python
>>> a + 2*a
array([ 3,  9, 21])
>>> 
```

## Skapa array med hjälp av linspace

Med hjälp av `linspace` kan du enkelt skapa arrayer med värdet som är jämnt
utspridda inom ett visst intervall. 

I exemplet nedan skapas en array med `5` värden jämnt fördelade inom
intervallet `1` till `3`. 

``` python
>>> np.linspace(1, 3, 5) 
array([1. , 1.5, 2. , 2.5, 3. ])
>>> 
```

I exemplet nedan skapas en array med `10` värden jämnt fördelade inom intervallet `1` till `10`. 

``` python
>>> np.linspace(1, 10, 10)
array([ 1.,  2.,  3.,  4.,  5.,  6.,  7.,  8.,  9., 10.])                                
>>> 
```

## Talet π 

När du använder NumPy finns talet `pi` tillgängligt som `np.pi`.

``` python
>>> np.pi
3.141592653589793
>>> 
```

## Sinus

I intervallet `0` till `2π` ser sinusfunktionen ut så här.

![](/images/python/numpy/sinus.png?width=600px)

På x-axeln finns det markeringar vid `0`, `π/4`, `π/2`, `3π/4`, `π`, ..., `2π`.
Totalt är det `9` markeringar. Skapa en array med 9 element jämt fördelade inom intervallet `0`, och `2π`.

``` python
>>> x = np.linspace(0, 2*np.pi, 9)
>>> x
array([0.        , 0.78539816, 1.57079633, 2.35619449, 3.14159265,
       3.92699082, 4.71238898, 5.49778714, 6.28318531])
>>>
```

Vi kan nu låta NumPy beräkna värdet på sinusfunktionen för alla värdet i
arrayen. 

``` python
>>> np.sin(x)
array([ 0.00000000e+00,  7.07106781e-01,  1.00000000e+00,  7.07106781e-01,
        1.22464680e-16, -7.07106781e-01, -1.00000000e+00, -7.07106781e-01,
       -2.44929360e-16])
>>> 
```
