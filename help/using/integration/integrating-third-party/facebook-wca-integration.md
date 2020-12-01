---
description: Den här sidan illustrerar processen att skapa WCA-pixlar (Custom Audiences) för Facebook för att skicka webbaserade målgruppssegment för Audience Manager till Facebook, för webbannonsering med förbättrad transparens.
seo-description: Den här sidan illustrerar processen att skapa WCA-pixlar (Custom Audiences) för Facebook för att skicka webbaserade målgruppssegment för Audience Manager till Facebook, för webbannonsering med förbättrad transparens.
seo-title: Integrering med Facebook WCA
solution: Audience Manager
title: Integrering med Facebook WCA
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 5%

---


# [!DNL Facebook WCA] Integrering  {#facebook-wca-integration}

Den här sidan visar processen att skapa [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixlar för att skicka webbaserade [!DNL Audience Manager] målgruppssegment till [!DNL Facebook], för onlineannonsering med förbättrad genomskinlighet.

## Översikt {#overview}

[Med WCA (Custom Audiences) på Facebook-webbplatsen ](https://www.facebook.com/business/help/449542958510885) kan du skapa en lista över personer som har besökt vissa sidor eller vidtagit särskilda åtgärder på din webbplats. [!DNL Audience Manager] aktiverar aktivering i  [!DNL WCA] med hjälp av  [!DNL URL] mål, med vilka du kan konfigurera en anpassad pixelbaserad integration för att skicka webbaserade målgrupper  [!DNL Facebook] till för målgruppsanpassning.

![Integrering med Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Den här funktionen kräver att du väljer alternativet [!UICONTROL Website] målgrupp för sociala plattformar i [URL-mål](/help/using/features/destinations/create-url-destination.md). Sociala plattformar kräver att referensinformation avmaskeras när den skickas till deras plattform. Observera att detta innebär att målplattformen/målpartnern kan se information i din referent [!DNL URL].

## Förutsättningar {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segment, redo att tilldelas till din nya  [!DNL Facebook] destination. Här är [hur du skapar ett segment](/help/using/features/segments/segment-builder.md) i gränssnittet för [!DNL Audience Manager].
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 eller senare. Ladda ned den senaste versionen **[här](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 eller senare, kan hämtas  **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Om du använder [SSF (Server-Side Forwarding)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) för att importera data till [!DNL Audience Manager] måste du använda AppMeasurement version 2.12 eller senare. Hämta [!DNL AppMeasurement] med [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Vi rekommenderar att du installerar eller uppgraderar biblioteken i steg 3 och 4 med [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) eller [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/sv-SE/dtm/using/dtm-home.html).

## Steg 1 - Skapa en [!UICONTROL Facebook Destination] i [!DNL Audience Manager] {#step-1-create-facebook-destination}

Skapa en ny [!UICONTROL URL Destination] i [!DNL Audience Manager] och ge den namnet [!DNL Facebook Website Custom Audiences]. Använd inställningarna nedan när du skapar målet. Du kan även gå till sidan [Konfigurera en URL-adress](/help/using/features/destinations/create-url-destination.md).

### Grundläggande information

* **[!UICONTROL Category]**: Egen
* **[!UICONTROL Type]**:  [!DNL URL]
* Markera kryssrutan **[!UICONTROL Auto-fill Destination Mapping]** och välj sedan **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Välj alternativet **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Den här exportetiketten förhindrar att data från tredje part och data som härletts från enhetsdiagram inkluderas i segmenten.

### Konfiguration

* **[!UICONTROL URL type]**: Välj  **[!UICONTROL Website audience for social platforms]**. Om du väljer det här [!UICONTROL URL Type]-alternativet skymmer inte [!DNL Audience Manager] referentinformationen när du trycker på en [!DNL URL]-pixel.[!DNL Facebook WCA]
* **[!UICONTROL Serialize]**: Välj  **[!UICONTROL Enable]**.
* I fälten **[!UICONTROL Base URL]** och **[!UICONTROL Secure URL]** anger du pixeln [!DNL Facebook WCA].
* **[!UICONTROL Delimiter]**:  `,`

Exempel på bas [!DNL URL]: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exempelpixel utlöses från sidan. I det här exemplet visas en användare som kvalificerar sig för tre [!DNL Audience Manager]-segment med ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beskrivning |
---------|----------|
| `id` | Ditt [!DNL Facebook]-pixel-ID som du hittar i [!DNL Facebook Ad Manager]-användargränssnittet när du skapar målgruppspixlar. |
| `ev` | Event.     Det här är ett godtyckligt värde som visas i [!DNL Facebook Ad Manager]-användargränssnittet när pixeln börjar utlösas på webbplatsen. Mer information finns i [!UICONTROL Include]-objektet i [Steg 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | En extra parameter, som börjar fylla i i användargränssnittet för [!DNL Facebook Ad Manager] när pixeln börjar brinna på webbplatsen. `segID` är också godtyckligt. |
| `%ALIAS%` | Ett [!DNL Audience Manager]-makro, som ersätts dynamiskt med de [!DNL Audience Manager] [!UICONTROL segment]-ID:n som besökaren kvalificerar sig för, avgränsade med kommatecken , |

Din [!UICONTROL URL destination]-konfiguration ska se ut som i bilden nedan:

![Målkonfiguration](/help/using/integration/assets/facebook-wca.png)

Spara [!UICONTROL destination]. Sedan kan du fortsätta till steget **Segmentmappningar**.

## Steg 2 - Segmentmappningar - Mappa segment till mål {#step-2-segment-mappings}

I arbetsflödet [Konfigurera URL-mål](/help/using/features/destinations/create-url-destination.md) mappar du det aktuella segmentet till din nyskapade [!UICONTROL destination]. Observera att mappningsvärdet fylls i automatiskt med [!DNL Audience Manager] [!UICONTROL segment ID].

Ange ett slutdatum om tillämpligt, annars lämnas tomt för inget slutdatum.

## Steg 3 - Skapa en [!UICONTROL Audience] inom [!DNL Facebook Ads Manager] {#step-3-create-audience}

Se [Skapa en anpassad målgrupp för en webbplats](https://www.facebook.com/business/help/666509013483225) i hjälpdokumentationen för [!DNL Facebook]. Välj [!UICONTROL Create Audience]-alternativen i tabellen nedan:

| Objekt | Beskrivning |
---------|----------|
| Webbplatstrafik | Anpassad kombination |
| Inkludera | <ul><li>Välj **[!UICONTROL Event]** > Välj **[!UICONTROL Adobe-Audience-Manager-Segment]**. Detta var värdet på parametern `ev` i exempelpixeln i steg 1. Observera, att om pixeln ännu inte har startats kanske inte **[!UICONTROL Event]**-alternativet eller **[!UICONTROL Adobe-Audience-Manager-Segment]** visas i [!DNL Facebook]-användargränssnittet.</li><li>Lägg till en parameter: Välj `segID`.</li><li><p>Markera **innehåller**-operatorn.</p><p>Detta är viktigt eftersom besökare kan kvalificera sig för flera segment, kan det finnas flera [!UICONTROL segment IDs] i pixelparametern. Om du använder operatorn lika med (`=`) kanske inte dina besökare kvalificerar sig för målgruppen, och du kommer att märka en lägre volym.</p></li><li>Lägg till ett värde: Ange segment-ID:t för [!DNL Audience Manager].</li></ul> |
| Lägg till nytt villkor | Valfri inställning. |
| I slutet av | Valfri inställning. |
| Målgruppsnamn | Vi rekommenderar att du använder samma [!DNL Audience Manager]-segmentnamn för att skapa en konsekvent upplevelse, såvida du inte lägger till ytterligare villkor till den här målgruppen. |

## Steg 4 - Tilldela [!UICONTROL Audience] till en [!UICONTROL Campaign] i [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

När du har skapat [!DNL Custom Audience] tilldelar du den till en annonskampanj. Skapa en ny kampanj eller redigera en befintlig så ser du att den nya målgruppen visas i [!DNL Facebook]-användargränssnittet. Din annonskampanj riktar sig till användare som har sett pixelbranden i sin webbläsare när de besöker din webbplats, om [!DNL Audience Manager] inkluderar dem i segmentet.

## Sammanfattning {#summary}

Nu när du har tilldelat ditt [!DNL Audience Manager]-segment till [!DNL Facebook WCA]-målet, kommer [!DNL Audience Manager] selektivt att utlösa pixeln [!DNL Facebook WCA] för användare av ett givet segment med respektive segment-ID i pixeln för att fylla i [!DNL Facebook Audience]. Detta resulterar i en gradvis ökning av [!DNL Facebook Audience] ju mer taggen skickas till rätt målgrupp på din webbplats.

>[!NOTE]
>
> Om en användare faller utanför [!DNL Audience Manager]-segmentet finns det för närvarande inget sätt för [!DNL Audience Manager] att informera [!DNL Facebook] om att ta bort användaren från [!DNL Custom Audience].

