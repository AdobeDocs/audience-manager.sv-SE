---
description: Konfigurera Open Ad Server som mål och skicka data från Audience Manager till den plattformen.
seo-description: Konfigurera Open Ad Server som mål och skicka data från Audience Manager till den plattformen.
seo-title: OAS som Audience Manager-destination
solution: Audience Manager
title: OAS som Audience Manager-destination
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 4%

---


# OAS som Audience Manager-destination {#oas-as-an-audience-manager-destination}

Konfigurera [!DNL Open Ad Server] som mål och skicka Audience Manager-data till den plattformen.

## Krav för OAS-destination {#oas-requirements}

Standarder för kodplacering, nyckelvärdesformat som stöds, rapporter och vilken typ av segmentdata som skickas till [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Måltypen kräver följande:

* **[!UICONTROL DIL]:**[!UICONTROL Data Integration Library]koden ska distribueras på ditt lager.[!UICONTROL DIL]hjälper till att eliminera behovet av att skriva särskild kod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata.
* **`get_aamCookie`Funktion:**Kod som hämtar användar-ID och cookie-data för Audience Manager. Placera[den här koden](../../features/destinations/get-aam-cookie-code.md)högst upp på sidan eller inuti`<head>`kodlåset.
* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) ska du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan vara i Raw-format, men varje post måste innehålla Audience Manager [!UICONTROL UUID]. Audience Manager kan hämta eller få dessa via [!DNL FTP].

### Cookie-format och nyckelvärdesdata

Audience Manager kan skicka segmentdata till en webbläsarcookie på följande sätt:

* Enknappar (`x=1&x=2`);
* Flera nycklar (`x=1&x=2&y=3&y=4`);
* Serialiserade värden (`x=1,2,3`).
* En standardvärdeavgränsare som används för att separera enskilda nyckelvärdepar.

### Endast kvalificerade segment skickas till OAS

Hur mycket data som skickas till [!DNL OAS] beror på hur många segment en viss användare kvalificerar sig för. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till OAS (inte alla 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-kod](../../features/destinations/get-aam-cookie-code.md)
>* [Förklaring av nyckelvärdespar](../../reference/key-value-pairs-explained.md)


## Skapa ett OAS-mål {#oas-dest-setup}

Skapa en cookie-baserad destination för [!DNL OAS] i Audience Manager.

<!-- aam-oas-destination-setup.xml -->

In Audience Manager, a *destination* is any other system (ad server, [!DNL DSP], ad network, etc.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *Målgruppsdata > Destinationer*. Kom igång genom att klicka **[!UICONTROL Add New Destination]** och följa stegen nedan.

### Steg 1: Grundläggande information

Så här slutför du [!UICONTROL Basic Information] avsnittet:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** i [!UICONTROL Type] listrutan.
1. Klicka **[!UICONTROL Save]** och gå vidare till avsnitten [!UICONTROL Configuration] och [!UICONTROL Segment Mappings] .

### Steg 2: Konfigurationsinformation

Så här slutför du [!UICONTROL Configuration] avsnittet:

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Cookie-domän:** Lämna tomt om du vill ange en cookie i domänen för användarens aktuella sida. Om du vill ange en domän ska du lägga till följande punkt i namnet `.mydomain.com`.
1. Välj ett nyckelalternativ i [!UICONTROL Data Format] avsnittet.
1. Om dina nycklar använder data med serialiserade värden markerar du **[!UICONTROL Serialize]** kontrollen och anger den seriella avgränsaren (tecknet som avgränsar de serialiserade värdena).
1. Klicka **[!UICONTROL Save]** och expandera [!UICONTROL Segment Mappings] avsnittet.

### Steg 3: Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. **Hitta segment:** Avsnittet innehåller två sökverktyg som hjälper dig att hitta segment [!UICONTROL Segment Mappings] . Så här söker du efter ett segment:
   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på texten. Klicka **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka **[!UICONTROL Browse All Segments]** för att öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka **[!UICONTROL Add Selected Segments]** när du är klar.
1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på **[!UICONTROL Save]**.
1. Klicka på **[!UICONTROL Done]**.

## OAS-inställningar {#oas-code-setup}

Ändra [!DNL OAS] inställningarna så att de fungerar med segmentdata från Audience Manager.

<!-- aam-oas-code.xml -->

Konfigurera [!DNL OAS]

* Installera [!UICONTROL DIL] kod på hela platsen.
* Skapa OAS som en cookie-destination i Audience Manager.
* Placera `get_aamCookie` funktionen överst på sidan, helst i `<head>` kodlåset. Koden är `get_aamCookie` tillgänglig [här](../../features/destinations/get-aam-cookie-code.md).
* Ändra din annonstagg för att anropa `get_aamCookie` funktionen och inkludera det cookie-namn du angav när du konfigurerade [!DNL OAS] målet. Om du till exempel namnger cookien `test_cookie`ska annonstaggen anropa `get_aamCookie` och referera till cookie-namnet.
* Din annonstagg kan se ut ungefär som i exemplet nedan.

   ```js
   <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
    "&etc&u=" + get_aamCookie('aam_uuid')
   ```

Kom ihåg att ta med `u=` variabeln. Den innehåller det faktiska unika användar-ID ([!UICONTROL UUID]) som skickades under ett annonsanrop.
