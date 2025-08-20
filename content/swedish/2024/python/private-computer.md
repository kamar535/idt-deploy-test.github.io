---
title: Python och VS Code på din egen dator
weight: 20
draft: true
---

För att vara förberedd inför kommande kurser är det starkt rekommenderat att du
försöker installera Python och VS Code på din egen dator om du inte redan har Python
och VS Code installerat.

Om redan har Python och VS code installerat är det start rekommenderat att du
ser till så att du även har NumPy och Matplotlib installerat. 

## Installera VS Code

Här hittar du [instruktioner][setup] för hur du laddar hem, installerar och kör
igång VS Code på din privata dator. 

[setup]: https://code.visualstudio.com/docs/setup/setup-overview

## Kontrollera om du redan har Python installerat

Starta VS Code. 

![](/images/2024/python/vscode/vscode-start.png?width=600px)

Öppna en terminal från menyn. 
   -  Windows: View > Terminal.
   -  macOS: Terminal > New Terminal
   -  Linux: ???

I undre halvan av VS Code öppnas nu en terminal.

![](/images/2024/python/vscode/vscode-terminal.png?width=600px)

I terminalen kan du nu testa om du redan har Python installerat. 

### Linux och macOS

På macOS och Linux skriver du in följande kommando i terminalen. 

``` text
python3 --version
```

Tryck enter för att utföra kommandot. Om du redan har Python installerat kommer
du nu se något liknande detta i terminalen. 

```text 
Python 3.11.6
```

Om du inte har Python installerat kommer du istället att se ett felmeddelande
liknande detta. 

``` text
command not found: python3
```

### Windows

På Windows skriver du in följande kommando i terminalen. 

```text
py -3 --version
```

Tryck enter för att utföra kommandot. Om du redan har Python installerat kommer
du nu se något liknande detta i terminalen. 

```text 
Python 3.11.6
```

Om du inte har Python installerat kommer du istället att se ett felmeddelande
liknande detta. 

``` text
command not found: py
```

## Python tillägg (extension) för VS Code

Klicka på **Extensions**.

![](/images/2024/python/vscode/vscode-extensions.png?width=600px)

Sök efter **Python** (1) och välj **Python extension from Microsoft** (2).

![](/images/2024/python/vscode/vscode-install-python-extension.png?width=600px)

Om du redan har detta tillägg installerat kommer du se en knapp för att
avinstallera (3) och annars kommer du på samma plats att se en knapp för att
installera. 

Om tillägget inte är installerat behöver du installera det. 

## Kontrollera om du har NumPy installerat

Från VS Code, tryck `Ctrl+Shift+P` (Windows och Linux) eller `Cmd+Shift+P`
(macOS) för att öppna kommandopaletten. Skriv `Start REPL` i sökrutan och välj
`Python: Start REPL`.

![](/images/2024/python/vscode/start-repl.png?width=600px)

I den nedre halvan av VS Code öppnas nu en terminal, med ett Python REPL.

![](/images/2024/python/vscode/python-repl.png?width=600px)

Skriv in följande vid prompten `>>>` och tryck enter. 

``` text
import numpy
```

Om du har `numpy` installerat får du direkt tillbaka en ny prompt `>>>` och annars får
du först ett felmeddelande och sedan en ny prompt. 

Testa på samma sätt om du har `matplotlib` installerat genom att skriva in
följande vid prompten `>>>` och tryck enter. 

``` text
import matplotlib
```

Om du har `matplotlib` installerat får du direkt tillbaka en ny prompt `>>>` och annars får
du först ett felmeddelande och sedan en ny prompt. 

## Installera NumPy 

Gör så här för att installera NumPy om det inte redan finns installerat. Öppna en terminal från menyn.  
   -  Windows: View > Terminal.
   -  macOS: Terminal > New Terminal
   -  Linux: ???


{{% notice style="warning" title="Terminal vs Python REPL" %}}

Om du i terminalen ser en prompt som ser ut så här `>>>` är du kvar i en
terminal där du tidigare startat ett Python REPL. Du behöver då starta en ny
terminal för att gå vidare. 

När prompten ser ut så här `$` vet du att du är terminalen och inte i Python REPL.
{{% /notice %}}

Vid prompten i terminalen skriver du nu in följande och trycker enter. 

``` text 
pip install numpy
```

Om detta inte fungerar kan du istället pröva med följande. 

``` text 
pip3 install numpy
```

## Installera Matplotlib

Gör så här för att installera Matplotlib om det inte redan finns installerat. Öppna en terminal från menyn.  
   -  Windows: View > Terminal.
   -  macOS: Terminal > New Terminal
   -  Linux: ???


{{% notice style="warning" title="Terminal vs Python REPL" %}}

Om du i terminalen ser en prompt som ser ut så här `>>>` är du kvar i en
terminal där du tidigare startat ett Python REPL. Du behöver då starta en ny
terminal för att gå vidare. 

När prompten ser ut så här `$` vet du att du är terminalen och inte i Python REPL.
{{% /notice %}}

Vid prompten i terminalen skriver du nu in följande och trycker enter. 

``` text 
pip install matplotlib
```

Om detta inte fungerar kan du istället pröva med följande. 

``` text 
pip3 install matplotlib
```

