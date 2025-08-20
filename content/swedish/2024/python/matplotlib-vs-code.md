---
title: Matplotlib
weight: 60
draft: true
---

[Matplotlib][matplotlib] är ett bibliotek som tillsammans med NumPy gör det
möjligt att skapa olika typer av grafiska visualiseringar i form av grafer och
diagram. 

[matplotlib]: https://matplotlib.org/


## Starta VS Code

Starta VS Code. 

![](/images/2024/python/vscode/vscode-start.png?width=600px)

## Explorer

Klicka på **Explorer** (1) i VS Code.

![](/images/2024/python/hello/explorer.png?width=600px)

## Öppna katalog 

Klicka på **Open folder** (2).

![](/images/2024/python/hello/open-folder.png?width=600px)

Sök dig fram till en katalog där du vill spara ditt Pythonprogram eller skapa en
ny katalog. I exemplet nedan öppnades den befintliga katalogen `python` som
skapades övningen [ett första program](../hello). Under explorer ser du
katalogen `python` och under den befintliga filen `hello.py` som också skapdes i
övningen [ett första program](../hello).

![](/images/2024/python/matplotlib/python-folder.png?width=600px)

## Lägg till fil

När du för musen över **PYTHON** visas några nya ikoner. Den första av dessa
ikoner ser ut så här och kallas för **New File**. 

![](/images/2024/python/vscode/new-file-icon.png)

Tryck på **New file** (4).

![](/images/2024/python/matplotlib/new-file.png?width=600px)

Ge den nya file namnet `lines.py`. 

{{% notice style="warning" title="Suffixet .py" %}}

Det är viktigt att filnamnet avslutat med suffixet `.py` för alla filer som
innehåller Pythonprogram. 
{{% /notice %}}

I Explorer dyker nu den nya filen upp (5) och
du en ny flik med namnet `lines.py` dyker upp till höger (6).

![](/images/2024/python/matplotlib/lines-py.png?width=600px)

Det är under fliken `lines.py` (6) som du redigerar innehållet i filen
`lines.py`. Längst ut till vänster visas radnumret för varje rad. För tillfället
finns endast en tom rad med radnummer `1`.

## Rita en rät linje

Lägg till följande rader kod. 

``` Python
import matplotlib.pyplot as plt
import numpy as np

# Array of x values
x = np.linspace(-10, 10, 100)

# Function f(x) to plot (array of y values)
two = 2*x

# Plot function
plt.plot(x, two)

# Display the generated diagram
plt.show()
```

Högst upp importeras biblioteken `matplotlib` och `numpy`.

``` Python
import matplotlib.pyplot as plt
import numpy as np
```

Sedan skapas en array med `100` värden jämnt fördelade i intervallet `-10` till
`10`.

``` python
# Array of x values
x = np.linspace(-10, 10, 100)
```

Den skapade arrayen multipliceras med talet `2` och resultatet lagras i
variabeln `two`. 

``` python
# Function f(x) to plot (array of y values)
two = 2*x
```

Ett diagram (plot) skapas med värden från arrayen `x` på x-axeln och
motsvarande värden från arrayen `two` på y-axeln. 

``` python
# Plot function
plt.plot(x, two)
```

Avslutningsvis visas det skapade diagrammet på skärmen.  

``` python
# Display the generated diagram
plt.show()
```

## Kör programmet

Tryck på **play-knappen** (7) för att köra programmet. 

![](/images/2024/python/matplotlib/play.png?width=600px)

Efter ett tag öppnas ett nytt fönster med det generade diagrammet. 

![](/images/2024/python/matplotlib/fig-1.png?width=600px)

## Lägg till rutnät

För att visa ett rutnät lägger du till `plt.grid()` på någon rad innan du gör
`plt.show()`. Kör programmet igen genom att trycka på **play**. Notera att diagrammet inte uppdateras. 

Programmet ser nu ut så här. 

```python 
import matplotlib.pyplot as plt
import numpy as np

# Array of x values
x = np.linspace(-10, 10, 100)

# Function f(x) to plot (array of y values)
two = 2*x

# Plot function
plt.plot(x, two)

# Show grid lines
plt.grid()

# Display the generated figure
plt.show()
```

## Stäng fönster med diagram för att se uppdaterat diagram

Stäng fönstret med diagrammet. Efter ett tag öppnas ett nytt fönster med det
uppdaterade diagrammet med rutnät. 

![](/images/2024/python/matplotlib/fig-2.png?width=600px)

Detta är en viktigt princip när du använder Matplotlib. Om det redan finns ett
öppet fönster med ett diagram kommer ditt program att ta en paus när det kommer
till `plt.show()` tills dessa att fönstret stängts. Efter det att fönstret
stängts fotsätter programmet och ett nytt fönster öppnas med det nya diagrammet.

## Lägg till beskrivningar för x- och y-axel

Lägg till följande rader någonstans i programmet innan raden med `plt.show()`.

``` python
# Add axis labels
plt.xlabel("x")
plt.ylabel("y")
```

Hela programmet ser nu ut så här. 

``` python
import matplotlib.pyplot as plt
import numpy as np

# Array of x values
x = np.linspace(-10, 10, 100)

# Function f(x) to plot (array of y values)
two = 2*x

# Plot function
plt.plot(x, two)

# Show grid lines
plt.grid()

# Add axis labels
plt.xlabel("x")
plt.ylabel("y")

# Display the generated diagram
plt.show()
```

Kör programmet. Glöm inte att stänga fönstret med den tidigare versionen av
diagrammet. Det nya diagrammet ser ut så här. 

![](/images/2024/python/matplotlib/fig-3.png?width=600px)

Notera att det till vänster om y-axeln nu står `y` och att det under x-axeln nu
står `x`.

## Ändra färg på linjen

Lägg till `colol="red"` när du genererar diagrammet. 

``` python
# Plot function
plt.plot(x, two, color="red")
```

Kör programmet. Glöm inte att stänga fönstret med den tidigare versionen av
diagrammet. Det nya diagrammet ser ut så här. 

![](/images/2024/python/matplotlib/fig-4.png?width=600px)

Notera att linjen nu är röd. 

## Lägg till förklaring 

Lägg till `label="2x"` när du genererar diagrammet. 

``` python
# Plot function
plt.plot(x, two, color="red", label="2x")
```

Lägg sedan till följande innan raden med `plt.show()`.

``` python
# Show legends
plt.legend()
```

Hela programmet ser nu ut så här. 

``` python
import matplotlib.pyplot as plt
import numpy as np

# Array of x values
x = np.linspace(-10, 10, 100)

# Function f(x) to plot (array of y values)
two = 2*x

# Plot function
plt.plot(x, two, color="red", label="2x")

# Show grid lines
plt.grid()

# Add axis labels
plt.xlabel("x")
plt.ylabel("y")

# Show legends
plt.legend()

# Display the generated figure
plt.show()
```

Kör programmet. Glöm inte att stänga fönstret med den tidigare versionen av
diagrammet. Det nya diagrammet ser ut så här. 

![](/images/2024/python/matplotlib/fig-5.png?width=600px)

I det övre vänstra hörnet av diagrammet har nu förklaringen `2x` lagts till för
den röda linjen. 

## Lägg till en titel

Lägg till följande innan raden med `plt.show()`.

``` python
# Add title
plt.title('En rät linje', fontweight="bold", size = 20, pad=10)
```

Detta kommer lägga till titen `En rät linje` i fet (`bold`) stil, textstorlek
`20` med avstånd `10` ovanför diagrammet. 

Hela programmet ser nu ut så här. 

``` python
import matplotlib.pyplot as plt
import numpy as np

# Array of x values
x = np.linspace(-10, 10, 100)

# Function f(x) to plot (array of y values)
two= 2*x

# Plot function
plt.plot(x, two, color="red", label="2x")

# Show grid lines
plt.grid()

# Add axis labels
plt.xlabel("x")
plt.ylabel("y")

# Show legends
plt.legend()

# Add title
plt.title('En rät linje', fontweight="bold", size = 20, pad=10)

# Display the generated diagram 
plt.show()
```

Kör programmet. Glöm inte att stänga fönstret med den tidigare versionen av
diagrammet. Det nya diagrammet ser ut så här. 

![](/images/2024/python/matplotlib/fig-6.png?width=600px)

Titeln `En rät linje` har nu lagts till överst i diagrammet. 

## Lägg till en linje till

Det går att plotta mer än en linje i taget. Lägg till följande rader. 

``` python
# Function f(x) to plot (array of y values)
one = 1*x
```

Du behöver nu plotta båda arrayerna `two` och `one`.

``` python
# Plot functions
plt.plot(x, two, color="red", label="2x")
plt.plot(x, one, color="blue", label="x")
```

Ändra även titeln. 

``` python
# Add title
plt.title('Två räta linjer', fontweight="bold", size = 20, pad=10)
```

Hela programmet ser nu ut så här. 

``` python
import matplotlib.pyplot as plt
import numpy as np

# Array of x values
x = np.linspace(-10, 10, 100)

# Function f(x) to plot (array of y values)
two = 2*x

# Function f(x) to plot (array of y values)
one = 1*x

# Plot functions
plt.plot(x, two, color="red", label="2x")
plt.plot(x, one, color="blue", label="x")

# Show grid lines
plt.grid()

# Add axis labels
plt.xlabel("x")
plt.ylabel("y")

# Show legends
plt.legend()

# Add title
plt.title('Två räta linjer', fontweight="bold", size = 20, pad=10)

# Display the generated diagram 
plt.show()
```
Kör programmet. Glöm inte att stänga fönstret med den tidigare versionen av
diagrammet. Det nya diagrammet ser ut så här. 

![](/images/2024/python/matplotlib/fig-7.png?width=600px)
