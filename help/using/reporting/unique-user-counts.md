---
description: Beskriver variationen i unika användarsummor mellan rapporter för samma egenskap och tidsperiod.
seo-description: Beskriver variationen i unika användarsummor mellan rapporter för samma egenskap och tidsperiod i Adobe Audience Manager
seo-title: Räkna unika användare i överlappning och allmänna rapporter i AAM
solution: Audience Manager
title: Räkna unika användare i överlappning och allmänna rapporter
uuid: 450f6a8c-f363-43de-b2d8-0a156f14ecae
feature: reporting reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 0%

---


# Räkna unika användare i överlappning och allmänna rapporter{#counting-unique-users-in-overlap-and-general-reports}

Den här sidan beskriver variationen i unika användarsummor mellan rapporter för samma egenskap och tidsperiod.

<!-- 

c_unique_user_counts.xml

 -->

## Överlappningsrapport: Unikt användarantal

Överlappningsrapporterna räknas användare som unika när de kvalificerar sig för en egenskap:

* Under rapportens valda tidsintervall.
* Det har ett [time-to-live](../features/traits/segment-ttl-explained.md) -värde som är längre än det valda tidsintervallet för rapporten.
* Om de betraktas som aktiva i vårt system (dvs. är kvalificerade för andra egenskaper, har en ID-synkronisering osv.) under de senaste 60 dagarna.

## Allmän rapport: Unikt användarantal

I rapporten Allmänt räknas webbplatsbesökare som unika om de kvalificerat sig för egenskapen under den valda tidsperioden.

>[!MORELIKETHIS]
>
>* [Interaktiva rapporter](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports)
>* [Allmänna rapporter](../reporting/general-reports.md#general-reports-overview)

