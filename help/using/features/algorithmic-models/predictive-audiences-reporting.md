---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Rapportering i Predictive Audiences
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 6%

---


# Rapportering i Predictive Audiences

När du har sparat en [!UICONTROL Predictive Audiences] modell börjar Audience Manager utbilda den. Inom några timmar kommer den beräknade modellen att börja analysera målgrupper på [datainsamlingsservrarna](https://docs.adobe.com/content/help/en/audience-manager/user-guide/reference/system-components/components-data-collection.html#dcs-pcs). Rapporteringen blir tillgänglig följande dag.

Om du vill se resultatet av din [!UICONTROL Predictive Audiences] klassificering går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** och klickar på modellen i listan.

Använd filteralternativen till vänster för att söka efter modellnamnet eller filtrera resultaten baserat på modelltyp.

![prediktiv-audiences-filter](assets/predictive-audiences-filter-models.png)

I modelltabellen visas följande information:

* **[!UICONTROL ID]**: Modell-ID som unikt identifierar varje modell i ditt Audience Manager-konto.
* **[!UICONTROL Name]**: namnet som du angav i steget för att skapa modellen,
* **[!UICONTROL Description]**: Den beskrivning som du angav i steget för att skapa modellen.
* **[!UICONTROL Model Type]**: Typ av modell ([!UICONTROL Look-Alike Modeling] eller [!UICONTROL Predictive Audiences]).
* **[!UICONTROL Status]**: Status för varje modell:
   * **[!UICONTROL Pending]**: Modellen initieras och börjar producera resultat inom kort.
   * **[!UICONTROL Active]**: Modellen fungerar bra och ger resultat.
   * **[!UICONTROL Warning]**: Modellen kunde inte ge några resultat på grund av otillräckliga data (dvs. låg baslinjespopulation är användarprofilerna inte tillräckliga).
   * **[!UICONTROL Error]**: det gick inte att köra modellen. Kontakta din Adobe-representant.

## Modellöversiktsrapport{#model-report}

När du har valt en modell läses rapportsidan in. Högst upp på sidan ser du de fem största prediktiva segmenten, baserat på 1 dagars realtidsrealisering, som modellen har klassificerat målgruppen efter. I **[!UICONTROL Other]** kategorin ingår resten av personerna, som inte ingick i de fem största prediktiva segmenten.

I Audience Manager visas både ett färgkodat ritdiagram och ett tidslinjediagram för ditt [!UICONTROL Predictive Audiences].

Om du klickar på personflikarna högst upp på sidan läggs de till eller tas bort från diagrammet och diagrammet.

Diagrammet visar en personbaserad uppdelning av målgruppen, medan diagrammet visar en dagars populationstrend för era prediktiva segment under de senaste sex dagarna.

Om modellstatusen är [!UICONTROL Pending], [!UICONTROL Warning]eller [!UICONTROL Error]visas modellstatusen i stället för diagrammen.

![smart-persona-rapport](assets/predictive-audiences-report.png)

I rapporttabellen visas följande information för varje [!UICONTROL Predictive Audiences] segment.

1. **[!UICONTROL SEGMENT ID]**: Segmentets-ID för det automatiskt skapade segment som är kopplat till varje person.
1. **[!UICONTROL NAME]**: personnamnet,
1. **[!UICONTROL STATUS]**: Status för [!UICONTROL Predictive Audiences] segmentet:
   * **[!UICONTROL Succeeded]**: användarna klassificeras i detta segment,
   * **[!UICONTROL Pending]**: segmentet fortfarande initieras,
   * **[!UICONTROL Insufficient Training Data]**: på grund av otillräckliga data delas användarna inte in i det här segmentet. Den totala baslinjepopulationen är för låg och ger inte tillräckligt med data för att lära sig av den.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Antalet segmentimplementeringar för varje person under de senaste 24 timmarna.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Procentandel segmentimplementeringar för varje person under de senaste 24 timmarna, av den totala modellpopulationen.

## Influentiella egenskaper{#influential-traits}

[!UICONTROL Influential Traits] är egenskaper som algoritmen har visat sig vara de starkaste prediktorerna för att fastställa en besökares personklassificering. [!UICONTROL Predictive Audiences]

Deras tecken anger om närvaron av egenskapen ökar (+) eller minskar (-) sannolikheten för användaren som tillhör den valda personen.

Om du vill visa de inflytelserika egenskaperna för alla dina profiler klickar du på [!UICONTROL View All Influential Traits].

I [!UICONTROL Influential Traits] fönstret visas följande information för varje profil i den valda modellen:

![influential-traits](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: ID för varje inflytelserik egenskap för den valda personen.
1. **[!UICONTROL NAME]**: Namnet på varje inflytelserik egenskap för den valda personen.
1. **[!UICONTROL DESCRIPTION]**: En beskrivning av varje inflytelserik egenskap för den valda personen.
1. **[!UICONTROL WEIGHT]**: vikten för varje inflytelserik egenskap för den valda personen. [!UICONTROL Influential Traits] sorteras som standard efter vikt i fallande ordning.  Viktarnas värde anger deras prediktiva effekt. Tecknet anger om närvaron av egenskapen ökar (+) eller minskar (-) sannolikheten för att tillhöra en person.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: antalet unika anpassade implementeringar för varje inflytelserik egenskap för den valda personen under de senaste 30 dagarna.
