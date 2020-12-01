---
description: Visa historikinformation för utgående batchjobb för en angiven mål- och tidsperiod.
seo-description: Visa historikinformation för utgående batchjobb för en angiven mål- och tidsperiod.
seo-title: Historik för utgående filer
solution: Audience Manager
title: Historik för utgående filer
uuid: 3621a59d-2bb5-4828-86f6-4c9bfa580764
feature: inbound and outbound reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 6%

---


# Historik för utgående filer {#outbound-file-history}

Visa historikinformation för utgående batchjobb för en angiven mål- och tidsperiod.

<!-- 

t_reports_outbound_history.xml

 -->

1. Klicka på **[!UICONTROL Analytics]** > **[!UICONTROL Outbound File History]**.

   ![Stegresultat](assets/outbound_history.png)

1. I rutan **[!UICONTROL Search for a Destination]** börjar du skriva och väljer önskat mål.
1. Ange start- och slutdatum för rapporten i rutan **[!UICONTROL Select a Date Range]** och klicka sedan på **[!UICONTROL Apply Date Filter]**.

   ![Stegresultat](assets/outbound_history_stats.png)

   Följande tabell innehåller information som motsvarar kolumnerna i rapporten:

<table id="table_93076D46AC50411395E72B9B987E99BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Linje </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Datasynkroniseringsfilnamn </td> 
   <td colname="col2"> <p>Lista över alla utgående filer som <span class="keyword"> Adobe</span> har genererats för det här målet och som har bearbetats tillsammans. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Slutförd </td> 
   <td colname="col2"> <p>Antal poster som har skickats från <span class="keyword"> Audience Manager</span> till målet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Misslyckades </td> 
   <td colname="col2"> <p>Antal poster som inte kunde skickas till målet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mottagna poster </td> 
   <td colname="col2"> <p>Totalt antal poster <span class="keyword"> Adobe</span> som genererats i filerna och som försökt skicka till målet. I de flesta fall bör detta vara det totala antalet slutförda och misslyckade filer. </p> </td> 
  </tr> 
 </tbody> 
</table>
