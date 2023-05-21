---
description: Returnerar data om hur många unika användare som delas mellan era segment.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Överlappningsrapport för segment till segment
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 10%

---

# Överlappningsrapport för segment till segment{#segment-to-segment-overlap-report}

Returnerar data om hur många unika användare som delas mellan era segment.

>[!NOTE]
>
>Överlappningsrapporterna i Audience Manager följer RBAC-principerna. Du kan bara se segment från datakällor som du har åtkomst till baserat på [RBAC-användargrupp](/help/using/features/administration/administration-overview.md) som du tillhör.

<!-- 

c_segment_segment_overlap.xml

 -->

## Översikt

The [!UICONTROL Segment-to-Segment Overlap] kan hjälpa dig med

* Identifiera segment med hög eller låg överlappning, beroende på dina behov. Med hög överlappning får ni en målgrupp, men färre unika besökare. Fällor med låg överlappning kan vara användbara för att nå en större, unik besökaruppsättning.
* Hitta oväntad överlappning och använd den informationen för att skapa nya högpresterande segment.

## Exempelrapport

Följande bild ger en översikt på hög nivå över [!UICONTROL Segment-to-Segment Overlap] rapport.

>[!NOTE]
>
>The [!UICONTROL Segment-to-Segment Overlap] rapporten returnerar ett tomt fält när den jämför samma segment med sig själv.

![](assets/segment-to-segment-overlap.png)

## Detaljgranska enskilda datapunkter

Markera en enskild punkt om du vill visa datainformation i ett popup-fönster. Dina klickåtgärder uppdaterar automatiskt data som visas i rapporten.

## Segment-till-segment överlappar definierade data-popup-fält {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

Popup för [!UICONTROL Segment-to-Segment Overlap] rapporten innehåller måtten nedan. Observera att det unika måttet i tabellen representerar *användare i realtid*.

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
>* [Filtrera rapportresultat med datareglage](../../reporting/dynamic-reports/data-sliders.md)
>* [Former, färger och storlekar som används i interaktiva rapporter](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Ikoner och verktyg för rapporter förklaras](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Överlappningsrapporter: Uppdatera schema och minsta segmentstorlek](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datainsamling och felfrekvens i valda rapporter för Audience Manager...](../../reporting/report-sampling.md)
>* [CSV-filer för överlappningsrapporter](../../reporting/dynamic-reports/overlap-csv-files.md)

