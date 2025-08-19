---
title: Uppgift 2 - Samarbete och branches
weight: 40
assignment: mandatory
---

I den här uppgiften bygger vi vidare på det du lärt dig i uppgiften [Kom
igång med git och GitHub](../assignment-1). Du skall nu få pröva på att använda
Git och GitHub för att samarbeta med andra kring ett gemensamt projekt bestående
av samling av filer.

## Detta behöver du

För att lösa uppgiften kommer varje student att behöva:

- En webbläsare
- En terminal
- Programmet `git`
- En [texteditor](/editors)

Uppgiften är testad på och går att utföra på Uppsala universitets Linuxsystem,
men även på egen dator om det som krävs finns installerat.

## Arbeta i par inom basgruppen

Denna uppgift skall göras i par om två studenter inom basgruppen. Är ni ett udda
antal i basgruppen kommer några behöva arbeta tre stycken tillsammans i en
trippel med denna uppgift.

Ni kommer arbeta tillsammans och hjälpas åt men endast en av er kommer behöva
lämna in den här uppgiften i Studium.

## Mål

Efter att paret/trippeln blivit godkända på denna uppgift kommer ni att känna
till hur ni använder Git för att:

- Samarbeta med andra kring samma projekt
- Skapa nya grenar (branches)
- Hantera merge-konflikter.

## Person A, B och C

För att hålla reda på vem som skall göra vad kommer följande beteckningar att
användas. 

Person A
: En person skall skapa ett repo på GitHub. Vi kommer kalla denna person för A. 

Person B
: Den andra personen i paret kommer att kallas för person B.

Person C
: Om ni är en trippel kommer den tredje personen att kallas person C. 

## Skapa ett nytt repo (A) 

Person A skapar ett nytt publikt repo på GitHub och döper det till
`abcd1234-abcd1234-git-collaboration` om ni är ett par eller
`abcd1234-abcd1234-abcd1234-git-collaboration` om ni är är en trippel, där ni
ersätter `abcd1234` med era användarnamn vid Uppsala universitet.

## Bjud in andra deltagare (A)

Person A bjuder in person B (och person C om det finns en tredje) till repot. 

![](/images/git/invite.jpg)

Person B (och person C) behöver acceptera inbjudan genom att logga in på sitt mejl. 

## Skicka repo-länken (A)

Person A skickar repo-länken till övriga (B och C) via *Studium* som meddelande.

## Klona repot (alla)

När ni alla har tillgång till repo-länken kan ni navigera till er hemkatalog och
klona repot med kommandot `git clone` följt av er länk. Exempelvis:

```shell
$> git clone https://github.com/KianRafi1/abcd1234_abcd1234-git-collaboration.git
``` 

## Skapa filen members.txt (A)

Person A skapar och lägger till filen `members.txt` till sitt lokala repo med
`git add`. I denna fil lägger sedan person A till följande information om sig
själv. 

- Användarnamn på GitHub.
- Namn.
- Epost-adress vid Uppsala universitet. 

Det skall se ut ungefär så här.

``` text
Användare på GitHub: ArneAnka
Namn: Arne Andersson
Epost: arne.andersson.1234@student.uu.se
```

Person A gör `git commit` på filen `members.txt` med ett lämpligt commit meddelande.
Sedan gör person A `git push` till repot på GitHub.

**Tips:** Om någon skulle få ett felmeddelande när de kör `git push` se till att hen använder ett personal access 
token och inte sitt lösenord. Instruktioner för hur man skapar dessa finns på denna länk: [Uppgift 1 - Personal access token](/git/assignment-1/#personal-access-token).

## Lägg till person B till members.txt (B)

Person B gör `git pull` för att få den senaste uppdateringen från person
A. Person B lägger sedan på egen hand till sina användarnamn, för- och efternamn och
epost-adresser till `members.txt`. Gör commit och pushar upp till repot på
GitHub. 

## Lägg till person C till members.txt (C)

Om ni är tre som arbetar tillsammans gör sedan person C `git pull`, lägger till
sin information i filen `members.txt`, commitar och pushar upp till repot på
GitHub. 

## Är ni i synk? (alla)

Alla gör nu en `git pull` för att se om det finns uppdateringar att hämta från
repot på GitHub. Om ni är tre stycken skall innehållet i filen `members.txt` nu
se ut ungefär så här i allas lokala repos.

``` text
Användare på GitHub: ArneAnka
Namn: Arne Andersson
Epost: arne.andersson.1234@student.uu.se

Användare på GitHub: brittan
Namn: Britta Bengtsson
Epost: britta.bengtsson.1234@student.uu.se

Användare på GitHub: Carro99
Namn: Carolina Collberg
Epost: carolina.collberg.1234@student.uu.se
```

## Skapa filen myList.txt (A)

Person A skapar filen `myList.txt` och klistra in följande:

```shell
1. First
```

## Publicera på GitHub (A)

Spara ändringarna med `git add` och committa med kommandot `git commit` och
meddelandet `First - added`.

Publicera detta sedan på GitHub med kommandot `git push`.

## Git pull (B)

Person B hämtar den nya versionen av repot från GitHub med kommandot `git pull`.

Person B kollar nu status för sitt lokala repo. 

``` shell
$> git status
```

Du bör nu se följande status. 

```shell
On branch main
```
alternativt 
```shell
On branch master
```

## Skapa en ny branch (B)

Person B skall nu skapa en ny branch med kommandot `git checkout -b` följt av den
nya branchens namn, till exempel så här. 

``` shell
$> git checkout -b nyBranch
```

I terminalen bör du se något liknande detta. 

```shell
Switched to a new branch 'nyBranch'
```

Använd kommandot `git branch` för att kontrollera vilken branch du är på. 

``` shell
$> git branch
```

I resultatet skall den nya branchen vara markerad med `*` vilket betyder att ni är på denna branch. 
  
```shell
  main
* nyBranch
```
alternativt
```shell
  master
* nyBranch
```
## Ändra myList.txt (B)

Öppna textfilen `myList.txt` och klistra in följande för att ersätta förra texten:

```shell
1. First
2. Second
```

## Committ (B)

Spara ändringen med `git add` och gör `git commit -m "Second - added"`.

## Byt branch (B)

Byt tillbaka till main branchen med kommandot `git checkout main`. Ni bör då se följande: 

```shell
Switched to branch 'main'
```
alternativt
```shell
Switched to branch 'master'
```
Kontrollera sedan vad som står i myList.txt i main branchen med kommandot `cat`.

Du bör se följande i myList.txt på main branchen: 

```shell
1. First
```

## Ändra myList.txt igen (B)

Se till att du är på *main* branchen och ändra myList.txt genom att lägga till i andra raden följande text: 

```shell 
2. Third
```
Så att det ser ut på följande sätt:

```shell
1. First
2. Third
``` 

Spara sedan detta och commita med meddelandet `"Third - added"`.

## Merge (B)

Använd dig av kommandot `git merge` följt av er branch namn.
Ni bör se följande: 

```shell
Auto-merging myList.txt
CONFLICT (content): Merge conflict in myList.txt
Automatic merge failed; fix conflicts and then commit the result.
```

## Fixa merge konflikt (B)

Printa ut innehållet i myList.txt med kommandot `cat`. Ser ni något liknande detta?

```shell
1. First
<<<<<<< HEAD
2. Third
=======
2. Second
>>>>>>> nyBranch
```

Ni ska få den att se ut på följande sätt:

```shell 
1. First
2. Third
3. Second
```
Notera att `2.` byts ut till `3.` på tredje raden. 

## Publicera detta på GitHub (B)

Slutligen kan den som fixat merge konflikten spara (`git add`), committa med
meddelandet `"Fixat merge konflikt"` (`git commit`) samt publicera detta på GitHub
med kommandot `git push`.

## Extra steg om ni är tre

Om ni är tre som arbetar tillsammans följer nu några extra steg som bara skall
utföras av denna tredje person C. Om ni är två personer som arbetar hoppar ni
direkt vidare till [inlämning](.#inlämning) längst ner på denna sida.

## Git pull (C)

Person C hämtar den senaste versionen av repot med kommandot `git pull`.

Person C kan kontrollera status med `git status`

``` shell
$> git status
```

Du bör nu se följande status. 

```shell
On branch main
```

## Ändra myList.txt (C)

Lägg till i myList.txt en fjärde punkt så att det ser ut som följande:

```shell
1. First
2. Third
3. Second
4. Fourth
```

Glöm inte att committa ändringen och pusha till repot på GitHub. 

## Inlämning

En av er kan kopiera adressen till repot ni skapat på GitHub och lämna in
adressen på angiven plats nedan. 

| Program    | Inlämning                       |
| :--------: | :--------:                      |
| IT/KandDv  | [Studium][it-kanddv-submission] |

[it-kanddv-submission]: https://uppsala.instructure.com/courses/48011/assignments/80140

Här hittar du mer information om hur du lämnar in uppgifter: 

- [Allmänt om inlämning i Canvas][canvas-submission].
- [Allmänt om inlämning i Studium][studium-submission].

[canvas-submission]: /submission-and-deadlines/#inlämning-av-uppgifter-i-canvas-es
[studium-submission]: /submission-and-deadlines/#inlämning-i-studium-för-alla-utom-es

