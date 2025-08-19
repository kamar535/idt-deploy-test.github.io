---
title: Uppgift 1 - Kom igång med Git och GitHub
weight: 20
assignment: mandatory
---

Med hjälp av denna uppgift kommer du få testa på grunderna vid arbete med Git och GitHub.

{{% notice style="warning" title="Viss terminalvana erfordras" %}}

Det är starkt rekommenderat att du löst uppgifterna i modulen
[Terminalen](/terminal) innan du påbörjar den här uppgiften.

{{% /notice %}}


## Arbeta och lämna in individuellt

Denna uppgift skall du arbeta med, lösa och lämna in på egen hand individuellt.
Om du kör fast får du gärna diskutera med andra i din basgrupp för att komma
vidare men se till att du själv lär dig och förstår vad du gör.

## Detta behöver du

För att lösa uppgiften kommer varje student att behöva:

- En webbläsare
- En terminal
- Programmet `git`
- En [texteditor](/editors)

Uppgiften är testad på och går att utföra på Uppsala universitets Linuxsystem,
men även på egen dator om det som krävs finns installerat.

## Mål

Efter att du blivit godkänd på denna uppgift kommer du att känna till hur man
använder Git för att:

- Skapa ett nytt lokalt repo
- Hanterar historiken för enskilda filer

Du kommer även lära dig att:

- Skapa ett publikt repo på GitHub
- Publicera ditt lokala repo på GitHub


## Öppna en terminal

Öppna en terminal. Längst till vänster nere i terminalen ser du prompten, det
kan se lite olika ut, till exempel så här:

``` shell
beurling>
```

Där `beurling> ` utgör prompten. I fortsättning kommer `$>` att användas för
att representera prompten i terminalen.

## Vem är du?

Använd kommandot `whoami` för att ta reda ditt användarnamn.

``` shell
$> whoami
```

I terminalen bör du nu se ditt användarnamn på formen `abcd1234`.

``` shell
abcd1234
```

Notera att du kommer se något annat än `abcd1234`, du kommer se ditt unika
användarnamn. I fortsättningen kommer dock `abcd1234` att användas för att
representera ditt användarnamn.

## Vart befinner du dig?

Använd kommandot `pwd` för att ta reda på den absoluta sökvägen till den katalog
som du nu befinner dig i.

``` shell
$> pwd
```

Resultatet ser troligen ut något liknande detta.

``` shell
/home/abcd1234
```

Notera att ditt användarnamn utgör den sista delen i den absoluta sökvägen. I
detta fall säger man att du står i din hemkatalog.

## Skapa en ny katalog

Skapa katalogen `abcd1234-git-test` med hjälp av kommandot `mkdir` där du byter
ut `abcd1234` mot ditt användarnamn.

``` shell
$> mkdir abcd1234
```

## Kontrollera att katalogen skapats

Utför kommandot `ls` för att lista alla filer och mappar i den aktuella
katalogen.

``` shell
$> ls
```
Resultatet kan se ut till exempel så här.

``` shell
abcd1234-git-test  public_html
```

Kontrollera att den nya mappen `abcd1234-git-test` nu finns med i resultat från
`ls`.

## Gå in i den nya katalogen

Använd kommandot `cd` för att gå in i den nya katalogen.

``` shell
$> cd abcd1234-git-test
```

Kontrollera att den absoluta sökvägen ändrats.


``` shell
$> pwd
```

Du bör nu se något liknande detta.


``` shell
/home/abcd1234/abcd1234-git-test
```

## Öppna en texteditor

Öppna en [texteditor](/editors). På universitetets Linux-system kan du till
exempel använda Gedit. Du hittar **Gedit** (3) från menyn **Applications** (1)
under kategorin **Accessories** (2).

![](/images/git/applications-accessories-gedit.png?width=555px)


## Skapa ny fil

Använd din texteditor för att skapa en fil med följande innehåll men där du
byter ut `brown` mot namnet på din favoritfärg.

``` text
My favorite color is brown.
```

Spara filen med namn `color.txt`.

## Kontrollera att filen skapats

Kontrollera från terminalen att filen skapats. Först med kommandot `ls`.

``` shell
$> ls
```

Nu bör du se `color.txt` i resultatet från `ls`.

``` shell
color.txt
```

Med kommandot `cat` kan du skriva ut innehållet en fil till terminalen.


``` shell
$> cat color.txt
```

Du bör nu se något liknande detta.


``` shell
My favorite color is brown.
```

## Initiera ett nytt Git-repo

Du har nu skapat en ny katalog som i sin tur innehåller en ny fil. För att kunna
spåra ändringar och kunna gå tillbaka till gamla versioner av filer är det nu
dags att göra katalogen `abcd1234-git-test` till ett Git-repo.

Använd kommandot `git init` i terminalen för att initiera ett nytt Git-repo.

``` shell
$> git init
```

Om det funkar bör du se något liknande detta som resultat i terminalen.

``` shell
Initialized empty Git repository in /home/abcd1234/abcd1234-git-test/.git/
```

## Kontrollera status

Kontrollera status på ditt nya repo med hjälp av kommandot `git status`.

``` shell
$> git status
```

I terminalen bör du nu se något liknande detta.

``` shell
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        color.txt

nothing added to commit but untracked files present (use "git add" to track)
```

Av detta status-meddelande framgår att du inte gjort några commits till repot
ännu samt att det finns en fil som ännu inte spåras av git (untracked files).

Notera att filen `color.txt` finns i katalogen `abcd1234-git-test` men att du
ännu inte berättat för Git att denna fil skall spåras av Git. Filen finns alltså
i katalogen men än så länge spåras den inte av Git och är inte med i repot.

## Spåra filen

För att berätta för Git att du vill att filen `color.txt` skall spåras av Git
använder du kommandot `git add`.

``` shell
$> git add color.txt
```

Om det går bra skrivs inget ut till terminalen.

## Kontrollera status

Kontrollera status på repot igen.

``` shell
$> git status
```

I terminalen bör du nu se något liknande detta.

``` shell
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

        new file:   color.txt

```

Filen `color.txt` spåras nu av Git.


## Commit

Varje gång du vill spara en viss version av en fil måste du göra commit. Det är
endast till dessa commits du kommer kunna gå tillbaka senare om du skulle ångra
några ändringar.

I meddelandet från `git status` ovan ser vi att filen `color.txt` finns listad
under `Changes to be committed`. När du gör en commit kommer alla filer som
listas under denna rubrik att tas med när du gör commit. Vid en commit måste du
även ange ett kort meddelande som beskriver vad du ändrat eller lagt till. För
att ange detta meddelande används flaggan `-m` följt av meddelandet inom
citattecken `"` och `"`. `

``` shell
$> git commit -m "I like brown"
```

Efter en lyckad commit bör du se något liknande följande i terminalen.

``` shell
[master (root-commit) c7762ff] I like brown
 Committer: Adam Andersson <abcd1234-test01@beurling.it.uu.se>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 1 insertion(+)
 create mode 100644 color.txt
```

## Kolla i loggen

Alla commits loggas. Du kan kontrollera loggen med kommandot `git log`.

``` shell
$> git log
```

I terminalen bör du nu se något liknande detta.

``` shell
commit c7762ffaa1d9cb6d32b0e33340542c63efc2fed0 (HEAD -> master)
Author: Adam Andersson <abcd1234-test01@beurling.it.uu.se>
Date:   Fri Aug 20 17:42:20 2021 +0200

    I like brown
```

Varje commit får ett unikt id, i detta fall
`c7762ffaa1d9cb6d32b0e33340542c63efc2fed0` som står överst. I loggen framgår
även datum och tidpunkt för varje commit. Efter datumet ser du sedan meddelandet
(beskrivningen) som du angav när du gjorde commit, i detta fall `I like brown`.

## Ändra favoritfärg

Använd din texteditor för att ändra favoritfärg. I detta exempel ändrar vi i
filen `color.txt` från

``` text
My favorite color is brown.
```

till

``` text
My favorite color is orange.
```

Glöm inte att spara filen.

## Kontrollera status

Kontrollera status på repot igen.

``` shell
$> git status
```

I terminalen bör du nu se något liknande detta.

``` shell
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   color.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Git har nu upptäckt att du gjort en ändring i filen `color.txt` sedan din senaste
commit.

## Gör en ny commit

Varje gång du vill göra en commit måste du först berätta för Git att filen skall
tas med genom att lägga till den med `git add`.

``` shell
$> git add color.txt
```

Kontrollera status igen.

``` shell
$> git status
```

Nu bör du se något liknande detta.

``` shell
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   color.txt
```

Återigen finns filen `color.txt` med under rubriken `Changes to be committed`. Nu
kan du göra en commit av denna nya version.

``` shell
git commit -m "I now like orange better"
```

## Kolla loggen

Vi kollar loggen igen.

``` shell
$> git log
```

I loggen ser vi nu båda våra commits.

``` shell
commit dca4e654d3cf6ffdb9ab4ce0a76633332a101a55 (HEAD -> master)
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 18:03:44 2021 +0200

    I now like orange better

commit c7762ffaa1d9cb6d32b0e33340542c63efc2fed0
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 17:42:20 2021 +0200

    I like brown
```


## Ändra favoritfärg

Använd din texteditor för att ändra favoritfärg en gång till. I detta exempel ändrar vi i
filen `color.txt` från

``` text
My favorite color is orange.
```

till

``` text
My favorite color is blue.
```

Glöm inte att spara filen.

## Kolla status

Kontrollera status igen.

``` shell
$> git status
```

Nu bör du se något liknande detta.

``` shell
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   color.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Git har återigen upptäckt att du ändrat filen `color.txt` sedan din senaste
commit.

## Se skillnad mellan senaste commit

Notera att vi ännu inte har gjort en commit på vår senaste ändring av `color.txt`. Om vi vill
ändra oss igen men glömt bort vilken vår gamla favoritfärg var kan vi fråga Git
med kommandot `git diff`.

``` shell
$> git diff
```

Du bör nu se något likande detta.

 ``` shell
diff --git a/color.txt b/color.txt
index 0fca394..01fa2ad 100644
--- a/color.txt
+++ b/color.txt
@@ -1 +1 @@
-My favorite color is orange.
+My favorite color is blue.
 ```

 I detta fall används `-` för att representera den senaste versionen som du gjort
 commit på och `+` den version du just nu arbetar på men ännu inte gjort commit
 på. Här ser vi alltså att vi ändrat favoritfärg från `orange` till `red`. För
 tillfället är det inte viktigt att vi sätter oss in i alla detaljer i
 resultatet från `git diff`. Det viktiga är att vi sett ett exempel på att Git
 håller reda på historiken på commits vi gjort.


## Återställ till din senaste commit

För att automatiskt återställa filen `color.txt` till den version du commitat kan
vi använda kommandot `git checkout`.

``` shell
$> git checkout color.txt
```

Du bör nu se något liknande detta.

``` shell
Updated 1 path from the index
```

Innehållet i filen `color.txt` skall nu ha återställts. Öppna filen i din
texteditor för att kontrollera att innehållet återställs. Ett annat sätt att
kontrollera innehållet i en fil direkt från terminalen är med hjälp av kommandot
`cat`.

``` shell
$> cat color.txt
```

Innehållet i filen `color.txt` skrivs nu ut i terminalen.

``` shell
My favorite color is orange.
```

## Kolla status

Kontrollera status igen.

``` shell
$> git status
```

Nu bör du se något liknande detta.

``` shell
On branch master
nothing to commit, working tree clean
```

## Återställ till specifik version

Med hjälp av Git går det även att återställa till en specifik version. Vi börjar
med att kolla i loggen.

``` shell
$> git log
```

I loggen ser vi två commits med den senaste längst upp och den första längst
ner.

``` shell
commit dca4e654d3cf6ffdb9ab4ce0a76633332a101a55 (HEAD -> master)
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 18:03:44 2021 +0200

    I now like orange better

commit c7762ffaa1d9cb6d32b0e33340542c63efc2fed0
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 17:42:20 2021 +0200

    I like brown
```

Varje commit börjar med raden `commit ` och sedan följer ett långt hexadecimalt
tal. Dessa hexadecimala tal är respektive commits unika id. I detta fall ser vi
att vår första commit längst ner har id `c7762ffaa1d9cb6d32b0e33340542c63efc2fed0`.

För att återställa till vår första version av filen `color.txt` kan vi använda
detta id tillsammans med `git checkout`.

``` shell
$> git checkout c7762ffaa1d9cb6d32b0e33340542c63efc2fed0 color.txt
```

Om det går bra bör du nu se något liknande detta i terminalen.

``` shell
Updated 1 path from f3d8575
```

Kolla om innehållet i `color.txt` har återställts.

``` shell
$> cat color.txt
```

Nu skall innehållet i den återställda filen skrivas ut i terminalen.

``` shell
My favorite color is brown.
```

## Kontrollera status

Kontrollera status igen.

``` shell
$> git status
```

Nu bör du se något liknande detta.

``` shell
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   color.txt
```

Notera att eftersom du återställt filen `color.txt` så har den ändrats. Denna
ändring har upptäckts av Git precis som om du skulle ha uppdaterat filen
manuellt.

## Gör en ny commit

Du har tillslut kommit fram till att brun är den bästa färgen. Innan du gör
commit måste du först lägga till filen men `git add`.

``` shell
$> git add color.txt
```

Nu kan du göra en commit.

``` shell
git commit -m "Sorry brown, you and me forever"
```

För säkerhets skull kollar vi loggen också.

``` shell
$> git log
```

Din nya commit skall nu finnas med överst i loggen.

``` shell
commit 88606137bc39ffe8d4529dbc934172f95e70e754 (HEAD -> master)
Author: kamar535 <karl.marklund@it.uu.se>
Date:   Fri Aug 20 19:40:34 2021 +0200

    Sorry brown, you and me forever

commit dca4e654d3cf6ffdb9ab4ce0a76633332a101a55 (HEAD -> master)
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 18:03:44 2021 +0200

    I now like orange better

commit c7762ffaa1d9cb6d32b0e33340542c63efc2fed0
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 17:42:20 2021 +0200

    I like brown
```

## Testa på egen hand

På egen hand skall du nu lägga till en fil till med namn `food.txt`. I denna fil
skall du skriva något likande detta.


``` shell
My favorite food is pizza.
```

Lägg till filen med `git add` och gör en commit med till exempel `git commit -m "I only eat
pizza"`. Ändra din favoritmat några gånger och gör en ny commit för varje ändring.

När du är klar skall katalogen `abcd1234-git-test` innehålla de två filerna
`color.txt` och `food.txt`. Testa att lista innehållet i ditt repo med kommandot
`ls`.

``` shell
$> ls
```

Resultatet skall se ut så här.

``` shell
color.txt  food.txt
```


Du kan även använda kommandot `tree` för att lista innehållet i en katalog som
ett träd.

``` shell
$> tree
```

Om du redan står i katalogen `abcd1234-git-test` kommer resultatet att se ut så
här.

``` shell
.
|-- color.txt
`-- food.txt

0 directories, 2 files
```

När du är klar skall Git-loggen se ut ungefär så här.


``` shell
commit 594cdc385692762e68e4a9672d4fae2a78c37d92 (HEAD -> master)
Author: kamar535 <karl.marklund@it.uu.se>
Date:   Fri Aug 20 19:49:08 2021 +0200

    So sweet

commit 62e83492a0d72c1721ae519a0079e4c6a7b36411
Author: kamar535 <karl.marklund@it.uu.se>
Date:   Fri Aug 20 19:47:27 2021 +0200

    Waffles are better

commit 11ee6f0d222e2b3123762781e7e5e662ae6536f7
Author: kamar535 <karl.marklund@it.uu.se>
Date:   Fri Aug 20 19:45:32 2021 +0200

    Pizza is the best

commit 88606137bc39ffe8d4529dbc934172f95e70e754 (HEAD -> master)
Author: kamar535 <karl.marklund@it.uu.se>
Date:   Fri Aug 20 19:40:34 2021 +0200

    Sorry brown, you and me forever

commit dca4e654d3cf6ffdb9ab4ce0a76633332a101a55 (HEAD -> master)
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 18:03:44 2021 +0200

    I now like orange better

commit c7762ffaa1d9cb6d32b0e33340542c63efc2fed0
Author: Adam Andersson <abcd1234@beurling.it.uu.se>
Date:   Fri Aug 20 17:42:20 2021 +0200

    I like brown
```

## Skapa konto på GitHub

För att enkelt kunna samarbeta med andra behövs ett gemensamt repo online.
GitHub erbjuder exakt detta. Innan du fortsätter behöver du skapa ett konto på
[GitHub][github] om du inte redan har ett sådant. Det är gratis att skapa ett
konto på GitHub och du kommer behöva ett sådant på kurser längre fram.

[github]: https://github.com/

## Skapa ett nytt repo på GitHub

När du loggat in på ditt konto på GitHub skall du nu skapa ett nytt repo på
GitHub. I övre vänstra hörnet trycker du först på knappen **New** (1).

![](/images/git/new.png)

Nu skall du ge repot ett namn.

![](/images/git/github-create-new-repo.png)

I fältet **Repository name** (2) skriver du `abcd1234-git-test` där du ersätter
`abcd1234` med användarnamnet på ditt studentkonto vid Uppsala universitet.
Kontrollera sedan att repot är publikt.

Kontrollera att repot är publikt (3).

Tryck sedan på **Create repository** (4). Nu skall du se något liknande detta.


![](/images/git/github-quick-setup.png)


Det vi för tillfället är intresserade av är alternativet **...or push an
existing repository from the command line**. Kopiera de tre raderna med
git-kommandon som listas här (5), vi kommer använda dem senare. 

## Personal access token

För att kunna pusha vårat lokala repository till vårat nya GitHub repo så kommer du att behöva skapa vad som kallas för
ett personal access token. Detta kommer du använda istället för ditt lösenord när du vill logga in 
på GitHub via terminalen eller via API.

### Steg 1

![](/images/git/stg1.jpg?width=244px)

Klicka på din profil på GitHub och klicka sedan på **settings**.

### Steg 2

![](/images/git/steg2.jpg?width=644px)

Klicka på **Developer settings**.

### Steg 3

![](/images/git/steg3_1.jpg?width=344px)

Klicka sedan på **Personal access tokens** 

![](/images/git/steg3_2.jpg?width=944px)

Sedan på **Generate new token**. 

### Steg 4
Skriv *"GitHub"* i **Note**.
Boka i **repo** fältet.

![](/images/git/steg4.jpg?width=944px)

Klicka sedan på **Generate token**. Se till att spara ditt nya personal access token om 
du vill använda det igen, du kan inte få fram det på GitHub igen efter att du skapat det.

### Steg 5
När du frågas om användarnamn och lösenord i terminalen så använder du sedan ditt GitHub användarnamn som användarnamn och ditt personal access token som lösenord.

Din personal access token kan exempelvis se ut såhär:
```shell
 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
 ```

## Pusha ditt lokala repo till GitHub

Nu kan du pusha ditt lokala repo till det publika repot på GitHub från
terminalen. Klistra sedan in raderna du fick på GitHub efter att du skapat ditt repo.

``` shell
git remote add origin https://github.com/YOUR-GITHUB-USERNAME/abcd1234-git-test.git
git branch -M main
git push -u origin main
```

Det är det första kommandot `git remote add origin` som sätter upp repot på
GitHub som en remote för ditt lokala repo. Det tredje kommandot `git push -u
origin master` pushar sedan ditt lokala repo till repot du satt som upp som
remote, dvs pushar till repot på GitHub.

Tryck **enter** för att utföra kommandona ovan. I terminalen skall du nu se
något liknande detta. 


``` shell
Enumerating objects: 16, done.
Counting objects: 100% (16/16), done.
Delta compression using up to 12 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (16/16), 1.36 KiB | 1.36 MiB/s, done.
Total 16 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), done.
To https://github.com/kamar535/abcd1234-git-test.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.
```

Ladda om webbsidan på GitHub. Det skall nu se ut ungefär så här. 

![](/images/git/github-after-inital-push.png)

## Kika på filer på GitHub

Klicka på `color.txt` (6). 

![](/images/git/github-click-on-color.png?width=600px)

Nu skall du se innehållet (7) i filen `color.txt`.

![](/images/git/github-color-1.png?width=600px)

Härifrån kan du klicka på **History** (8). 

![](/images/git/github-color-2.png?width=600px)

Nu får du se historiken för just den här filen.
 
![](/images/git/github-color-history.png?width=600px)

## Inlämning

Klicka på `abcd1234-git-test` (9) överst på sidan för att komma tillbaka till
startsidan för repot. 

![](/images/git/github-color-3.png?width=600px)

Klicka sedan på **Code** (10).

![](/images/git/github-code-button.png?width=600px)

Kopiera adressen till repot (11). 

![](/images/git/github-clone-url.png?width=600px)

Lämna in den kopierade adressen till repot på angiven plats nedan. 

| Program    | Inlämning                       |
| :--------: | :--------:                      |
| IT/KandDv  | [Studium][it-kanddv-submission] |

[it-kanddv-submission]: https://uppsala.instructure.com/courses/48011/assignments/80138

Här hittar du mer information om hur du lämnar in uppgifter: 

- [Allmänt om inlämning i Canvas][canvas-submission].
- [Allmänt om inlämning i Studium][studium-submission].

[canvas-submission]: /submission-and-deadlines/#inlämning-av-uppgifter-i-canvas-es
[studium-submission]: /submission-and-deadlines/#inlämning-i-studium-för-alla-utom-es

