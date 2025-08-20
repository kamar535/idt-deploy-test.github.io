---
title: Uppgift
weight: 100
assignment: mandatory
---

I denna uppgift skall du skriva ett Pythonprogram som med hjälp av
[NumPy](../numpy) och [Matplotlib](../matplotlib) generar följande diagram. 

![](/images/2024/python/assignment/final-diagram.png?width=600px)

I titeln på diagrammet skall du byta ut `abcd1234` mot namnet på ditt
[studentkonto](/preparation/#studentkonto). 

## Skapa ett nytt program

Öppna en ny fil i Spyder ch ge filen namnet `curves.py`.

## Ett första försök

Utgå från följande program. 

``` python
import matplotlib.pyplot as plt
import numpy as np

# x values
x = np.linspace(-10, 10, 100)

# f(x) curves to plot (arrays of y values)
linear = x
quadratic = x*x
sinus = 10*np.sin(2*x)

# Plot functions
plt.plot(x, quadratic, color="blue", label="x^2")

# Display the generated figure
plt.show()
```

När du kör programmet genereras följande diagram. 

![](/images/2024/python/assignment/skeleton-diagram.png)

## Uppgift

Din uppgift är nu att lägga till:

- Ett rutnät. 
- Förklaringen `y` till vänster om y-axeln.
- Förklaringen `x` under x-axeln. 
- Den räta linjen i rött. 
- Sinuskurvan i grönt.
- Förklaringar (labels) för de olika kurvorna.
- Ändra titeln till namnet på ditt studentkonto på formen `abcd1234`
  
## Det färdiga diagrammet 

När du är klar skall diagrammet se ut så här fast du bytt ut `abcd1234` mot
namnet på ditt [studentkonto](/preparation/#studentkonto). 

![](/images/2024/python/assignment/final-diagram.png?width=600px)

## Ladda upp programmet i Studium

När du är klar skall du ladda upp programmet `curves.py` på angiven plats i
Studium.