---
description: Med Destination Builder kan du skapa cookie-baserade URL-mål eller DNL-URL-mål. Du kan inte skapa server-till-server-mål (S2S) med Destination Builder, men du kan hantera deras segmentmappningar. Kontakta din konsult för att konfigurera ett S2S-mål. Destination Builder finns i Målgruppsdata > Destinationer.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Destinationsverktyget
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Destinationsverktyget {#destination-builder}

Med [!UICONTROL Destination Builder] kan du skapa cookie-baserade mål eller [!DNL URL] mål. Du kan inte skapa server-till-server-mål ([!DNL S2S]) med [!UICONTROL Destination Builder], men du kan hantera deras segmentmappningar. Kontakta din konsult för att konfigurera ett [!DNL S2S]-mål. [!UICONTROL Destination Builder] finns i **[!UICONTROL Audience Data > Destinations]**.

## Inställningar för målverktyget {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] består av följande avsnitt och inställningar:

| [!UICONTROL Destination Builder] avsnitt | Syfte |
|--- |--- |
| Grundläggande information | Används för att namnge målet, beskriva det och välja måltyp ([!DNL URL] eller [!DNL cookie]) och plattform (all, [!DNL Android], webbläsare eller [!DNL iOS]). |
| Konfiguration | Inkluderar kontroller för: <br/><ul><li>Nyckelvärdedata skickas till [!DNL URL] mål. Du kan skicka data som enskilda eller serialiserade nyckelvärdepar. Mer information finns i [Målserialisering](../../features/destinations/key-value-pairs.md#destination-serialized) och [Standardpar och serienyckelvärdepar](../../features/destinations/key-value-pairs.md). </li><li>Element i en cookie-destination som cookie-namn, domän, storlek, utgångsintervall, dataformat osv.</li></ul> |
| Segmentmappningar | Gör att du kan: <br/><ul><li>Sök efter, lägga till och hantera segment som är kopplade till alla måltyper. </li><li>Ange leveransprioriteter för enskilda segment (endast för [!DNL cookie]-baserade segment).</li></ul> |

## Metoder för dataöverföring {#data-delivery-methods}

Skicka information till ett mål genom att skicka den via en [!DNL URL]-sträng, genom att skriva till en webbläsare [!DNL cookie] eller genom dataöverföringar från server till server offline.

* [!DNL URL] och cookie-baserade mål skickar data synkront när en användare utför åtgärder på en sida.
* Överföringen av data från server till server är asynkron och kan ske långt efter att en användare har lämnat sidan. Vilken leveranstyp du väljer beror på dina affärsbehov och hur en viss datapartner vill eller kan ta emot data.

Mer information finns i [Så här väljer du en måltyp](../../features/destinations/destinations.md).
