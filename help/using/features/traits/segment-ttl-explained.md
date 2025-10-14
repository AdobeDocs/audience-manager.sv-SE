---
description: Hur TTL-intervall (time-to-live) påverkar segmentmedlemskapet.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Förklara segmenttiden till Live
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 0%

---

# Förklara segment och egenskaper för time-to-Live {#segment-time-to-live-explained}

Hur egenskapsintervallet [!UICONTROL time-to-live] ([!DNL TTL]) påverkar segmentmedlemskapet.

<!-- segment-ttl-explained.xml -->

## Live-tid

[!DNL TTL] definierar hur länge en besökare stannar kvar i ett segment efter den senaste kvalificeringshändelsen. [!DNL TTL] är inställt på egenskaper och inte på segment. Besökare faller bort från ett segment om de inte är kvalificerade för en egenskap före slutet av intervallet [!DNL TTL]. Standardvärdet [!DNL TTL] för nya egenskaper är 120 dagar. Om värdet är 0 dagar förfaller egenskapen aldrig. [Ange TTL-värdet](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) när du skapar eller redigerar en egenskap i avsnittet [!UICONTROL Advanced Options] i gränssnittet för att skapa egenskaper.

### 1 dagars TTL förklarad

När du ställer in [!DNL TTL] på 1 dag startar TTL-timern nästa dag efter att trait realiserats, utan att räkna antalet återstående timmar på trait-realiseringsdagen.

Audience Manager beräknar [!DNL TTL] förfallodatum för traits med 1 dag [!DNL TTL] baserat på följande formel:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exempel 1**: Ett trait realiserat vid 1:00 [!DNL UTC], med 1 dag [!DNL TTL]. [!DNL TTL] går ut 24 + 24 - 1 = 47 timmar senare.
* **Exempel 2**: Ett trait realiserat vid 23:00 [!DNL UTC], med 1 dag [!DNL TTL]. [!DNL TTL] upphör att gälla 24 + 24 - 23 = 25 timmar senare.

## [!DNL TTL] och släpper ut ur ett segment

En användare faller bort från ett segment om de inte är kvalificerade för någon av sina egenskaper inom intervallet [!DNL TTL]. Om du t.ex. har ett 1-trait-segment med 30 dagar [!DNL TTL], kommer användaren att lämna det segmentet om han/hon inte är berättigad att utnyttja erbjudandet igen inom 30 dagar.

![](assets/ttl-explained.png)

## [!DNL TTL] och segmentförnyelse

[!DNL TTL] återställs och användaren stannar kvar i ett segment om de kvalificerar sig för segmentets egenskap inom [!DNL TTL]-perioden. Eftersom de flesta segment innehåller flera egenskaper med egna [!DNL TTL]-intervall, kan en användare finnas kvar i ett segment och återställa [!DNL TTL]-intervallet, så länge som de kvalificerar sig för eventuella egenskaper som är kopplade till segmentet.

Anta till exempel att du har segment 1 bestående av grupp A (30 dagar [!DNL TTL]) och avdelning B (15 dagar [!DNL TTL]). Om en besökare bara kvalificerar sig för varje egenskap en gång, visas förnyelseprocessen [!DNL TTL] och den totala längden i segmentet i bilden nedan.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL:er är oberoende av TTL-inställningar från tredje part

Kom ihåg att [!DNL TTL]-uppsättningen på din [!DNL Audience Manager] -pixel fungerar oberoende av [!DNL TTL]-uppsättningen på andra pixlar som används av tredje part ([!DNL DSP]s, annonsnätverk osv.).

>[!MORELIKETHIS]
>
>* [Ange ett förfallointervall för trait &#x200B;](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
