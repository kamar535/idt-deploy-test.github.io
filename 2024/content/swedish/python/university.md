---
title: Python och VS Code på universitetets datorer
weight: 10
draft: true
---


I alla datorsalar för studenter på campus [Ångströmlaboratiet][ångström] finns det datorer
med Windows. 

[ångström]: https://angstrom.uu.se/

{{< figure 
    width="555px" 
    src="/images/linux/hus-10-pc.jpg" 
    title="Arbetsplats med dator som kör Windows." 
>}}

Om datorn är på lyser power-knappen nere i skärmens högra hörn. Väck upp datorn genom att röra på mussen eller trycka på någon av tangenterna på
tangentbordet. Om power-knappen inte lyser måste du trycka på power-knappen för
att slå på datorn. 
c
## Logga in i Windows

För att logga in i Windows anger du användarnamnet för ditt **studentkonto** på
formen `abcd1234` och **Lösenord A**.

![](/images/linux/windows-10-login.jpg?width=444px)

## Software Center (ZENworks)

Någonstans på skrivbordet hittar du **Software center (Zenworks)**.


![](/images/linux/software-center-icon.png)

Dubbelklicka på ikonen för **Software center (Zenworks)**. Nu öppnas ett nytt
fönster med tillgänglig mjukvara. 

![](/images/linux/software-center.png)

Den mjukvara som du hittar här kan redan vara installerad på den dator du
sitter vid. Om ett program inte redan är installerad kommer det att installeras första gången du
försöker använda programmet. 

## Visual Studio Code 

Skrolla ner tills du hittar två ikoner för **Visual Studio**. 

![](/images/python/university/software-center/visual-studio-icons.png)

Notera att den ena ikonen är något mörkare och den andra är något ljusare.
Klicka en gång på varje ikon för att se hela namnet. Den mörka ikonen heter
**Visual Studio Pro** och den ljusa ikonen heter **Visual Studio Code**.

![](/images/python/university/software-center/visual-studio-code-icon.png?width=300px)

I det här fallet är ikonen för Visual Studio Code markerat med ett kryss uppe i
vänstra hörnet. Detta betyder att programmet för tillfället inte är installerat
på denna dator. 

Dubbelklicka på ikonen för **Visual Studio Code**. Om programmet redan är
installerat på datorn kommer programmet att starta, annars kommer det först att
laddas ner. Under tiden programmet laddas ner visar en stapel hur lång tid det
är kvar innan programmet är nedladdat. 

![](/images/python/university/software-center/visual-studio-code-downloading.png?width=100px)

## Starta Visual Studio Code

När programmet har laddats försvinner krysset upp i vänstra hörnet. 

![](/images/python/university/software-center/visual-studio-code-downloaded.png?width=100px)

Dubbelklicka på ikonen för **Visual Studio Code** för att starta programmet. Så
här ser programmet ut när det startat. 

![](/images/python/university/vs-code.png?width=600px)


## Python tillägg (extension) för VS Code

Klicka på **Extensions**.

![](/images/python/vscode/vscode-extensions.png?width=600px)

Sök efter **Python** (1) och välj **Python extension from Microsoft** (2).

![](/images/python/vscode/vscode-install-python-extension.png?width=600px)

Om du redan har detta tillägg installerat kommer du se en knapp för att
avinstallera (3) och annars kommer du på samma plats att se en knapp för att
installera. 

Om tillägget inte är installerat behöver du installera det. 

## Skapa en ny katalog 

Du behöver nu skapa en ny katalog för dina kommande experiment med Python. 

Klicka på ikonen för **Explorer**. 

![](/images/python/university/explorer.png?width=600px)

Klicka på **Open Folder**.

Öppna en befintlig katalog eller skapa en ny katalog. I detta exempel skapades
den nya katalogen **python**. I explorer skall du nu se namnet på den (nya)
öppnade katalogen. 

![](/images/python/university/explorer-python.png?width=600px)

## Skapa en Python Virtual Environment

Innan du kan installera Pythonbibliotek behöver du först
skapa en **Python Virtual Environment**. 

Öppna **Command Palette** genom att trycka på **Ctrl+Shift+P**. Skriv sedan
`Python create` i sökfältet.

![](/images/python/university/command-palette-python-create.png?width=600px)

Välj **Python: Create Environment**.

![](/images/python/university/create-venv.png?width=600px)

Välj **Venv Creates a \`.venvt\` virtual environment in the current workspace**. 

## Välj version av Python

Det kan finnas flera versioner av Python installerade samtidigt på din dator
och du behöver nu välja vilken av dessa du vill använda dig av. I detta exempel finns två versioner tillgängliga. Välj den med högst version, i
detta fall **Python 3.10.2**.

![](/images/python/university/select-interpreter.png?width=600px)

När den nya Python Virtual Environment har skapats dyker det upp en ny
underkatalog `.venv` i Explorer. 

![](/images/python/university/env-created.png?width=600px)

Allt som har med din nya Python Virtual Environment kommer lagras i denna ny
katalog. 

## Öppna en ny terminal

Öppna **Command Palette** genom att trycka på **Ctrl+Shift+P**. Skriv sedan
`new terminal create` i sökfältet. 

![](/images/python/university/open-new-terminal.png?width=600px)

Välj **Terminal: Create New Terminal**. 

I den undre delen av VS Code öppnas det nu upp en ny **Terminal**. 

![](/images/python/university/env-terminal.png?width=600px)

Notera att det i början av terminalprompten nu skall stå **(.venv)**.

## Installera NumPy

Installera `numpy` genom att skriva in följande i terminalen och tryck enter. 

``` text
pip install numpy
```

Det kan ta lite tid innan installationen blir klar.

## Installera PyQt5 

Installera `pyqt5` genom att skriva in följande i terminalen och tryck enter. 

``` text
pip install pyqt5
```

Det kan ta lite tid innan installationen blir klar.

## Installera Matplotlib

Installera `matplotlib` genom att skriva in följande i terminalen och tryck enter. 

``` text
pip install matplotlib
```

Det kan ta lite tid innan installationen blir klar.

## Testa att det fungerar

Klicka på **New File** i explorer. 

![](/images/python/university/new-file.png?width=200px)

Ge den nya filen namnet `test.py` och klistra in följande kod.

``` python
import matplotlib.pyplot as plt
import numpy as np

print(np.pi)

plt.grid()

plt.show()
```

Klicka på **Run Python File (Play)**. 

![](/images/python/university/run-test-py.png?width=600px)

I terminalen skall du nu värdet av `π` skrivas ut.

![](/images/python/university/test-py-terminal-result.png?width=600px)

Ett nytt fönster med ett rutnät skall också öppnas. 

![](/images/python/university/test-fig.png?width=400px)