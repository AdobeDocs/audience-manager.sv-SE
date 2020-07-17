---
description: Hur TTL-intervall (time-to-live) påverkar segmentmedlemskapet.
seo-description: Hur TTL-intervall (time-to-live) påverkar segmentmedlemskapet.
seo-title: Förklara segment- och anpassningstid till livstid
solution: Audience Manager
title: Förklara segmenttiden till Live
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 3%

---


# Förklaring av TTL (time-to-live) för segment och traits {#segment-time-to-live-explained}

Hur egenskapsintervall [!UICONTROL time-to-live] ([!DNL TTL]) påverkar segmentmedlemskapet.

<!-- segment-ttl-explained.xml -->

## Live-tid

[!DNL TTL] definierar hur länge en besökare stannar kvar i ett segment efter den senaste kvalificeringshändelsen. [!DNL TTL] anges för traits och inte för segment. Visitors fall out of a segment if they do not qualify for a trait before the end of the [!DNL TTL] interval. Standardvärdet [!DNL TTL] för nya egenskaper är 120 dagar. Om värdet är 0 dagar förfaller egenskapen aldrig. [Ange TTL-värdet](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) när du skapar eller redigerar en egenskap i delen [!UICONTROL Advanced Options] av gränssnittet där egenskaperna skapas.

### 1 dagars TTL förklarad

När TTL-timern ställs in [!DNL TTL] på 1 dag startar den följande dagen efter att trait-implementeringen har slutförts, utan att antalet timmar som återstår på trait-implementeringsdagen räknas.

Audience Manager beräknar [!DNL TTL] utgångsdatum för egenskaper med 1 dag [!DNL TTL] baserat på följande formel:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Exempel 1**: Ett trait realiserat klockan 1:00 [!DNL UTC]med en dag [!DNL TTL]. [!DNL TTL] går ut 24 + 24 - 1 = 47 timmar senare.
* **Exempel 2**: Ett trait realiserat kl. 23:00 [!DNL UTC]med en dag [!DNL TTL]. [!DNL TTL] går ut 24 + 24 - 23 = 25 timmar senare.

## [!DNL TTL] och släppa ut ur ett segment

En användare faller bort från ett segment om de inte är kvalificerade för någon av sina egenskaper inom [!DNL TTL] intervallet. Om du t.ex. har ett segment med en radie på 30 dagar [!DNL TTL], kommer användaren att lämna det segmentet om han/hon inte är berättigad att utnyttja erbjudandet igen inom 30 dagar.

![](assets/ttl-explained.png)

## [!DNL TTL] och segmentförnyelse

Återställer och användaren stannar kvar i ett segment om de kvalificerar sig för segmentets egenskap inom [!DNL TTL] [!DNL TTL] perioden. Eftersom de flesta segment innehåller flera egenskaper med sina egna [!DNL TTL] intervall, kan användaren också stanna kvar i ett segment och återställa [!DNL TTL] intervallet, så länge som de kvalificerar sig för eventuella egenskaper som är kopplade till segmentet.

Exempel: Du har segment 1 bestående av grupp A (30 dagar [!DNL TTL]) och fack B (15 dagar [!DNL TTL]). Om en besökare bara kvalificerar sig för varje egenskap en gång, visar bilden nedan förnyelseprocessen [!DNL TTL] och den totala längden i segmentet.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTL:er är oberoende av TTL-inställningar från tredje part

Kom ihåg att [!DNL TTL] uppsättningen på din [!DNL Audience Manager] pixel fungerar oberoende av uppsättningen [!DNL TTL] på andra pixlar som används av tredje part ([!DNL DSP]s, annonsnätverk osv.).

>[!MORELIKETHIS]
>
>* [Ange ett förfallointervall för trait](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

