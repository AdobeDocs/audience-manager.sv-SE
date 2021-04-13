---
description: Rapporten Segmenttrender returnerar data om visningar och klickfrekvenser för mappade och omappade segment över tiden. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Jämför trender och volym för valda mätvärden för att få en bättre bild av hur era målgrupper beter sig över tid.
seo-description: Rapporten Segmenttrender returnerar data om visningar och klickfrekvenser för mappade och omappade segment över tiden. Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning. Jämför trender och volym för valda mätvärden för att få en bättre bild av hur era målgrupper beter sig över tid.
seo-title: Trendrapport för segment
solution: Audience Manager
title: Trendrapport för segment
uuid: f84e8d0a-74e5-430c-b61c-efb696faee93
feature: Audience Optimization-rapporter
exl-id: 1fdca05a-b661-4875-88d7-b0893e2ca08f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# Trendrapport för segment{#segment-trend-report}

Rapporten Segmenttrender returnerar data om visningar och klickfrekvenser för mappade och omappade segment över tiden.

Ett mappat segment är ett segment som du skapar och skickar till ett mål för målanpassning. Ett omappat segment är ett segment som du har skapat men inte skickat till ett mål för målgruppsanpassning.

Jämför trender och volym för valda mätvärden för att få en bättre bild av hur era målgrupper beter sig över tid.

## Användningsexempel {#use-cases}

Använd [!UICONTROL Segment Trend]-rapporten för att validera ett segments prestanda över tid och för att identifiera trender baserat på höga prestanda eller skalbarhet.

Med den här rapporten kan du förstå vilka av dina webbegenskaper som visar en ökning av antalet fel och felsökning efter behov. Den här rapporten är nästa steg efter att du har identifierat en viss målgrupp i [!UICONTROL Segment Performance]-rapporten, för att säkerställa att de starka eller dåliga prestanda du såg på fliken [!UICONTROL Segment Performance] är konsekventa över tiden.

## Använda segmenttrendrapporten {#using-the-report}

Växla mellan **[!UICONTROL Mapped]** och **[!UICONTROL Unmapped]** för att markera segment som är mappade till ett mål eller inte. Välj **[!UICONTROL All]** om du vill inkludera alla dina segment i rapporten.

Justera bakåtfönstret med reglaget **[!UICONTROL Date Through]**.

Klicka på något av segmenten under reglaget **[!UICONTROL Date Through]** för att visa alternativet att bara behålla det segmentet i rapporten eller exkludera det.

Använd listrutan **[!UICONTROL Line Item]** för att välja de egenskaper i portföljen som du vill returnera information för.

I listrutan **[!UICONTROL Segment Data Source]** markerar du datakällorna som innehåller de segment som du vill se i rapporten.

Använd listrutan **[!UICONTROL Segment]** för att välja vilka segment du vill se i rapporten.

>[!IMPORTANT]
>
>När du aktiverar [!UICONTROL Audience Optimization for Publishers] måste du inkludera beskrivande metadata för [!UICONTROL Line Item] ID:n, enligt beskrivningen i steg 3 av [Importera Google Ad Manager-datafiler (tidigare DFP) till Audience Manager](../../../reporting/audience-optimization-reports/aor-publishers/import-dfp.md). Genom att göra detta försäkrar du dig om att rapporten anger webbegenskapen som [!UICONTROL Line Item] i stället för [!UICONTROL Line Item]-ID:t.

## Tolka resultaten {#interpreting-results}

Rapporten [!UICONTROL Segment Trend] returnerar data i ett linjediagram endast för 14-dagarsintervall. I det här exemplet visar rapporten intrycks- och klickningstrender för en uppsättning mappade och omappade segment.

Håll pekaren över en linje för att få mer information om den aktuella segmenttrenden. Se beskrivningarna för ytterligare information i tabellen nedan.

![](assets/publisher_segment_trend.png)

<table id="table_AFE2540583C34835B04584693ADFD26A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Objekt </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment</span> </p> </td> 
   <td colname="col2"> <p>Det alfanumeriska namn som du tilldelade det här segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment-ID</span> </p> </td> 
   <td colname="col2"> <p>Det unika ID:t för det här segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Radartikel</span> </p> </td> 
   <td colname="col2"> <p>Den webbegenskap som du ser den här rapporten för. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Klickningar</span> </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har klickat på objekt i din webbegenskap. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Impressions</span> </p> </td> 
   <td colname="col2"> <p>Antalet gånger som medlemmar i den här egenskapen har exponerats för ditt lager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> CTR</span> </p> </td> 
   <td colname="col2"> <p>Klickfrekvens. Det här måttet visar hur många procent av intrycken som ska följas av klickningar. Dela upp klickningarna med avtryck för att få fram mätvärdet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Segment Uniques</span> </p> </td> 
   <td colname="col2"> <p>Antalet segmentmedlemmar under de senaste 30 dagarna. </p> </td> 
  </tr> 
 </tbody> 
</table>
