---
title: Ett första program
weight: 40
draft: true
---

Efter att ha testat att utföra enklare beräkningar i Python REPL är det nu dags
att skapa ditt första Pythonprogram. 


## Starta VS Code

Starta VS Code. 

![](/images/python/vscode/vscode-start.png?width=600px)

## Explorer

Klicka på **Explorer** (1) i VS Code.

![](/images/python/hello/explorer.png?width=600px)

## Öppna katalog 

Klicka på **Open folder** (2).

![](/images/python/hello/open-folder.png?width=600px)

Sök dig fram till en katalog där du vill spara ditt Pythonprogram eller skapa en
ny katalog. I exemplet nedan öppnades en katalog med namn `python` vilket du ser
under Explorer (3).

![](/images/python/hello/python-folder.png?width=600px)

## Lägg till fil

När du för musen över **PYTHON** visas några nya ikoner. Den första av dessa
ikoner ser ut så här och kallas för **New File**. 

![](/images/python/vscode/new-file-icon.png)

Tryck på **New file** (4).

![](/images/python/hello/new-file.png?width=600px)

Ge den nya file namnet `hello.py`. 

{{% notice style="warning" title="Suffixet .py" %}}

Det är viktigt att filnamnet avslutat med suffixet `.py` för alla filer som
innehåller Pythonprogram. 
{{% /notice %}}

I Explorer dyker nu den nya filen upp (5) och
du en ny flik med namnet `hello.py` dyker upp till höger (6).

![](/images/python/hello/hello-py.png?width=600px)

Det är under fliken `hello.py` (6) som du redigerar innehållet i filen
`hello.py`. Längst ut till vänster visas radnumret för varje rad. För tillfället
finns endast en tom rad med radnummer `1`.

## Lägg till kod

Lägg till följande rader kod. 

``` Python
a = 1
b = 4
c = a + b
```

## Kör programmet

Tryck på **play-knappen** (7) för att köra programmet. 

![](/images/python/hello/play.png?width=600px)

Nu öppnas en ny terminal längst ner (8).

![](/images/python/hello/result-1.png?width=600px)

Namnet `hello.py` på programmet som körts skrivs ut och sedan en ny
terminalprompt `$`.

## Lägg till utskrift

När du arbetar i Python REPL skriver du in en rad kod i taget och resultatet (om
det finns något) skrivs sedan automatiskt ut på nästa rad. 

När du kör ett Pythonprogram utförs programmet rad för rad, uppifrån och ner.
Men, inga automatiska utskrifter sker. 

Om du vill se resultat måste du själv skriva ut med hjälp av funktionen `print`.

Lägg till följande rad sist i programmet. 

``` python
print(c)
```

Hela programmet skall nu se ut så här. 

``` python
a = 1
b = 4
c = a + b

print(c)
```

Kör programmet igen genom att klicka på **Play** (9). Den här gånger skrivs
värdet `5`på variablen `c` ut i terminalen (10).

![](/images/python/hello/play-2-result.png?width=600px)

## Lägg till kommentarer

I Python används tecknet `#` för att påbörja en kommentar. Kommentaren sträcker
sig från tecknet `#` till slutet av raden. Vid körning ignorerar Python alla
kommentarer. Det är vanligt att programmerare lägger till kommentarer i sina
program för att förklara eller förtydliga för sig själv och andra vad
programmet gör. 

Pröva att lägga till några kommentarer till progammet, till exempel så här. 

``` python
# Three variables.
a = 1
b = 4
c = a + b

# Print the value of variable c.
print(c)
```

Pröva sedan att köra programmet igen. Testa nu att lägga till tecknet `#` längst
till vänster på sista raden med `print(c)`.

``` python
# Three variables.
a = 1
b = 4
c = a + b

# Print the value of variable c.
# print(c)
```

Vad tror du händer när du kör programmet igen?

## Skriv ut strängar (text)

Av programmerare brukar text som omslutes av enkla eller dubbla citattecken
kallas för en **sträng**. Exempel på strängar: `"Hej på dig!"`, `'Tack skall du
ha'`.

I Python kan du använda `print` för att skriva ut strängar. Pröva att lägga till
utskrift av några stängar, till exempel så här. 

```python
# Three variables.
a = 1
b = 4
c = a + b

# Print the value of variable c.
print(c)

# Print strings.
print("Hello!")
print('Hello!')
```

När du kör programmet ovan skrivs följande ut i terminalen. 

``` text
5
Hello!
Hello!
```



