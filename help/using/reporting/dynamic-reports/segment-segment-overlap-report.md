---
description: Returnerar data om hur många unika användare som delas mellan era segment.
seo-description: Returnerar data om hur många unika användare som delas mellan era segment.
seo-title: Överlappningsrapport för segment-till-segment
solution: Audience Manager
title: Överlappningsrapport för segment-till-segment
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: overlap reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---


# Överlappningsrapport för segment-till-segment{#segment-to-segment-overlap-report}

Returnerar data om hur många unika användare som delas mellan era segment.

>[!NOTE]
>
>Överlappningsrapporterna i Audience Manager följer RBAC-principerna. Du kan bara se segment från datakällor som du har åtkomst till baserat på den [RBAC-användargrupp](/help/using/features/administration/administration-overview.md) som du tillhör.

<!-- 

c_segment_segment_overlap.xml

 -->

## Översikt

Rapporten kan vara till hjälp för dig [!UICONTROL Segment-to-Segment Overlap] :

* Identifiera segment med hög eller låg överlappning, beroende på dina behov. Med hög överlappning får ni en målgrupp, men färre unika besökare. Fällor med låg överlappning kan vara användbara för att nå en större, unik besökaruppsättning.
* Hitta oväntad överlappning och använd den informationen för att skapa nya högpresterande segment.

## Exempelrapport

Följande bild ger en översikt över [!UICONTROL Segment-to-Segment Overlap] rapporten på hög nivå.

>[!NOTE]
>
>Rapporten returnerar ett tomt fält när den jämför samma segment med sig själv. [!UICONTROL Segment-to-Segment Overlap]

![](assets/segment-to-segment-overlap.png)

## Detaljgranska enskilda datapunkter

Markera en enskild punkt om du vill visa datainformation i ett popup-fönster. Dina klickåtgärder uppdaterar automatiskt data som visas i rapporten.

## Segment-till-segment överlappar definierade data-popup-fält {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

Popup-fönstret för [!UICONTROL Segment-to-Segment Overlap] rapporten innehåller måtten nedan. Observera att tabellens unika mätvärden representerar *realtidsanvändare*.

| Mått | Beskrivning |
|---|---|
| **[!UICONTROL Base Segment ID]** | Unikt numeriskt ID för det segment som visas i rapportresultatet. Visas som rad-ID för segmentet. |
| **[!UICONTROL Base Segment Name]** | Namnet på det segment som visas i rapportresultatraden. |
| **[!UICONTROL Overlapping Segment ID]** | Unikt numeriskt ID för det segment som du valde när rapporten kördes. Visas som kolumn-ID för segmentet. |
| **[!UICONTROL Overlapping Segment Name]** | Namnet på det segment du valde när rapporten kördes. Visas i rapportresultatkolumnen. |
| **[!UICONTROL Base Segment Uniques]** | Antalet unika besökare i ditt bassegment. |
| **[!UICONTROL Base Segment Uniques]** | Antalet unika besökare i det överlappande segmentet. |
| **[!UICONTROL Overlapping Uniques]** | Antalet unika besökare som delas mellan jämförda segment. |
| **[!UICONTROL Overlap %]** | För att få överlappningen % använder Audience Manager följande formel: Överlappande uniques / (Base Segment Uniques + Overlapping Segment Uniques - Overlapping Uniques) |



>[!MORELIKETHIS]
>
>* [Filtrera rapportresultat med datareglagen](../../reporting/dynamic-reports/data-sliders.md)
>* [Former, färger och storlekar som används i interaktiva rapporter](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ikoner och verktyg för rapporter förklaras](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Överlappningsrapporter: Uppdatera schema och minsta segmentstorlek](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datainsamling och felfrekvens i rapporter från markerade Audience Manager..](../../reporting/report-sampling.md)
>* [CSV-filer för överlappningsrapporter](../../reporting/dynamic-reports/overlap-csv-files.md)