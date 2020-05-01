---
description: Den här sidan illustrerar processen att skapa WCA-pixlar (Custom Audiences) för Facebook för att skicka webbaserade målgruppssegment för Audience Manager till Facebook, för annonsanpassning online med förbättrad transparens.
seo-description: Den här sidan illustrerar processen att skapa WCA-pixlar (Custom Audiences) för Facebook för att skicka webbaserade målgruppssegment för Audience Manager till Facebook, för annonsanpassning online med förbättrad transparens.
seo-title: Integrering med Facebook WCA
solution: Audience Manager
title: Integrering med Facebook WCA
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Integrering med Facebook WCA {#facebook-wca-integration}

Den här sidan illustrerar processen att skapa WCA-pixlar (Custom Audiences) för Facebook för att skicka webbaserade målgruppssegment för Audience Manager till Facebook, för annonsanpassning online med förbättrad transparens.

## Översikt {#overview}

[Med anpassade målgrupper på Facebooks webbplats (WCA)](https://www.facebook.com/business/help/449542958510885) kan du skapa en lista över personer som har besökt vissa sidor eller vidtagit särskilda åtgärder på din webbplats. Audience Manager aktiverar aktivering i WCA med URL-adresser, med vilka du kan konfigurera en anpassad pixelbaserad integrering för att skicka webbaserade målgrupper till Facebook för målgruppsanpassning.

![Integrering med Facebook WCA](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Den här funktionen kräver att du väljer alternativet Webbplatsens målgrupp för sociala plattformar i [URL-mål](/help/using/features/destinations/create-url-destination.md). Sociala plattformar kräver att referensinformation avmaskeras när den skickas till deras plattform. Observera att detta innebär att målplattformen/målpartnern kan se information i din referens-URL.

## Förutsättningar {#prerequisites}

1. Facebook-annonskonto
2. Audience Manager-segment, redo att tilldelas till ditt nya Facebook-mål. Så här [skapar du ett segment](/help/using/features/segments/segment-builder.md) i gränssnittet för Audience Manager.
3. Adobe Experience Platform Identity Service (ECID) version 4.1.0 eller senare. Ladda ned den senaste versionen **[här](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. Audience Manager Data Integration Library (DIL) version 9.0 eller senare, kan laddas ned **[här](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Om du använder[SSF (Server-Side Forwarding)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)för att importera data till Audience Manager måste du använda AppMeasurement version 2.12 eller senare. Hämta AppMeasurement med[Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html).

Vi rekommenderar att du installerar eller uppgraderar biblioteken i steg 3 och 4 med [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) eller [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html).

## Steg 1 - Skapa ett Facebook-mål i Audience Manager {#step-1-create-facebook-destination}

Skapa en ny URL-destination i Audience Manager och ge den namnet Anpassa målgrupper på Facebooks webbplats. Använd inställningarna nedan när du skapar målet. Du kan även gå till sidan [Konfigurera ett URL-mål](/help/using/features/destinations/create-url-destination.md) .

**Grundläggande information**

* **Kategori**: Egen
* **Typ**: URL
* Markera kryssrutan **Autofyll målmappning** och välj sedan **Segment-ID**.

**Dataexportetiketter**

Välj alternativet **Detta mål kan aktivera en kombination med personligt identifierbar information (PII)**.

>[!NOTE]
>
> Den här exportetiketten förhindrar att data från tredje part och data som härletts från enhetsdiagram inkluderas i segmenten.

**Konfiguration**

* **URL-typ**: Välj publik **för webbplatser för sociala plattformar**. Om du väljer det här alternativet för URL-typ skymmer Audience Manager inte referensens URL-information när en Facebook WCA-pixel aktiveras.
* **Serialisera**: Välj **Aktivera**.
* Ange Facebooks WCA-pixel i fältet **Bas-URL** och **Säker URL** .
* **Avgränsare**: ,

Exempel på bas-URL: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Exempelpixel utlöses från sidan. I det här exemplet visas en användare som kvalificerar sig för tre Audience Manager-segment, med ID 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`


| Parameter | Beskrivning |
---------|----------|
| `id` | Ditt pixel-ID för Facebook, som du hittar i gränssnittet för Facebook Ad Manager när du skapar målgruppspixlar. |
| `ev` | Händelse. Det här är ett godtyckligt värde som visas i gränssnittet för Facebook-annonshanteraren när pixeln börjar brinna på webbplatsen. Mer information finns i Inkludera objekt i [steg 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience). |
| `cd[segID]` | Ytterligare en parameter som börjar fylla i gränssnittet för Facebook Ad Manager när pixeln börjar brinna på webbplatsen. `segID` är också godtyckligt. |
| `%ALIAS%` | Ett Audience Manager-makro, som dynamiskt ersätts med det segment-ID för Audience Manager som besökaren kvalificerar sig för, avgränsat med kommatecken , |

URL-målkonfigurationen ska se ut så här i bilden nedan:

![Målkonfiguration](/help/using/integration/assets/facebook-wca.png)

Spara målet. Sedan kan du gå vidare till steget **Segmentmappningar** .

## Steg 2 - Segmentmappningar - Mappa segment till mål {#step-2-segment-mappings}

Mappa det aktuella segmentet till det nya målet i arbetsflödet [Konfigurera URL-mål](/help/using/features/destinations/create-url-destination.md) . Observera att mappningsvärdet fylls i automatiskt med segment-ID för Audience Manager.

Ange ett slutdatum om tillämpligt, annars lämnas tomt för inget slutdatum.

## Steg 3 - Skapa en publik i Facebook Ads Manager {#step-3-create-audience}

Se [Skapa en anpassad målgrupp](https://www.facebook.com/business/help/666509013483225) för en webbplats i hjälpdokumentationen för Facebook. Välj alternativen för att skapa målgrupp i tabellen nedan:


| Objekt | Beskrivning |
---------|----------|
| Webbplatstrafik | Anpassad kombination |
| Inkludera | <ul><li>Välj **Händelse** > Välj **Adobe-Audience-Manager-Segment**. Det här var värdet på parametern ev i exempelpixeln i steg 1. Observera, att om pixeln ännu inte har startats kanske inte alternativet **Event** eller **Adobe-Audience-Manager-Segment** visas i Facebooks användargränssnitt.</li><li>Lägg till en parameter: Välj `segID`.</li><li><p>Markera operatorn **innehåller** .</p><p>Detta är viktigt eftersom besökare kan kvalificera sig för flera segment, kan det finnas flera segment-ID:n i pixelparametern. Om du använder operatorn lika med (=) kanske besökarna inte är kvalificerade för målgruppen, och du kommer att märka en lägre volym.</p></li><li>Lägg till ett värde: Ange segment-ID för Audience Manager.</li></ul> |
| Lägg till nytt villkor | Valfri inställning. |
| I slutet av | Valfri inställning. |
| Målgruppsnamn | Vi rekommenderar att du använder samma Audience Manager-segmentnamn för att uppnå enhetlighet, såvida du inte lägger till ytterligare villkor till denna Audience. |

## Steg 4 - Tilldela målgruppen till en kampanj i Facebook Ads Manager {#step-4-assign-audience-to-campaign}

När du har skapat den anpassade målgruppen tilldelar du den till en annonskampanj. Skapa en ny kampanj eller redigera en befintlig så ser du att din nya målgrupp finns med i Facebooks användargränssnitt. Din annonskampanj riktar sig till användare som har sett pixelbranden i sin webbläsare när de besöker din webbplats, om Audience Manager inkluderar dem i segmentet.

## Sammanfattning {#summary}

Nu när du har tilldelat ditt Audience Manager-segment till Facebooks WCA-mål, kommer Audience Manager selektivt att utlösa Facebooks WCA-pixel till användare i ett visst segment med respektive segment-ID i pixeln för att fylla på Facebook-målgruppen. Detta leder till en gradvis ökning av Facebook-målgruppen ju mer taggen skickas till den tillämpliga målgruppen på din webbplats.

>[!NOTE]
>
> Om en användare faller utanför Audience Manager-segmentet finns det för närvarande inget sätt för Audience Manager att informera Facebook om att ta bort användaren från den anpassade målgruppen.

