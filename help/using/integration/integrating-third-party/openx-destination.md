---
description: Konfigurera OpenX som mål och skicka segmentdata från Audience Manager till den plattformen.
seo-description: Set up OpenX as a destination and send Audience Manager segment data to that platform.
seo-title: OpenX as an Audience Manager Destination
solution: Audience Manager
title: OpenX som Audience Manager-mål
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third-party Integration
exl-id: 938a518b-c8b0-4e86-885f-daf79b2cba38
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '681'
ht-degree: 0%

---

# OpenX som Audience Manager-mål{#openx-as-an-audience-manager-destination}

Konfigurera [!DNL OpenX] som mål och skicka segmentdata från Audience Manager till den plattformen.

>[!NOTE]
>
>Endast för målgruppsanpassning på plats och servrar.

## Krav för OpenX-mål {#openx-requirements}

Standarder för kodplacering, nyckelvärdesformat som stöds, rapporter och den typ av segmentdata som skickas till [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Granska följande innan du konfigurerar [!DNL OpenX] som ett Audience Manager-mål:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] kod ska distribueras på din plats. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva specialkod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata.
* **`get_aamCookie`Funktion:** Kod som samlar in användar-ID och cookie-data för Audience Manager. Placera [den här koden](../../features/destinations/get-aam-cookie-code.md) överst på sidan eller inuti `<head>`-kodlåset.
* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) kan du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager `UUID`. Audience Manager kan hämta dessa via [!DNL FTP].

### Nyckelvärdedata: Formatkrav

Audience Manager skickar data i form av nyckelvärdepar. Skapa nyckelvärdepar enligt följande specifikationer:

* Förgränssnittstangenter med `c.` (t.ex. `c.color` eller `c.price`).
* Separata serialiserade värden kopplade till en enskild nyckel med kommatecken (t.ex. `c.color = red, green, blue`).
* Separera flera nyckelvärdepar med ett et-tecken (t.ex. `c.color=red & c.price = 100 & c.condition = new`).
* Nyckelnamn får inte innehålla specialtecken som accent- och skiljetecken eller andra symboler.

### Endast kvalificerade segment skickas till OpenX

Mängden data som skickas till [!DNL OpenX] beror på hur många segment en viss användare kvalificerar sig för. Exempel: du skapar 100 Audience Manager-segment. Om en webbplatsbesökare kvalificerar sig för fem av dem skickas endast dessa fem segment till [!DNL OpenX] (inte alla 100).

## Skapa ett OpenX-mål {#openx-destination}

Skapa en cookie-destination för [!DNL OpenX] i Audience Manager.

<!-- aam-openx-destination.xml -->

I Audience Manager är ett *mål* vilket annat system (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som du kan använda för att skapa och hantera dessa dataleveransprocesser. Audience Manager målfunktioner finns i *Målgruppsdata > Destinationer*. Kom igång genom att klicka på **[!UICONTROL Add New Destination]** och följa stegen nedan.

### Steg 1: Grundläggande information

Så här slutför du avsnittet [!UICONTROL Basic Information]:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** i listrutan [!UICONTROL Type].
1. Klicka på **[!UICONTROL Next]** och gå vidare till avsnitten [!UICONTROL Configuration] och [!UICONTROL Segment Mappings].

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

## Inställningar för OpenX {#openx-code-setup}

Ändra inställningarna för [!DNL OpenX] om du vill arbeta med Audience Manager segmentdata.

<!-- aam-openx-code.xml -->

Så här konfigurerar du [!DNL OpenX]:

* Installera [!UICONTROL DIL]-kod på hela platsen.
* Skapa [!DNL OpenX] som en cookie-destination i Audience Manager.
* Placera funktionen `get_aamCookie` högst upp på sidan, helst i kodlåset `<head>`. Koden `get_aamCookie` är tillgänglig [här](../../features/destinations/get-aam-cookie-code.md).
* Ändra din annonstagg för att anropa funktionen `get_aamCookie` och inkludera det cookie-namn du angav när du konfigurerade målet för [!DNL OpenX]. Om du till exempel namngav cookien `test_cookie` bör annonstaggen anropa `get_aamCookie` och referera till cookie-namnet.
* Din annonstagg kan se ut ungefär som i exemplet nedan.

  ```
  <a href= "https://client.adserver.net/?" + get_aamCookie('test_cookie') +
   "&etc&xid=" + get_aamCookie('aam_uuid')
  ```

Kom ihåg att ta med `xid=`. Den innehåller det faktiska unika användar-ID ([!UICONTROL UUID]) som skickades under ett annonsanrop.

Det fullständiga annonsanropet kan se ut ungefär så här:

```
https://client.adserver.net/?c.key1=val1&c.key2=val2&etc& xid =3286487458745343
```
