---
title: Arbeta tillsammans
pre: <i class="fas fa-users"></i>
weight: 14
draft: true
---

Här hittar du några råd och exempel på hur du kan komma att använda Git och Github i framtiden. 

## Sådant som bör versionhanteras 

En viktig tumregel är att bara versionshanterat sådant som är direkt skapat av
 en människa. Exempel på sådant som bör versionshanteras: 

- Programkod
- Andra typer av textdokument
- Bilder 

## Sådant som ej bör versionshanteras

Om sådant som inte skapats direkt av en människa versionshanteras är risken stor
för konstiga merge-konflikter. Till exempel om resultatet av kompilerad kod versionshanteras
är kan merge-konflikter uppstå när alla i gruppen har
kompilerat varsitt lite olika program.

Exempel på sådant som normalt inte bör versionhanteras:

- genererad dokumentation.
- PDF:er.
- tillfälliga filer skapade av din
editor.
- resultatet av kompilerad kod (körbara programfiler).


## Små projekt

För små projekt med få personer och lite kod brukar det gå bra att bara
utveckla direkt mot `master`-branchen och synkronisera mot samma
repository på t.ex. GitHub. 

## Större projekt

När projekten blir lite större (i antal
personer speciellt) börjar lite mer avancerade metoder krävas.
Ett vanligt arbetssätt i sådana situationer är feature-branches. Det
innebär att bara mer eller mindre färdig kod som är testad och fungerar
tillåts på `master`-branchen. All egentlig utveckling sker sedan i
branches, som döps till något relaterat till vad de gör
(exv. `feature/svt-play-support`). 

## Feature-branch

Tanken är att en enskild funktion i
programmet man tillverkar utvecklas och mognar i en egen feature-branch, och att
denna branch hålls uppdaterad mot `master`, men inte andra parallellt
utvecklade funktioner. På så sätt kan flera grupper inom projektet jobba
på olika saker utan att hela tiden kliva varandra på tårna. I `master-branch` finns det på detta sätt 
alltid en senast fungerande version av programmet att jämföra med
om något går sönder.

## Pull requests

När en funktion i en feature-branch är klar skickas sedan en pull request
(detta förutsätter förstås att GitHub används) mot `master` från
feature-branchen. Ofta brukar GitHub säga till om det går skapa en pull-request
från ex. nyligen uppskickade committs eller liknande.

{{< figure src="/images/git/git-compare-and-pull-request.png"
            title="GitHub är hjälpsam nog att föreslå att jag skickar en pull request från branchen jag precis push:ade till." >}}
            
Någon annan än den/de som utvecklat funktionen får då ansvaret
att gå igenom alla ändringar (som dessutom går att se med hjälp av både
GitHubs verktyg och `git diff` som vi tittade på tidigare) och försöka
hitta brister i koden. Först när alla är nöjda och övertygade om att
allt fungerar mergas branchen in i master. En ny branch skapas för nästa
funktion -- och processen börjar om.

{{< figure src="/images/git/git-create-new-pull-request.png"
title="Dialogruta på GitHub för att göra en Pull Request för att merga in den här guiden i resten av materialet." >}}

