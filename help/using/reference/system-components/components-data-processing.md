---
description: Komponenterna för databehandling är bland annat Hadoop, Snowflake, SOLR och Tableau.
seo-description: Komponenterna för databehandling är bland annat Hadoop, Snowflake, SOLR och Tableau.
seo-title: Databearbetningskomponenter
solution: Audience Manager
title: Databearbetningskomponenter
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 0%

---


# Databearbetningskomponenter{#data-processing-components}

Komponenterna för databehandling är bland annat Hadoop, Snowflake, SOLR och Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager använder följande komponenter för att bearbeta data:

## Hadoop {#hadoop}

Hadoop [!DNL Audience Manager]är i sin tur huvuddatabasen som innehåller allt [!DNL Audience Manager] om en användare. När till exempel [profilcacheservrarna](../../reference/system-components/components-data-collection.md) skapar loggfiler som innehåller data om dina användare, skickas dessa data till Hadoop för lagring. Andra viktiga Hadoop-element är:

* **Hive:** data warehouse för Hadoop. Hive hanterar ad hoc-frågor till data som lagras i Hadoop.

* **HBase:** En mycket stor Hadoop-databas. Den behandlar och hanterar inkommande och utgående data, varumärkesregler, algoritmisk modelleringsinformation och utför många andra funktioner som rör lagring och flyttning av data till olika system.

Kunderna har inte direktåtkomst till dessa system. Men kunderna arbetar med dem indirekt eftersom de här komponenterna lagrar viktiga data om webbplatsens besökare.

## Snöflinga {#snowflake}

[Snowflake](https://www.snowflake.net/) är en enorm molndatabas. Den tillhandahåller data till många av kontrollpanelens diagram och tillhörande textrutor som visar ändringen i procent för varje objekt i diagrammet. Om du använder [!DNL Audience Manager] och tittar på kontrollpanelsrapporterna interagerar du med data från [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Detta är inte på något sätt en heltäckande lista, men några vanliga kontrollpanelrapporter som [!UICONTROL Snowflake] ansvarar för är:

* [Rapport över variationer för daglig trait](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Alla överlappande rapporter (se avsnittet [Interaktiva rapporter](/help/using/reporting/dynamic-reports/dynamic-reports.md) för information om varje överlappningsrapport).
* [Rapport om oanvända signaler](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR är en databas och ett serversystem med öppen källkod från Apache. Det ger robusta och snabba sökfunktioner över våra stora datauppsättningar. Som [!DNL Audience Manager] kund kan ni se hur SOLR fungerar när ni bygger segment. Den tillhandahåller data till [!UICONTROL Estimated Historic Segment Size] rapporten. SOLR är idealiskt för den här rollen på grund av dess snabbhet. SOLR kan till exempel uppdatera historikdata när du skapar regler och lägger till nya egenskaper i ett segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] använder [Tableau](https://www.tableausoftware.com/) för att visa data i [interaktiva rapporter](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) och [målgruppsoptimeringsrapporter](../../reporting/audience-optimization-reports/audience-optimization-reports.md). De interaktiva rapporterna visar prestanda och överlappar data för egenskaper och segment. I stället för att använda siffror ordnade i kolumner och rader, returnerar de data med olika former, färger och storlekar. Dessutom kan du välja enskilda eller grupper av datapunkter och gå ned i rapportresultaten för mer information. Dessa visualiseringstekniker och rapportinteraktivitet gör stora mängder numeriska data lättare att förstå.



![](assets/advertiser_analytics.png)

