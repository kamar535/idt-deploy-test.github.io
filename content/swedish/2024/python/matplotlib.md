---
title: Matplotlib
weight: 60
---

[Matplotlib][matplotlib] är ett bibliotek som tillsammans med NumPy gör det
möjligt att skapa olika typer av grafiska visualiseringar i form av grafer och
diagram. 

[matplotlib]: https://matplotlib.org/


Starta [Spyder](../spyder) om du inte redan gjort det. 

## Editor

Till vänster i Spyder hittar du en **kodeditor**.

![](/images/python/spyder/editor.png)

## New file lines.py

Tryck på ikonen **New File** och skapa en fil med namnet `lines.py`.


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

I editorn skall det nu se ut så här. 

![](/images/python/matplotlib/lines-py-1.png)

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

Tryck på **Run** (play). I Python Console får du nu en varning som berättar att
det genererade diagrammet visas under fliken **Plots** i vyn högst upp till
höger i Spyder. 

![](/images/python/matplotlib/lines-py-1-warning.png)

Nu visas diagrammet. 

![](/images/python/matplotlib/lines-py-1-plot.png)

## Lägg till rutnät

För att visa ett rutnät lägger du till `plt.grid()` på någon rad innan du gör
`plt.show()`. Programmet ser nu ut så här. 

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

Kör programmet igen genom att trycka på **play**.

Ett nytt diagram visas nu med samma linje som tidigare fast nu även med ett
rutnät. 

![](/images/python/matplotlib/lines-py-2-plot.png)


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
 
Det nya diagrammet ser ut så här. 

![](/images/python/matplotlib/lines-py-3-plot.png)


Notera att det till vänster om y-axeln nu står `y` och att det under x-axeln nu
står `x`.

## Ändra färg på linjen

Lägg till `colol="red"` när du genererar diagrammet. 

``` python
# Plot function
plt.plot(x, two, color="red")
```

Kör programmet. Det nya diagrammet ser ut så här. 

![](/images/python/matplotlib/lines-py-4-plot.png)

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

Kör programmet. Det nya diagrammet ser ut så här. 

![](/images/python/matplotlib/lines-py-5-plot.png)

I det övre vänstra hörnet av diagrammet har nu förklaringen `2x` lagts till för
den röda linjen. 

## Lägg till en titel

Lägg till följande innan raden med `plt.show()`.

``` python
# Add title
plt.title('En rät linje', fontweight="bold", size = 20, pad=10)
```

Detta kommer lägga till titeln `En rät linje` i fet (`bold`) stil, textstorlek
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

Kör programmet. Det nya diagrammet ser ut så här. 

![](/images/python/matplotlib/lines-py-6-plot.png)

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
Kör programmet. Det nya diagrammet ser ut så här. 

![](/images/python/matplotlib/lines-py-7-plot.png)
