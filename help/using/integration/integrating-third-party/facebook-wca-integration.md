---
description: På den här sidan illustreras processen att skapa Facebook WCA-pixlar (Web Site Custom Audiences) för att skicka webbaserade Audience Manager-målgruppssegment till Facebook, för webbannonsering med förbättrad transparens.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Integrering med Facebook WCA
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 3%

---

# [!DNL Facebook WCA] Integrering {#facebook-wca-integration}

Den här sidan visar processen att skapa [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixlar för att skicka webbaserade [!DNL Audience Manager] målgruppssegment till [!DNL Facebook], för webbannonsering med förbättrad transparens.

## Översikt {#overview}

[Facebook WCA (Web Site Custom Audiences)](https://www.facebook.com/business/help/449542958510885) Med kan du skapa en lista över personer som har besökt vissa sidor eller vidtagit särskilda åtgärder på webbplatsen. [!DNL Audience Manager] aktiverar aktivering i [!DNL WCA] använda [!DNL URL] mål, med vilka du kan konfigurera en anpassad pixelbaserad integration för att skicka webbaserade målgrupper till [!DNL Facebook] för målinriktning.

![Integrering med Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Den här funktionen kräver att du väljer [!UICONTROL Website] för sociala plattformar i [URL-mål](/help/using/features/destinations/create-url-destination.md). Sociala plattformar kräver att referensinformation avmaskeras när den skickas till deras plattform. Observera att detta innebär att målplattformen/målpartnern kan se information i din referent [!DNL URL].

## Förutsättningar {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segment, redo att tilldelas till dina nya [!DNL Facebook] mål. Här är [hur du skapar ett segment](/help/using/features/segments/segment-builder.md) i [!DNL Audience Manager] Gränssnitt.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Version 4.1.0 eller senare. Ladda ned den senaste versionen **[här](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) version 9.0 eller senare, kan hämtas från **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Om du använder [SSF (Server-Side Forwarding)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) att importera data till [!DNL Audience Manager]måste du använda AppMeasurement version 2.12 eller senare. Hämta [!DNL AppMeasurement] med [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

Vi rekommenderar att du installerar eller uppgraderar biblioteken i steg 3 och 4 med [Adobe Experience Platform-taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Steg 1 - Skapa en [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Skapa ett nytt [!UICONTROL URL Destination] in [!DNL Audience Manager] och namnge [!DNL Facebook Website Custom Audiences]. Använd inställningarna nedan när du skapar målet. Du kan även referera till [Konfigurera ett URL-mål](/help/using/features/destinations/create-url-destination.md) sida.

### Grundläggande information

* **[!UICONTROL Category]**: Egen
* **[!UICONTROL Type]**: [!DNL URL]
* Välj **[!UICONTROL Auto-fill Destination Mapping]** markera kryssrutan och sedan markera **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Välj alternativet **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Den här exportetiketten förhindrar att data från tredje part och data som härletts från enhetsdiagram inkluderas i segmenten.

### Konfiguration

* **[!UICONTROL URL type]**: Välj **[!UICONTROL Website audience for social platforms]**. Genom att markera detta [!UICONTROL URL Type] option, [!DNL Audience Manager] inte skymmer referenten [!DNL URL] information när en [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Välj **[!UICONTROL Enable]**.
* I **[!UICONTROL Base URL]** och **[!UICONTROL Secure URL]** fält, ange [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Bas [!DNL URL] exempel: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exempelpixel utlöses från sidan. I det här exemplet visas en användare som kvalificerar sig för tre [!DNL Audience Manager] segment, med ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beskrivning |
|---------|----------|
| `id` | Dina [!DNL Facebook] pixel-ID som du hittar i [!DNL Facebook Ad Manager] när du skapar målgruppspixlar. |
| `ev` | Event.     Detta är ett godtyckligt värde som visas i [!DNL Facebook Ad Manager] -användargränssnittet när pixeln börjar brinna på webbplatsen. Se [!UICONTROL Include] artikel i [Steg 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), för mer information. |
| `cd[segID]` | Ytterligare en parameter som börjar fyllas i i [!DNL Facebook Ad Manager] -användargränssnittet när pixeln börjar brinna på webbplatsen. `segID` är också godtyckligt. |
| `%ALIAS%` | An [!DNL Audience Manager] makro, som ersätts dynamiskt med [!DNL Audience Manager] [!UICONTROL segment] ID:n som besökaren uppfyller kraven för, avgränsade med kommatecken , |

Dina [!UICONTROL URL destination] bör se ut som i bilden nedan:

![Målkonfiguration](/help/using/integration/assets/facebook-wca.png)

Spara [!UICONTROL destination]. Sedan kan du gå vidare till **Segmentmappningar** steg.

## Steg 2 - Segmentmappningar - Mappa segment till mål {#step-2-segment-mappings}

I [Konfigurera URL-mål](/help/using/features/destinations/create-url-destination.md) arbetsflöde, mappa det aktuella segmentet till det nyskapade [!UICONTROL destination]. Observera att mappningsvärdet fylls i automatiskt med [!DNL Audience Manager] [!UICONTROL segment ID].

Ange ett slutdatum om tillämpligt, annars lämnas tomt för inget slutdatum.

## Steg 3 - Skapa en [!UICONTROL Audience] inom [!DNL Facebook Ads Manager] {#step-3-create-audience}

Se [Skapa en anpassad webbplats](https://www.facebook.com/business/help/666509013483225) i [!DNL Facebook] hjälpdokumentation. Välj [!UICONTROL Create Audience] i tabellen nedan:

| Objekt | Beskrivning |
|---------|----------|
| Webbplatstrafik | Anpassad kombination |
| Inkludera | <ul><li>Välj **[!UICONTROL Event]** > Välj **[!UICONTROL Adobe-Audience-Manager-Segment]**. Detta var värdet på `ev` i exempelpixeln i steg 1. Observera, att om pixeln ännu inte har börjat brinna, **[!UICONTROL Event]** eller **[!UICONTROL Adobe-Audience-Manager-Segment]** kanske inte visas i [!DNL Facebook] användargränssnitt.</li><li>Lägg till en parameter: Välj `segID`.</li><li><p>Välj **innehåller** -operator.</p><p>Detta är viktigt, med tanke på att besökare kan kvalificera sig för flera segment, kan det finnas flera [!UICONTROL segment IDs] i pixelparametern. Använda lika med (`=`) kanske inte är rätt för besökarna och du kommer att märka en lägre volym.</p></li><li>Lägg till ett värde: Ange [!DNL Audience Manager] segment-ID.</li></ul> |
| Lägg till nytt villkor | Valfri inställning. |
| I slutet av | Valfri inställning. |
| Målgruppsnamn | Vi rekommenderar att du använder samma [!DNL Audience Manager] Segmentnamn för enhetlighet, såvida du inte lägger till ytterligare villkor till den här målgruppen. |

## Steg 4 - Tilldela [!UICONTROL Audience] till [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

När du har skapat [!DNL Custom Audience], tilldela den till en annonskampanj. Skapa en ny kampanj eller redigera en befintlig så ser du att den nya målgruppen listas i [!DNL Facebook] användargränssnitt. Din annonskampanj riktar sig till användare som har sett pixelbranden i sin webbläsare när de besöker din webbplats, om [!DNL Audience Manager] innehåller dem i segmentet.

## Sammanfattning {#summary}

Nu när du har tilldelat [!DNL Audience Manager] segmentera [!DNL Facebook WCA] destination, [!DNL Audience Manager] kommer att utlösa [!DNL Facebook WCA] pixel till användare av ett givet segment med respektive segment-ID i pixeln för att fylla i [!DNL Facebook Audience]. Detta leder till en gradvis ökning av [!DNL Facebook Audience] ju mer taggen skickas till den tillämpliga publiken på er webbplats.

>[!NOTE]
>
> Om en användare faller bort från [!DNL Audience Manager] segment, det finns för närvarande inget sätt att [!DNL Audience Manager] att informera [!DNL Facebook] för att ta bort användaren från [!DNL Custom Audience].
