---
description: Med Destination Builder kan du skapa cookie-baserade URL-mål eller DNL-URL-mål. Du kan inte skapa server-till-server-mål (S2S) med Destination Builder, men du kan hantera deras segmentmappningar. Kontakta din konsult för att konfigurera ett S2S-mål. Destination Builder finns i Målgruppsdata > Destinationer.
seo-description: Med Destination Builder kan du skapa cookie-baserade URL-mål eller DNL-URL-mål. Du kan inte skapa server-till-server-mål (S2S) med Destination Builder, men du kan hantera deras segmentmappningar. Kontakta din konsult för att konfigurera ett S2S-mål. Destination Builder finns i Målgruppsdata > Destinationer.
seo-title: Destinationsverktyget
solution: Audience Manager
title: Destinationsverktyget
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 0%

---


# Destinationsverktyget {#destination-builder}

[!UICONTROL Destination Builder] gör att du kan skapa cookie-baserade mål eller [!DNL URL] mål. Du kan inte skapa server-till-server-mål ([!DNL S2S]) med [!UICONTROL Destination Builder], men du kan hantera deras segmentmappningar. Kontakta din konsult för att konfigurera en [!DNL S2S] destination. [!UICONTROL Destination Builder] finns i **[!UICONTROL Audience Data > Destinations]**.

## Inställningar för målverktyget {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] består av följande avsnitt och inställningar:

| [!UICONTROL Destination Builder] Avsnitt | Syfte |
|--- |--- |
| Grundläggande information | Används för att namnge målet, beskriva det och välja måltyp ([!DNL URL] eller [!DNL cookie]) och plattform (all, [!DNL Android], webbläsare eller [!DNL iOS]). |
| Konfiguration | Innehåller kontroller för: <br/><ul><li>Data för nyckelvärde skickas till [!DNL URL] destinationer. Du kan skicka data som enskilda eller serialiserade nyckelvärdepar. Mer information finns i [Målserialisering](../../features/destinations/key-value-pairs.md#destination-serialized) och [Standard- och Serial Key-Value-par](../../features/destinations/key-value-pairs.md). </li><li>Element i en cookie-destination som cookie-namn, domän, storlek, utgångsintervall, dataformat osv.</li></ul> |
| Segmentmappningar | Gör att du kan: <br/><ul><li>Sök efter, lägga till och hantera segment som är kopplade till alla måltyper. </li><li>Ange leveransprioriteter för enskilda segment (endast för [!DNL cookie]baserade segment).</li></ul> |

## Leveransmetoder {#data-delivery-methods}

Skicka information till ett mål genom att skicka den via en [!DNL URL] sträng, genom att skriva till en webbläsare [!DNL cookie]eller genom dataöverföringar från server till server offline.

* [!DNL URL] och cookie-baserade mål skickar data synkront när en användare utför åtgärder på en sida.
* Överföringen av data från server till server är asynkron och kan ske långt efter att en användare har lämnat sidan. Vilken leveranstyp du väljer beror på dina affärsbehov och hur en viss datapartner vill eller kan ta emot data.

Mer information finns i [Välja måltyp](../../features/destinations/destinations.md) .