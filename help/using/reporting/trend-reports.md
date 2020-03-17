---
description: En trendrapport returnerar trenddata för egenskaper och segment.
seo-description: En trendrapport returnerar trenddata för egenskaper och segment.
seo-title: Trendrapporter
solution: Audience Manager
title: Trendrapporter
uuid: bedbe7d4-7cbb-4403-9104-312f9230aea1
translation-type: tm+mt
source-git-commit: 18bb00d494d44d7028dcc51dcb2fc57b23420142

---


# Trendrapporter{#trend-reports}

En trendrapport returnerar trenddata för egenskaper och segment.

## Översikt {#trend-report-overview}

<!-- 

c_trend_reports.xml

 -->

[!DNL Audience Manager] använder [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) för att utöka användargruppsbehörigheter till [!UICONTROL Trend] rapporter. Användarna kan bara se de egenskaper och segment i rapporter som de har behörighet att visa. [!UICONTROL RBAC] kan ni styra vilka rapportdata som interna team kan visa.

En byrå som till exempel hanterar olika annonsörkonton kan konfigurera användargruppbehörigheter så att ett team som hanterar Advertiser A:s konto inte kan se annonsörens B:s rapportdata.

Kör en [!UICONTROL Trend] rapport när du behöver:

* Granska trenddata efter egenskaper och segment.
* Spåra trender med 1, 7, 14, 30, 60 och 90 dagars intervall.
* Jämför trender för egenskaper och segment över tid.
* Identifiera starka eller dåliga prestationsegenskaper och segment.
* Exportera data (.csv-format) för vidare analys och delning.

Följande bild ger en översikt på hög nivå över viktiga element i [!UICONTROL Trend] rapporten.

![](assets/trend_reports.png)

1. Konfigurera följande alternativ:

   **Typ av rapportering:** Välj önskad rapporttyp (Trait (Trait) eller Segment).

   **Datumintervall:** Ange datumintervallet för rapporten (startdatum och slutdatum).

   **Visningsintervall:** Ange visningsintervall (1, 7, 14, 30, 60 och 90 dagars intervall).

2. Sök efter ett varumärke eller segment efter namn eller ID.
3. Dra och släpp de egenskaper eller segment som du vill rapportera i mapplistan till [!UICONTROL Selections] panelen till höger.
4. Generera rapporten som ska visas i grafiskt format eller exportera rapporten till CSV-format.

## Kör en trendrapport {#run-trend-report}

I den här proceduren beskrivs hur du kör en [!UICONTROL Trend] rapport.

<!-- 

t_working_with_trend_reports.xml

 -->

1. Klicka på på **[!UICONTROL Analytics]** kontrollpanelen **[!UICONTROL Trend Reports]**.
1. Välj önskad typ i **[!UICONTROL Report Type]** listrutan: **[!UICONTROL Trait]** eller **[!UICONTROL Segment]**.
1. Klicka på datumrutorna för att visa en kalender och välj sedan start- och slutdatum för rapporten.
1. Ange visningsintervall: med 1, 7, 14, 30, 60 eller 90 dagar.
1. Sök efter ett varumärke eller segment efter namn eller ID.
1. Dra och släpp de egenskaper eller segment som du vill rapportera i mapplistan till [!UICONTROL Selections] panelen till höger.

   För bästa prestanda ska du köra en [!UICONTROL Trend] rapport på färre än 20 egenskaper eller segment åt gången.
1. Klicka **[!UICONTROL Graph Traits]** eller **[!UICONTROL Graph Segments]**, beroende på vilken typ av rapport du visar (Traits eller Segments).

   Dessa alternativ ignorerar alla mappar och diagram endast individuellt markerade egenskaper eller segment.

   eller

   Klicka **[!UICONTROL Export to CSV]** för att exportera trait- eller segmentdata och alla mappar i CSV-format för vidare analys och delning. Detta exporterar [!UICONTROL Unique Trait Realizations], [!UICONTROL Total Trait Realizations]och [!UICONTROL Total Trait Population] för alla dagintervall.

   >[!NOTE]
   >
   >[!UICONTROL Total Trait Realizations] beräknas [!UICONTROL Rule-based Traits] endast för.

1. (Valfritt) För musen över enskilda egenskaper eller segment för att visa antalet besök och datumet för varje datapunkt.

   Du kan klicka på kolumnrubrikerna i tabellen om du vill sortera resultaten i stigande eller fallande ordning.

För [!UICONTROL Trended Trait] rapporter visar nollor att det inte [!DNL Audience Manager] samlats in data för den dagen. Tomma poster anger att egenskapen inte fanns. I följande exempel visas exempel på båda typerna av poster:

![](assets/trended_data.png)
