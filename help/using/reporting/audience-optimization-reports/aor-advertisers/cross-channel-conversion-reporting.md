---
description: Med alternativet Konvertering över flera kanaler i Audience Optimization-rapporterna kan du attribuera offlinekonverteringar till serverade onlinevisningar eller -klick.
seo-description: The Cross Channel Conversion option in the Audience Optimization reports allows you to attribute offline conversions to served online impressions or clicks.
seo-title: Cross Channel Conversion
solution: Audience Manager
title: Konvertering över flera kanaler
uuid: 0fecec23-e502-490b-b7dd-47a3753a3f75
feature: Audience Optimization Reports
exl-id: 7412a43f-81b5-477e-8acf-89d6c8661f1e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 0%

---

# Konvertering över flera kanaler{#cross-channel-conversion}

Med alternativet Konvertering över flera kanaler i Audience Optimization-rapporterna kan du attribuera offlinekonverteringar till serverade onlinevisningar eller -klick.

Rapporterna från [!UICONTROL Cross Channel Conversion] kombinerar resultat från plattformen [!DNL Google Campaign Manager] med konverteringsegenskaperna [!DNL Audience Manager]. På så sätt kan du länka offlinekonverteringar till online-visningar eller -klick.

Du kan använda [!UICONTROL Cross Channel Conversion] för rapporterna [Segmentprestanda](../../../reporting/audience-optimization-reports/aor-advertisers/segment-performance.md) och [Optimal Frequency](../../../reporting/audience-optimization-reports/aor-advertisers/optimal-frequency.md).

Om du vill visa [!UICONTROL Cross Channel Conversion]-rapporterna markerar du **[!UICONTROL AAM + Ad Server Name]**-objektet i listrutan **[!UICONTROL Platform]**.

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
   <td colname="col1"> <p>Minst en konverteringsegenskap måste tilldelas till en datakälla för att <span class="wintitle">-kanalskonverteringsrapporterna </span> ska kunna köras. Mer information om egenskaper finns i <a href="../../../features/traits/create-onboarded-rule-based-traits.md"> Grundläggande information om traits</a>. </p> </td> 
  </tr>
  <tr> 
   <td> <p>Attributionsfönster </p> </td> 
   <td> <p> <b><span class="uicontrol"> Attributeringsfönstret för AAM+Google Campaign Manager</span></b> är 14 dagar, vilket innebär att endast konverteringsegenskaper som har visats under de senaste två veckorna beaktas. </p> </td> 
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
