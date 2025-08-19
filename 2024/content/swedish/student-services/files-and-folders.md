---
title: Filer och mappar
weight: 3
---

På en dator lagras information på hårddisken som filer. En mapp (katalog)
används för att samla filer som på något sätt hör ihop.  Förutom filer kan en
mapp i sin tur innehålla andra mappar. 

## Trädstruktur

Filer och mappar bildar en trädstruktur. Trädet börjar i **roten** och varje
mapp bildar en egen gren i trädet. Trädet avbildas vanligen uppochner med roten
överst som i detta exempel med **roten** (1) överst. 

![](/images/studenttjanster/windows/file-tree-example.png?width=300px)

I katalogen **roten** (1) ligger filerna **bosse** (2) och **apa** (3) samt mapparna
**kompisar** (4) och **djur** (7). 

I mappen **kompisar** (4) ligger filerna **nisse** (5) och **bosse** (6).

I mappen **djur** (7) ligger filerna **katt** (8) och **apa** (9).

Utan trädstrukturen skulle alla filer behöva ha ett unikt namn. Med hjälp av
trädstrukturen kan vi använda samma namn på olika filer så länge de ligger i
olika mappar. Filen **bosse** (2) som ligger i mappen **roten** (1) har samma
namn som filen **bosse** (6) som ligger i mappen **kompisar** (4). Filerna har
samma namn men är separata filer. På samma sätt har filen **apa** (3) som ligger
i mappen **roten** (1) samma namn som filen **apa** (9) som ligger i mappen
**djur** (7). 

## Sökväg

I trädet har varje mapp och varje fil en unik **sökväg**. Sökvägen utgår från
roten och efter varje mapp (gren) lägger man till symbolen `\`. Mappen **djur**
(7) har följande sökväg. 

``` text
roten\djur
```

Filen **nisse** (5) har följande sökväg.

``` text
roten\kompisar\nisse
```

Filer **bosse** (2) har samma namn som filen **bosse** (6), men de har unika
sökvägar. Filen **bosse** (2) har följande sökväg. 

``` text
roten\bosse
```

Filen **bosse** (6) har följande sökväg. 

``` text
roten\kompisar\bosse
```