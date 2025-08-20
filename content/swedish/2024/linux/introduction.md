---
title: Introduktion
weight: 20
---

Ett Operativsystem är i korthet ett system som fördelar en dators resurser till
olika program. De mest kända operativsystemen idag är Microsoft
[Windows](https://www.microsoft.com/en-us/windows/), [Mac
OS](http://www.apple.com/osx/) och [Linux](https://www.kernel.org/), men det
finns många fler. Linux[^GNU/Linux] bygger på [öppen källkod][open-source]
(engelska: open source), vilket innebär att vem som helst lagligt kan se och
ändra hur det fungerar. Därför är det oerhört flexibelt och används för allt
från mobiltelefoner till superdatorer. Uppsala universitets Linux-system
använder en populär version av Linux som kallas [Ubuntu][ubuntu].

[wp-windows]: https://sv.wikipedia.org/wiki/Microsoft_Windows
[wp-linux]: https://sv.wikipedia.org/wiki/Linux
[wp-macos]: https://sv.wikipedia.org/wiki/Mac_OS
[open-source]: https://sv.wikipedia.org/wiki/%C3%96ppen_k%C3%A4llkod
[ubuntu]: https://sv.wikipedia.org/wiki/Ubuntu

## Användargränssnitt

Användargränssnittet på Linux-systemet är konfigurerat för att se ut och bete
sig likt Windows och Mac OS. Detta gör att du sannolikt kommer kunna använda dem
på liknande sätt som de datorer du är van vid sedan tidigare.


[computer-labs]: http://www.it.uu.se/datordrift/maskinpark/labbsalar

##  Hemkatalogen

Varje student har en personlig hem-mapp kopplat till Linux-kontot, där även
inställningar för program sparas. Kontot är döpt efter ditt användarnamn. Detta
fungerar på samma sätt som på de flesta plattformar. Med andra ord kommer dina
inställningar finnas kvar när du loggar in igen.

{{% notice style="warning" title="Lagringsutrymme" %}}

I dagsläget är varje students lagringskvota ca 250 Megabyte. Med en
nedladdningshastighet av 100 Mbit/s skulle det fyllas upp på 20 sekunder.
Eftersom detta inkluderar
[cache](http://askubuntu.com/questions/102046/is-it-okay-to-delete-cache)-filer
och annan tillfällig data från program krävs ständig uppmärksamhet, då program
kan sluta fungera utan fritt lagringsutrymme. Moderna webbläsare tenderar att
göra detta mycket snabbt.

{{% /notice %}}


## Filhantering

Du kan bläddra i din hemkatalog genom att dubbelklicka på mappen **Home** på
skrivbordet. Då öppnas en grafisk filhanterare som beter sig likt den i Windows
och Mac OS. Du kan dubbelklicka på filer och mappar för att öppna dem. Tänk dock
på att program som är gjorda för Windows och Mac OS inte alltid fungerar på
Linux.

{{< figure 
    src="/images/2024/linux/filhanteraren.png"
    title="Filhanteraren i Ubuntu."
>}}

Verktygsfältet näst längst upp till höger låter dig söka, visa som lista och
(via kugghjulet) skapa nya filer och mappar. Precis som i de flesta grafiska
filhanterare kan du använda musen för att markera flera filer eller flytta dem
mellan mappar, genom att klicka, dra och släppa.

## Spara endast filer under din hemkatalog

Spara alltid dina filer under din hemkatalog. Filer som sparas utanför
hemkatalogen raderas när du loggar ut.


## Starta program

Genom att klicka på ikonen längst upp till vänster på skrivbordet får du upp en meny, som
liknar **startmenyn** i Windows. Där listas ett antal program under olika
kategorier. Du öppnar dessa genom att klicka på dem.

## Kända problem

Sedan Linux-systemet blev driftsatt under hösten 2015 finns det en del buggar
som ställer till problem för användare. Exempel på dessa är

+ Anslutning av USB-minnen
+ In- och utloggningssvårigheter
+ Felaktig skärmupplösning
+ Problem med att komma ifrån skärmsläckaren

En fullständig lista med åtgärder på dessa problem finns
[här](http://www.it.uu.se/datordrift/faq/thinlinc%20#TipsAndProblems).



[^GNU/Linux]: Att använda namnet "GNU/Linux" istället för "Linux" kan anses vara mer korrekt och ger erkännande åt [GNU-projektet](https://www.gnu.org/gnu/thegnuproject.en.html).
