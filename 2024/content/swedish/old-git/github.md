---
title: Github
pre: <i class="fab fa-github"></i>
weight: 12
draft: true
---

[GitHub](https://github.com) är en av de
största tjänsterna på webben för att samarbeta över Git. Flera kurser på
Uppsala universitet använder GitHub för att koordinera
grupparbeten. Förutom att tillhandahålla remotes för git-repositories så
har GitHub också ett antal egna funktioner. 

## Konto på Github

Att skaffa ett konto på [GitHub](https://github.com) är gratis.

## Privata repositores

På GitHub kan du välja att göra dina repositories privata eller publika. Tänk på
att regler kring fusk och plagiat kan göra det _nödvändigt_ att använda privata
repositories för grupparbeten! Om du är osäker -- fråga din lärare!

## Pull och push

När man arbetar mot GitHub -- precis som vilken annan Git-server som
helst -- så används kommandona `git pull` respektive `git push` för att
hämta hem- respektive skicka upp sina commits till servern. Tänk på att
det bara är committade ändringar som skickas! Att göra en `git pull`
innan man börjar arbeta och en `git push` så fort man är klar är en bra
vana att skaffa sig!

## Vad tillför Github?

Förutom att GitHub låter dig husera din repository hos sig, visa
historik och commits för ett repository, och annat som redan finns i
kommandoradsklienten  erbjuder Github också två funktioner som saknas i
kommandorads-Git: _fork_ och _pull request_. Det finns också stöd för
att hantera kommentarer, buggrapporter, med mera, men vi kommer inte att
gå in på det här.

### Fork

En fork är helt enkelt en fullständig kopia av en annan repository som
hamnar under ditt konto på Github. De används speciellt när man vill fortsätta på
någon annans kod ostört, lite som en branch. Säg t.ex. att jag skulle
vilja lägga till stöd för att spara ner video från SVT Play till
`youtube-dl`, som vi laddade ner [tidigare](../introduction/#hämta-kod-med-git-clone). 
Då skulle jag kunna gå till
`youtube-dl`:s sida på GitHub, klicka på "fork" och få en egen kopia
under mitt egna konto som jag kan arbeta med.

### Pull request

När jag är klar med SVT Play-ändringarna vill jag gärna ha ett sätt att
få tillbaka dem till den officiella versionen av `youtube-dl`, och det
är här pull requests kommer in. En pull request är helt enkelt ett
standardiserat sätt att snällt be någon "vänligen gör en merge
härifrån". Om en merge kan göras utan konflikter finns det dessutom en
funktion i GitHub för att göra den direkt från webben.

## Automatisering med Travis


[Travis](http://travis-ci.org) är en tjänst som erbjuder automatisering
för projekt som använder GitHub. Travis är gratis att använda för
personer med studentkonton på GitHub och för Open Source-projekt (i princip:
alla med publika repositories). Bland annat kan Travis användas för att
automatiskt köra tester mot nya ändringar och pull
requests.
