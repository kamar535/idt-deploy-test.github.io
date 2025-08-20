---
title: SSH
weight: 15
---

{{% notice style="warning" title="Frivillig-sektion" %}}

Denna sektion är tillagd för att hjälpa de som inte vill logga in på universitetets Linux-klienter på campus och är frivillig.

Det är dock väldigt bra att vara bekant med SSH, så läs gärna igenom sidan om du har tid.
{{% /notice %}}

I vissa fall vill kanske du vill komma åt terminalen på en dator eller server du inte sitter vid. Det vanligaste sättet
att göra detta på idag är via ett protokoll som kallas för SSH. Denna sida kommer att förklara grunderna för
hur du ansluter via SSH.

## Introduktion till SSH

Först och främst, vad är SSH? SSH står för *secure shell* och det är 
ett protokoll som tillåter dig att skapa en krypterad anslutning mellan din dator
och en annan dator. Denna anslutning används främst för att ge tillgång till terminalen
på distans, men kan också användas för att exempelvis skicka filer.

För att kunna skapa en SSH-anslutning krävs det att du som användare har en SSH-klient och att servern du försöker
ansluta till har en SSH-server. Många Linux-distributioner har SSH-servrar förinstallerade, vi kommer dock inte fokusera
på SSH-servrar här. Universitets Linux-servrar är förinställda för att användas över SSH så vi behöver inte tänka på det.
Om ni är intresserade av att installera Linux själva så kan ni läsa på om det på egen hand då.

## SSH-klienter

För att ansluta via SSH så behöver man en s.k. SSH-klient. Det finns ett antal av dessa med 
olika funktioner, och med stöd för olika plattformar. Nedan går vi igenom ett par för Windows,
Mac OS och Linux, men det finns varianter för Android och iOS också.

### OpenSSH (Windows 10/11, Mac OS och Linux)

{{< figure 
    src="/images/2024/terminalen/SSH/OpenSSH.png" 
    title="OpenSSH." 
>}}

På Windows 10 (fr. version 1809), Windows 11, Mac OS och Linux så finns en inbyggd SSH-klient som kallas för OpenSSH. Denna 
går att komma åt via *terminalen* på Mac OS och Linux eller *kommandotolken* på Windows 10. 
För att använda OpenSSH så använder du detta kommando:

``` shell
ssh <användarnamn>@<servernamn>
```

Där `<användarnamn>` ersätts med ditt användarnamn på servern och `<servernamn>` 
ersätts med adressen till servern. Exempelvis om du vill ansluta till skolans
server *Arrhenius* så skulle du skriva:

``` shell
ssh abcd1234@arrhenius.it.uu.se
```

I vissa fall kan man behöva specificera vilken port du vill ansluta över. Standardporten 
är 22, men vissa servrar ändrar detta, du behöver då specificera port. För OpenSSH
använder du parametern `-p`. Säg att du ska ansluta till som `oliver` till servern
`emu` över port 212, då skulle du skriva:

``` shell
ssh -p 212 oliver@emu
```

**Notera:** Universitets Linux-servrar använder sig av standardporten 22 så du behöver inte specificera port när du ska ansluta till dem.

### PuTTY

På äldre versioner av Windows så finns inte OpenSSH, du kan då
använda dig av andra klienter. Ett populärt alternativ är [PuTTY](http://www.putty.org/).
När du öppnar PuTTY så får du upp detta fönster:

{{< figure 
    src="/images/2024/terminalen/SSH/PuTTY.png" 
    title="PuTTY." 
>}}

Som Host Name fyller du då i adressen till servern du vill ansluta till, och om du behöver specificera port
fyller du i det också. När du trycker open så kommer du sedan få en fråga om användarnamn och lösenord när
du trycker på anslut.

## Filöverföring

Den krypterade anslutningen via SSH kan som tidigare nämnt även användas för att överföra filer.
Detta kan då göras med hjälp av `scp` (*secure copy*). 

Kommandot `scp` fungerar väldigt likt `cp` men det används för att kopiera filer mellan 
fjärranslutna enheter. Kommandot för att kopiera filen `example.file` från en av universitets 
Linux-servrar till mappen `Documents` ser ut såhär:

``` shell
scp abcd1234@arrhenius.it.uu.se:~/example.file ~/Documents/
```

Och för att gå åt andra hållet, och kopiera filen till universitets Linux-server, så skulle
man skriva såhär:

``` shell
scp example.file abcd1234@arrhenius.it.uu.se:~/Documents/
```

**Notera:** `example.file` antas vara i den aktuella katalogen

### SFTP-klienter

I vissa fall kanske man vill ha ett grafiskt gränssnitt vid kopiering av filer, 
man kan då använda sig av ett program som exempelvis [FileZilla](https://filezilla-project.org/).
Detta låter dig helt enkelt dra-och-släppa för att överföra filer, likt de grafiska filhanteringsprogram du
är van vid.

{{< figure 
    src="/images/2024/terminalen/SSH/FIlezilla.png" 
    title="FileZilla." 
>}}

Oavsett vad du väljer för SFTP-klient så loggar du in på samma sätt som i en SSH-klient,
du fyller helt enkelt i användarnamn, serveradress och port (oftast 22).

**Notera:** om servern använder en annan port än 22 i FileZilla så kan du behöva trycka på
pilen bredvid quickconnect för att välja SFTP och inte FTP.

## Avslutning

Universitet tillhandhåller ett antal Linux-servrar som studenter kan ansluta till, 
en lista med dessa finns [här](http://www.it.uu.se/datordrift/maskinpark/linux).
Du ansluter med ditt studentkonto (abcd1234) och lösenord A.

När du är färdig med det du vill göra via en SSH anslutning så avslutar du anslutningen med
kommandot `exit`.

{{< figure 
    src="/images/2024/terminalen/SSH/SSHexit.png" 
    title="OpenSSH." 
>}}
