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


# [!DNL Facebook WCA] Integrering {#facebook-wca-integration}

Den här sidan visar processen att skapa [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixlar för att skicka webbaserade [!DNL Audience Manager] målgruppssegment till [!DNL Facebook], för webbannonsering med förbättrad transparens.

## Översikt {#overview}

[Med anpassade målgrupper på Facebooks webbplats (WCA)](https://www.facebook.com/business/help/449542958510885) kan du skapa en lista över personer som har besökt vissa sidor eller vidtagit särskilda åtgärder på din webbplats. [!DNL Audience Manager] aktiverar aktivering i [!DNL WCA] med hjälp av [!DNL URL] målgrupper, med vilka du kan konfigurera en anpassad pixelbaserad integration för att skicka webbaserade målgrupper till [!DNL Facebook] för målgruppsanpassning.

![Integrering med Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Den här funktionen kräver att du väljer målgrupp [!UICONTROL Website] för sociala plattformar i [URL-mål](/help/using/features/destinations/create-url-destination.md). Sociala plattformar kräver att referensinformation avmaskeras när den skickas till deras plattform. Observera att detta innebär att målplattformen/målpartnern kan se information i din referent [!DNL URL].

## Förutsättningar {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segment, klara att tilldelas till din nya [!DNL Facebook] destination. Så här [skapar du ett segment](/help/using/features/segments/segment-builder.md) i [!DNL Audience Manager] användargränssnittet.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 eller senare. Ladda ned den senaste versionen **[här](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 eller senare, kan hämtas **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Om du använder[SSF (Server-Side Forwarding)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)för att importera data till[!DNL Audience Manager]måste du använda AppMeasurement version 2.12 eller senare. Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/sv-SE/analytics/admin/admin-tools/code-manager-admin.html).

Vi rekommenderar att du installerar eller uppgraderar biblioteken i steg 3 och 4 med [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) eller [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/sv-SE/dtm/using/dtm-home.html).

## Steg 1 - Skapa en [!UICONTROL Facebook Destination] i [!DNL Audience Manager] {#step-1-create-facebook-destination}

Skapa ett nytt [!UICONTROL URL Destination] i [!DNL Audience Manager] och ge det ett namn [!DNL Facebook Website Custom Audiences]. Använd inställningarna nedan när du skapar målet. Du kan även gå till sidan [Konfigurera ett URL-mål](/help/using/features/destinations/create-url-destination.md) .

### Grundläggande information

* **[!UICONTROL Category]**: Egen
* **[!UICONTROL Type]**: [!DNL URL]
* Markera **[!UICONTROL Auto-fill Destination Mapping]** kryssrutan och markera sedan **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Välj alternativet **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Den här exportetiketten förhindrar att data från tredje part och data som härletts från enhetsdiagram inkluderas i segmenten.

### Konfiguration

* **[!UICONTROL URL type]**: Välj **[!UICONTROL Website audience for social platforms]**. Om du väljer det här [!UICONTROL URL Type] alternativet skymmer [!DNL Audience Manager] inte [!DNL URL] referensinformationen när en [!DNL Facebook WCA] pixel utlöses.
* **[!UICONTROL Serialize]**: Välj **[!UICONTROL Enable]**.
* Ange **[!UICONTROL Base URL]** pixeln i fältet **[!UICONTROL Secure URL]** och [!DNL Facebook WCA] .
* **[!UICONTROL Delimiter]**: `,`

Exempel [!DNL URL] på bas: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exempelpixel utlöses från sidan. I det här exemplet visas en användare som kvalificerar sig för tre [!DNL Audience Manager] segment med ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beskrivning |
---------|----------|
| `id` | Ditt [!DNL Facebook] pixel-ID som du hittar i [!DNL Facebook Ad Manager] användargränssnittet när du skapar målgruppspixlar. |
| `ev` | Event.     Det här är ett godtyckligt värde som visas i [!DNL Facebook Ad Manager] användargränssnittet när pixeln börjar utlösas på webbplatsen. Mer information finns under [!UICONTROL Include] posten i [steg 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ytterligare en parameter, som börjar fylla i i [!DNL Facebook Ad Manager] användargränssnittet när pixeln börjar brinna på webbplatsen. `segID` är också godtyckligt. |
| `%ALIAS%` | Ett [!DNL Audience Manager] makro, som dynamiskt ersätts med de [!DNL Audience Manager] ID: [!UICONTROL segment] n som besökaren kvalificerar sig för, avgränsat med kommatecken , |

Din [!UICONTROL URL destination] konfiguration ska se ut som i bilden nedan:

![Målkonfiguration](/help/using/integration/assets/facebook-wca.png)

Spara [!UICONTROL destination]. Sedan kan du gå vidare till steget **Segmentmappningar** .

## Steg 2 - Segmentmappningar - Mappa segment till mål {#step-2-segment-mappings}

I arbetsflödet [Konfigurera URL-mål](/help/using/features/destinations/create-url-destination.md) mappar du det aktuella segmentet till det nya [!UICONTROL destination]segmentet. Observera att mappningsvärdet fylls i automatiskt med [!DNL Audience Manager][!UICONTROL segment ID].

Ange ett slutdatum om tillämpligt, annars lämnas tomt för inget slutdatum.

## Steg 3 - Skapa ett [!UICONTROL Audience] inom [!DNL Facebook Ads Manager] {#step-3-create-audience}

Se [Skapa en anpassad målgrupp](https://www.facebook.com/business/help/666509013483225) för en webbplats i [!DNL Facebook] hjälpdokumentationen. Markera [!UICONTROL Create Audience] alternativen i tabellen nedan:

| Objekt | Beskrivning |
---------|----------|
| Webbplatstrafik | Anpassad kombination |
| Inkludera | <ul><li>Välj **[!UICONTROL Event]** > Markera **[!UICONTROL Adobe-Audience-Manager-Segment]**. Detta var värdet på `ev` parametern i exempelpixeln i steg 1. Observera, att om pixeln ännu inte har startats kanske alternativet eller **[!UICONTROL Event]** inte visas i **[!UICONTROL Adobe-Audience-Manager-Segment]** [!DNL Facebook] användargränssnittet.</li><li>Lägg till en parameter: Välj `segID`.</li><li><p>Markera operatorn **innehåller** .</p><p>Detta är viktigt eftersom besökare kan kvalificera sig för flera segment, kan det finnas flera [!UICONTROL segment IDs] i pixelparametern. Om du använder likhetsoperatorn (`=`) kanske inte besökarna är kvalificerade för målgruppen, och du kommer att märka en lägre volym.</p></li><li>Lägg till ett värde: Ange [!DNL Audience Manager] segmentets ID.</li></ul> |
| Lägg till nytt villkor | Valfri inställning. |
| I slutet av | Valfri inställning. |
| Målgruppsnamn | Vi rekommenderar att du använder samma [!DNL Audience Manager] segmentnamn för att skapa en konsekvent upplevelse, såvida du inte lägger till ytterligare villkor till den här målgruppen. |

## Steg 4 - Tilldela [!UICONTROL Audience] till en [!UICONTROL Campaign] i [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Tilldela [!DNL Custom Audience]det till en annonskampanj när du har skapat den. Skapa en ny kampanj eller redigera en befintlig så ser du att den nya målgruppen visas i [!DNL Facebook] användargränssnittet. Er annonskampanj riktar sig till användare som har sett pixelbranden i sin webbläsare när de besöker er webbplats, om de [!DNL Audience Manager] ingår i segmentet.

## Sammanfattning {#summary}

Nu när du har tilldelat ditt [!DNL Audience Manager] segment till [!DNL Facebook WCA] målet [!DNL Audience Manager] aktiveras pixeln selektivt av [!DNL Facebook WCA] användare i ett givet segment med respektive segment-ID i pixeln för att fylla i [!DNL Facebook Audience]. Detta resulterar i en gradvis ökning av ju mer taggen skickas till rätt målgrupp på din webbplats. [!DNL Facebook Audience]

>[!NOTE]
>
> Om en användare faller bort från [!DNL Audience Manager] segmentet finns det för närvarande inget sätt att informera om [!DNL Audience Manager] att ta bort användaren från [!DNL Facebook] [!DNL Custom Audience].

