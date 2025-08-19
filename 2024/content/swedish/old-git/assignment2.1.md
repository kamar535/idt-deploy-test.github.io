---
title: Uppgift 2 - Git reset & Merge-konflikter
weight: 20
pre: <i class="far fa-keyboard"></i>
draft: true
---

## Mål

Efter att du blivit godkänd på denna uppgift kommer du att känna till hur du använder Git och GitHub för att:

- Ångra sig med git reset
- Skapa nya grenar
- Hantera merge-konflikter.

## Detta behöver du

För att lösa uppfiten kommer du att behöva:

- En terminal
- Git
- GitHub konto
- Textredigeringsprogram
- Tar

Uppgiften är testad på och går att utföra på Uppsala universitets Linuxsystem,
men även på egen dator om det som krävs finns installerat.

## Uppgift

Materialet som tas upp i uppgiften diskuteras på [introduktionssidan för Git](../).

### Del 1: Git reset

Ni ska nu jobba **tillsammans** och hjälpas åt men endast en av er kommer behöva lämna in den här uppgiften på Studium. 

Ni skall skapa en textfil och "råka" ta bort den för att sedan återställa repositoryn.

Se till att ha den nyaste versionen av er repository innan ni utför uppgiften. 

Så här gör ni:

**Steg 1** Öppna terminalen och navigera till er mapp `abcd1234_abcd1234-GruppX` (eller `abcd1234_abcd1234_abcd1234-GruppX` om ni är tre). 

**Steg 2** Använd kommandot `ls`. Ser ni filerna *Begrepp* och *Begrepp-Svar*? 

**Steg 3** Väl inne i mappen skapar ni textfilen *DO-NOT-REMOVE* (använd er av kommandot `nano`) och klistra in följande i filen.

```shell
Vad du än gör, ta inte bort den här filen!!!
```

**Steg 4** Kolla med `ls` att den nya textfilen finns i er mapp tillsammans med *Begrepp* och *Begrepp-Svar*

**Steg 5** Kolla Gits status och lägg till den nya filen med `git add`. 

**Steg 6** Kolla Gits status igen och commita med `git commit -m "Ny fil tillagd"` (meddelandet kan underlätta när vi ska leta efter den gamla versionen)

**Steg 7** Nu ska ni publicera detta med `git push`. Skriv användarnamnet och lösenordet för den som utför detta. Gå sedan in på GitHub och kolla att ni fått med filen *DO-NOT-REMOVE*. 

**Steg 8** Gå nu tillbaka till terminalen och ta bort filen *DO-NOT-REMOVE* med kommandot `rm` följt av filen ni vill ta bort. 

**Steg 9** Kolla Gits status. 

**Steg 10** Ni ska nu publicera detta men istället för `git add` vill ni använda `git rm` eftersom ni tagit bort någonting. För att commita skriver ni `git commit -m "tagit bort en fil"` och sedan publicerar ni. När ni publicerat går ni in på er GitHub och kontrollerar att filen *DO-NOT-REMOVE* inte finns med (eftersom ni tagit bort den).  

{{< figure src="/images/git/uppgift2rm.png"
title="Endast dessa filer bör finnas i er repository">}}

**Steg 11** Ni ska nu kolla alla commits (Gits historik). Det gör ni med kommandot `git log`. Ni bör se den nyaste commiten överst och en commit (under den senaste) med en unik nyckel (ex. `1094074c045140e9a91b521b0a933f394a7bba91`) och meddelandet "Ny fil tillagd". Vi vill gå tillbaka till den commiten så vi måste **kopiera** den unika nyckeln till den commiten vi vill gå tillbaka till. Avsluta med `q` när du kopierat nyckeln.

**Steg 12** Skriv `git checkout <unika-nyckeln> .`. Exempelvis `git checkout 1094074c045140e9a91b521b0a933f394a7bba91 .`. Glöm inte att få med '.' (punkten). Punkten betyder nuvarande katalog. Ni bör se något liknande:

```shell
Updated 1 path from d527941
```

**Steg 13** Kolla Gits status och skriv `git commit -m "Tbx till den gamla versionen"`. 

**Steg 14** Nu är det bara att publicera detta på GitHub. Kontrollera att filen *DO-NOT-REMOVE* finns i er repository på GitHub.  

{{< figure src="/images/git/oldversionUppgift2.png"
title="Ni bör se dessa filer i er repository">}}

### Del 2: Merge-konflikter

Ni ska fortsätta jobba **tillsammans**.

Ni ska få skapa en ny branch och hantera merge konflikter. 

Så här gör ni:

**Steg 1** Navigera till er mapp `abcd1234_abcd1234-GruppX` (eller `abcd1234_abcd1234_abcd1234-GruppX` om ni är tre). Där ska ni kolla Gits status. Ni bör se följande:

```shell
On branch main
```
Right?
 
**Steg 2** Öppna textfilen *Begrepp* med kommandot `nano` och klistra in följande:

```shell
Begrepp

1. Algoritm
2. Funktion
3. Bit
```

Spara och commita (`git add` och `git commit -m`) med meddelandet *“ny version av Begrepp”*.

**Steg 3** Skapa en ny branch nu. Det gör ni med kommandot `git checkout -b` följt av en branch namn. Exempelvis `git checkout -b nyBranch`. Ni borde se något liknande:

```shell
Switched to a new branch 'nyBranch'
```

Om ni skriver `git branch` bör ni se vilken branch ni är på.

```shell
  main
* nyBranch
```

**Steg 4** I den nya branchen ska ni lägga till följande på nästa rad efter *"3. bit"* i textfilen *Begrepp*:

```shell
4. Funktion
```

Spara sedan detta och committa med meddelandet *“nytt begrepp ny branch”*. 

**Steg 5** Byt tillbaka till `main` branchen. Det gör ni genom att skriva `git checkout main`.

Ni bör då se följande:

```shell
Switched to branch 'main'
```

**Steg 6** I den här branchen ska ni göra som i *steg 4* men ni ska istället lägga till följande i textfilen *Begrepp*:

```shell
4. Rekursion
```

Spara och committa med meddelandet *“main branch nytt begrepp”*.

**Steg 7** Time to merge! Det gör ni med kommandot `git merge` följt av branchen ni skapat. **Se till att ni är på main branchen**. Exempel: `git merge nyBranch`.

Ni bör se följande:

```Shell
Auto-merging Begrepp
CONFLICT (content): Merge conflict in Begrepp
Automatic merge failed; fix conflicts and then commit the result.
```

**Steg 8** På rad fyra (4) har vi olika begrepp i main branchen och branchen ni skapat vilket gör att vi får en merge konflikt. Ni ska fixa detta. Gå in i textfilen Begrepp med kommandot `nano` för att redigera textfilen.

Ni bör se något liknande:

```shell
Begrepp

1. Algoritm
2. Funktion
3. Bit
<<<<<<< HEAD
4. Rekursion
=======
4. Funktion
>>>>>>> nyBranch
```
Ni ska redigera texten så att det ser ut såhär:

```shell
Begrepp

1. Algoritm
2. Funktion
3. Bit
4. Rekursion
5. Funktion
```

**Steg 9** Ni kan slutligen commita och lägga till meddelandet *"fixat merge konflikt"*. Sedan är det bara att pusha!

## Inlämning

När ni är klara kan den sista i gruppen som publicerat på GitHub komprimera mappen `abcd1234_abcd1234-GruppX` (eller `abcd1234_abcd1234_abcd1234-GruppX` om ni är tre) till en tar.gz-fil och skicka in den i Studium. Tänk på att navigera ut från filen först för att komprimera hela mappen. Det gör ni genom kommandot `cd ..`. 

   + För att komprimera till gzip skriver ni `tar -cvzf abcd1234_abcd1234-GruppX-U2.tar.gz abcd1234_abcd1234-GruppX` (eller `abcd1234_abcd1234_abcd1234-GruppX-U2.tar.gz` om ni är tre). Notera att er filnamn kommer efter. Glöm heller inte `-U2` på slutet. Ni ersätter `abcd1234` med era användarnamn för er studentkonto och `GruppX` med vilken basgrupp ni är i.
   + Mer information om hur du komprimerar mappar med kommandot `tar` hittar du [här](/terminal/introduction/#komprimerade-mappar).

{{% notice style="warning" title="Komprimera rätt!" %}}

Det räcker inte att komprimera filerna som finns i mappen, utan hela mappen måste komprimeras.
Annars tappas git-historiken och git-informationen som används för att kontrollera inlämningsuppgiften.

{{% /notice %}}

Ni laddar upp arkivet under uppgiften **Git** i Studium. Läs mer [här](/submission-and-deadlines) om
hur du sedan laddar upp filen i Studium.
