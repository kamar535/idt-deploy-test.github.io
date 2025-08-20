---
title: Råd och tips
weight: 43
---

Här hittar du några råd, tips och exempel på hur du kan komma att använda Git
och Github i framtiden.

## Lägga till allt som ändrats till staging area

För att lägga till alla filer som ändrats till staging area används kommandot
`git add` tillsammans med flaggan `-A`. 

``` shell
$> git add -A
```

För att se vilka filer som har ändrats och kommer läggas till staging area utan
att lägga till dem kan flaggan `--dry-run` användas.

``` shell
$> git add -A --dry-run
```

## Sådant som bör versionhanteras 

En viktig tumregel är att bara versionshanterat sådant som är direkt skapat av
 en människa. Exempel på sådant som bör versionshanteras: 

- Programkod
- Andra typer av textdokument
- Bilder 

## Sådant som ej bör versionshanteras

Om sådant som inte skapats direkt av en människa versionshanteras är risken stor
för konstiga merge-konflikter. Till exempel om resultatet av kompilerad kod
versionshanteras är kan merge-konflikter uppstå när alla i gruppen har
kompilerat varsitt lite olika program. Exempel på sådant som normalt inte bör
versionhanteras:

- genererad dokumentation.
- PDF:er.
- tillfälliga filer skapade av din editor.
- resultatet av kompilerad kod (körbara programfiler)
- andra typer av filer som skapas automatiskt på något sätt.


## Små projekt

För små projekt med få personer och lite kod brukar det gå bra att bara
utveckla direkt mot `master`-branchen och synkronisera mot samma
repository på t.ex. GitHub. 

## Större projekt

När projekten blir lite större (i antal
personer speciellt) börjar lite mer avancerade metoder krävas.
Ett vanligt arbetssätt i sådana situationer är feature branches. Det
innebär att bara mer eller mindre färdig kod som är testad och fungerar
tillåts på `master`-branchen. All egentlig utveckling sker sedan i
branches, som döps till något relaterat till vad de gör
(exv. `feature/svt-play-support`). 

## Feature branch

En vanlig metod är att använda sig av så kallade feature branches. 
Tanken är att en väl avgränsad del av systemet (en feature) utvecklas och
mognar i en egen feature branch. Denna branch hålls uppdaterad mot
`master`, men inte mot andra parallella feature branches. På så sätt kan flera
grupper inom projektet jobba på olika saker utan att hela tiden kliva varandra
på tårna. I `master-branch` finns det på detta sätt alltid en senast fungerande
version av programmet att jämföra med om något går sönder.

När man är nöjd med arbetet i en feature branch kan den slås ihop (merge) med
master. 

## Pull requests

En funktion som inte finns i Git men som GitHub har lagt till är pull requests.
Med en pull request kan du meddela andra att du pushat ändringar till en branch.
När en pull requests har skapats kan den granskas och diskuteras för att se om
den skall accepteras och slås ihop (merge) med master branch.

När arbetet i en feature branch är klart skickas sedan en pull request
(detta förutsätter förstås att GitHub används) mot `master` från
feature branchen. Ofta brukar GitHub säga till om det går skapa en pull-request
från ex. nyligen uppskickade committs eller liknande.

Någon annan än den/de som utvecklat feature branchen får då ansvaret att gå
igenom alla ändringar. Dessa ändringar går att granska med hjälp av både GitHubs
inbyggda verktyg och `git diff` för att försöka hitta brister i koden. Först när
alla är nöjda och övertygade om att allt fungerar görs slås feature branchen
ihop (merge) med master.
