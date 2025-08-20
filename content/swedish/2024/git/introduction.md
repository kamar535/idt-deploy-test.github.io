---
title: Introduktion
weight: 10
---

Git och GitHub används flitigt i industrin och är verktyg som kommer användas på
många kurser längre fram. Det är därför nödvändigt att du redan nu börjar lära
dig grunderna.

![](/images/2024/git/git-github.png?width=444px)

## Vad är Git?

Git är ett system som hjälper programmerare att hålla reda på förändringar av
programkod eller annan text som de själva eller andra gjort. Med hjälp av Git
byggs en historik upp över förändringar vilket bland annat gör det möjligt att
gå tillbaka till tidigare versioner.

I dag har Git kommit att bli ett av de vanligaste verktygen för
versionshantering och samarbete kring kod. Git används både vid utveckling av
fri mjukvara och inom den kommersiella industrin.

Du kan använda dig av Git på din egen dator utan att behöva vara uppkopplat mot
internet. Det är först när du vill samarbeta med andra inom samma projekt som
du behöver dela information om din version av projektet med andra över internet.

## Vad är GitHub?

GitHub är en webbaserad och centraliserad lagring av versionshistorik för Git
som underlättar samarbete kring kod.

## Varför är Git viktigt?

Git är på många sätt ett bättre alternativ till att hela tiden maila nya
versioner av ett program mellan de personer som samarbetar med utvecklingen av
koden. Git är även ett bättre alternativ än att använda Dropbox för att dela
olika versioner av den kod som skrivs av flera programmerare tillsammans.

Även om du arbetar helt ensam är det bra att använda Git eftersom det gör det
möjligt att gå tillbaka till gamla versioner av koden.

## Historik

Varje textfil delas upp i ett antal mindre block och ändringar av dessa block
lagras. Det betyder att ändringar kan spolas både framåt och bakåt, jämföras och
slås ihop.

## Working directory, staging area och historik

För att förstå hur Git fungerar behöver vi skilja på working directory, staging
area och commit historik (repository).

![](/images/2024/git/working-directory-staging-area-commit-history.png?width=444px)

<!-- Image adopted from https://stackoverflow.com/a/35882869 -->

### Working directory

Den katalog där alla dina filer finns kalas för working directory. Detta är en
helt vanlig katalog på din dator.

### Staging area

När du vill spara en ögonblicksbild (snapshot) av en fil vid en viss tidpunkt
gör du det genom att lägga till den till en så kallad staging area. Detta
innebär att tiden fryses och det skapas en version av filen sparas så
som den såg ut precis vid denna tidpunkt.

Vanligt är att förändringar av flera filer som på något sätt hör ihop läggs till
i staging area. Det kan på detta sätt finnas fler än en fil i staging area
samtidigt.

Det kommando som används för att lägga till en eller flera filer från
working directory till staging area är `git add`.

### Commit historik

När du sedan är nöjd med de ändringar du lagrat i staging area måste du göra
en commit. Det är först efter att du gjort commit som du skapat en tidpunkt i
historiken som du sedan kan gå tillbaka till. Historiken lagras i det som
rent tekniskt ibland brukar kallas för repository.

Det kommando som används för att göra en commit av alla filer i staging area
till historiken är `git commit`.

## Git repo

Rent tekniskt är det i repository som historiken sparas. Men, i många fall
brukar man kalla en samling av filer och
mappar som Git håller koll på- och hanterar ändringar i för ett Git repository,
eller kort och gott för Git repo, eller ännu kortare bara repo.

Ett repo är en vanlig mapp på din dator. I denna mapp kommer Git att skapa dolda
mappar och filer för att hålla reda på historiken. Ett förenklat sätt att tänka
på ett Git repo är att det består de tre delarna: working directory, staging area
och commit historik.

![](/images/2024/git/git-repo-main-components.png?width=555px)

<!-- Img src: https://www.atlassian.com/git/tutorials/resetting-checking-out-and-reverting -->

## Tillstånd

Så som Git ser på det kan varje fil befinna sig i ett av följande fyra
tillstånd.

- Untracked
- Staged
- Modified
- Commited

En fil, eller mer exakt en ändring på en fil, rör sig sedan mellan dessa
tillstånd enligt följande diagram.

![](/images/2024/git/git-state-transitions.svg?width=555px)

<!-- Image src: https://snipcademy.com/git-fundamentals -->

### Untracked

Från början är alla filer untracked. Det betyder att Git inte bryr sig om dessa
filer över huvud taget. Dessa filer kommer helt att ignoreras av Git och inte
omfattas av någon versionshantering.

### Staged

När du vill spara en ögonblicksbild (snapshot) av en fil gör du det genom att
först lägga till den till staging area. Mer exakt, det sparas inte några frysta
versioner, det är endast en beskrivning av vad som förändrats som sparas.
I staging area finns nu en beskrivning som gör det möjligt att
återställa filen så som den såg ut exakt vid denna tidpunkt.

Vanligt är att förändringar av flera filer som på något sätt hör ihop läggs till
i staging area. Det kan på detta sätt finnas fler än en fil i staging area samtidigt.

Det kommando som används för att lägga till filer från working directory till
staging area är `git add`.

### Committed

För att lagra alla frysta versioner av filer som för tillfället befinner sig i
staging area behöver dessa committas. När en ändring väl committats sparas den
för evigt i repots historik. Mer exakt så lagras inte frysta versioner i
historiken. På samma sätt som i staging area är det istället beskrivningar av
förändringar som lagras i historiken.

Även om ändringarna (committen) skulle ångras och
rullas tillbaka går det att gå tillbaka till just den versionen av repots
historia och se hur saker såg ut då. Detta är mycket användbart vid t.ex.
avlusning (debugging) av kod, när man ska ta reda på hur en bugg introducerats.
Det är också mycket svårt att på riktigt råka ta bort något från ett
Git-repository när det väl committats.

Det kommando som används för att göra en commit av alla filer i staging area
till historiken area är `git commit`.

### Modified

Om du lägger till en fil till staging area lagras alltså en snapshot av filen i
staging area. Vad händer nu om du ändrar något i filen innan du gör commit? Jo,
Git kommer att upptäcka detta och filen kommer nu att finnas i två versioner, en
i staging area och en i working directory som Git markerar som modified. 

När du gör commit är det endast versionen i staging area som läggs till i
historiken. Vill du även spara eventuella nya uppdateringar du gjort mellan `git
add` och `git commit` till historiken måste du första lägga till dessa ändringar
till staging area och sedan göra ytterligare en commit.

## Skapa ett nytt repo

Ett repo är en helt vanlig katalog med särskilt innehåll (dolda mappar
och filer) som Git lagt dit för att hålla reda på dina vanliga filer och mappar.

För att skapa ett nytt repo navigerar du i terminalen till den katalog du vill
göra till ett repo. Sedan utför du kommandot `git init`. Git kommer nu lägga
till dolda kataloger och filer som sedan används av Git för att hålla reda på
historiken. Där är med hjälp av dessa dolda mappar och filer som Git hanterar
bland annat staging area och historiken (repository).

## Arbetsordning

Detta är den normala arbetsordningen vid arbete med Git.

1. Skapa ett repo med `git init`.
2. Skapa, redigera, byt namn på eller ta bort filer.
3. Lägg till ändringar som på något sätt hör ihop till staging area med `git
   add`.
4. Lägg till ändringar till den permanenta historiken med `git commit`.

## Lokalt repo

Det Git repo du har skapat och hanterar på din egen dator kalas för ett lokalt
Git repo.

## Remote repo

Ett Git repo som finns på någon annan dator på ett nätverk, till exempel på
internet kallas för remote repo. Ett enkelt sätt att sätta upp ett remote repo
är att göra det på GitHub.

## Synka med push och pull

För att hålla ett lokalt repo och ett remote repo i synk används push och pull. 

![](/images/2024/git/local-repo-network-gihub-remote.png?width=555px)

Med push skickar du upp din senaste commit till ett remote repo för att det
skall hamna i synk med ditt lokala repo. Kommandot som används för att göra en
push är `git push`.

Med pull kollar du om det finns några ändringar gjorda av andra i remote repo
som du inte tagit del av för att ditt lokala repo skall komma i synk med remote
repo.. Kommandot som används för att göra en pull är `git pull`.

## Backup med hjälp av remote repo på GitHub

Även om du inte samarbetar med andra kring ditt repo är det mycket värdefullt
att koppla ihop dit lokala repo med ett remote repo på GitHub och håller dessa i
synk med hjälp av push och pull. 

Om något händer med din hårddisk eller dator kan det lätt hända att du blir av
med hela ditt lokala repo och allt arbete du lagt ner går förlorat. Om du har
satt upp ett remote repo på GitHub och synkat detta med ditt lokala repo har du
en backup på GitHub som du kan använda för att återställa ditt lokala repo. 

## Klona ett remote repo

Genom att klona ett remote repo skapar du ett nytt lokalt repo som är en kopia av ett
befintligt remote repo, till exempel ett repo på GitHub. 

![](/images/2024/git/clone-from-github.png?width=555px)

Ett klonat repo får automatiskt det ursprungliga repot uppsatt som sin remote. 
Kommandot som används för att klona ett remote repo är `git clone`.

## Återställ ett förlorat repo

Om du av något anledning blivit av med ditt lokala repo men har ett backup repo
på GitHub kan du alltså enkelt återställa ditt lokala repo med genom att klona
repot från GitHub. 

