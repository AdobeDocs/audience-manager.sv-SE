---
description: Konfigurera Open Ad Server som mål och skicka data från Audience Manager till den plattformen.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS som Audience Manager-destination
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 4%

---

# OAS som Audience Manager-destination {#oas-as-an-audience-manager-destination}

Konfigurera [!DNL Open Ad Server] som mål och skicka data från Audience Manager till den plattformen.

## Krav för OAS-destination {#oas-requirements}

Standarder för kodplacering, nyckelvärdesformat som stöds, rapporter och vilken typ av segmentdata som skickas till [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Måltypen kräver följande:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] koden ska distribueras på ditt lager. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva särskild kod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata.
* **`get_aamCookie`Funktion:** Kod som hämtar användar-ID och cookie-data för Audience Manager. Montera [den här koden](../../features/destinations/get-aam-cookie-code.md) överst på sidan eller innanför `<head>` kodlås.
* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) ska du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager [!UICONTROL UUID]. Audience Manager kan hämta dessa via [!DNL FTP].

### Cookie-format och nyckelvärdesdata

Audience Manager kan skicka segmentdata till en webbläsarcookie på följande sätt:

* Enstaka tangenter (`x=1&x=2`).
* Flera tangenter (`x=1&x=2&y=3&y=4`).
* Serialiserade värden (`x=1,2,3`).
* En standardvärdeavgränsare som används för att separera enskilda nyckelvärdepar.

### Endast kvalificerade segment skickas till OAS

Mängden data som skickas till [!DNL OAS] beror på hur många segment en viss användare är berättigad till. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till OAS (inte alla 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-kod](../../features/destinations/get-aam-cookie-code.md)
>* [Förklaring av nyckelvärdespar](../../reference/key-value-pairs-explained.md)


## Skapa ett OAS-mål {#oas-dest-setup}

Skapa en cookie-baserad destination för [!DNL OAS] i Audience Manager.

<!-- aam-oas-destination-setup.xml -->

I Audience Manager *mål* är ett annat system (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *Målgruppsdata > Destinationer*. Kom igång genom att klicka **[!UICONTROL Add New Destination]** och följ stegen nedan.

### Steg 1: Grundläggande information

Slutför [!UICONTROL Basic Information] avsnitt:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** från [!UICONTROL Type] nedrullningsbar lista.
1. Klicka **[!UICONTROL Save]** och gå vidare till [!UICONTROL Configuration] och [!UICONTROL Segment Mappings] -avsnitt.

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

## OAS-inställningar {#oas-code-setup}

Ändra [!DNL OAS] inställningar för att arbeta med segmentdata från Audience Manager.

<!-- aam-oas-code.xml -->

Konfigurera [!DNL OAS]

* Installera [!UICONTROL DIL] koda på hela webbplatsen.
* Skapa OAS som en cookie-destination i Audience Manager.
* Placera `get_aamCookie` längst upp på sidan, helst i `<head>` kodlås. The `get_aamCookie` koden är tillgänglig [här](../../features/destinations/get-aam-cookie-code.md).
* Ändra din annonstagg för att anropa `get_aamCookie` och inkludera det cookie-namn du angav när du konfigurerade [!DNL OAS] mål. Om du till exempel namngav cookien `test_cookie`, bör annonstaggen anropa `get_aamCookie` och referera till cookie-namnet.
* Din annonstagg kan se ut ungefär som i exemplet nedan.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Kom ihåg att inkludera `u=` variabel. Det innehåller det faktiska unika användar-ID:t ([!UICONTROL UUID]) passerade in under ett reklamsamtal.
