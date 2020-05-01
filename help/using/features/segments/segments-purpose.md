---
description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-title: Segmentsyfte, komposition och regler
solution: Audience Manager
title: Segmentsyfte, komposition och regler
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Segment: Syfte, komposition och regler {#segments-purpose-composition-and-rules}

Beskriver segment, deras beståndsdelar och regelgenerering med [!UICONTROL Segment Builder].

## Syfte med segment

En *`segment`* (eller en *`audience`*) är en uppsättning användare som delar gemensamma attribut. I Audience Manager skapar du segment med regler på serversidan. Med dessa regler kan ni skapa målgruppsgrupper baserat på webbplatsens besökarattribut, till exempel:

* Beteende
* Demografi (ålder, kön, inkomst osv.);
* Andra egenskaper som du kan definiera i användargränssnittet.

## Segmentkomposition

Ett Audience Manager-segment är en regel på serversidan som består av enskilda eller grupper av egenskaper. Traits består av dataelement som kallas nyckelvärdepar. Förutom regler som du anger på segmentnivå innehåller dessa nyckelvärdepar de kriterier som kvalificerar besökare för trait- och segmentmedlemskap.

## Överväganden om segmentmappning i Adobe Analytics

När du mappar Adobe Analytics-segment eller rapportsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande, skrivskyddade segment och egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa segment med Audience Manager. Alla ändringar som ni gör i era mappade Adobe Analytics-segment eller rapportsviter återspeglas i Audience Manager.

>[!TIP]
>
>Audience Manager-segment skiljer sig från [!DNL Adobe Analytics] segment. Läs [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) om du vill ha en detaljerad beskrivning av skillnaderna.

## Skapa regelbaserade segment med segmentbyggaren

Till skillnad från traditionella pixlar som utlöses som svar på enkla ja/nej-villkor, kan du skapa komplexa segmentkrav med segmentverktyget. Precis som egenskaper utvärderar segment data med hjälp av [!DNL Boolean] uttryck ([!DNL AND], [!DNL OR], [!DNL NOT]), jämförelseoperatorer (större än, mindre än, lika med, osv.) och kriterier för senaste/frekvens. Dessa funktioner hjälper er att skapa fokuserade målgruppssegment som är relevanta för företagets behov.

## Fördelar

Segmenten blir bättre med vanliga pixelbaserade målgrupps-/segmenteringsprocesser eftersom de gör att du kan:

* Bygg relevanta, användbara segment med egna egenskaper och tredjepartsegenskaper.
* Skapa sofistikerade och komplexa segmenteringsregler med booleska operatorer, jämförelseuttryck och kriterier för senaste/frekvens.
* Skicka segmentdata till en målpartner.
* Övervaka prestanda med Audience Manager-rapporter.

>[!MORELIKETHIS]
>
>* [Signaler, egenskaper och segment](../../reference/signal-trait-segment.md)

