---
description: Med alternativet Konvertering över flera kanaler i rapporten Audience Optimization kan du attribuera offlinekonverteringar till serverade onlinevisningar eller -klick.
seo-description: Med alternativet Konvertering över flera kanaler i rapporten Audience Optimization kan du attribuera offlinekonverteringar till serverade onlinevisningar eller -klick.
seo-title: Konvertering över flera kanaler
solution: Audience Manager
title: Konvertering över flera kanaler
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Konvertering över flera kanaler{#cross-channel-conversion}

Med alternativet Konvertering över flera kanaler i rapporten Audience Optimization kan du attribuera offlinekonverteringar till serverade onlinevisningar eller -klick.

I [!UICONTROL Cross Channel Conversion] rapporterna kombineras resultat från [!DNL DoubleClick Campaign Manager] DCM-plattformen med [!DNL Audience Manager] konverteringsegenskaper. På så sätt kan du länka offlinekonverteringar till online-visningar eller -klick.

Du kan använda [!UICONTROL Cross Channel Conversion] för [Segmentprestanda](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) - och [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md) -rapporter.

Om du vill visa [!UICONTROL Cross Channel Conversion] rapporter markerar du **[!UICONTROL AAM+DCM]** objektet i **[!UICONTROL Platform]** listrutan.

I följande tabell visas viktiga aspekter när du konfigurerar [!UICONTROL Cross Channel Conversion]:

<table id="table_62590B4AB7624B619EC9AA8FF89722C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Övervägande </th> 
   <th class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col01"> <p>Minsta antal konverteringsegenskaper </p> </td> 
   <td colname="col1"> <p>Minst en konverteringsegenskap måste tilldelas till en datakälla för att rapporterna för <span class="wintitle"> kanalkonvertering</span> ska kunna köras. Mer information om egenskaper finns i <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Grundläggande information om traits</a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <p>Maximalt antal konverteringsegenskaper </p> </td> 
   <td colname="col1"> <p>Rapporterna innehåller <i>högst</i> 50 konverteringsegenskaper från användaren. Om du når det högsta värdet används de första 50 konverteringsegenskaperna baserat på trait-ID, i stigande ordning. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Attributionsfönster </p> </td> 
   <td> <p> <b><span class="uicontrol"> AAM+DCM</span></b> -attribueringsfönstret är 14 dagar, vilket innebär att endast konverteringsegenskaper som visats under de senaste två veckorna beaktas. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Senaste beröringsmetod </p> </td> 
   <td> <p>Det kreativa som användaren såg senast innan konverteringen gjordes är det som tilldelats konverteringen. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Klick jämfört med visningar </p> </td> 
   <td> <p>Ett klick har företräde framför ett intryck när attribuering bestäms om de inträffar samtidigt. På en sida där flera kreatörer visas tilldelas den som du klickar på konverteringen. </p> </td> 
  </tr> 
  <tr> 
   <td> <p>Dataveriod </p> </td> 
   <td> <p>Rapporterna beräknas alltid för data som var tillgängliga föregående dag. </p> </td> 
  </tr> 
 </tbody> 
</table>
