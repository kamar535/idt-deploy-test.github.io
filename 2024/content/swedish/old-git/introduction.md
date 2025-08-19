---
title: Introduktion
pre: <i class="fas fa-info-circle"></i>
weight: 10
draft: true
---

{{% notice style="warning" title="Viss terminalvana erfordras" %}}

Det är starkt rekommenderat att du gått igenom modulen
[Terminalen](/terminal) innan du påbörjar denna modul.

{{% /notice %}}

Git används flitigt i industrin och är ett verktyg som du kommer behöva lära dig
använda redan nu eftersom det används på flera kurser under din utbildning.

## Vad är Git?

I dag har Git kommit att bli ett av de vanligaste verktygen för att samarbeta kring
kod. Git används både vid utveckling av fri mjukvara och inom den kommersiella
industrin.

Git är på många sätt ett bättre alternativ till att hela tiden maila nya
versioner av ett program mellan de personer som samarbetar med utvecklingen av
koden. Git är även ett bättre alternativ än att använda Dropbox för att dela
olika versioner av den kod som skrivs av flera programmerare tillsammans.

Även om du arbetar helt ensam är det bra att använda Git eftersom det gör det
möjligt att gå tillbaka till gamla versioner av koden.

I princip arbetar Git med ett trädliknande modell. Varje textfil delas
upp i ett antal mindre block, och ändringar till dessa block lagras. Det
betyder att ändringar kan spolas både framåt och bakåt, jämföras och
slås ihop. Vi kommer här att visa några exempel på hur man kan arbeta
med Git för att samarbeta i ett kodprojekt liknande de som du kommer att
arbeta i under din utbildning.

## Viktiga principer

### Git repository

En "git-repository" är en samling av filer och mappar som Git håller
koll på- och hanterar ändringar i. Varje git-repository har en egen
mapp, som kan heta t.ex. `ospp-projekt-grupp-1` eller något liknande,
egentligen vad som helst. Varje fil i ett git-repository kan vara i ett av
tre tillstånd:

1. **Inte incheckad**
2. **Stage:ad**
3. **Committad**

En fil (eller mer precis: en _ändring_ på en fil) rör sig från 1 till 3
i listan. Först _stage_:as ändringen, vilket innebär att tiden fryses
och filen sparas så som den såg ut. När alla ändringar som hör ihop är
stage:ade _committar_ man dem i klump, vilket betyder att man buntar
ihop dem tillsammans med ett meddelande om vad för ändringar som har
gjorts.

När en ändring väl committats sparas den för evigt i repositoryts
historia. Även om ändringarna (committen) skulle ångras och rullas
tillbaka går det att gå tillbaka till just den versionen av repositoryts
historia och se hur saker såg ut då. Detta är mycket användbart vid
t.ex. avlusning (debugging) av kod, när man ska ta reda på hur en
bugg introducerats. Det är också mycket svårt att på riktigt råka ta
bort något från ett Git-repository när det väl committats.

Från början är _alla_ filer inte incheckade. Det betyder att Git inte
bryr sig om ändringar som görs på filerna alls. Det första steget när
man skapar en ny fil i ett git-repository är därför att lägga till och
stage:a den, så att Git vet att den finns.

Arbetsordningen med Git är alltså:

1. **Redigera (eller skapa, ta bort, byt namn på) filer**
2. **Stage:a ändringarna för att frysa dem i tiden**
3. **Committa dem med ett meddelande som beskriver vad ändringarna gör**

{{< figure src="/images/git/git-workflow.gif" title="Snabb inmatning: man kan stage:a och committa med ett enda kommando" >}}

### Branches

Tillståndet som ett repository för tillfället står på kallas
för _HEAD_ (som i "läshuvud"). Men det går också att gå i sidled och ha
alternativa tidslinjer (precis som i science fiction). Det kallas för
_branches_ eftersom de grenar ut historiken i ett träd. Vi kommer att gå
igenom hur man kan använda branches för att samarbeta i en grupp med ett
kodprojekt senare. Egentligen görs i princip ingen skillnad mellan den
första grenen (som brukar kallas `master`) och andra branches -- det går
t.o.m. att ta bort `master` om man skulle vilja!

### Remotes

Det som gör Git användbart vid samarbete med andra är framför allt
möjligheten att synkronisera repositories med sina branches via servrar,
s.k. _remotes_. En remote sparar den senaste gemensamma versionen av
projektets historia så att alla kan hämta hem andras ändringar -- men
också skicka upp sina egna. Ett inbyggt låssystem ser till att det är
omöjligt att skicka upp sina ändringar utan att först ha hämtat de
senaste gemensamma ändringarna från remoten. På så sätt kan man
säkerställa att alla i projektet är överens om hur den gemensamma koden
ser ut, även om man arbetar oberoende av varandra.

### Merge

Det går också att slå ihop branches till en gemensam tidslinje igen,
vilket kallas för en _merge_ (lämpligt nog). Det betyder att Git gör
sitt bästa för att passa ihop ändringarna som gjorts sedan den
gemensamma brytpunkten för två branches. Ofta kan detta göras automatiskt,
men ibland uppstår en konflikt och användaren måste hjälpa till. I
praktiken görs också en merge när kod hämtas från en remote. Det innebär
att om en gruppmedlem har hunnit göra ändringar som du inte har sett så
kommer Git att göra sitt bästa för att pussla ihop projektet ändå åt er
(och åtminstone varna om det inte går).


## En kort kom-igång-guide

Det normala arbetsflödet med git är helt kommandoradsbaserat och utgår
från programmet `git`. Många editorer har dock stöd för att interagera
med Git direkt.

### Hämta kod med git clone

Man börjar använda git på ett av två sätt. Antingen hämtar man hem kod
som redan finns genom kommandot `git clone` ("clone" eftersom man
"klonar" en kopia av koden och dess historik till sin dator):

{{< figure src="/images/git/anim/clone.gif" class="medium" >}}

``` shell
$ git clone https://github.com/rg3/youtube-dl
Cloning into 'youtube-dl'...
remote: Counting objects: 70370, done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 70370 (delta 8), reused 0 (delta 0), pack-reused 70349
Receiving objects: 100% (70370/70370), 38.71 MiB | 3.28 MiB/s, done.
Resolving deltas: 100% (51112/51112), done.
Checking connectivity... done.
```

Här användes adressen till programmet `youtube-dl`:s källkod, men vilken
adress som helst fungerar **så länge den pekar till ett git-repository**.

#### Klona till specifik mapp
Om man inte anger en mapp efter adressen kommer git att skapa en mapp där
du står som heter samma sak som repositoryt (oftast slutet på adressen),
i det här fallet `youtube-dl`. Om du t.ex. skulle vilja klona `youtube-dl`
till en mapp kallad *min-kopia-av-ytdl* skulle kommandot se ut så här:
```shell
$ git clone https://github.com/rg3/youtube-dl min-kopia-av-ytdl
```

### Visa historik med git log

Nu kan vi ställa oss i mappen som git skapade med `cd youtube-dl` som
vanligt och börja köra kommandon. Om man t.ex. kör `git log` får man en
historik över alla commits med nyast överst, liknande den här:

{{< figure src="/images/git/anim/log.gif" class="medium" >}}

```shell
commit 1094074c045140e9a91b521b0a933f394a7bba91
Author: Remita Amine <MAILADRESS BORTTAGEN>
Date:   Thu Aug 4 09:38:37 2016 +0100

    [kaltura] extract subtitles and reduce requests

commit 217d5ae0137943829db23d13eee425e5fd7c08ae
Author: Remita Amine <MAILADRESS BORTTAGEN>
Date:   Thu Aug 4 09:37:27 2016 +0100

    [vodplatform] Add new extractor
```

Här kan vi alltså se två commits. Varje commit har en unik nyckel
(ex. `1094074c045140e9a91b521b0a933f394a7bba91`) som identifierar
commiten, vem som checkat in den (*Author*), när den checkades in (*Date*),
och den kommentar som lämnades vid incheckning. Notera att båda
ändringarna är sammanhängande funktioner som lagts till programmet.

Avsluta med `q` och bläddra upp och ned med piltangenterna.

### Jämföra ändringar med git diff

Om man vill veta vad som ändrades mellan de båda commitsen kan man
använda `git diff` och deras namn. Om man inte orkar kopiera hela deras
unika namn räcker det nästan alltid med de första tecknen i dem, så här:
`git diff 217d5a 1094074`.

{{< figure src="/images/git/diff.png" title="git diff mellan två commits" class="medium" >}}

Här ser vi alltså rader som tagits bort (minus) och lagts till
(plus). På många system är också raderna färgade i rött och grönt som
ovan. Notera att ordningen på argumenten spelar roll, eftersom det är
skillnaden mellan att jämföra framåt och bakåt!

Avsluta igen med `q` och scrolla upp och ner med piltangenterna.

### Starta en egen repository med git init

För att starta en tom git-repository kör man kommandot `git init` i
mappen man vill ha den (typiskt mappen man har sin källkod i). Om du
börjar helt från början måste du alltså först skapa en mapp att ha ditt
projekt i. Om du tidigare stod i `youtube-dl`-repositoryn som vi hämtade, tänk
på att göra `cd ..` för att inte skapa din nya mapp inuti den gamla.

Vi tänker oss nu att vi sätter upp ett repository med textfiler för en
fest vi ska planera:

{{< figure src="/images/git/anim/init.gif" class="medium" >}}

```shell
$ mkdir min-fest <- skapa en mapp som heter `min-fest`
$ cd min-fest <- byt nu till denna mapp
$ git init <- starta en tom git repository
Initialized empty Git repository in /Users/albin/min-fest/.git/
```

Din sökväg blir förstås annorlunda beroende på vad din användare heter
och var du gjorde den tomma mappen.

### Lägg till filer med git add

Skapa filerna `gastlista.txt` och `matar.txt`, och lägg till några rader
text i dem. Så här ser mina ut:

{{< figure src="/images/git/anim/skapa_filer.gif" class="medium" >}}

Använd dig av kommandot `nano` för att skapa textfilerna. Sedan kan du alltid se innehållet i mappen du är i med `ls`. Hittar du textfilerna? 

Använd dig nu av `cat` för att skriva ut innehållet i textfilerna. 

```shell
$ cat matar.txt
1. Sallad
2. Grillad tofu med potatis
3. Glass

$ cat gastlista.txt
- Oppfinnarjocke
- Kalle Anka
- Störiga mostern
```

Vi kan fråga Git vad den tycker om livet med `git status`:

{{< figure src="/images/git/anim/status.gif" class="medium" >}}

``` shell
$ git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	gastlista.txt
	matar.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Här får vi massor av information. Git berättar att vi är på branchen
master (som skapades automatiskt och just nu är den enda branchen vi
har), att det inte finns någon tidigare historik loggad ("Initial
commit"), och att det finns två oincheckade filer som git inte har koll
på; `gastlista.txt` och `matar.txt`. Sist av allt får vi veta att det
inte finns något stage:at för att committa.

För att lägga till våra nya filer gör vi som Git föreslår:

{{< figure src="/images/git/anim/add.gif" class="medium" >}}

``` shell
$ git add gastlista.txt matar.txt
$ git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   gastlista.txt
	new file:   matar.txt
```

Nu förklarar Git för oss att det _finns_ ändringar som är stage:ade för
att committas, och vilka ändringar som har gjorts (två nya filer har
registrerats).

Om vi bara skriver `git commit` så kommer git att öppna vår inställda editor för att skriva ett meddelande. Men eftersom den kan vara lite vad som helst på universitetets datorer föreslår vi att du skickar med ett meddelande direkt på kommandoraden istället:

{{< figure src="/images/git/anim/commit.gif" class="medium" >}}

``` shell
$ git commit --message "Initial commit"
[master (root-commit) 74c2b5b] Initial commit
 2 files changed, 6 insertions(+)
 create mode 100644 gastlista.txt
 create mode 100644 matar.txt

```

Git berättar för oss vilka ändringar den sparar. Om vi nu tittar i
historiken och `git status` så ser vi att ändringarna är sparade:

``` shell
$ git status
On branch master
nothing to commit, working directory clean

$ git log
commit 74c2b5bedb58e818b6c550b646ff29d13bc5950c
Author: Albin Stjerna <MAILADRESS BORTTAGEN>
Date:   Thu Aug 4 14:00:28 2016 +0200

    Initial commit

```

### Registrera ändringar med git stage och git commit

Låt oss säga att vi lägger till någon i gästlistan:

{{< figure src="/images/git/anim/modify.gif" class="medium" >}}

*`echo` är ett kommando som skriver ut texten vi ger, i detta fall "- Joakim von Anka", till
terminalen. På så vis kan vi utnyttja  [piping till filer](/terminalen/#använda-filer) för att enkelt
skriva till en fil.*

``` shell
$ echo "- Joakim von Anka" >> gastlista.txt
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   gastlista.txt

no changes added to commit (use "git add" and/or "git commit -a")

$ git diff
diff --git a/gastlista.txt b/gastlista.txt
index 4570554..84680c2 100644
--- a/gastlista.txt
+++ b/gastlista.txt
@@ -1,3 +1,4 @@
 - Oppfinnarjocke
 - Kalle Anka
 - Störiga mostern
+- Joakim von Anka
```

Nu kan vi notera att `git diff` utan argument jämför de ändringar som
för tillfället finns med de senaste registrerade och committade
ändringarna. Här ser vi med andra ord att vi längst ner i filen
`gastlista.txt` har lagt till en rad för Joakim von Anka.

För att spara de nya ändringarna använder vi `git stage`:

{{< figure src="/images/git/anim/modify_commit.gif" class="medium" >}}

``` shell
$ git stage gastlista.txt
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   gastlista.txt
```

Nu kan vi committa ändringarna precis som när vi lade till filer:

``` shell
$ git commit --message "Lade till en besökare till"
[master 57673a6] Lade till en besökare till
 1 file changed, 1 insertion(+)

$ git status
On branch master
nothing to commit, working directory clean

$ git log
commit 57673a6759f1bb395731d2778cab3b1024b083c7
Author: Albin Stjerna <MAILADRESS BORTTAGEN>
Date:   Thu Aug 4 14:15:22 2016 +0200

    Lade till en besökare till

commit 74c2b5bedb58e818b6c550b646ff29d13bc5950c
Author: Albin Stjerna <MAILADRESS BORTTAGEN>
Date:   Thu Aug 4 14:00:28 2016 +0200

    Initial commit

```

### Ångra sig med git reset

Låt oss säga att vi råkade ta bort gästlistan av misstag:
``` shell
$ rm gastlista.txt

$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	deleted:    gastlista.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Då kan vi återställa hela repositoryt som den såg ut vid den senaste
committen (alltså `HEAD`, om du minns från tidigare):

{{< figure src="/images/git/anim/reset.gif" class="medium" >}}

``` shell
$ git reset --hard HEAD
HEAD is now at 57673a6 Lade till en besökare till

$ git status
On branch master
nothing to commit, working directory clean

$ cat gastlista.txt
- Oppfinnarjocke
- Kalle Anka
- Störiga mostern
- Joakim von Anka
```

Det fungerar även om man har redigerat filer och vill återställa
ändringarna, men det är också farligt eftersom det **kastar bort alla
ocommitade ändringar**!

### Skapa- och byta mellan branches

Vi kan visa vilken branch vi för tillfället är på med hjälp av `git
branch`:

{{< figure src="/images/git/branch.png" class="medium" >}}

``` shell
$ git branch
* master
```

Kanske inte så spännande -- det finns en branch och den är vi på. Vi kan
skapa en ny med hjälp av `git checkout`:

{{< figure src="/images/git/anim/branch_create.gif" class="medium" >}}

``` shell
$ git checkout -b better-desserts
Switched to a new branch 'better-desserts'

$ git branch
* better-desserts
  master
```

Nu kan vi lägga till lite fler efterrätter (bara en är trots allt lite snålt!):

{{< figure src="/images/git/anim/branch_edit.gif" class="medium" >}}

``` shell
$ din-favorit-editor matar.txt
$ git diff
diff --git a/matar.txt b/matar.txt
index 38e1bc6..3711a8a 100644
--- a/matar.txt
+++ b/matar.txt
@@ -1,3 +1,6 @@
 1. Sallad
 2. Grillad tofu med potatis
 3. Glass
+4. Crème brûlée
+5. Mer glass
+6. Kladdkaka

$ git stage matar.txt
$ git commit --message "Mer efterrätt!"
[better-desserts 29e50b5] Mer efterrätt
 1 file changed, 3 insertions(+)
```

Låt oss säga att vi är klara med de här ändringarna nu och vill ha
tillbaka dem till `master`. Då måste vi först byta tillbaka till
`master` från `better-desserts` och göra en `merge` mellan dem:

{{< figure src="/images/git/anim/branch_merge.gif" class="medium" >}}

``` shell
$ git checkout master
Switched to branch 'master'

$ git merge better-desserts
Updating 57673a6..29e50b5
Fast-forward
 matar.txt | 3 +++
 1 file changed, 3 insertions(+)

$ git status
On branch master
nothing to commit, working directory clean
```

Eftersom skillnaden mellan brancharna var trivial kunde Git räkna ut hur
de skulle slås ihop.

### Merge-konflikter

Merge-konflikter är något som du troligtvis kommer stöta på en hel del.
Till en början kan de verka skrämmande och komplicerade, men har man väl
förstått hur dessa fungerar kan man lösa de flesta konflikter utan större
svårigheter.

Låt oss simulera en lite mer komplicerad interaktion som kan uppstå när
man samarbetar på samma kod. Ofta märker man av det när man arbetar mot
fjärr-repositories med flera personer och använder `git pull` för att dra
hem de senaste ändringarna (mer om detta i sektionen [Arbeta mot fjärr-repositories](#arbeta-mot-fjärr-repositories)).

Här fortsätter vi dock med våra två branchar:

{{< figure src="/images/git/anim/mergeconflict_setup.gif" class="medium" >}}

``` shell
$ din-favorit-editor matar.txt
$ git diff
diff --git a/matar.txt b/matar.txt
index 3711a8a..d6a2168 100644
--- a/matar.txt
+++ b/matar.txt
@@ -4,3 +4,4 @@
 4. Crème brûlée
 5. Mer glass
 6. Kladdkaka
+7. Sesamkakor

$ git commit -a --message "Ännu mer efterrätt!"
[master 6b5c412] Ännu mer efterrätt
 1 file changed, 1 insertion(+)

$ git checkout better-desserts
Switched to branch 'better-desserts'

$ cat matar.txt
1. Sallad
2. Grillad tofu med potatis
3. Glass
4. Crème brûlée
5. Mer glass
6. Kladdkaka

$ din-favorit-editor matar.txt
$ git diff
diff --git a/matar.txt b/matar.txt
index 3711a8a..7d33dc4 100644
--- a/matar.txt
+++ b/matar.txt
@@ -4,3 +4,4 @@
 4. Crème brûlée
 5. Mer glass
 6. Kladdkaka
+7. Honungspudding

$ git commit -a --message "OM NOM NOM"
[better-desserts 039a4dc] OM NOM NOM
 1 file changed, 1 insertion(+)
```

Nu har vi alltså lagt till en ny rad på samma ställe i båda brancharna,
oberoende av varandra. Det betyder att vi kommer att stöta på problem
när vi ska slå ihop dem senare:

``` shell
$ git checkout master
Switched to branch 'master'

$ git merge better-desserts
Auto-merging matar.txt
CONFLICT (content): Merge conflict in matar.txt
Automatic merge failed; fix conflicts and then commit the result.
```

Git berättar för oss att ändringarna i `matar.txt` är inkompatibla och
måste slås ihop för hand. Om vi öppnar den i valfri editor ser vi det
här:

``` shell
1. Sallad
2. Grillad tofu med potatis
3. Glass
4. Crème brûlée
5. Mer glass
6. Kladdkaka
<<<<<<< HEAD
7. Sesamkakor
=======
7. Honungspudding
>>>>>>> better-desserts
```

Vilket ska läsas som "på den här raden i HEAD finns "7. Sesamkakor"
medan det i better-desserts finns "7. Honungspudding". Vi får helt
enkelt öppna filen i vår editor och ändra de berörda raderna till något
rimligt (och ta bort Gits tillägg). Sen gör vi som Git föreslår och
committar den lagade versionen:
``` shell
$ din-favorit-editor matar.txt
$ git diff
diff --cc matar.txt
index d6a2168,7d33dc4..0000000
--- a/matar.txt
+++ b/matar.txt
@@@ -4,4 -4,4 +4,5 @@@
  4. Crème brûlée
  5. Mer glass
  6. Kladdkaka
 -7. Honungspudding
 +7. Sesamkakor
++8. Honungspudding

$ git commit -a --message "Fix merge conflict"
[master 0fc4b75] Fix merge conflict
```

{{< figure src="/images/git/anim/mergeconflict_fix.gif" class="medium" title="Löser en merge-konflikt" >}}


#### Ångra en merge
Om allt blev jättjobbigt och vi ångrar oss finns alltid möjligheten att
köra `git merge --abort` för att återställa tillståndet som det var
innan vi försökte oss på en merge.

{{< figure src="/images/git/anim/mergeconflict_abort.gif" class="medium" >}}

## Arbeta mot fjärr-repositories
En stor fördel med Git, utöver vad vi redan gått genom, är att man kan
skapa s.k. fjärr-repositories (remote repository) mot vilka flera
personer kan arbeta --- på så vis är det väldigt enkelt att arbeta tillsammans
i grupp på ett projekt. Ett fjärr-repository kan ses som en server där man
lagrar sit repository, från vilken man hämtar hem filer/ändringar till sin dator.
Generellt sett följer arbetsprocessen med fjärr-repositories följande:

#### Om repositoryt inte redan är klonat
1. Klona ett repository till datorn (lokalt)
2. Arbeta med ändringar lokalt
3. Commita ändringar lokalt
4. Ladda upp commits till fjärr-repository via `push`

#### Om repositoryt redan klonats
1. Hämta commits/ändringar från fjärr via `pull`
2. Arbeta med ändringar lokalt
3. Commita ändringar lokalt
4. Ladda upp commits till fjärr-repository via `push`

Det finns ett flertal verktyg för att skapa- och hantera fjärr-repositories,
exempel är [GitHub](#github) som tas upp senare i modulen. Fjärr-repositories
är med andra ord inget man kan skapa via kommandon i git.

### Klonade repositories
Om man klonar ett repository följer det automatiskt med vilket fjärr-repository
repositoryt tillhör. I och med detta är det enklaste sättet att få ett repository som
är förinställt med fjärr-möjlighet att skapa ett repository via valfri tjänst
(ex. [GitHub](#github)) för att sedan klona det.

### Ladda upp lokalt repository till fjärr-repository
Om du har ett lokalt repository du vill ladda upp till ett fjärr-repository
måste fjärr-repositoryt kopplas till ditt lokala repository. **Först måste du
se till att du skapat ett nytt fjärr-repository via valfri tjänst** och därefter kan
du koppla ditt lokala repository till fjärr-repositoryt via:

```shell
$ git remote-add origin <URL TILL FJÄRR-REPOSITORY BORTTAGEN>
```

Detta ställer in fjärr-repository till det repository du angav URL till.

### Vad är `origin`?
`origin` är standardnamnet som används för att koppla fjärr-repository. Tekniskt sett
skulle man kunna döpa fjärr-repositoryn till andra namn, men det är inte rekommenderat
då origin är "industristandarden".

### `Push` - ladda upp commits till fjärr-repository
`git push` är det kommando som används för att ladda upp commits/ändringar som gjorts-
och sparats lokalt. Kommandot ser ut som följer:
```shell
$ git push origin <branch-name>
```
där *branch-name* är namnet på den branch vi vill ladda upp ändringar för. Om
vi arbetar i branchen *master* och vill ladda upp ändringar för denna skriver
vi:
```shell
$ git push origin master

Counting objects: 3, done.
Writing objects: 100% (3/3), 280 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To <URL TILL FJÄRR-REPOSITORY BORTTAGEN>
   44aab50..e1a086f  master -> master
```

Om vi däremot är inne i en annan branch, låt säga *min-branch* och vill ladda upp
dess ändringar till fjärr-repositoryt skriver vi:
```shell
$ git push origin min-branch

Total 0 (delta 0), reused 0 (delta 0)
To <URL TILL FJÄRR-REPOSITORY BORTTAGEN>
 * [new branch]      min-branch -> min-branch
```
Om branchen *min-branch* inte redan finns i fjärr-repositoryt kommer det automatiskt
skapas och ändringarna laddas upp, som i exemplet ovan.

**För att vår branch ska komma ihåg vilken fjärr-branch den ska arbeta mot**
kan vi ställa in detta genom att lägga till `-u`-flaggan när vi pushar:
```shell
$ git push -u origin min-branch

Branch min-branch set up to track remote branch min-branch from origin.
Everything up-to-date
```

därefter behöver vi ej heller skriva vilket fjärr-repository och branch vi vill push:a
till, eftersom vi ställt in det för vår branch:

```shell
$ git push

Counting objects: 3, done.
Writing objects: 100% (3/3), 280 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To <URL TILL FJÄRR-REPOSITORY BORTTAGEN>
   44aab50..e1a086f  min-branch -> min-branch
```


### `Pull` - ladda hem commits från fjärr-repository
Om man är flera som arbetar mot samma fjärr-repository eller om man använder fler än
en dator behöver man hämta ändringar som andra laddat upp. Detta gör man via
kommandot `git pull origin <branch-name>`.

```shell
$ git pull origin master

Updating e1a086f..c3c96b6
Fast-forward
 enfil.txt | 3 +++
 1 file changed, 3 insertions(+)
```

Om vi är i branch _master_ **eller** har ställt in att vår branch vet vilken
fjärr-branch den ska arbeta mot behöver vi bara skriva `git pull`:
```shell
$ git pull

Updating e1a086f..c3c96b6
Fast-forward
 enfil.txt | 3 +++
 1 file changed, 3 insertions(+)
```

## Git på din egen dator

Du kan ladda ner Git för macOS, Windows och GNU/Linux
på Gits [nedladdningssida](https://git-scm.com/downloads). Där finns
också närmare instruktioner. De flesta GNU/Linux-distributioner har
också Git i sina pakethanterare. Om du har installerat XCode till macOS
så får du också Git på köpet.

## Avancerade funktioner att lära sig på egen hand

Nedan följer en lista på funktioner som kan vara värda att lära sig på
egen hand, men som inte tas upp här:

- `amend` -- ändra och formulera om commits. Användbart om man råkat
  skriva fel.
- `patch` -- generera patchfiler från git-ändringar
- `rebase` -- som `merge`, men skriver om historien. Gör det möjligt att
  slå ihop commits, ta bort commits helt, och att flytta om t.ex. en
  feature branch på en `master` som uppdaterats sedan den startade.
- `cherry-pick` -- välj specifika commits från en branch och lägg dem på
  en annan branch

## Läs mer

- [Atalassians Git-guider](https://www.atlassian.com/git/)
- [Den officiella Git-manualen](https://git-scm.com/book/en/v2)
- GitHubs officiella manual: [Bootcamp](https://help.github.com/categories/bootcamp/) (kom-igång-guider)
