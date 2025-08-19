---
title: Ett första program
weight: 40
---

Efter att ha testat att utföra enklare beräkningar i Python Console (REPL) är det nu dags
att skapa ditt första Pythonprogram. 

## Starta Spyder

Starta [Spyder](../spyder) om du inte redan gjort det. 

## Editor

Till vänster i Spyder hittar du en **kodeditor**.

![](/images/python/spyder/editor.png)

## New file hello.py

Tryck på ikonen **New File** och skapa en fil med namnet `hello.py`.

![](/images/python/spyder/new-file.png)

En ny flik med den nya filen `hello.py` visas nu i editorn. 

![](/images/python/spyder/hello-created.png)

Raderna 1 - 6 utgörs av kommentarer som Spyder lagt till när du skapade filen.
Du kan ta bort dessa kommentarer om du vill. 

## Strängar

Av programmerare brukar text som omslutes av enkla eller dubbla citattecken
kallas för en **sträng**. Exempel på strängar: `"Hej på dig!"`, `'Tack skall du
ha'`.

## Print Hello!

I Python används funktionen `print` för att skriva ut till till Python Console. 
Skriv in `print("Hello!")` i filen `hello.py` för att skriva ut strängen
`"Hello!"` till Python Console. 

![](/images/python/spyder/hello-py-1.png)

## Kör programmet

Tryck på **Run** (play). 

![](/images/python/spyder/run-button.png)

## Run settings

Första gången du kör programmet får du upp följande ruta. 

![](/images/python/spyder/run-hello-settings.png)

Du behöver inte ändra på något utan kan trycka direkt på **Run**. 

## Resultat av körning i Python Console

I Python Console ser du nu resultatet av körningen. 

![](/images/python/spyder/hello-py-1-output.png)

I detta fall blir resultatet att texten `Hello!` skriv ut på en egen rad. 


## Lägg till kod

Lägg till `1+1` på en egen rad. 

``` Python
print("Hello!")

1+1
```

Tryck på **play-knappen** för att köra programmet. I Python Console ser du
återigen utskriften `Hello!`. Resultatet `2`av `1+1` skrivs dock inte ute. 

När du arbetar i Python Console (REPL) skriver du in en rad kod i taget och resultatet (om
det finns något) skrivs sedan automatiskt ut på nästa rad. 

När du kör ett Pythonprogram utförs programmet rad för rad, uppifrån och ner.
Men, inga automatiska utskrifter sker. 

## Lägg till utskrift av 1 + 1 

Om du vill se resultat av `1+1` måste du själv skriva ut det med hjälp av
funktionen `print`. Ändra så att programmet ser ut så här. 

``` Python
print("Hello!")

print(1+1)
```

Kör programmet igen genom att klicka på **Play**. Den här gånger skrivs
värdet först `Hello!` ut och sedan skrivs även `2` ut. 

## Lägg till kommentarer

I Python används tecknet `#` för att påbörja en kommentar. Kommentaren sträcker
sig från tecknet `#` till slutet av raden. Vid körning ignorerar Python alla
kommentarer. Det är vanligt att programmerare lägger till kommentarer i sina
program för att förklara eller förtydliga för sig själv och andra vad
programmet gör. 

Vi bygger ut vårt exempel så det ser ut så här. 

``` python
print("Hello!")

print(1+1)

# Three variables.
a = 1
b = 4
c = a + b

# Print the value of variable c.
print(c)
```

Vid körning sker nu följande utskrifter till Python Console.

``` text 
Hello!

2

5
```

Först skrivs strängen `"Hello!"` ut. Sedan skrivs värdet av beräkning `1+1` ut,
dvs `2` skrivs ut. Slutligen skrivs värdet av variabeln `c` ut, dvs `5` skrivs
ut.  

Testa att lägga till tecknet `#` längst till vänster på sista raden med `print(c)`.

``` python
print("Hello!")

print(1+1)

# Three variables.
a = 1
b = 4
c = a + b

# Print the value of variable c.
#print(c)
```

Vad tror du händer när du kör programmet igen?
