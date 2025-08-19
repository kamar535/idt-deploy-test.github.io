---
title: Uppgift
weight: 20
pre: <i class="far fa-keyboard"></i>
draft: true
---

## Mål

Efter att du blivit godkänd på denna uppgift kommer du att känna till hur du använder Git för att:

- klona ett befintligt git-repository
- skapa ett nytt git-repository
- lägga till och committa filer
- skapa nya grenar
- hantera merge-konflikter.

## Detta behöver du

För att lösa uppfiten kommer du att behöva:

- en terminal
- git

Uppgiften är testad på och går att utföra på Uppsala universitets Linuxsystem,
men även på egen dator om det som krävs finns installerat.

## Uppgift

Materialet som tas upp i uppgiften diskuteras på [introduktionssidan för Git](../).

Ett git-repository är en katalog som hanteras av Git. För enkelhets skull kommer
*git-repo* fortsättningsvis att användas synonymt med *git-repository*.

{{% notice style="warning" title="Var noggrann!" %}}

Det är viktigt att samtliga delar av uppgiften utförs i korrekt ordning,
annars kommer inlämningen inte stämma och sannolikt resultera i komplettering!

{{% /notice %}}
### Del 1: Klona ett befintligt git-repo

På många kurser kommer du utgå från befintliga filer för att lösa olika typer av
uppgifter. Ett vanligt sätt att hantera detta, speciellt på
programmeringskurser, är att dessa filer finns tillgängliga i publikt
git-repo och att du hämtar hem dem genom att klona detta repo.

De filer du ska hämta hem denna gång finns på följande publika repo på
GitHub:

- https://github.com/uu-it-teaching/introduktion-till-datorer-2019-git-uppgift

Om du klickar på länken ovan bör en ny flik eller ett nytt fönster öppnas och du
kan där bland annat se vilka filer som ingår i detta repo. Sidan som
öppnas bör se ut ungefär som på bilden nedan.

{{< figure src="/images/git/git-GitHub-repository.png"
title="Publikt repo på GitHub med filer du behöver för att lösa denna uppgift" >}}

Du kan direkt i din webläsare kika på innehållet i filerna. Prova till exempel
att klicka på filen `dikt.txt` och se vad den innehåller.

Istället för att ladda ner filerna en och en ska du klona hela repot.
Öppna terminalen och navigera till din hem-mapp. Väl inne i mappen, klona
repot genom att köra kommandot:

```shell
git clone https://github.com/uu-it-teaching/introduktion-till-datorer-2019-git-uppgift.git
```

I terminalen bör du nu se något liknande detta:

```shell
Cloning into 'introduktion-till-datorer-2019-git-uppgift'...
remote: Counting objects: 12, done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 12 (delta 0), reused 6 (delta 0), pack-reused 0
Unpacking objects: 100% (12/12), done.
Checking connectivity... done.
```

Som resultat av kloningen har nu katalogen
`introduktion-till-datorer-2019-git-uppgift` skapats. Navigera till denna
katalog.


```shell
cd introduktion-till-datorer-2019-git-uppgift  
```

Du kan nu lista alla filer i den nya katalogen:

```shell
ls -1
```

Med hjälp av flaggan `-1` (siffran 1, inte bokstaven l) listas namnen på alla
filer (och kataloger) på en egen rad och i terminalen bör du nu se följande:

```shell
README.md
dikt.txt
introduktionskurser.txt
kurser.txt
strunt.txt
```

Du har nu lyckats klona repot och vi kommer återkomma till filerna i detta
repo längre fram.

### Del 2: Skapa ett nytt git-repo

Navigera till din hem-mapp i terminalen. Skapa en ny mapp
som du döper till `abcd1234_git`, där du ersätter `abcd1234` med
användarnamnet för ditt studentkonto. Navigera därefter till
denna mapp.

Väl inne i mappen, initiera ett nytt git-repo:
```
git init
```

När du skapat repot ska du ställa in namn och e-post. Det
är denna information git (och system som GitHub) använder för att
identifiera vem som utfört specifika ändringar. 

{{% notice style="warning" title="Glöm inte detta!" %}}

Det är viktigt
att du ställer in detta korrekt så vi kan se att det är du som
utfört ändringarna i uppgiften.

{{% /notice %}}

Det finns två sätt att göra detta, *lokalt* och *globalt*:

#### Lokal (per repo) konfiguration
Det går konfigurera denna information på en "per repo"-basis, dvs.
det är möjligt att ställa in olika mailadresser och namn för olika
repon. För att ställa in detta för ett enskilt repo navigerar du
till repo-mappen och skriver följande kommandon:

```shell
git config user.name "abcd1234"
git config user.email "abcd1234@student.uu.se"
```
Även här ersätter du `abcd1234` med användarnamnet för ditt studentkonto.

{{% notice style="info" title="" %}}

På detta sätt har du ställt in detta användardamn och denna e-postadress för
endast detta repo.

{{% /notice %}}

#### Global konfiguration
Det går även att konfigurera git globalt, vilket gör att dina inställningar
används för alla nya repon du skapar- samt alla repon du inte redan ställt in. För att göra detta används `--global`-flaggan. 

Så här ser inställningarna
ut då:

```shell
git config --global user.name "abcd1234"
git config --global user.email "abcd1234@student.uu.se"
```

Detta är väldigt bekvämt i de flesta fall.

### Del 3: Lägg till nya filer

Du ska nu lägga till filer i ditt nya repo.

I ditt nya repo, skapa en ny textfil med namn `introduktionskurs.txt`. I denna fil
ska du kopiera in det block med text som innehåller information om din utbildnings introduktionskurs från filen `introduktionskurser.txt`. 

{{% notice style="info" title="" %}}

Filen `introduktionskurser.txt` ska redan finnas i
repot `introduktion-till-datorer-2019-git-uppgift` som du klonade i [Del 1](#del-1-klona-ett-befintligt-git-repo).

{{% /notice %}}

Du ska även lägga till en kopia av filen `kurser.txt` som du också fick med
när du klonade repot i
[Del 1](#del-1-klona-ett-befintligt-git-repo). Detta kan du göra direkt
från terminalen genom att:

- Navigera till din hem-mapp.
- Använda kommandot `cp` för att kopiera filen:
    - `cp introduktion-till-datorer-2019-git-uppgift/kurser.txt abcd1234_git/kurser.txt`,
      där du ersätter `abcd1234` med användarnamnet för ditt studentkonto.


Kontrollera nu att du har filerna `introduktionskurs.txt` och `kurser.txt` i ditt nya
repo.

För att se status för repot, kör kommandot `git status` i terminalen. Git
berättar då följande:

```shell
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

       	introduktionskurs.txt
       	kurser.txt

nothing added to commit but untracked files present (use "git add" to track)
```

För att Git ska hålla reda på historiken på de två nya filerna måste de först
läggas till med kommondot `git add` .

```shell
git add introduktionskurs.txt kurser.txt
```

Kontrollerar du status igen med kommandot `git status` berättar Git följande:

```shell
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

       	new file:   introduktionskurs.txt
       	new file:   kurser.txt
```

Git känner nu till filerna och du kan spara nuvarande versioner av dessa med kommandot `git
commit -m "Initial commit"` där du kan byta ut meddelandet *Initial commit*
till något annat om du så önskar. I terminalen bör du nu se något liknande:

```shell
[master (root-commit) c2a7571] Initial commit
 2 files changed, 583 insertions(+)
 create mode 100644 introduktionskurs.txt
 create mode 100644 kurser.txt
```

Slutligen, om du testar status igen med kommandot `git status` berättar Git
följande:

```shell
On branch master
nothing to commit, working directory clean
```

<br/>
### Del 4: Skapa en ny branch
Nu ska du skapa en ny branch som ska kallas `mitt-urval` och byta till denna:
```shell
git checkout -b <branch-name>
```

När du bytt till denna nya branch ska du skapa filen `urval.txt`. I denna fil ska
du **lägga till två (2) kurser från `kurser.txt`**.

{{% notice style="warning" title="Viktigt!" %}}

Ta inte bort kurserna från `kurser.txt`, kopiera dem!

{{% /notice %}}

Spara sedan filen, se till att Git känner till ändringarna i den och committa med meddelandet **"kopierade kurser till urval"**.

<br/>
### Del 5: Byta gren och modifiera filer
Nu ska vi byta tillbaka till `master`. Här ska vi nu skapa filen `urval.txt` på nytt.

När du gjort detta ska du **klippa ut tre (3) kurser ur `kurser.txt`** och lägga till dem i
`urval.txt`. 

Checka sedan in både den nya filen och ändringarna i
`kurser.txt`, för att sedan committa dem med meddelandet **"flyttade kurser till urval"**.

<br/>
### Del 6: Merge & merge-konflikt
Nu ska vi slå samman ändringarna från vår branch `mitt-urval` med vår `master`-branch.

När du gör detta kommer du märka att en merge-konflikt uppstår, då vi lagt till
filen `urval.txt` i både `mitt-urval` och `master`. 

{{% notice style="info" title="" %}}

Notera att vi inte får konflikt i
`kurser.txt` då vi bara ändrat denna i en branch.

{{% /notice %}}

**Din uppgift** är att *lösa konflikten* i `urval.txt` så att **alla kurser du valt finns med
endast en (1) gång var**. 

När du löst konflikten, se till att Git känner till ändringen och committa sedan med
meddelandet **"löste konflikt"**.

<br/>
### Slutgiltigt repo
När du är färdig med uppgiften bör ditt repo se ut såhär:

```shell
.
└── abcd1234_git
    ├── .git         #(vanligtvis dold mapp med all git-data för repot)
    ├── introduktionskurs.txt
    ├── kurser.txt
    └── urval.txt
```
om du kör `git branch` bör du se detta:
```shell
* master
  mitt-urval
```

och om du kör `git log` bör loggen se ut något liknande detta:

{{% notice style="info" title="Några poster för mycket?" %}}

Om du stött på problem under uppgiftens gång och har ett fåtal
fler poster än exemplet nedan gör det inget, så länge samtliga
poster finns närvarande och det går se att du utfört uppgitens alla steg.
{{% /notice %}}

```shell
commit ea926724103ce4f399b63a8c1abfdf0e35109c44
Merge: c5150d9 ee7cdd9
Author: abcd1234 <abcd1234@student.uu.se>
Date:   Mon Aug 15 20:46:06 2019 +0200

    löste konflikt

commit c5150d9eb273958613067e2b19ed0604f76bc0eb
Author: abcd1234 <abcd1234@student.uu.se>
Date:   Mon Aug 15 20:43:32 2019 +0200

    flyttade kurser till urval

commit ee7cdd91e9869386859af8856ea2b2703db49aca
Author: abcd1234 <abcd1234@student.uu.se>
Date:   Mon Aug 15 20:42:02 2019 +0200

    kopierade kurser till urval

commit 78ec16cf653f2ee67e3bf9b19745b0b5c873c32f
Author: abcd1234 <abcd1234@student.uu.se>
Date:   Mon Aug 15 20:39:56 2019 +0200

    initial commit (eller valfritt meddelande)
```


## Inlämning

Komprimera mappen `abcd1234_git` till en tar.gz-fil och döp denna till `abcd1234_git.tar.gz`, där du
ersätter `abcd1234` med användarnamnet för ditt studentkonto.

   + För att komprimera till gzip och skriva ut alla inkluderade filer och mappar använder du kommandot `tar` tillsammans med flaggorna `-cvzf`.
   + Mer information om hur du komprimerar mappar med kommandot `tar` hittar du [här](/terminal/introduction/#komprimerade-mappar).

{{% notice style="warning" title="Komprimera rätt!" %}}

Det räcker inte att komprimera filerna som finns i mappen, utan hela mappen måste komprimeras.
Annars tappas git-historiken och git-informationen som används för att kontrollera inlämningsuppgiften.

{{% /notice %}}

När du är klar laddar du upp arkivet (med namn på formen `abcd1234_git.tar.gz`
under uppgiften **Git** i Studium. Läs mer [här](/submission-and-deadlines) om
hur du sedan laddar upp filen i Studium.
