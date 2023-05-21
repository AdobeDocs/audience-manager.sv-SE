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
source-wordcount: '354'
ht-degree: 3%

---

# Förklaring av TTL (time-to-live) för segment och traits {#segment-time-to-live-explained}

Instruktioner [!UICONTROL time-to-live] ([!DNL TTL]) påverkar segmentmedlemskapet.

<!-- segment-ttl-explained.xml -->

## Live-tid

[!DNL TTL] definierar hur länge en besökare stannar kvar i ett segment efter den senaste kvalificeringshändelsen. [!DNL TTL] anges för traits och inte för segment. Besökare faller bort från ett segment om de inte är berättigade till en egenskap före slutet av [!DNL TTL] intervall. Standardvärdet [!DNL TTL] för nya egenskaper är 120 dagar. Om värdet är 0 dagar förfaller egenskapen aldrig. [Ange TTL-värde](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) när du skapar eller redigerar en egenskap i [!UICONTROL Advanced Options] i gränssnittet för att skapa egenskaper.

### 1 dagars TTL förklarad

När du anger [!DNL TTL] till 1 dag börjar TTL-timern dagen efter att trait-implementeringen har slutförts, utan att antalet timmar som återstår på trait-implementeringsdagen räknas.

Audience Manager-beräkningar [!DNL TTL] utgångsdatum för traits med 1 dag [!DNL TTL] baserat på följande formel:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exempel 1**: Ett drag realiserat kl. 1:00 [!DNL UTC], med en dag [!DNL TTL]. [!DNL TTL] går ut 24 + 24 - 1 = 47 timmar senare.
* **Exempel 2**: Ett trait realiserat kl. 23:00 [!DNL UTC], med en dag [!DNL TTL]. [!DNL TTL] går ut 24 + 24 - 23 = 25 timmar senare.

## [!DNL TTL] och släppa ut ur ett segment

En användare faller bort från ett segment om de inte är kvalificerade för någon av sina egenskaper inom [!DNL TTL] intervall. Om du t.ex. har ett 1-trait-segment med 30 dagar [!DNL TTL]kommer användaren att lämna det segmentet om han/hon inte är berättigad till detta inom 30 dagar.

![](assets/ttl-explained.png)

## [!DNL TTL] och segmentförnyelse

The [!DNL TTL] återställs och användaren stannar kvar i ett segment om de kvalificerar sig för segmentets egenskap i [!DNL TTL] punkt. Dessutom eftersom de flesta segment innehåller flera egenskaper med egna egenskaper [!DNL TTL] kan användaren stanna kvar i ett segment och återställa [!DNL TTL] intervall så länge de kvalificerar sig för eventuella egenskaper som är kopplade till segmentet.

Anta till exempel att du har segment 1 som består av grupp A (30 dagar) [!DNL TTL]) och fack B (15 dagar) [!DNL TTL]). Om en besökare bara kvalificerar sig för varje drag en gång visas bilden nedan [!DNL TTL] förnyelseprocess och total segmentlängd.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL:er är oberoende av TTL-inställningar från tredje part

Kom ihåg [!DNL TTL] på din [!DNL Audience Manager] pixeln fungerar oberoende av [!DNL TTL] anges på andra pixlar som används av tredje part ([!DNL DSP]s, annonsnätverk osv.).

>[!MORELIKETHIS]
>
>* [Ange ett förfallointervall för trait](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

