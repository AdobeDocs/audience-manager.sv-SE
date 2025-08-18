---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Reporting
solution: Audience Manager
title: Rapportering om prediktiva målgrupper
feature: Algorithmic Models
exl-id: 43a4272c-d9be-47f6-9b81-15472b0366ab
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 2%

---

# Rapportering om prediktiva målgrupper

När du har sparat en [!UICONTROL Predictive Audiences]-modell börjar Audience Manager utbilda den. Inom några timmar kommer den beräknade modellen att börja analysera målgrupper på [datainsamlingsservrarna](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=sv-SE#dcs-pcs). Rapporteringen blir tillgänglig följande dag.

Om du vill se resultatet av din [!UICONTROL Predictive Audiences]-klassificering går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** och klickar på modellen i listan.

Använd filteralternativen till vänster för att söka efter modellnamnet eller filtrera resultaten baserat på modelltyp.

![prediktiv-audiences-filter](assets/predictive-audiences-filter-models.png)

I modelltabellen visas följande information:

* **[!UICONTROL ID]**: Modell-ID:t identifierar unikt varje modell i ditt Audience Manager-konto.
* **[!UICONTROL Name]**: namnet som du angav när du skapade modellen;
* **[!UICONTROL Description]**: beskrivningen som du angav när du skapade modellen;
* **[!UICONTROL Model Type]**: typen för varje modell ([!UICONTROL Look-Alike Modeling] eller [!UICONTROL Predictive Audiences]);
* **[!UICONTROL Status]**: status för varje modell:
   * **[!UICONTROL Pending]**: modellen initieras och börjar producera resultat inom kort;
   * **[!UICONTROL Active]**: modellen körs och ger resultat;
   * **[!UICONTROL Warning]**: Det gick inte att skapa resultat för modellen på grund av otillräckliga data (dvs. låg baslinjepopulation, användarprofiler är inte rika);
   * **[!UICONTROL Error]**: Det gick inte att köra modellen. Kontakta Adobe.

## Modellöversiktsrapport{#model-report}

När du har valt en modell läses rapportsidan in. Högst upp på sidan ser du de fem största prediktiva segmenten, baserat på 1 dagars realtidsrealisering, som modellen har klassificerat målgruppen efter. Kategorin **[!UICONTROL Other]** innehåller resten av personerna, som inte ingick i de fem största prediktiva segmenten.

I Audience Manager visas både ett färgkodat ritdiagram och ett tidslinjediagram för din [!UICONTROL Predictive Audiences].

Om du klickar på personflikarna högst upp på sidan läggs de till eller tas bort från diagrammet och diagrammet.

Diagrammet visar en personbaserad uppdelning av målgruppen, medan diagrammet visar en dagars populationstrend för era prediktiva segment under de senaste sex dagarna.

Om modellstatusen är [!UICONTROL Pending], [!UICONTROL Warning] eller [!UICONTROL Error] visas modellstatusen i stället för diagrammen.

![smart-persona-report](assets/predictive-audiences-report.png)

I rapporttabellen visas följande information för varje [!UICONTROL Predictive Audiences]-segment.

1. **[!UICONTROL SEGMENT ID]**: Segment-ID för det automatiskt skapade segment som är associerat med varje persona.
1. **[!UICONTROL NAME]**: personnamnet;
1. **[!UICONTROL STATUS]**: statusen för [!UICONTROL Predictive Audiences]-segmentet:
   * **[!UICONTROL Succeeded]**: användare klassificeras i det här segmentet;
   * **[!UICONTROL Pending]**: segmentet initieras fortfarande;
   * **[!UICONTROL Insufficient Training Data]**: användare klassificeras inte i det här segmentet på grund av otillräckliga data. Den totala baslinjepopulationen är för låg och ger inte tillräckligt med data att lära sig av.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION]**: Antalet segmentrealiseringar för varje person under de senaste 24 timmarna.
1. **[!UICONTROL 1 DAY REAL TIME POPULATION %]**: Procentandelen segmentrealiseringar för varje person under de senaste 24 timmarna, av den totala modellpopulationen.

## Inflytelserika egenskaper{#influential-traits}

[!UICONTROL Influential Traits] är egenskaper som algoritmen [!UICONTROL Predictive Audiences] upptäckte vara de starkaste prediktorerna för att fastställa personklassificeringen för en besökare.

Deras tecken anger om närvaron av egenskapen ökar (+) eller minskar (-) sannolikheten för användaren som tillhör den valda personen.

Om du vill visa de inflytelserika egenskaperna för alla dina profiler klickar du på [!UICONTROL View All Influential Traits].

Fönstret [!UICONTROL Influential Traits] visar följande information för varje profil i den valda modellen:

![Inflytelserika egenskaper](assets/predictive-audiences-influential-traits.png)

1. **[!UICONTROL TRAIT ID]**: ID:t för varje inflytelserik egenskap för den valda personen,
1. **[!UICONTROL NAME]**: namnet på varje inflytelserik egenskap för den valda personen;
1. **[!UICONTROL DESCRIPTION]**: Beskrivning av varje inflytelserik egenskap för den valda personen.
1. **[!UICONTROL WEIGHT]**: vikten för varje inflytelserik egenskap för den valda personen. [!UICONTROL Influential Traits] sorteras som standard efter vikt i fallande ordning.  Viktens värde anger deras prediktiva effekt. Tecknet anger om närvaron av egenskapen ökar (+) eller minskar (-) sannolikheten för att tillhöra en person.
1. **[!UICONTROL 30 DAY REAL TIME POPULATION]**: Antalet unika trait-realisationer för varje inflytelserik egenskap för den valda personen under de senaste 30 dagarna.
