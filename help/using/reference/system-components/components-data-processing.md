---
description: Komponenterna för databehandling är Hadoop, Snowflake, SOLR och Tableau.
seo-description: Komponenterna för databehandling är Hadoop, Snowflake, SOLR och Tableau.
seo-title: Databearbetningskomponenter
solution: Audience Manager
title: Databearbetningskomponenter
uuid: d458d869-7a23-4016-871d-0b994cf4af06
feature: 'Systemkomponenter '
exl-id: 9ff2b82b-aad0-4d24-96e6-230763019311
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 4%

---

# Databearbetningskomponenter{#data-processing-components}

Komponenterna för databehandling är Hadoop, Snowflake, SOLR och Tableau.

<!-- 

c_comproc.xml

 -->

Audience Manager använder följande komponenter för att bearbeta data:

## Hadoop {#hadoop}

I [!DNL Audience Manager] är Hadoopet huvuddatabasen som innehåller allt [!DNL Audience Manager] vet om en användare. När till exempel [profilcacheservrarna](../../reference/system-components/components-data-collection.md) skapar loggfiler som innehåller data om dina användare, skickas dessa data till Hadoopet för lagring. Andra viktiga element inom Hadoopet är:

* **Hive:** En data warehouse för Hadoop. Hive hanterar ad hoc-frågor till data som lagras i Hadoopet.

* **HBase:** En mycket stor Hadoopen databas. Den behandlar och hanterar inkommande och utgående data, varumärkesregler, algoritmisk modelleringsinformation och utför många andra funktioner som rör lagring och flyttning av data till olika system.

Kunderna har inte direktåtkomst till dessa system. Men kunderna arbetar med dem indirekt eftersom de här komponenterna lagrar viktiga data om webbplatsens besökare.

## Snowflake {#snowflake}

[Snowflakeis ](https://www.snowflake.net/) är en enorm molndatabas. Den tillhandahåller data till många av kontrollpanelens diagram och tillhörande textrutor som visar ändringen i procent för varje objekt i diagrammet. Om du använder [!DNL Audience Manager] och tittar på kontrollpanelsrapporterna interagerar du med data från [!UICONTROL Snowflake].



![](assets/dashboardreport.png)

Det här är inte på något sätt en heltäckande lista, men en del vanliga instrumentpaneler rapporterar att [!UICONTROL Snowflake] ansvarar för:

* [Daglig rapport över trait-variationer](/help/using/reporting/audience-optimization-reports/daily-trait-variation-report.md)
* Alla överlappningsrapporter (se avsnittet [Interaktiva rapporter](/help/using/reporting/dynamic-reports/dynamic-reports.md) för information om varje överlappningsrapport).
* [Rapport om oanvända signaler](/help/using/reporting/dynamic-reports/unused-signals.md)

## SOLR {#solr}

SOLR är en databas och ett serversystem med öppen källkod från Apache. Det ger robusta och snabba sökfunktioner över våra stora datauppsättningar. Som [!DNL Audience Manager]-kund kan du se hur SOLR fungerar när du skapar segment. Den tillhandahåller data till [!UICONTROL Estimated Historic Segment Size]-rapporten. SOLR är idealiskt för den här rollen på grund av dess snabbhet. SOLR kan till exempel uppdatera historikdata när du skapar regler och lägger till nya egenskaper i ett segment.



![](assets/audsize.png)

## Tableau {#tableau}

[!DNL Audience Manager] använder  [](https://www.tableausoftware.com/) tabelldata för automatisk visning i  [interaktiva ](../../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) rapporter och  [Audience Optimization-rapporter](../../reporting/audience-optimization-reports/audience-optimization-reports.md). De interaktiva rapporterna visar prestanda och överlappar data för egenskaper och segment. I stället för att använda siffror ordnade i kolumner och rader, returnerar de data med olika former, färger och storlekar. Dessutom kan du välja enskilda eller grupper av datapunkter och gå ned i rapportresultaten för mer information. Dessa visualiseringstekniker och rapportinteraktivitet gör stora mängder numeriska data lättare att förstå.



![](assets/advertiser_analytics.png)
