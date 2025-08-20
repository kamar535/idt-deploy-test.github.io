---
title: Uppgift
weight: 20
assignment: mandatory
---

## Mål

Efter att du blivit godkänd på denna uppgift kommer du att känna till hur du:

- skapar ett LaTeX-dokument som går att rendera (som PDF)
- lägger till paket i preamble
- använder grundläggande kommandon för att generera en titel, innehållsförteckning och matematiska uttryck
- använder miljöer (*environments*)
- infogar en (numrerad) lista
- infogar en bild med tillhörande bildtext och referens
- använder bibtex för att referera och skapa en källförteckning



## Detta behöver du

Det är starkt rekommenderat att du skapar ett konto på [Overleaf](https://www.overleaf.com)
men om du föredrar någon
annan metod behöver du:

+ en LaTeX-kompatibel editor
+ möjlighet att rendera PDF-filer
+ tillgång till paketen *babel*, *fontenc*, *inputenc*, *bibtex*.
    + De flesta kompletta LaTeX-distributioner har dessa inbyggda.

Inlämning för alla uppgifter sker i Studium. För detta krävs ett studentkonto.

## Uppgift

Materialet som tas upp i uppgiften diskuteras på [introduktionssidan till LaTeX](../introduction).

### Del 1: skapa ett grundläggande dokument

1. Öppna din favorit-editor [(så här kommer du igång med Overleaf)](../introduction/#overleaf).
2. Skapa ett dokument av typen `article` med alternativen `12pt, a4paper`.
3. Lägg in början och slut för miljön `document` med hjälp av kommandona
   `\begin` och `\end`
4. För att testa om du har gjort rätt kan du skriva någonting i miljön `document` och kompilera. Din text borde då synas i det renderade dokumentet.

Vid det här laget ska dokumentet kunna renderas för att skapa en PDF-fil.


### Del 2: Ladda in paket

1. Använd `\usepackage` för att ladda in `babel` med alternativet `swedish`
2. Använd `\usepackage` för att ladda in `fontenc` med alternativet `T1`
3. Använd `\usepackage` för att ladda in `inputenc` med alternativet `utf8`
4. Använd kommandot `\tableofcontents` i miljön `document`

{{% notice style="info" title="Kom ihåg!" %}}

Dokumentet saknar ännu rubriker. Därför kommer bara texten "Innehåll" renderas i innehållsförteckningen då du kompilerar.

{{% /notice %}}

Om dokumentet fortfarande renderas utan problem har du tillgång till dessa
paket. Om inte har du troligen gjort något fel, eller råkat använda en minimal
installation av LaTeX (om du använder något annat än Overleaf).


### Del 3: Använda enkla kommandon för att skapa en titel

1. Skriv följande 3 kommandon i preamble:
    + Använd `\title` för att skriva in namnet på ditt **studentkonto** som
   titel.
    + Använd `\author` för att skriva in ditt **riktiga** namn som författare.
    + Använd `\date` för att skriva in datumet då du påbörjar detta dokument.
2. Skriv kommandot `\maketitle` direkt efter `\begin{document}`.

En titel borde nu dyka upp när du renderar dokumentet.


### Del 4: Skapa ny sida och rubriker
Påbörja en ny sida i ditt dokument med hjälp av kommandot `\newpage`. Skapa sedan fyra rubriker med kommandot `\section` vilka du döper till:

+ Numrerad lista
+ Ekvation
+ Bild
+ Citat

{{% notice style="info" title="Kom ihåg!" %}}

Innehållsförteckningen på första sidan i ditt dokument bör uppdateras och nu innehålla de fyra nyskapade rubrikerna. 

{{% /notice %}}

### Del 5: Numrerad lista
Placera följande kommandon under rubriken *Numrerad lista* i dokumentet.

1. Skapa en *numrerad lista* med hjälp av miljön `enumerate`.
2. Skapa följande punkter i listan:
    + Första punkten
    + Andra punkten
    + Tredje punkten

Du bör nu ha en numrerad lista i ditt dokument:

{{< figure src="/images/latex/latex-uppgift-enumerate.png" title="En numrerad lista." >}}
### Del 6: Ekvation
Placera följande kommandon under rubriken *Ekvation* i dokumentet.

1. Använd miljön `equation` för att göra en ekvationsmiljö.
2. Skriv formeln för volymen av ett klot (se nedan).

I det renderade dokumentet ska ekvationen se ut så här:
{{< figure src="/images/latex/ekvation-uppgift.png" title="Volymen av ett klot." >}}

### Del 7: Bild med tillhörande referens

1. Hitta en valfri bild och ladda upp i samma mapp som ditt nuvarande `main.tex`-fil.

2. Ladda in paketet `graphicx` så bilder kan renderas.

3. Infoga bilden under rubriken *Bild* med hjälp av miljön `figure`.

4. Ge bilden:
    + ett referensnamn med hjälp av kommandot `\label`.
    + en figurtext med hjälp av kommandot `\caption`. 

5. Skriv en valfri mening och gör en referens till bilden genom kommandot `\ref`. Referensen ska automatiskt formateras till ett figurnummer.

{{% notice style="info" title="Kom ihåg!" %}}

Ladda paketet `hyperref` om du vill att referensen ska vara klickbar!

{{% /notice %}}

### Del 8: Citat och källreferens

1. Hitta ett citat från en valfri artikel som du placerar under rubriken *Citat*. **Kom ihåg att sätta ut citattecken.**

2. Referera till citatet genom att skriva `\cite{referens}` där du byter "referens" mot ett valfritt passande namn till din referens.

3. Skapa en **ny fil** som du döper till `referenser.bib` i samma mapp som `main.tex`-filen. I den här uppgiften räcker det att inkludera författare, rubrik samt vilket år artikeln publicerades.
    + När man refererar till en artikel använder man sig av referenstypen `@article{...}`.
    + Se syntax på [introduktionssidan för LaTeX](../introduction/#referenser) för hur referenser ska skrivas.

3. För att få en synlig källreferens till citatet måste bibliografin skrivas ut. Detta gör du genom att lägga till `\bibliographystyle{plain}` följt av `\bibliography{referenser.bib}` innan slutet av dokumentet.




### Slutgiltigt dokument

Den resulterande PDF:en ska nu ha en sida med titel och innehållsförteckning, fyra rubriker innehållande en numrerad lista, en ekvation, en bild och bildreferens och citat. En lista med referenser ska också finnas. Du kan använda bilden nedan som mall för hur sidorna i ditt dokument bör se ut.

{{< figure class="border" src="/images/latex/latex-final-uppg.png" title="Färdigt dokument." >}}

## Inlämning

Döp om den slutgiltiga PDF:en till `abcd1234_latex.pdf`, där du ersätter
`abcd1234` med  användarnamnet för ditt studentkonto. Lämna sedan in filen på
anvisad plats i Studium (UU) eller Canvas (ES/SLU).
