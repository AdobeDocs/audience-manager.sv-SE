---
description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-title: Segmentsyfte, komposition och regler
solution: Audience Manager
title: Segmentsyfte, komposition och regler
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: 'Segment '
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# Segment: Syfte, sammansättning och regler {#segments-purpose-composition-and-rules}

Beskriver [!UICONTROL segments], deras beståndsdelar och hur regler skapas med [!UICONTROL Segment Builder].

## Syfte med [!UICONTROL Segments]

En *`segment`* (eller en *`audience`*) är en uppsättning användare som delar gemensamma attribut. I Audience Manager skapar du [!UICONTROL segments] med regler på serversidan. Med dessa regler kan ni skapa målgruppsgrupper baserat på webbplatsens besökarattribut, till exempel:

* Beteende
* Demografi (ålder, kön, inkomst osv.);
* Andra egenskaper som du kan definiera i användargränssnittet.

## [!UICONTROL Segment] Disposition

En Audience Manager [!UICONTROL segment] är en regel på serversidan som består av enskilda egenskaper eller grupper av egenskaper. Traits består av dataelement som kallas nyckelvärdepar. Förutom regler som du anger på [!UICONTROL segment]-nivån innehåller dessa nyckelvärdepar de kriterier som kvalificerar besökare för trait och [!UICONTROL segment]-medlemskap.

## Överväganden för [!UICONTROL Adobe Analytics] [!UICONTROL Segment]-mappning

När du mappar Adobe Analytics [!UICONTROL segments] eller rapporterar programsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande skrivskyddade [!UICONTROL segments]-egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa [!UICONTROL segments] från Audience Manager. Alla ändringar du gör i dina mappade Adobe Analytics [!UICONTROL segments] eller rapportsviter visas i Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] skiljer sig från [!DNL Adobe Analytics] [!UICONTROL segments]. Läs [Förstå segment i analys och Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) om du vill ha en detaljerad beskrivning av skillnaderna.

## Skapa regelbaserad [!UICONTROL Segments] med [!UICONTROL Segment Builder]

Till skillnad från traditionella pixlar som utlöses som svar på enkla ja/nej-villkor kan du med [!UICONTROL Segment Builder] skapa komplexa [!UICONTROL segment]-krav. Precis som [!UICONTROL traits] utvärderar [!UICONTROL segments] data med [!DNL Boolean]-uttryck ([!DNL AND], [!DNL OR], [!DNL NOT]), jämförelseoperatorer (större än, mindre än, lika med, osv.) och kriterier för senaste/frekvens. Dessa funktioner hjälper er att skapa en målgrupp [!UICONTROL segments] som är anpassad efter era affärsbehov.

## Fördelar

[!UICONTROL Segments] förbättra de vanliga pixelbaserade målgruppsprocesserna för att skapa/segmentera, eftersom de gör att du kan:

* Bygg relevanta, användbara [!UICONTROL segments] med egenskaper från första och tredje part.
* Skapa sofistikerade och komplexa segmenteringsregler med booleska operatorer, jämförelseuttryck och kriterier för senaste/frekvens.
* Skicka [!UICONTROL segment]-data till en målpartner.
* Övervaka prestanda med rapporter från Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaler, traits och segment](../../reference/signal-trait-segment.md)

