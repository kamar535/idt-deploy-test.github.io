---
menuTitle: På egen dator
title: Linux på egen dator
weight: 40
---

Här kan du som är intresserad av att installera Linux på din egen dator eller
använda Windows Subsystem for Linux (WSL) läsa mer om just detta. 


## POSIX och Linux

UNIX-system, som Linux och Mac OS, använder den så kallade
[POSIX-standarden](https://en.wikipedia.org/wiki/POSIX). Denna standard nyttjas
i senare kurser inom IT/KandDV. Det är därför en fördel om du som student fixar
så du kan använda ett Posix-system på någon av dina privata datorer. 

Windows-användare bör åtminstone känna till hur man installerar Linux eller
något annat Posix-kompatibelt på en dator. Linux är dessutom kul och lätt att
komma igång med på en vanlig hemdator.

## Installation på en virtuell maskin

Virtuella maskiner simulerar en dator vilket låter dig starta ett
operativsystem som om det vore vilken dator som helst!

Fördelarna är att det är riskfritt och mycket enkelt att komma igång med,
oavsett vilken dator du använder. Du slipper dessutom mycket krångel som kan
uppstå med icke-kompatibel hårdvara, i de flesta linux distributioner så
fungerar virtuella maskiner out-of-the-box.

Nackdelen med denna metod är främst att det är resurskrävande. Om din dator har
mindre än 4 GB RAM kommer många populära Linux-distributioner, som Ubuntu, vara
svåra att köra i virtuella maskiner. Detta eftersom virtuella maskiner delar
resurser med ditt *host* ("vanliga") operativsystem.

För att skapa virtuella maskiner använder man sig av en s.k. *hypervisor*. På
Windows eller Mac OS skulle detta kunna vara ett program som
[VirtualBox](https://www.virtualbox.org/) eller någon
[Vmware](https://www.vmware.com/products/desktop-hypervisor.html) variant.

VirtualBox är gratis och det finns en väldigt bra guide för hur man kommer igång
med det på deras [hemsida](https://www.virtualbox.org/manual/ch01.html). Se dock
till att virtualisering är påslaget. På Mac är virtualisering påslaget som
standard, och har varit i ett par år, på PC kan man behöva slå på det i BIOS.
Leta då efter *VT-X* om du har Intel processor eller *SVM* om du har AMD
processor.

En sak att notera är att med hypervisors som du installerar som program (typ 2) går
det inte att komma åt specialiserad hårdvara som GPU:er eller liknande från
virtuella maskiner. Kräver din applikation detta borde du titta på en annan
metod för att köra Linux eller typ 1 hypervisors. Typ 1 hypervisors är
definitivt utanför denna kurs men kan vara spännande att prova för den som är
intresserad.


## WSL


Windows Subsystem for Linux (WSL) är ett projekt utvecklat av Microsoft för att
ge enklare tillgång till Linux utvecklingsverktyg på Windows. Det finns
tillgängligt i Windows 10 (från version 1607). Det är relativt enkelt att komma
igång med, Microsoft har en
[guide](https://docs.microsoft.com/en-us/windows/wsl/install-win10).

En stor fördel med WSL över till exempel virtuella maskiner är att WSL ger
direkt tillgång till filsystemet på Windows. Har du redan påbörjat ett projekt
på Windows så behöver du inte flytta det till Linux bara för att du behöver ett
verktyg som inte finns på Windows. Det finns också möjlighet till
GPU-acceleration till skillnad från virtuella maskiner i typ 1 hypervisors (tex
VirtualBox).

Nackdelen med WSL är prestanda, även om prestandan har förbättrats kontinuerligt
sedan WSL släpptes så är den fortfarande inte lika bra som Linux på bare-metal
och kan i vissa fall vara sämre än i virtuella maskiner (kan vara bättre i vissa
fall också).


## Live-distribution


Denna metod syftar på att installera en distribution på, exempelvis, ett
USB-minne och starta om datorn till den. Det fungerar på ungefär samma sätt som
när du först installerar Windows på en tom hårddisk, med skillnaden att du har
ett komplett, användbart operativsystem.

Fördelen med live-distributioner är att de inte rör resten av datorn utan din
tillåtelse. Du kan alltså räkna med att ditt befintliga operativsystem är kvar
precis som det är. Dessutom kan du använda detta för att återställa data när ett
operativsystem har kraschat helt.

Nackdelen med detta är att prestandan begränsas av överföringshastigheten för
mediet det är installerat på. En SSD är exempelvis många gånger snabbare än ett
USB-minne. Dessutom är ofta externa lagringsenheter inte anpassade för det
slitage som hårddiskar och SSD:er är gjorda för, vilket kan leda till stora
problem efter längre tid (d.v.s. om datorn är påslagen länge).

Allt som behövs är en USB-minne, installationsmediet för distributionen du vill
prova och ett program för att skriva installationsmediet på minnet med (tex
Rufus på Windows och disk manager på Mac OS). När du skrivit installationsmediet
på USB-minnet så behöver du bara boota mot det. Många Linux-distributioner
installeras via en live-distribution så när du startat mot USB-minnet är du
igång.


## Bare-metal

Du kan även installera Linux på en systemdisk i datorn, s.k. bare-metal
installation. Det går både att ha det som enda operativsystem, eller sida vid
sida med exempelvis Windows. Det senare kallas för *dual-boot*.

Många Linux-distributioner gör bare-metal installation mycket enkel, men
eftersom det ofta innebär att göra fundamentala skillnader på en disk du redan
använder bör du göra en back-up på *allt* du vill ha kvar innan du börjar. Detta
gäller även om du vill använda dual-boot (även om du installerar på en annan
disk från datan du vill behålla).

Dessutom är det rekommenderat att ha någon form av återställningsmedia för den
dator du vill installera på, inklusive eventuella installationsnycklar. Tänk på
att om du bestämmer dig för att skriva över hårddisken och enbart använda Linux,
kommer även eventuella återställningspartitioner försvinna. Om du inte är
förberedd kommer du därmed behöva använda en annan dator för att återställa den
du har. Oavsett är det alltid en bra idé att ha ett separat återställningsmedia
(förslagsvis ett USB-minne), om exempelvis hårddisken går sönder.

Fördelen med Linux på bare-metal är att prestandan blir så bra den kan bli.
Nackdelen är att om du misslyckas med något riskerar att göra din dator
(åtminstone tillfälligt) oanvändbar, samt att du kan bli beroende av fungerande
drivrutiner. Wi-Fi, skrivare och ljud tenderar att vara det som leder till
störst kompatibilitetsproblem, men detta har blivit mycket bättre under senare
år och det *allra mesta* brukar fungera out-of-the-box, åtminstone på de
nybörjarvänliga Linux distributionerna.

Ett hett tips om det är första gången du installerar Linux och har ett
grafikkort från Nvidia är att börja med en distribution som förinstallerar
Nvidia drivrutiner. Det finns open-source drivrutiner som förinstalleras på de
flesta distributioner, så du kommer få bild även utan Nvidias egna drivrutiner,
men de har dålig prestanda och saknar många funktioner. På grund av Nvidias
licens får deras drivrutiner inte inkluderas utan måste installeras separat.
Vissa distributioner som Pop!_OS och Manjaro inkluderar dem dock ändå och kan
därför vara ett bra val om det är första gången.

Allt detta är väldigt lärorikt och har du aldrig installerat ett operativsystem
tidigare bör du definitivt testa vid tillfälle!


## Populära Linux-distributioner


Nedan följer en lista av vanliga Linux-distributioner för skrivbordsbruk. Den är inte på något sätt komplett, men ger förhoppningsvis några exempel på vad som finns. 

+ [Ubuntu](http://www.ubuntu.com/) är troligen den mest populära
    + Erbjuder kompatibilitet med en stor mängd hårdvara, eftersom kerneln inte alltid är den nyaste kan nyare hårdvara ibland vara lite svårare att få att fungera dock.
    + Fungerar out-of-the-box, dvs, du behöver oftast inte göra mycket för att få det att fungera.
    + Eftersom det har så många användare, finns många guider och program tillgängliga.
    - Gränssnittet är ganska resurskrävande och fungerar mindre bra på svagare laptops.
    - Har varit med om vissa skandaler gällande personlig data och programkompatibilitet
+ **Ubuntu deriverade distributioner** bygger direkt på Ubuntu och (de flesta) följer samma uppdaterings schema. Delar också många av för- och nackdelarna som Ubuntu har.
    + [Elementary OS](https://elementary.io/) bygger på mycket av den designfilosofi som ligger bakom Mac OS.
        + Gränssnittet är enhetligt, lätt att använda, är *mycket* stiligt och samtidigt resurssnålt.
        + Helt gratis, om du väljer att inte donera.
        + Bygger på Ubuntu och har samtliga av dess fördelar.
        - Det har dock samma kernel och är lite omständligt på nya datorer.
    + [Pop!_OS](https://pop.system76.com/) Anpassat för att vara ett bra insteg till Linux och ge en bekant men förbättrad användarupplevelse.
        + Gratis.
        + Utvecklas av en datortillverkare som specialiserar sig på hårdvara med
          stöd för Linux.
        + Har strömsparfunktioner för laptops förinbyggda, till exempel ges möjligheten att styra vilken grafikprocessor som används. 
        + Finns en variant med Nvidias drivrutiner förinstallerade.
+ [Linux Mint](https://www.linuxmint.com/) väldigt populär distribution som bygger på Ubuntu.
    + Är helt öppet och anpassat för användarvänlighet i första hand.
    + Du kan välja gränssnitt, där skrivbordsmiljön Xfce är det mest lättviktiga, men även Cinnamon fungerar bra på äldre datorer.
    + Bygger i grunden på Ubuntu och har därmed samtliga av dess fördelar.
    - Det har dock samma kernel och är lite omständligt på nya datorer.
+ [Debian](https://www.debian.org/distrib/) var grunden till Ubuntu och åtskilliga andra distributioner
    + Känt för sin stabilitet
    + Fungerar på nästan allt
    - Eftersom fokus ligger på stabilitet finns inte alltid tillgång till de nyaste programmen
+ **RHEL-baserade distributioner** och RHEL (Red Hat Enterprise Linux) i ordning av hur tidigt de uppdateras. Red Hat släpper uppdateringar i steg och ger möjlighet att välja distribution efter hur tidigt man vill få uppdateringar, och hur stor vikt man lägger vid stabilitet. Även om detta innebär att de skiljer sig en del så står de på samma grund och brukar därför grupperas.
    + [Fedora](https://getfedora.org/) Utvecklas av Red Hat för de som vill ha/behöver tillgång till nya funktioner tidigt.
        + Får nya funktioner tidigt.
        + Tidigt uppdaterad kernel gör Fedora till ett enkelt val för väldigt ny hårdvara, drivrutiner kommer tidigt.
        + Nya versioner släpps ungefär var sjätte månad, varje version får uppdateringar i 12 månader. 
    + [RHEL](https://www.redhat.com/en/store/red-hat-enterprise-linux-workstation) Red Hats huvudprodukt
        + Kostar pengar.
        + Känt för sin stabilitet och supporttjänst.
        + Används antagligen främst i servrar på stora organisationer men används också på arbetsstationer.
    + [Alma Linux](https://almalinux.org/) / [Rocky Linux](https://rockylinux.org/) båda tänkta ersättare till CentOS som Red Hat lägger ner i slutet på 2021.
        + Bygger på RHEL, men är gratis och har inte samma möjligheter till support.
        + Eftersom de utgår ifrån RHEL får de dock uppdateringar aningen efter RHEL.
        + Strävar efter samma stabilitet som gjorde CentOS så populärt i arbetsstationer och servrar.
        + Utvecklas av organisationer skilda från Red Hat.
+ [Arch Linux](https://www.archlinux.org/) erbjuder stor valfrihet, men kräver lite mer av användaren
    + Mycket flexibelt utan att vara alltför svår att använda
    + Kräver, i sig, nästan inga resurser alls och går att använda utan grafiskt gränssnitt.
    - Installation görs via ett textbaserat gränssnitt. Guiderna är mycket utförliga, men det kan kännas lite obehagligt för ovana användare.
    - Du kommer behöva läsa på lite mer för att få datorn att fungera som du vill. Därmed kommer du garanterat behöva en extra enhet med webbläsare, exempelvis en smartphone.
    - Rullande release, inga nya versioner släpps utan alla paket och delar uppdateras separat.
+ [Manjaro](https://manjaro.org/) är väldigt likt Arch Linux men erbjuder en förenklad installation med lite fler automatiserade verktyg.
    + Rullande release, likt Arch Linux.
    + Kan vara lite svårare att underhålla än vissa andra användarvänliga distributioner. Men man kan använda Arch Linux wiki:n som är väldigt bra.
    + Finns en variant med Nvidias drivrutiner förinstallerade.
+ [Slackware](http://www.slackware.com/) är en av de allra äldsta, levande, distributionerna
    + Har i princip samma fördelar och nackdelar som Arch Linux.
    + Känt för sin stabilitet.
    - Är något svårare att använda än Arch Linux.
+ [Gentoo](https://www.gentoo.org/) är för vana användare som vill lära sig mer om Linux
    + Source-baserad, vilket innebär att du kompilerar allting på datorn själv. Fördelen med detta är att det ökar prestanda.
    + Lätt att använda de senaste versionerna för det mesta.
    + Du kommer lära dig väldigt mycket mer om din dator.
    - Tidskrävande att göra nya saker med.
    - *Svårt* att göra nya saker med.
+ [Funtoo](http://www.funtoo.org/Welcome) är som Gentoo, fast roligare.
    + Har samtliga för- och nackdelar som Gentoo.
    + Vissa designprinciper skiljer sig, vilket i första hand gör det smidigare att använda.
+ [Linux from scratch](http://www.linuxfromscratch.org/) rekommenderas för *mycket* vana användare.

Det finns som sagt många fler distributioner än dessa. [DistroWatch](https://distrowatch.com/) är en bra för att få information om distributioner du är intresserad av, tillsammans med distributionernas egna sidor.
