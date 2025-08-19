---
title: Uppgift 1 - GitHub
weight: 20
pre: <i class="far fa-keyboard"></i>
draft: true
---

{{% notice style="warning" title="Viss terminalvana erfordras" %}}

Det är starkt rekommenderat att du löst uppgifterna i modulen
[Terminalen](/terminal) innan du påbörjar den här uppgiften.

{{% /notice %}}

## Arbeta i par inom basgruppen

Denna uppgift skall göras i par om två studenter inom basgruppen. Är ni ett udda antal i
basgruppen kommer några behöva arbeta tre stycken tillsammans med denna uppgift.

## Detta behöver du

För att lösa uppfiten kommer varje student att behöva:

- En terminal
- Programmet `git`
- Konto på [GitHub](https://github.com/)
- Textredigeringsprogram
- Programmet `tar`

Uppgiften är testad på och går att utföra på Uppsala universitets Linuxsystem,
men även på egen dator om det som krävs finns installerat.

## Mål

Efter att paret blivit godkända på denna uppgift kommer ni att känna till hur ni
använder Git och GitHub för att:

- Skapa ett nytt repository på GitHub
- Klona ett git-repository
- Lägga till och committa filer
- Publicera den nya versionen på GitHub

## Uppgift

Materialet som tas upp i uppgiften diskuteras på [introduktionssidan för Git](../introduction).

Ett git-repository är en katalog som hanteras av Git. För enkelhets skull kommer
*git-repo* fortsättningsvis att användas synonymt med *git-repository*.

På många kurser kommer du utgå från befintliga filer för att lösa olika typer av
uppgifter. Ett vanligt sätt att hantera detta, speciellt på
programmeringskurser, är att dessa filer finns tillgängliga i publikt
git-repo och att du hämtar hem dem genom att klona detta repo.

### Del 1: Skapa ett GitHub konto (alla)

Om du inte redan gjort det behöver du skapa ett konto på
[GitHub](https://github.com/). Detta gäller **alla i paret**.

### Del 2: En skapar ett nytt repository på GitHub (skaparen)

**En i paret** ska sedan skapa ett nytt repository på GitHub. I fortsättning
kommer denna person att kallas **skaparen**. 

För att skapa ett nytt repository klickar du på den gröna knappen *New*.

{{< figure src="/images/git/newRepository.png"
title="Tryck på 'New' för att skapa ett repo" >}}

I fältet *Repository name* skriver ni `abcd1234_abcd1234-GruppX` där ni ersätter
`abcd1234` med användarnamnet för era respektive studentkonton. Om ni är tre i en grupp kan
ni även lägga till den tredje personens användarnamn
(`abcd1234_abcd1234_abcd1234`). Ni ersätter även `GruppX` med vilken basgrupp ni
tillhör. Kontrollera sedan att repot är publikt.

{{< figure src="/images/git/newRepositoryName.png"
title="Publikt repo på GitHub">}}

### Del 3: Bjud in andra (skaparen)

Den som skapat repot behöver bjuda in sin partner. Det kan ni göra genom att
**1. klicka på settings** **2. manage access** **3. invite a collaborator.** Ni
skriver sedan in användarnamnet. Partnern behöver sedan godkänna inbjudandet
från sitt konto.

{{< figure src="/images/git/settings-manageaccess.png"
title="Bjud in er partner">}}

### Del 4: Skapa filer (skaparen)

Den som skapat repot på GitHub skall nu skapa och lägga till några filer till
repot. Normalt görs detta direkt från terminalen men det finns även stöd på
GitHub för att göra detta direkt i webbläsaren. Som ett första steg använder vi
funktionerna på GitHubb. Längre fram kommer du få lära dig hur du använder
terminalen på motsvarande sätt. 

Klicka på *code* och sedan *create new file* och namnge filen till *Begrepp*.

{{< figure src="/images/git/newfile.png"
title="Skapa en ny fil">}}

Kopiera och klistra in följande i er fil. 

```shell

Begrepp

Algoritm:

-- KLISTRA IN SVARET HÄR --

Lus (bugg):

-- KLISTRA IN SVARET HÄR --

Bit: 

-- KLISTRA IN SVARET HÄR --


```
Skrolla ner och klicka på *Commit new file*.

Nu ska ni få skapa en till fil. Klicka på *Add file* och *Create new file*.

{{< figure src="/images/git/newfile2.png"
title="Skapa en ny fil">}}

Namnge filen till "Begrepp-Svar" och klistra in följande:

```shell

Begrepp

Algoritm:

En algoritm är en systematisk procedur som i ett ändligt antal steg utför en beräkning eller löser ett givet problem.

Lus (bugg):

En bugg, även lus, är en felaktighet i datorprogram som gör att programmet inte beter sig som tänkt.
Det kan leda till att programmet ger felaktigt resultat eller att det kraschar.

Bit: 

Bit (från engelska binary digit). En bit kan anta ett av två värden, som vanligen representeras av 0 eller 1.

```

{{% notice style="warning" title="Var noggrann!" %}}

Det är viktigt att samtliga delar av uppgiften utförs i korrekt ordning,
annars kommer inlämningen inte stämma och sannolikt resultera i komplettering!

{{% /notice %}}

### Del 5: Klona repot (alla)

Var och en skall nu klona repot och kopiera ett av svaren från textfilen *Begrepp-Svar*
och klistra in i textfilen *Begrepp*. 

**Steg 1 till 3 ska ni alla göra i er
grupp. Efter steg 3 ska endast en av er utföra steg 4 till 12.** Den andra kan
så klart hjälpa till.

Så här gör ni:

**Steg 1.** Öppna terminalen och kolla vilken map ni befinner er i med kommandot
`pwd`. Är du i din hemkatalog? Om du vill navigera till någon annan katalog gör
du det med kommandot `cd`. 

**Steg 2.** Klona ertr repo genom att kopiera länken från er repository. 

{{< figure src="/images/git/link.png" title="Er länk till repositoryn">}}

**Steg 3.** I terminalen, skriv `git clone`, följt av er länk, till exempel så
här: 

``` shell
$> git clone http://github.com/KianRafi1/abcd1234_abcd1234-grupp-X.git
```

Tryck **enter** för att utföra kommandot. I terminalen bör ni nu se något liknande detta:

```shell
    Cloning into 'abcd1234_abcd1234-GruppX'...
    remote: Counting objects: 12, done.
    remote: Compressing objects: 100% (10/10), done.
    remote: Total 12 (delta 0), reused 6 (delta 0), pack-reused 0
    Unpacking objects: 100% (12/12), done.
    Checking connectivity... done.
```

## Del 5: ändra och publicera

**Steg 4.** Den i gruppen som utför steg 4 till 12 kontrollerar med `ls` att mappen finns i er hemkatalog

**Steg 5.** Navigera till mappen med `cd` och kontrollera med `ls` att textfilerna *Begrepp* och *Begrepp-Svar* som ni skapat finns.

**Steg 6.** Kopiera nu ett av svaren i *Begrepp-Svar* filen och klistra in den i *Begrepp*.

Detta gör du med hjälp av kommandot `cat` följt av textfilen med svar för att printa ut innehållet. 

Använd dig nu av kommandot `nano` följt av textfilen utan svar för att redigera textfilen. 

Printa sedan ut textfilen du redigerat för att kontrollera att det ändrats. (Använd alltså `cat`) 

**Steg 7.** Nu kan vi fråga Git vad den tycker om livet. Så skriv `git status`. 

Du bör se ett oincheckat fil i rött. 

**Steg 8.** Lägg till den nya filen genom att använda kommandot `git add` följt av ditt oincheckade fil (alternativt `git stage`)

**Steg 9.** Kolla status igen. Är det grönt?

**Steg 10.** Nu kan du commita med hjälp av kommandot `git commit -m "Klistrat in första begreppet`. 

**Steg 11.** Kolla status igen. 

**Steg 12.** Slutligen, använd dig av kommandot `git push` för att publicera ändringarna på GitHub. Skriv sedan in ditt användarnamn och lösenord. 

**Steg 13.** Din partner skall nu använda sig av kommandot `git pull` för att hämta de nya ändringarna. Kontrollera att ni är i hemkatalogen.

**Steg 14.** Nu kan din partner repetera steg 4 till 12 för att klistra in ett annat svar från textfilen *Begrepp-Svar* till textfilen *Begrepp*. **OBS!** i *Steg 10* skriver partnern som meddelande `"Klistrat in andra begreppet"` (alternativt `"Klistrat in tredje begreppet"` om det är den tredje i gruppen som utför detta). Är ni tre i gruppen skall alla tre utföra steg 4 till 12.

## Inlämning

När ni är klara kan den sista i gruppen som publicerat på GitHub komprimera mappen `abcd1234_abcd1234-GruppX` (eller `abcd1234_abcd1234_abcd1234-GruppX` om ni är tre) till en tar.gz-fil och skicka in den i Studium. Tänk på att navigera ut från filen först för att komprimera hela mappen. Det gör ni genom kommandot `cd ..`. 

   + För att komprimera till gzip skriver ni `tar -cvzf abcd1234_abcd1234-GruppX.tar.gz abcd1234_abcd1234-GruppX` (eller `abcd1234_abcd1234_abcd1234-GruppX.tar.gz` om ni är tre). Notera att er filnamn kommer efter. Ni ersätter `abcd1234` med era användarnamn för er studentkonto och `GruppX` med vilken basgrupp ni är i.
   + Mer information om hur du komprimerar mappar med kommandot `tar` hittar du [här](/terminal/introduction/#komprimerade-mappar).

{{% notice style="warning" title="Komprimera rätt!" %}}

Det räcker inte att komprimera filerna som finns i mappen, utan hela mappen måste komprimeras.
Annars tappas git-historiken och git-informationen som används för att kontrollera inlämningsuppgiften.

{{% /notice %}}

Ni laddar upp arkivet under uppgiften **Git** i Studium. Läs mer [här](/submission-and-deadlines) om
hur du sedan laddar upp filen i Studium.
