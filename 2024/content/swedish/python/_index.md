---
title: Python
weight: 1003
---

På kurser längre fram i din utbildning kommer du få lära dig
programmeringsspråket [Python][wp-python]. I denna modul kommer du få testa på att:

-  använda Python som en interaktiv miniräknare (Python REPL)
-  skapa och köra ett enklare Python program
-  rita grafer med Python, NumPy och Matplotlib.

[wp-python]: https://sv.wikipedia.org/wiki/Python_(programspr%C3%A5k)


## Anaconda och Spyder

Vi kommer använda oss av [Anaconda][anaconda] och [Spyder][spyder] för att testa på Python. 

- På universitetets datorer finns Anaconda och Spyder tillgängliga.
- För att vara förberedd inför kommande kurser är det starkt rekommenderat
  att du försöker [installera Anaconda][download-anaconda] på din egen
  dator. 
  
[download-anaconda]: https://www.anaconda.com/download/

[anaconda]: https://en.wikipedia.org/wiki/Anaconda_(Python_distribution)

[spyder]: https://en.wikipedia.org/wiki/Spyder_(software) 


  
## NumPy

[NumPy][numpy] är ett bibliotek som används för numeriska beräkningar i Python. 

[numpy]: https://numpy.org/

## Matplotlib

[Matplotlib][matplotlib] är ett bibliotek som tillsammans med NumPy gör det
möjligt att skapa olika typer av grafiska visualiseringar i form av grafer och
diagram. 

[matplotlib]: https://matplotlib.org/

## Viktiga begrepp

Förkortningen [REPL][repl] står för Read Evaluate Print Loop och används för
textbaserade system där man kan mata in kommandon av olika slag vilket i sin tur
resulterar i någon form av textbaserat svar tillbaka. 

[repl]: https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop
Ett svenskt namn för REPL är [kommandotolk][kommandotolk].

[kommandotolk]: https://sv.wikipedia.org/wiki/Kommandotolk

En [terminal][terminal] är ett texbaserat gränssnitt som låter dig ge kommandon till
operativsystemet. En terminal är en sorts REPL. 
 

[terminal]: https://sv.wikipedia.org/wiki/Terminalemulator

Ett **Pythonprogram** lagras i en fil på din dator. Du kan sedan låta Python
köra programmet från början till slut. 

Med hjälp av ett **Python REPL** kan du skriva in Pythonkod en rad i taget för
att steg för steg testa dig fram. Efter varje rad (kommando) du matar in skrivs
resultatet (om det finns något) ut automatiskt innan du kan mata in nästa
kommando. 

En **Prompt** är en eller flera symboler som används för att markera att ett
REPL är redo att ta emot ett nytt kommando. Vanligt är att: 

- `$` används som prompt i **terminalen**.
- `>>>` används som prompt i **Python REPL**.

En [textredigerare][textredigerare] eller **editor** eller **kodeditor** är ett datorprogram för att redigera
oformaterad text, i den meningen att filen inte innehåller dolda koder för
textstorlek, typsnitt och liknande.

[textredigerare]: https://sv.wikipedia.org/wiki/Textredigerare

En [Integrated Development Environment (IDE)][ide] är ett program som innehåller en samling funktioner
avsedda att underlätta vid programmering. 

[ide]: https://sv.wikipedia.org/wiki/Integrerad_utvecklingsmilj%C3%B6

[Spyder][spyder] är ett program som kombinerar en **kodeditor**, ett **Python
REPL** som då kallas **Python Console** och funktioner för att visa grafik.
Spyder är ett exempel på en IDE. 


En [operator][operator] är inom matematiken en symbol eller funktion som representerar en
matematisk operation. 

[operator]: https://sv.wikipedia.org/wiki/Operator

En [operand][operand] är inom matematiken ett av invärdena (argumenten) till en
operator. Till exempel i beräkningen `3 + 6` är `+` operatorn och `3` och `6`
operanderna.

[operand]: https://sv.wikipedia.org/wiki/Operand

En operator som tar två operander kallas [binär operator][binär-operator]. Några exempel på
binära aritmetiska operatorer är `+`, `-`, `*` och `/` som står för att två element
skall adderas, subtraheras, multipliceras respektive divideras.

[binär-operator]: https://sv.wikipedia.org/wiki/Bin%C3%A4r_operator

Ett [uttryck][uttryck] är i matematik meningsfull sammanställning av tecken, det vill
säga tecken ordnade så att de går att tolka matematiskt. Inom programmering
avser man med ett uttryck något som kan beräknas till ett värde. 

[uttryck]: https://sv.wikipedia.org/wiki/Matematiskt_uttryck

Av programmerare brukar text som omslutes av enkla eller dubbla citattecken
kallas för en **sträng**. Exempel på strängar: `"Hej på dig!"`, `'Tack skall du
ha'`.
