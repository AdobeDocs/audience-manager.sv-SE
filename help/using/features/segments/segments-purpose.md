---
description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-description: Describes segments, their constituent parts, and rule creation with Segment Builder.
seo-title: Segments  Purpose, Composition, and Rules
solution: Audience Manager
title: Syfte, disposition och regler för segment
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
exl-id: 4e4da7a7-3267-4564-b1c5-663dcddf2b93
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Segment: Syfte, Disposition och Regler {#segments-purpose-composition-and-rules}

Beskriver [!UICONTROL segments], deras beståndsdelar och regelgenerering med [!UICONTROL Segment Builder].

## Syfte med [!UICONTROL Segments]

En *`segment`* (eller en *`audience`*) är en uppsättning användare som delar gemensamma attribut. I Audience Manager skapar du [!UICONTROL segments] med regler på serversidan. Med dessa regler kan ni skapa målgruppsgrupper baserat på webbplatsens besökarattribut, till exempel:

* Beteende
* Demografi (ålder, kön, inkomst osv.);
* Andra egenskaper som du kan definiera i användargränssnittet.

## [!UICONTROL Segment]-komposition

En Audience Manager [!UICONTROL segment] är en regel på serversidan som består av enskilda egenskaper eller grupper av egenskaper. Traits består av dataelement som kallas nyckelvärdepar. Förutom regler som du anger på nivån [!UICONTROL segment] innehåller dessa nyckelvärdepar de kriterier som kvalificerar besökare för rätt och [!UICONTROL segment]-medlemskap.

## Överväganden för [!UICONTROL Adobe Analytics] [!UICONTROL Segment]-mappning

När du mappar Adobe Analytics [!UICONTROL segments] eller rapportsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande, skrivskyddade [!UICONTROL segments] och egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa [!UICONTROL segments] från Audience Manager. Alla ändringar som du gör i dina mappade Adobe Analytics [!UICONTROL segments] eller rapportsviter visas i Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] skiljer sig från [!DNL Adobe Analytics] [!UICONTROL segments]. Läs [Förstå segment i Analytics och Audience Manager](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) om du vill ha en detaljerad beskrivning av skillnaderna.

## Skapa regelbaserad [!UICONTROL Segments] med [!UICONTROL Segment Builder]

Till skillnad från traditionella pixlar som utlöses som svar på enkla ja/nej-villkor kan du skapa komplexa [!UICONTROL Segment Builder]-krav med [!UICONTROL segment]. Precis som [!UICONTROL traits] utvärderar [!UICONTROL segments] data med [!DNL Boolean] uttryck ([!DNL AND], [!DNL OR], [!DNL NOT]), jämförelseoperatorer (större än, mindre än, lika med osv.) och villkor för senaste och frekvens. De här funktionerna hjälper dig att skapa en fokuserad målgrupp [!UICONTROL segments] som är relevant för dina affärsbehov.

## Fördelar

[!UICONTROL Segments] förbättrar de vanliga pixelbaserade målgruppsprocesserna för att skapa/segmentera målgrupper eftersom du kan:

* Bygg relevanta, användbara [!UICONTROL segments] med egenskaper från första och tredje part.
* Skapa sofistikerade och komplexa segmenteringsregler med booleska operatorer, jämförelseuttryck och kriterier för senaste/frekvens.
* Skicka [!UICONTROL segment]-data till en målpartner.
* Övervaka prestanda med Audience Manager-rapporter.

>[!MORELIKETHIS]
>
>* [Signaler, traits och segment](../../reference/signal-trait-segment.md)
