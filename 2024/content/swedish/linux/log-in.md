---
title: Logga in
weight: 10
---

Här hittar du information om hur du loggar in på Universitetets Linux-system
från någon av datorsalarna för studenter på campus Ångströmlaboratoriet


## Windows i alla salar

I alla datorsalar för studenter på campus Ångströmlaboratiet finns det datorer
med Windows. 

{{< figure 
    width="555px" 
    src="/images/linux/hus-10-pc.jpg" 
    title="Arbetsplats med dator som kör Windows." 
>}}

## Linux med ThinLinc

På campus Ångströmlaboratoriet finns ett antal stora datorer ([servrar][server]) som kör
Linux någonstans i en källare. Som student kommer du inte i fysik kontakt med
dessa servrar. Istället loggar du in mot dessa servrar från Windows och får upp
skrivbordsmiljön för Linux på samma skärm som Windows. Systemet som används
för detta heter [ThinLinc][thinlinc]. 

[server]: https://sv.wikipedia.org/wiki/Server

[thinlinc]: https://en.wikipedia.org/wiki/ThinLinc

- För att komma åt Linux-systemet måste du först logga in i Windows och från
Windows använda ThinLinc Client för att logga in mot en Linux-server.

## Logga in i Windows


För att logga in i Windows anger du användarnamnet för ditt **studentkonto** på
formen `abcd1234` och **Lösenord A**.

![](/images/linux/windows-10-login.jpg?width=444px)

## Software Center (ZENworks)

Någonstans på skrivbordet hittar du **Software center (Zenworks)**.


![](/images/linux/software-center-icon.png)

Dubbelklicka på ikonen för **Software center (Zenworks)**. Nu öppnas ett nytt
fönster med tillgänglig mjukvara. 

![](/images/linux/software-center.png)

Den mjukvara som du hittar här kan redan vara installerad på den dator du
sitter vid. Om ett program inte redan är installerad kommer det att installeras första gången du
försöker använda programmet. 

## Starta ThinLinc client

Från **Software Center** letar du nu reda på **ThinLinc client**.

![](images/linux/software-center-thinlinc-client-icon.png)

Dubbelklicka på **ThinLinc Client**. Om ThinLinc Client redan finns installerat
på dator du arbetar vid kommer det gå fort att starta. Om det inte finns
installerat redan kommer det först installeras och sedan startas. 

## Windows taskbar

När ThinLinc client startat dyker ikonen för ThinLinc client upp nere i
**taskbar** i Windows.

![](/images/linux/windows-taskbar-thinlinc-client.png)

## Logga in med ThinLinc Client

Klicka på ikonen för **Thinlinc Client** nere i **taskbar**. Nu skall du se en
ruta för inloggning mot Linux-systemet. 

- I fältet **Server** skall det stå `thinlinc.student.it.uu.se`.
- I fältet **Username** skriver du användarnamnet för ditt **studentkonto** på
formen `abcd1234`.
- I fältet **Password** skriver du ditt **Lösenord A**.


![](/images/linux/thinlinc-login.png?width=500px)

Klicka på **Connect** för att logga in. Första gången du gör det kan du mötas av
följande meddelande. 

![](/images/linux/trust-this-host.png?width=500px)

Om du ser meddelandet ovan, klicka på **Continue**. 

## Skrivbordet 

Om du lyckas logga in öppnas ett nytt fönster med skrivbordsmiljön för Linux.
Detta fönster kan du maximera eller ändra storlek på, precis som för vilket
annat fönster som helst i Windows. I fönstret i Windows ser du alltså
skrivbordet för Linux som i själva verket körs på en server någon annanstans.

![](/images/linux/linux-desktop.png)


