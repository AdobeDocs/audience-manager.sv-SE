---
description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-description: Beskriver segment, deras beståndsdelar och regelgenerering med Segment Builder.
seo-title: Segmentsyfte, komposition och regler
solution: Audience Manager
title: Segmentsyfte, komposition och regler
uuid: 886d4abe-b1b6-4983-b4fb-b552d54d51ba
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 5%

---


# Segment: Syfte, sammansättning och regler {#segments-purpose-composition-and-rules}

Beskriver [!UICONTROL segments]och deras beståndsdelar samt skapar regler med [!UICONTROL Segment Builder].

## Syfte med [!UICONTROL Segments]

A *`segment`* (or an *`audience`*) is a set of users who share common attributes. I Audience Manager skapar du [!UICONTROL segments] med regler på serversidan. Med dessa regler kan ni skapa målgruppsgrupper baserat på webbplatsens besökarattribut, till exempel:

* Beteende
* Demografi (ålder, kön, inkomst osv.);
* Andra egenskaper som du kan definiera i användargränssnittet.

## [!UICONTROL Segment] Disposition

En Audience Manager [!UICONTROL segment] är en regel på serversidan som består av enskilda egenskaper eller grupper av egenskaper. Traits består av dataelement som kallas nyckelvärdepar. Förutom regler som du anger på [!UICONTROL segment] nivå innehåller dessa nyckelvärdepar de kriterier som kvalificerar besökare för rätt och [!UICONTROL segment] medlemskap.

## Att tänka på vid [!UICONTROL Adobe Analytics][!UICONTROL Segment] mappning

När du mappar Adobe Analytics [!UICONTROL segments] eller rapportsviter till din Experience Cloud-organisation skapar Audience Manager automatiskt nya, motsvarande, skrivskyddade [!UICONTROL segments] och anpassade egenskaper. Du kan inte redigera eller ändra lagringsplatsen för dessa [!UICONTROL segments] från Audience Manager. Alla ändringar du gör i Adobe Analytics [!UICONTROL segments] eller rapportsviterna återspeglas i Audience Manager.

>[!TIP]
>
>Audience Manager [!UICONTROL segments] skiljer sig från [!DNL Adobe Analytics] [!UICONTROL segments]. Read [Understanding Segments in Analytics and Audience Manager](https://docs.adobe.com/content/help/sv-SE/analytics/integration/audience-analytics/audience-analytics-workflow/aam-analytics-segments.html) for an in-depth description of the differences.

## Skapa regelbaserade [!UICONTROL Segments] med [!UICONTROL Segment Builder]

Till skillnad från traditionella pixlar som aktiveras som svar på enkla ja/nej-villkor, [!UICONTROL Segment Builder] kan du skapa komplexa [!UICONTROL segment] krav. Som [!UICONTROL traits]exempel kan du [!UICONTROL segments] utvärdera data med [!DNL Boolean] uttryck ([!DNL AND], [!DNL OR], [!DNL NOT]), jämförelseoperatorer (större än, mindre än, lika med, osv.) och kriterier för senaste/frekvens. Dessa funktioner hjälper er att skapa fokuserade målgrupper [!UICONTROL segments] som är relevanta för era affärsbehov.

## Fördelar

[!UICONTROL Segments] förbättra de vanliga pixelbaserade målgruppsprocesserna för att skapa/segmentera, eftersom de gör att du kan:

* Bygg relevanta, användbara [!UICONTROL segments] med egenskaper från första och tredje part.
* Skapa sofistikerade och komplexa segmenteringsregler med booleska operatorer, jämförelseuttryck och kriterier för senaste/frekvens.
* Skicka [!UICONTROL segment] data till en målpartner.
* Övervaka prestanda med rapporter från Audience Manager.

>[!MORELIKETHIS]
>
>* [Signaler, traits och segment](../../reference/signal-trait-segment.md)

