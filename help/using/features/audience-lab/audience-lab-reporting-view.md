---
description: Rapporteringsavsnittet för testgruppen returnerar information om konverteringar av testgrupper, vilket gör det enkelt att jämföra testsegmentets effekt. Det finns många filter och dimensioner för datavisualisering.
seo-description: Rapporteringsavsnittet för testgruppen returnerar information om konverteringar av testgrupper, vilket gör det enkelt att jämföra testsegmentets effekt. Det finns många filter och dimensioner för datavisualisering.
seo-title: Testgruppsrapporter
solution: Audience Manager
title: Testgruppsrapporter
uuid: 21303c3e-4c05-4728-a759-96c2a1d99b69
feature: 'Audience Lab '
exl-id: 5d959002-e904-44df-87e6-e4c85838b076
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 3%

---

# Testgruppsrapporter {#test-group-reporting}

Rapporteringsavsnittet för testgruppen returnerar information om konverteringar av testgrupper, vilket gör det enkelt att jämföra testsegmentets effekt. Det finns många filter och dimensioner för datavisualisering.

[!UICONTROL Audience Lab] returnerar detaljerad rapportinformation för de testsegment som du har skapat och gör att du kan spara rapportdata som  [!DNL CSV] filer. Du kan välja mellan **[!UICONTROL Aggregate Reporting]** och **[!UICONTROL Trend Reporting]**.

**[!UICONTROL Aggregate Reporting]** returnerar de absoluta talen för testsegmenten. **[!UICONTROL Trend Reporting]** returnerar ett diagram över trenden  *under en viss period*. Med fyra flikar kan du anpassa rapporterna:

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Omräkningshastighet för populationer</span></b> </p> </td> 
   <td colname="col2"> <p>Returnerar procentandelen enheter som tillhör ett visst testsegment, som har konverterats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Konverterare</span></b> </p> </td> 
   <td colname="col2"> <p>Returnerar antalet enheter som har visat de konverteringsegenskaper som valts i testgrupperna. <a href="https://helpx.adobe.com/audience-manager/kt/using/creating-conversion-traits-feature-video-use.html" format="https" scope="external"> I den här </a> videon får du lära dig hur du skapar konverteringsegenskaper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Totalt antal konverteringar</span></b> </p> </td> 
   <td colname="col2"> <p>Returnerar antalet konverteringar som genereras av testsegmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Testa segmentpopulationer</span></b> </p> </td> 
   <td colname="col2"> <p>Returnerar antalet enheter som tillhör testsegmenten. Växla mellan <b><span class="uicontrol"> Total population</span></b> eller <b><span class="uicontrol"> Realtidspopulation</span></b>. Skillnaden förklaras i <a href="../../faq/faq-reporting.md"> Vanliga frågor om rapportering</a>. </p> </td>
  </tr>
 </tbody>
</table>

Du kan välja en specifik konverteringsegenskap som rapporten ska genereras för, eller så kan du välja alla egenskaper tillsammans. Du kan definiera ett datumintervall för vilket informationen ska returneras och exportera rapporten som en [!DNL CSV]-fil.

>[!NOTE]
>
>* Rapportering för en testgrupp fylls i dagen efter startdatumet.
>* En konvertering räknas bara för en enhet efter startdatumet för en provning och efter att enheten har lagts till i ett testsegment. Om en konvertering inträffar för den enheten innan den tilldelas en testgrupp räknas inte konverteringen.


Ett returnerat **[!UICONTROL Aggregate Reporting]**-diagram kan se ut så här:

![](assets/aggregate-reporting.PNG)

Ett returnerat **[!UICONTROL Trend Reporting]**-diagram kan se ut som det nedan. Markera **[!UICONTROL Normalized]** i kryssrutan om du vill ignorera de absoluta talen och helt enkelt fokusera på trenderna för testsegmenten.

![](assets/trend-reporting.PNG)
