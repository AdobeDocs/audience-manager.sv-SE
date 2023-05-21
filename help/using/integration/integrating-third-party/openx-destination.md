---
description: Konfigurera OpenX som mål och skicka segmentdata från Audience Manager till den plattformen.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX som Audience Manager-destination
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 2%

---

# OpenX som Audience Manager-destination{#openx-as-an-audience-manager-destination}

Konfigurera [!DNL OpenX] som mål och skicka segmentdata från Audience Manager till den plattformen.

>[!NOTE]
>
>Endast för annonsering på plats.

## Krav för OpenX-mål {#openx-requirements}

Standarder för kodplacering, nyckelvärdesformat som stöds, rapporter och vilken typ av segmentdata som skickas till [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Granska följande innan du konfigurerar [!DNL OpenX] som mål för Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] koden ska distribueras på din plats. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva särskild kod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata.
* **`get_aamCookie`Funktion:** Kod som hämtar användar-ID och cookie-data för Audience Manager. Montera [den här koden](../../features/destinations/get-aam-cookie-code.md) överst på sidan eller innanför `<head>` kodlås.
* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) ska du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager `UUID`. Audience Manager kan hämta dessa via [!DNL FTP].

### Nyckelvärdedata: Formatkrav

Audience Manager skickar data i form av nyckelvärdepar. Skapa nyckelvärdepar enligt följande specifikationer:

* Förinställningsnycklar med `c.` (t.ex. `c.color` eller `c.price`).
* Separata serialiserade värden kopplade till en enskild nyckel med kommatecken (t.ex. `c.color = red, green, blue`).
* Avgränsa flera nyckelvärdespar med ett et-tecken (t.ex. `c.color=red & c.price = 100 & c.condition = new`).
* Nyckelnamn får inte innehålla specialtecken som accent- och skiljetecken eller andra symboler.

### Endast kvalificerade segment skickas till OpenX

Mängden data som skickas till [!DNL OpenX] beror på hur många segment en viss användare är berättigad till. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till [!DNL OpenX] (inte alla 100).

## Skapa ett OpenX-mål {#openx-destination}

Skapa en cookie-destination för [!DNL OpenX] i Audience Manager.

<!-- aam-openx-destination.xml -->

I Audience Manager *mål* är ett annat system (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *Målgruppsdata > Destinationer*. Kom igång genom att klicka **[!UICONTROL Add New Destination]** och följ stegen nedan.

### Steg 1: Grundläggande information

Slutför [!UICONTROL Basic Information] avsnitt:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** från [!UICONTROL Type] nedrullningsbar lista.
1. Klicka **[!UICONTROL Next]** och gå vidare till [!UICONTROL Configuration] och [!UICONTROL Segment Mappings] -avsnitt.

### Steg 2: Konfigurationsinformation

Slutför [!UICONTROL Configuration] avsnitt:

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Cookie-domän:** Lämna tomt om du vill ange en cookie i domänen för användarens aktuella sida. Om du vill ange en domän ska du lägga till följande punkt som prefix till namnet: `.mydomain.com`.
1. Välj ett nyckelalternativ i [!UICONTROL Data Format] -avsnitt.
1. Om dina nycklar använder data med serialiserade värden väljer du **[!UICONTROL Serialize]** styr och anger den seriella avgränsaren (tecknet som avgränsar de serialiserade värdena).
1. Klicka **[!UICONTROL Save]** och utöka [!UICONTROL Segment Mappings] -avsnitt.

### Steg 3: Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. **Hitta segment:** The [!UICONTROL Segment Mappings] I finns två sökverktyg som hjälper dig att hitta segment. Så här söker du efter ett segment:
   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på texten. Klicka **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka **[!UICONTROL Browse All Segments]** om du vill öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka **[!UICONTROL Add Selected Segments]** när det är klart.
1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på **[!UICONTROL Save]**.
1. Klicka på **[!UICONTROL Done]**.

## Inställningar för OpenX {#openx-code-setup}

Ändra [!DNL OpenX] inställningar för att arbeta med segmentdata från Audience Manager.

<!-- aam-openx-code.xml -->

Konfigurera [!DNL OpenX]:

* Installera [!UICONTROL DIL] koda på hela webbplatsen.
* Skapa [!DNL OpenX] som en kakdestination i Audience Manager.
* Placera `get_aamCookie` längst upp på sidan, helst i `<head>` kodlås. The `get_aamCookie` koden är tillgänglig [här](../../features/destinations/get-aam-cookie-code.md).
* Ändra din annonstagg för att anropa `get_aamCookie` och inkludera det cookie-namn du angav när du konfigurerade [!DNL OpenX] mål. Om du till exempel namngav cookien `test_cookie`, bör annonstaggen anropa `get_aamCookie` och referera till cookie-namnet.
* Din annonstagg kan se ut ungefär som i exemplet nedan.

   ```
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&xid=" + get_aamCookie('aam_uuid')
   ```

Kom ihåg att inkludera `xid=` . Det innehåller det faktiska unika användar-ID:t ([!UICONTROL UUID]) passerade in under ett reklamsamtal.

Det fullständiga annonsanropet kan se ut ungefär så här:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
