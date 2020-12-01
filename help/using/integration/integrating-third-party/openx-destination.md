---
description: Konfigurera OpenX som mål och skicka segmentdata från Audience Manager till den plattformen.
seo-description: Konfigurera OpenX som mål och skicka segmentdata från Audience Manager till den plattformen.
seo-title: OpenX som Audience Manager-destination
solution: Audience Manager
title: OpenX som Audience Manager-destination
uuid: 5e86ba73-281c-403b-af06-64a1d427526a
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%

---


# OpenX som Audience Manager-destination{#openx-as-an-audience-manager-destination}

Ange [!DNL OpenX] som mål och skicka Audience Manager segmentdata till den plattformen.

>[!NOTE]
>
>Endast för annonsering på plats.

## Krav för OpenX-mål {#openx-requirements}

Standarder för kodplacering, nyckelvärdesformat som stöds, rapporter och typen av segmentdata som skickas till [!DNL OpenX].

<!-- aam-openx-requirements.xml -->

Granska följande innan du konfigurerar [!DNL OpenX] som mål för Audience Manager:

* **[!UICONTROL DIL]:** [!UICONTROL Data Integration Library] kod ska distribueras på din plats. [!UICONTROL DIL] hjälper till att eliminera behovet av att skriva särskild kod för datainsamling, integrering, läsning av cookie-värden och återställning av siddata.
* **`get_aamCookie`Funktion:** Kod som samlar in användar-ID och cookie-data för Audience Manager. Placera [den här koden](../../features/destinations/get-aam-cookie-code.md) högst upp på sidan eller inuti `<head>`-kodblocket.
* **Skicka leveransloggar till Audience Manager:** Om du vill ha en segmentleveransrapport (valfritt) kan du förse Audience Manager med en daglig logg som innehåller leveransdata på visningsnivå. Data kan ha Raw-format, men varje post måste innehålla Audience Manager `UUID`. Audience Manager kan hämta eller ta emot dessa via [!DNL FTP].

### Nyckelvärdedata: Formatkrav

Audience Manager skickar data i form av nyckelvärdepar. Skapa nyckelvärdepar enligt följande specifikationer:

* Förinställningsnycklar med `c.` (t.ex. `c.color` eller `c.price`).
* Separata serialiserade värden kopplade till en enskild nyckel med kommatecken (t.ex. `c.color = red, green, blue`).
* Separera flera nyckelvärdepar med ett et-tecken (t.ex. `c.color=red & c.price = 100 & c.condition = new`).
* Nyckelnamn får inte innehålla specialtecken som accent- och skiljetecken eller andra symboler.

### Endast kvalificerade segment skickas till OpenX

Hur mycket data som skickas till [!DNL OpenX] beror på hur många segment en viss användare kvalificerar sig för. Exempel: du skapar 100 Audience Manager-segment. Om en besökare kvalificerar sig för fem av dem skickas endast dessa fem segment till [!DNL OpenX] (inte alla 100).

## Skapa ett OpenX-mål {#openx-destination}

Skapa en cookie-destination för [!DNL OpenX] i Audience Manager.

<!-- aam-openx-destination.xml -->

I Audience Manager är ett *mål* vilket annat system som helst (annonsserver, [!DNL DSP], annonsnätverk osv.) som du vill dela data med. [!UICONTROL Destination Builder] innehåller de verktyg som gör att du kan skapa och hantera dessa dataleveransprocesser. Målfunktionerna för Audience Manager finns i *Måldata > Destinationer*. Kom igång genom att klicka på **[!UICONTROL Add New Destination]** och följa stegen nedan.

### Steg 1: Grundläggande information

Så här slutför du avsnittet [!UICONTROL Basic Information]:

1. Namnge målet.
1. Välj **[!UICONTROL "Cookie"]** i listrutan [!UICONTROL Type].
1. Klicka på **[!UICONTROL Next]** och gå vidare till avsnitten [!UICONTROL Configuration] och [!UICONTROL Segment Mappings].

### Steg 2: Konfigurationsinformation

Så här slutför du avsnittet [!UICONTROL Configuration]:

1. **Cookie-namn:** Ange ett kort beskrivande namn för din cookie.
1. **Cookie-domän:** Lämna tomt om du vill ange en cookie i domänen för användarens aktuella sida. Om du vill ange en domän anger du följande punkt som prefix för namnet: `.mydomain.com`.
1. Välj ett nyckelalternativ i avsnittet [!UICONTROL Data Format].
1. Om dina nycklar använder data med serialiserade värden väljer du kontrollen **[!UICONTROL Serialize]** och anger den seriella avgränsaren (tecknet som avgränsar de serialiserade värdena).
1. Klicka på **[!UICONTROL Save]** och expandera avsnittet [!UICONTROL Segment Mappings].

### Steg 3: Segmentmappningar

Så här lägger du till ett segment i en cookie-destination:

1. **Hitta segment:** I  [!UICONTROL Segment Mappings] avsnittet finns två sökverktyg som hjälper dig att hitta segment. Så här söker du efter ett segment:
   * Alternativ 1: Börja skriva ett segmentnamn i sökfältet. Fältet uppdateras automatiskt baserat på texten. Klicka på **[!UICONTROL Add]** när du har hittat det segment du vill använda.
   * Alternativ 2: Klicka på **[!UICONTROL Browse All Segments]** för att öppna ett fönster där du kan bläddra efter segment efter namn eller lagringsplats. Klicka på **[!UICONTROL Add Selected Segments]** när du är klar.
1. **Lägg till mappningar:** Ange segment-ID i mappningsfältet i mappningsfönstret och klicka på  **[!UICONTROL Save]**.
1. Klicka på **[!UICONTROL Done]**.

## Inställningar för OpenX {#openx-code-setup}

Ändra [!DNL OpenX]-inställningarna om du vill arbeta med segmentdata från Audience Manager.

<!-- aam-openx-code.xml -->

Så här konfigurerar du [!DNL OpenX]:

* Installera [!UICONTROL DIL]-kod på hela platsen.
* Skapa [!DNL OpenX] som cookie-mål i Audience Manager.
* Placera funktionen `get_aamCookie` högst upp på sidan, helst i kodlåset `<head>`. Koden `get_aamCookie` är tillgänglig [här](../../features/destinations/get-aam-cookie-code.md).
* Ändra din annonstagg för att anropa funktionen `get_aamCookie` och inkludera det cookie-namn du angav när du konfigurerade [!DNL OpenX]-målet. Om du till exempel namngav cookien `test_cookie` bör annonstaggen anropa `get_aamCookie` och referera till cookie-namnet.
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
