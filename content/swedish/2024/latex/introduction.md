---
title: Introduktion
weight: 10
---

*LaTeX* är ett *typsättningssystem* som används för att skapa vetenskapliga artiklar och tekniska rapporter.

## Fördelar med LaTeX

Det finns ett antal fördelar med att skriva dokument i LaTeX.

### Fokus på innehåll

En fördel med LaTex är att dokumentets innehåll (som text, vilka bilder som finns med och vad som står i tabeller) är frikopplat från dokumentets utseende rent estetiskt (som radavstånd och typsnittsstorlekar). Detta gör att du kan fokusera på rapportens innehåll och att "skelettet" för rapportens utseende kan återanvändas till framtida rapporter. 

### Konsekvent formatering

För att bestämma hur det färdiga dokumentet ska se ut gör du olika typer av
inställningar som sedan gäller för hela dokumentet. Du kommer alltså slippa
problemet med att olika avsnitt skiljer sig i stil, eftersom hela dokumentet
följer samma regler. LaTeX är även väldigt bra på att rendera matematiska formler.

### Standard för vetenskapliga rapporter

LaTeX och andra snarlika system är något av en standard inom många tekniska och
vetenskapliga områden vid framställande av tidningsartiklar, vetenskapliga
avhandlingar och rapporter.

LaTeX kan också hantera referenser på ett bra sätt och det är lätt att få ett snyggt och enhetligt utseende på det slutliga dokumentet.


## Skaffa LaTeX

Du kan antingen köra LaTeX online eller lokalt på din dator.

### Skapa LaTeX-dokument online

I dagsläget är Overleaf förmodligen det bästa alternativet vad gäller online-redigerare:

+ [Overleaf](https://www.overleaf.com/)
    - Stöd för inloggning via Google- och Twitterkonto, eller e-postadress/lösenord
    - I princip hur många dokument (s.k. *projekt*) som helst kan skapas och lagras på Overleaf. 
    - Det är gratis att låta flera olika skribenter bidra till ett och samma
        dokument.
    - Dokument kan inte "låsas" utan att betala, finns fler extrafunktioner man kan betala för.
    - Integrerar väl med Dropbox, Github och Zotero om man så önskar.
   - Har stöd för editor-syntax, dvs kan bete sig som Emacs och Vim om man är bekant med dessa.

Overleaf är mycket lätt att komma igång med och rekommenderas att använda för den här modulen om du inte redan har en nedladdad version på din dator.



### Använda LaTeX lokalt

För att installera ett TeX-system lokalt beror det på vilket operativsystem du använder.

+ Windows-användare kan välja mellan dessa:
    - [TeX Live](https://www.tug.org/texlive/windows.html) är den "officiella" versionen som även har större fokus på säkerhet.
    - [MikTeX](https://miktex.org/download) är mer anpassad för Windows specifikt, vilket innebär att det *känns* mer som ett Windows-program (på gott och ont).
+ Mac OS-användare rekommenderas använda [MacTeX](https://tug.org/mactex/).
+ För Linux beror det lite på vilken distribution du använder:
    - Ubuntu-baserade distributioner kan följa denna [guide](https://help.ubuntu.com/community/LaTeX)
    - För Arch-användare gäller [denna](https://wiki.archlinux.org/index.php/TeX_Live)
    - För Gentoo-användare gäller [denna](https://wiki.gentoo.org/wiki/TeX_Live)
    - För övriga hänvisar vi till respektive distribution för support.

I de flesta lokala installationer ingår det en textredigerare. Du kan dock redigera dokumenten i andra program, som Notepad, Visual Studio Code, Vim, Emacs eller liknande.



## Strukturen av LaTeX-projekt

I följande avsnitt beskrivs hur ett LaTeX-projekt är strukturerat. 

### Filstruktur

Varje dokument som skrivs med LaTeX har en `.tex`-fil, som ofta kallas för `main.tex`.
Beroende på storlek av projektet, kan denna fil antingen innehålla allt material, eller agera som ett skelett där exempelvis inställningar och/eller textavsnitt importeras.
Bilder och bibliografi brukar placeras separat.

### Dokumentets struktur

Huvudfilen inleds med en *preamble*, där inställningar gällande dokumentets stil, titel, författare och liknande brukar stå. Det som *alltid* finns med är inställningen `\documentclass`.

Därefter börjar delen som själva texten står i. Du känner igen detta genom att den börjar med raden `\begin{document}` och slutar med `\end{document}`

### Grundläggande syntax

Kommandon i LaTeX följer stilen `\kommando[alternativ,meralternativ]{inställning}`.
Ovannämnda `\documentclass` är ett bra exempel.
För att skriva ett dokument av typen `article` med 11 punkters typsnittsstorlek för utskrift på A4, inleder du med följande rad:

```latex
\documentclass[11pt,a4paper]{article}
```

Det finns även många andra typer av dokument, som `book`, `report` och liknande.

Delar som använder sig av särskild syntax, som tabeller, beräkningar och till och med hvudtexten, skapas med `\begin{miljö} ... \end{miljö}`. Detta illustreras kanske enklast med ett exempel; på detta sätt kan man centrera text:

```latex
Denna text är inte centrerad.

\begin{center}
    Denna text är centrerad.
\end{center}

Denna text är inte heller centrerad.
```

Det resulterande dokumentet ser ut så här:

{{< figure src="/images/2024/latex/latex-centered.png" title="Centrerad text i LaTeX" >}}

## Påbörja ett LaTeX-dokument



### Skapa ett dokument (editor)

Om du valt att jobba med LaTeX lokalt på din dator börjar du med att öppna ett
helt tomt dokument i din editor.

### Skapa ett dokument (Overleaf)

När du har skapat ett konto hos [Overleaf](https://www.overleaf.com/) kan du skapa ett nytt projekt från startsidan genom att klicka på ikonen *New project* i det övre vänstra hörnet. För att få ett tomt dokument att skriva i väljer du sedan *Blank Project* i listan. Du kommer då få något som liknar detta:

{{< figure src="/images/2024/latex/overleaf-intro.png" title="Start till ett projekt i Overleaf" >}}

I sidofältet längst till vänster finns de filer du jobbar med. I den vänstra av de två stora rutorna skrivs text och kommandon. Dokumentets utseende visas i den högra rutan. För att i högra rutan se resultatet av det man skrivit i den vänstra rutan måste dokumentet först kompileras genom att trycka på den gröna knappen "Recompile".

Instruktionerna som följer utgår från ett helt tomt dokument utan några kommandon, så du kan ta bort allt som står i den vänstra rutan. 

### Grundläggande kommandon

Vi kommer nu att ha en noggrann genomgång av vad alla nödvändiga kommandon gör. Det kommer finnas ett kopierbart exempel i slutet av detta avsnitt som du kan använda.


### Preamble

*Preamble* är dokumentets inställningar. Det finns några praktiska inställningar som rekommenderas för dokument som skrivs på det svenska språket avsett för utskrift på formatet A4.

| Kommando  | Förklaring |
| --------- | ---------- |
| `\documentclass[12pt,a4paper]{article}` | Väljer dokumenttyp |
| `\usepackage[swedish]{babel}` | Ställa in dokumentets språk |
| `\usepackage[T1]{fontenc}`    | Förbättrar rendering av tecken som `å ä ö` |
| `\usepackage[utf8]{inputenc}` | Förbättrad tolkning av specialtecken |

`\usepackage` importerar helt enkelt ett *paket* med vissa inställningar för användning i ditt dokument. De används även för att lägga till extra kommandon, som särskilda matematiska tecken.

Språkvalet ställer in också automatiskt genererade ord, som "Innehåll" i innehållsförteckningen, samt hur radbrytningar hanteras.


### Dokumentmiljön

Efter preamble kan du börja skriva själva innehållet i miljön `document` . Ett komplett exempel följer nedan:

```latex
\documentclass[12pt, a4paper]{article}
\usepackage[swedish]{babel}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}

\begin{document}
Dokumentets innehåll står här!
\end{document}
```

När du har detta bör du kunna kompilera och se saker dyka upp i förhandsvisningen av det färdiga dokumentet (höger sida på Overleaf)!

## Skriva ett LaTeX-dokument

Syntaxen kan verka lite skrämmande i början, men så fort man lär sig vad alla kommandon betyder är det mycket enkelt att förstå och använda sig av dem.

Eftersom det finns många användningsområden för LaTeX är det inte möjligt att lära sig *alla* kommandon och hur *allt* fungerar utantill. Det viktigaste i denna modul är att prova på de delar som är relevanta för din utbildning, så att du vet att du kan kolla upp och göra det som krävs när det väl behövs.


### Strukturera text

Du använder kommandona `\section{rubrik}`, `\subsection{underrubrik}` och `\subsubsection{underunderrubrik}` för att skapa rubriker. Dessa skrivs i miljön `document` och kommer automatiskt att synas i innehållsförteckningen. Om du inte vill ha numrerade rubriker så lägger du till en asterix innan rubrikens namn (se exempel).

För att strukturera upp brödtexten skapas olika stycken antingen genom att helt enkelt lämna en blankrad mellan styckena eller sätta ut `\par` för att börja ett nytt stycke. Val mellan indrag för nya stycken, blankrad och anpassning av dessas storlek görs i preamble. I koden används dock alltid blankrad eller `\par` likt i exemplet nedan. (Irrelevanta delar av preamble står inte med i exemplet) 

```latex
\documentclass[12pt, a4paper]{article}

% Styckesindelning (Detta är en kommentar förresten)

\setlength{\parskip}{1em} % Lämna en blankrad
\setlength{\parindent}{0em} % Indentera inte nya stycken

\begin{document}

% Numrerade rubriker

\section{Numrerad rubrik}
\subsection{Numrerad underrubrik}

Detta är ett väldigt kort exempel stycke.

Detta är ett annat stycke. Notera att det är en blankrad mellan styckena.

% Onumrerade rubriker

\section*{Onumrerad rubrik}
\subsection*{Onumrerad underrubrik}

Detta är ett väldigt kort stycke. \par Detta är ett annat stycke.

\end{document}
```


{{< figure src="/images/2024/latex/sections.png" title="Exempel på styckesindelning i LaTeX" >}}

### Skapa en titel

Du lägger till kommandona `\title{Dokumentets titel}`, `\author{Författare}` och `\date{Datum}` för titel, författare respektive datum i preamble. Om du inte anger ett datum i `\date` kommer dagens datum att användas automatiskt.

I miljön `document` skriver du sedan `\maketitle` där du vill ha titeln.

Ett exempel följer nedan. Notera att de irrelevanta delarna av preamble inte finns med.


```latex
\title{Titel}
\author{Författare}

\begin{document}
\maketitle

Dokumentets innehåll står här!
\end{document}
```

{{< figure src="/images/2024/latex/titel.png" title="Enkel titel i LaTeX" >}}


### Generera en innehållsförteckning

För att skapa en innehållsförteckning lägger du till kommandot `\tableofcontents` där du vill ha den.
Alla *numrerade* rubriker kommer då dyka upp i den.

{{< figure src="/images/2024/latex/toc.png" title="En (något överflödig) innehållsförteckning." >}}

### Listor

Den enklaste typen av lista gör du med miljön `itemize`, där varje post i listan påbörjas med `\item`

```latex
\begin{itemize}
    \item En grej
    \item En till grej
\end{itemize}
```

{{< figure src="/images/2024/latex/itemize.png" title="Lista med itemize." >}}

För att göra nästlade listor påbörjar du en ny miljö inuti den befintliga.

Du kan även göra numrerade listor med miljön `enumerate`.

```latex
\begin{enumerate}
    \item En numrerad grej
        \begin{enumerate}
            \item En nästlad, numrerad grej
            \item En till nästlad, numrerad grej
        \end{enumerate}
    \item En till numrerad grej
\end{enumerate}
```

{{< figure src="/images/2024/latex/enumerate.png" title="Nästlad lista med enumerate." >}}

För att skriva ordboksliknande listor använder du enklast miljön `description`. Varje inlägg skrivs då `\item[Term]`

```latex
\begin{description}
    \item[En grej] Grejens förklaring
    \item[En till grej] En till förklaring
\end{description}
```

{{< figure src="/images/2024/latex/description.png" title="Lista med tillhörande förklaringar." >}}


### Tabeller

För att göra en tabell använder du miljön `tabular`. Kolumnernas utseende specificeras med de alternativ som finns i tabellen nedan:

| Alternativ | Förklaring |
| :--: | ---- |
| `l`  | vänster-justifierad kolumn |
| `c`  | centrerad kolumn |
| `r`  | höger-justifierad kolumn |
| \| | separator med enkel linje |
| \|\| | separator med två linjer |

Väl i tabellen använder du `&` för att separera kolonner och `\\` för att avsluta en rad. Om du vill göra en linje mellan två rader använder du kommandot `\hline`. 

Detta kan låta lite klurigt, så här följer ett kopierbart exempel som du gärna kan experimentera med:

```latex
\begin{tabular}{| l c || r}
    Första kolumnen & Andra kolumnen        & Tredje kolumnen \\
    \hline
    Denna är vänsterjustifierad
                    & Denna är centrerad    & Denna är högerjustifierad \\
    Denna har en linje till vänster
                    & Två linjer till höger & Två linjer till vänster \\
\end{tabular}
```

{{< figure src="/images/2024/latex/tabular.png" title="Den resulterande tabellen" >}}

Notera att mellanslag och radbrytningar i den råa texten inte spelar någon roll. Därför kan du anpassa detta för att göra det så läsligt som möjligt för dig själv.

### Formler och ekvationer

I detta avsnitt är målet att visa grunderna för matematiska syntax i LaTeX. Eftersom detta är en av LaTeX stora styrkor finns det förstås mycket mer att säga om detta; en mer omfattande guide kan du hitta [här](https://en.wikibooks.org/wiki/LaTeX/Mathematics).

För att använda matematik i LaTeX rekommenderas paketet `mathtools`. Du lägger till den genom att lägga till

```latex
\usepackage{mathtools}
```

i preamble.

I princip all tänkbar formatering som är relevant för matematik går att formatera i LaTeX. Faktum är att det var ett av skälen till att det skapades.

#### Grundläggande matematisk syntax

Du använder samma tecken som i de flesta datorprogram, dvs `+ - / ^` för att skriva formler, med undantag för uppställda bråk och multiplikation:

+ Uppställda bråk görs med `\frac{täljare}{nämnare}`. Exempelvis genererar du \(\frac{a}{b}\) genom att skriva `\frac{a}{b}`
+ För multiplikationstecken är det snyggast att använda `\cdot`, t.ex. `2 \cdot 3` för att skriva \\(2 \cdot 3\\).
+ Parenteser skrivs som vanligt, men måsvingar och hakparenteser kräver särskild formatering (`\` framför).
+ Grekiska tecken skrivs ut med `\` framför precis som de flesta kommandon i LaTeX. Exempelvis ger `\alpha` tecknet \\(\alpha\\). För versaler inleds kommandot med versal: `\Gamma` ger tecknet \\(\Gamma\\).
+ För att gruppera exempelvis en potens med flera tecken i exponenten, används `{}`. Exempelvis formateras \\(x^{2c}\\) med `x^{2c}`.
+ Du kan även göra subskript med hjälp av `_`. För att visa \\(x_0\\) skriver du alltså `x_0`.

**Matematisk syntax måste dock skrivas i speciella miljöer, vilka beskrivs nedan.**
#### Matematik i löpande text

För att skriva ut matematiska formler och dylikt i löpande text omger du den matematiska syntaxen med två `$`. Det är klokt att använda detta även runt variabler och konstanter som du skriver om i texten för att tydligt visa att de är just variabler.

Om du exempelvis vill diskutera \\(\lambda_{\alpha/2}\\) i din text skriver du 

```latex
$\lambda_{\alpha/2}$
```

#### Ekvationer och beräkningar

Om man vill att ekvationer eller matematiska beräkningar inte ska stå i texten utan vara som egna "figurer" kan kommandona `\begin{equation}` och `\end{equation}` användas. Samma matematiska syntax som beskrivits tidigare gäller även i denna miljö.  

```latex
Formeln för volymen av en kon:

\begin{equation}

V=\frac{\pi r^2h}{3}

\end{equation}
```

{{< figure src="/images/2024/latex/ekvation.png" title="Uppställda ekvationen för en kon" >}}

### Specialtecken

En stor skillnad mot att skriva i ex. Microsoft Word,
är att LaTeX inte gissar att du menar något annat än vad du skriver. Word
ändrar glatt raka citationstecken `"` till sneda `”` och bindestreck `-` till
tankestreck `–`, men i LaTeX behöver du ange rätt tecken själv.
Eftersom några tecken är definierade att inleda kommandon måste dessa anges med ett
omvänt snedstreck `\` som prefix om du vill skriva ut dessa i texten. I tabellen nedan ser du några vanliga tecken och
hur du skriver dem i Latex. [^special-characters]

[^special-characters]: http://www.parnyman.com/files/texts/latexintro.pdf

| Tecken | Utseende | LaTeX-kod |
| ----   | ----     | ----      |
| Enkelt citationstecken* | ’ |  `'` |
| Dubbelt citationstecken* | Vänster: “ eller Höger: ” | Vänster: `` och Höger '' (två apostrofer ' )| 
| Ampersand | & | `\&` | 
| Procenttecken | % | `\%` | 
| Dollartecken | $ | `\$` |

***Notera:** På svenska så används högra citationstecken både för att öppna och stänga citat. På engelska används vänster för att öppna och höger för att stänga. Läs mer på t.ex. [wikipedia](https://sv.wikipedia.org/wiki/Citattecken#Dubbla_citattecken). 

### Grafik

För att använda grafik och bilder i LaTeX använder du paketet `graphicx`.
Du gör detta genom att lägga till följande rad i preamble.

```latex
\usepackage{graphicx}
```
Generatorn kommer nu leta efter bilder i samma mapp som du har din `main.tex`-fil i.

För att därefter lägga in en bild i dokumentet skriver du `\includegraphics{bildnamn}`, utan filändelse. Du kan specificera storlek på bilden i kommandots alternativ: om du exempelvis vill lägga in bilden `foto.jpg` med halva textens bredd, skriver du `\includegraphics[width=0.5\textwidth]{foto}`.

Miljön `figure` låter dig även skapa bildtexter och referenser till dina bilder och diagram. Ett enkelt exempel följer nedan:

```latex
Se figur \ref{fig:foto1}.

\begin{figure}[h]
    \includegraphics[width=0.5\textwidth]{foto}
    \caption{Ett foto}
    \label{fig:foto1}
\end{figure}
```

+ Alternativet `h` för miljön specificerar att figuren ska placeras "här".
+ `\caption` skriver ut figurens nummer samt figurtext.
+ `\label` gör att du kan referera till bilden med kommandot `\ref`. LaTeX genererar då automatiskt löpande figurnummer för varje figur; du behöver alltså inte ändra dessa själv om du exempelvis skulle lägga till en ny figur tidigare i texten.

{{% notice style="info" title="Klickbara referenser" %}}

Ladda gärna paketet `hyperref`; om du då klickar på en referens kommer den ta dig till 
bilden den refererar till!

{{% /notice %}}

{{< figure src="/images/2024/latex/figure.png" title="En kul figur i LaTeX." >}}

### Referenser

LaTeX har stöd för flera omfattande system för att hantera referenser. De två
vanligaste paketen för hantering av referenser är *bibtex* och *biblatex*. Bibtex kan vara lite svårare att lära sig men är bättre i långa loppet.

I följande exempel visar vi hur det kan se ut när paketet bibtex används för
att hantera referenser.

Referenser skrivs i ett **separat dokument** med **ändelsen `.bib`**. 

`referenser.bib` skrivs enligt följande syntax:
```latex
@misc{MultiRust,
title = {Multirust},
author = {Brian Anderson and others},
howpublished = "\url{https://github.com/brson/multirust}",
note = {visited on 2016-04-27}
}

@book{Tanenbaum2006,
author={Tanenbaum, Andrew S. and Woodhull, Albert S.},
title={Operating systems : design and implementation},
publisher={Pearson Prentice Hall},
address={Upper Saddle River, NJ},
year=2006,
edition={3. ed.},
isbn={0-13-142938-8 (korr.) (inb.)}
}
```

För att därefter citera en text skriver du helt enkelt `\cite{referens}`, exempelvis `\cite{MultiRust}`. För att URL-länken ska kunna skrivas ut kan du behöva inkludera paketet `\usepackage{url}`.

För att slutligen skriva ut bibliografin skriver du ett kommando för vilken stil referenserna ska ha `\bibliographystyle{plain}` samt ett kommando för att skriva ut referenserna `\bibliography{referenser.bib}`.

Vissa program och paket är inte kompatibla med vissa standarder. Exempelvis kan du inte använda IEEE-standarden med biblatex i Overleaf, men däremot ska det fungera med TeX-Live om du har en ny version.

### Kommentera text

Du kan göra kommentarer som ignoreras av renderingen genom att påbörja raden med `%`.
Detta är smidigt för att göra markörer som "TODO" för saker som du ska komma ihåg att göra, eller tillfälligt kommentera bort delar av dokumentet när du experimenterar.

```latex
Detta syns i det färdiga dokumentet!

% Detta syns inte i det färdiga dokumentet!
```

### Tips och trix

- En bra hemsida som man kan använda av för att översätta matematiska uttryck direkt till LaTEX-kod är [MathPix](https://www.mathpix.com/). Fördelen med denna hemsida är att konverteringen tar mindre än en minut.  

- En annan bra hemsida är [Tables Generator](https://www.tablesgenerator.com/), den gör det väldigt enkelt att skapa tabeller för LaTeX och gör det möjligt att klistra in tabelldata direkt från tex Excel eller Matlab.

- Om man har som avsikt att skriva ett längre arbete eller rapporter med hjälp
  av LaTeX så finns det färdiga mallar som man kan använda sig av. Det enda
  som behöver göras är att ladda ner en valfri mall och fylla den med valfri
  innehåll. Det kan dock vara en bra idé att skapa sin egen mall, det är väldigt
  bra träning och man lär sig mycket på vägen.

- För grupparbeten i Overleaf när flera ska jobba i samma dokument går det att skapa en delbar länk i "share"-menyn som man kan skicka till sin grupp. Att bjuda in andra kräver ett premium konto men det är gratis att dela en redigerbar länk.

- För en mer ingående förklaring av någon del kan [Overleafs dokumentation](https://www.overleaf.com/learn) vara bra att titta på, oavsett om du använder Overleaf eller någon annan Latex distribution.


