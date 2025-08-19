---
title: Anaconda och Spyder
weight: 10
---

Ett enkelt sätt att komma igång med Python är att använda [Anaconda][anaconda]
och [Spyder][spyder] vilka redan finns tillgängliga på datorer i [datorsalarna][computer-rooms] på Campus
[Ångströmlaboratiet][ångström]. 

Det är starkt rekommenderat att du [installerar Anaconda][download] som
inkluderar Spyder på din egen dator.

Instruktionerna på dessa sidor kommer visa hur du använder Anaconda och Spyder på en dator
i datorsal på Campus Ångström. Om du installerar och kör Anaconda på din egen
dator bör du kunna följa alla instruktioner utom de som rör hur du startar
Anaconda och Spyder.

[computer-rooms]: computer-rooms/#campus-ångströmlaboratoriet
[ångström]: https://angstrom.uu.se/
[anaconda]: https://www.anaconda.com/
[spyder]: https://www.spyder-ide.org/
[download]: https://www.anaconda.com/download/

## Logga in på en dator i datorsal

[Logga in][login] på en dator i en datorsal på Campus Ångström. 

[login]: computer-rooms/#logga-in-p%C3%A5-dator-i-datorsal-p%C3%A5-campus-%C3%A5ngstr%C3%B6m

## Starta Anaconda Navigator

Skriv in `anaconda` i sökrutan i aktivitetsfältet (1).

![](/images/python/spyder/search-anaconda-navigator.png)

Högst upp bland resultaten skall du nu se  **Anaconda Navigator** (2) och
kan nu starta detta program. 

## Anaconda Navigator

Första gången du startar Anaconda Navigator möts du av följande ruta där du får
valet att skapa ett Anaconda Cloud account. 

![](/images/python/spyder/cloud-login.png)

Om du inte vill skapa ett Anaconda Cloud account stänger du helt enkelt denna
ruta. Efter att du stängt denna får du se en lista med program som finns
tillgängliga i Anaconda Navigator. 

![](/images/python/spyder/navigator.png)

## Starta Spyder

Leta reda på Spyder och tryck på **Launch**. 

![](/images/python/spyder/launch-spyder.png)

Så här ser Spyder ut första gången du startar programmet. 

![](/images/python/spyder/first-look.png)

## Känt problem med Spyder på Mac

Om du installerat Anaconda och Spyder på Mac kan det hända att du får ett felmeddelande om
**Segmentation fault 11** liknande detta när du försöker starta Spyder.

![](/images/python/spyder/segmentation-fault-11.png?width=300px)

I så fall, klicka på kugghjulet upp i högra hörnet. 

![](/images/python/spyder/launch-settings.png?width=300px)

Välj sedan **Install specific version** och byt till Spyder version **5.4.3**.
Förhoppningsvis kan du nu starta Spyder. 

## Python Console och prompten

Nere till höger i Spyder hittar du **Python Console** vilket är ett Python REPL. 

![](/images/python/spyder/python-console.png)

I Python Console används `In [1]:` som prompt. Här kan du skriva in Pythonkod en
rad i taget och resultatet skriv sedan automatiskt ut på en egen rad. 

Skriv in `1+1` vid prompten och tryck enter. Resultatet `2` visas nu på nästa rad med prefixet `Out[1]`. 

En ny prompt `In [2]:` visas nu. Skriv in `3*3 + 5` och tryck enter. Resultatet
`14` visas nu på nästa rad med prefixet `Out[2]`.  

![](/images/python/spyder/console-first-try.png)

Prompten visar en siffra som räknar antal kommandon du utfört. Samma siffra
används även av det efterföljande resultatprefixet. 

## Förenklad prompt 

I alla kommande exempel kommer den förenklade prompten `>>>` användas och
resultatprefixet kommer utelämnas. Följande exempel i Python Console:

``` text
In [1]: 1+1
Out[1]: 2

In [2]: 
```

, kommer i alla kommande exempel att se ut så här: 

``` text
>>> 1+1
2
>>> 
```

Den första raden: 

``` text
>>> 1+1
```

, betyder inte att du skall skriva skriva in `>>> 1+1` i Python Console. Det
betyder att du skall skriva in `1+1` efter prompten i Python Console. 

En rad med endast `>>>`: 

``` text 
>>>
```` 

, betyder att en ny prompt kommer visas här i Python Console. 