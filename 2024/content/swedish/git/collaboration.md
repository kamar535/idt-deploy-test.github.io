---
title: Samarbete & Branches
weight: 30
---

Tidigare har du fått testa på att använda Git och GitHub för att hålla reda
på historiken på ett projekt du arbetar på helt själv. Vi skall nu kika på hur
Git och GitHub kan användas för att underlätta för flera personer att samarbeta
kring ett och samma projekt. 

## Linjär och förgrenad commit historik

I tidigare exempel har du skapat en linjär historik över förändringar genom att
göra en serie commits där tiden hela tiden går framåt. Med Git går det även att
låta historiken förgrena sig i så kallade branches. På detta sätt är det möjligt
att skapa alternativa tidslinjer (precis som i science fiction). 

![](/images/git/linear-and-branched-commit-history.png)

Det visar sig att förgreningar (branches) kan vara mycket användbara för att
underlätta samarbete med andra kring ett projekt. 

## Den dolda katalogen .git/branches

Kommer du ihåg den [dolda katalogen](../init/#git-har-lagt-till-en-dold-katalog)
`.git` som Git använder sig av? Git använder sig av katalogen
`.git/branches` för att hålla reda på grenar (branches) i ett repo.

## Master branch

Egentligen görs i princip ingen skillnad mellan den
första grenen (som brukar kallas `master`) och andra branches -- det går
t.o.m. att ta bort `master` om man skulle vilja.
kodprojekt senare. 

## Ta reda på vilken branch du befinner dig

Vi kan visa vilken branch vi för tillfället är på med hjälp av kommandot  `git
branch`:

``` shell
$> git branch
```

Om du inte tagit bort eller ändrat namn på den ursprungliga branchen kommer
resultatet att se ut så här: 

``` shell
* master
```

De kan hända att ditt system är uppsatt på ett sätt som gör att du istället ser
något liknande detta:

``` shell
* master
(END)
```

I detta fall måste du trycka på `q` för att komma tillbaka till prompten i terminalen efter
det att Git visas namnet på den branch du befinner dig på. 

I båda exemplen ovan visar Git att du att du befinner dig på branchen med namn
`master`, dvs den branch som repot alltid startar med.

{{% notice style="warning" title="Du måste har gjort minst en commit" %}}

Om du inte gjort något commit i ditt repo ännu kommer `git branch` inte att ge något
resultat. Du måste göra minst en commit i ditt repo för att den första branchen
`master` automtiskt skall skapas. 

{{% /notice %}}


## Skapa en ny branch

För att skapa en ny branch används kommandot `git checkout -b`. För att till
exempel skapa en ny branch med namnet `experiments` gör du så här. 

``` shell
$> git checkout -b experiments
```

Git svarar då med följande. 

``` shell
Switched to a new branch 'experiments'
```

För säkerhets skull kollar vi vilken branch vi nu befinner oss i. 

``` shell
$> git branch
```

Denna gång svarar Git så här. 

``` shell
* experiments
  master
```

Git listar alltså alla branches och markerar den branch du för tillfälle
befinner dig på med  `*`.

## Hoppa mellan branches 

För att hoppa mellan befintliga branches används kommandot `git checkout`,
denna gång utan flaggan `-b` som endast används när vi skapar en ny branch. För
att hoppa tillbaka till branchen `master` gör du så här. 

``` shell
$> git checkout master
```

Git visar att du hoppat till branchen `master` med följande meddelande. 

``` shell
Switched to branch 'master'
```

## Remotes

Det som gör Git användbart vid samarbete med andra är framför allt möjligheten
att synkronisera repositories med sina branches via servrar, s.k. _remotes_. Ett
vanligt fall som vi redan kikat på är att sätta upp ett remote repo på GitHub.

En remote sparar den senaste gemensamma versionen av
projektets historia så att alla kan hämta hem andras ändringar -- men
också skicka upp sina egna. Ett inbyggt låssystem ser till att det är
omöjligt att skicka upp sina ändringar utan att först ha hämtat de
senaste gemensamma ändringarna från remoten. På så sätt kan man
säkerställa att alla i projektet är överens om hur den gemensamma koden
ser ut, även om man arbetar oberoende av varandra.

## Merge

Det går att slå ihop branches till en gemensam tidslinje igen, vilket kallas för
en _merge_ (lämpligt nog). Det betyder att Git gör sitt bästa för att passa ihop
ändringarna som gjorts sedan den gemensamma brytpunkten för två branches. I
praktiken görs också en merge när kod hämtas från en remote med `git pull`.

![](/images/git/branch-and-merge.png?width=333px)

Om någon gjort en ändring i en branch som du inte har sett och du gör merge med
kommer Git att göra sitt bästa för att pussla de två grenarna och varna om det
inte går.

## Merge conflict

Git gör sitt bästa för att automatiskt pussla ihop olika förändringar vid en
merge. Ibland kan dock inte Git göra detta automatiskt och då uppstår det som
kallas före en merge conflict.

Vid en merge conflict kommer Git att ge en varning. Det är nu upp till den
mänskliga användaren att på egen hand avgöra hur konflikten skall lösas. När
konflikten löst gör du sedan en ny commit precis som vanligt. 
