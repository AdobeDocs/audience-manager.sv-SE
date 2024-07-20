---
description: Konfigurera Open Ad Server som mål och skicka data från Audience Manager till den plattformen.
seo-description: Set up Open Ad Server as a destination and send Audience Manager data to that platform.
seo-title: OAS as an Audience Manager Destination
solution: Audience Manager
title: OAS som mål för Audience Manager
uuid: 5891a063-5a4b-4ea7-865f-b24e17ca735f
feature: Third-party Integration
exl-id: cf919c27-691f-424b-be83-040f03e34455
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# OAS som mål för Audience Manager {#oas-as-an-audience-manager-destination}

Konfigurera [!DNL Open Ad Server] som mål och skicka Audience Manager-data till den plattformen.

## Krav för OAS-destination {#oas-requirements}

Standarder för kodplacering, nyckelvärdesformat som stöds, rapporter och den typ av segmentdata som skickas till [!DNL OAS].

<!-- aam-oas-requirements.xml -->

Måltypen kräver följande:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] kod ska distribueras i ditt lager. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva specialkod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata.
* **`get_aamCookie`Funktion:** Kod som hämtar användar-ID och cookie-data för Audience Manager. Placera [den här koden](../../features/destinations/get-aam-cookie-code.md) överst på sidan eller inuti `<head>`-kodlåset.
* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) kan du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager [!UICONTROL UUID]. Audience Manager kan hämta eller ta emot dessa via [!DNL FTP].

### Cookie-format och nyckelvärdesdata

Audience Manager kan skicka segmentdata till en webbläsarcookie på följande sätt:

* Enkeltangenter (`x=1&x=2`);
* Flera nycklar (`x=1&x=2&y=3&y=4`);
* Serialiserade värden (`x=1,2,3`);
* En standardvärdeavgränsare som används för att separera enskilda nyckelvärdepar.

### Endast kvalificerade segment skickas till OAS

Mängden data som skickas till [!DNL OAS] beror på hur många segment en viss användare kvalificerar sig för. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till OAS (inte alla 100).

>[!MORELIKETHIS]
>
>* [get_aamCookie-kod](../../features/destinations/get-aam-cookie-code.md)
>* [Förklaring av nyckelvärdespar](../../reference/key-value-pairs-explained.md)

## Skapa ett OAS-mål {#oas-dest-setup}

Skapa ett cookie-baserat mål för [!DNL OAS] i Audience Manager.

<!-- aam-oas-destination-setup.xml -->

I Audience Manager är ett *mål* vilket annat system som helst (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som du kan använda för att skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *Målgruppsdata > Destinationer*. Kom igång genom att klicka på **[!UICONTROL Add New Destination]** och följa stegen nedan.

### Steg 1: Grundläggande information

Så här slutför du avsnittet [!UICONTROL Basic Information]:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** i listrutan [!UICONTROL Type].
1. Klicka på **[!UICONTROL Save]** och gå vidare till avsnitten [!UICONTROL Configuration] och [!UICONTROL Segment Mappings].

### Steg 2: Konfigurationsinformation

Så här slutför du avsnittet [!UICONTROL Configuration]:

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Cookie-domän:** Lämna tomt om du vill ange en cookie i domänen för användarens aktuella sida. Om du vill ange en domän ska du lägga till följande punkt i namnet: `.mydomain.com`.
1. Välj ett nyckelalternativ i avsnittet [!UICONTROL Data Format].
1. Om dina nycklar använder data med serialiserade värden väljer du kontrollen **[!UICONTROL Serialize]** och anger den seriella avgränsaren (tecknet som avgränsar de serialiserade värdena).
1. Klicka på **[!UICONTROL Save]** och expandera avsnittet [!UICONTROL Segment Mappings].

### Steg 3: Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. **Hitta segment:** Avsnittet [!UICONTROL Segment Mappings] innehåller två sökverktyg som hjälper dig att hitta segment. Så här söker du efter ett segment:
   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på texten. Klicka på **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka på **[!UICONTROL Browse All Segments]** för att öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka på **[!UICONTROL Add Selected Segments]** när du är klar.
1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på **[!UICONTROL Save]**.
1. Klicka på **[!UICONTROL Done]**.

## OAS-inställningar {#oas-code-setup}

Ändra inställningarna för [!DNL OAS] om du vill arbeta med segmentdata för Audience Manager.

<!-- aam-oas-code.xml -->

För att konfigurera [!DNL OAS]

* Installera [!UICONTROL DIL]-kod på hela platsen.
* Skapa OAS som en cookie-destination i Audience Manager.
* Placera funktionen `get_aamCookie` högst upp på sidan, helst i kodlåset `<head>`. Koden `get_aamCookie` är tillgänglig [här](../../features/destinations/get-aam-cookie-code.md).
* Ändra din annonstagg för att anropa funktionen `get_aamCookie` och inkludera det cookie-namn du angav när du konfigurerade målet för [!DNL OAS]. Om du till exempel namngav cookien `test_cookie` bör annonstaggen anropa `get_aamCookie` och referera till cookie-namnet.
* Din annonstagg kan se ut ungefär som i exemplet nedan.

  ```js
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&u=" + get_aamCookie('aam_uuid')
  ```

Kom ihåg att ta med variabeln `u=`. Den innehåller det faktiska unika användar-ID ([!UICONTROL UUID]) som skickades under ett annonsanrop.
