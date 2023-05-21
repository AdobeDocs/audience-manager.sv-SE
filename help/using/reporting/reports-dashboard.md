---
description: Använd instrumentpanelen för att visa information om dina partners unika besöksantal uppdelat efter egenskapstyper och segment för en angiven tidsram.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Kontrollpanel för rapporter
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---

# Kontrollpanel för rapporter {#reports-dashboard}

Använd kontrollpanelen för att visa information om dina unika besöksantal uppdelade efter egenskapstyper och segment för en angiven tidsram.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] användningsområden [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) för att utöka användargruppsbehörigheter till [!UICONTROL Dashboard]. Användarna kan bara se information på kontrollpanelen som de har behörighet att visa. [!UICONTROL RBAC] kan ni styra vilka rapportdata som interna team kan visa.

En byrå som till exempel hanterar olika annonsörkonton kan konfigurera användargruppbehörigheter så att ett team som hanterar Advertiser A:s konto inte kan se annonsörens B:s rapportdata. Den här instrumentpanelen kan användas för att felsöka dataleveransproblem.

Om du t.ex. märker en dip, eller spike, för totalt antal unika användare med en uppdelning av typ av unik användare (regelbaserad kontra ombord), har du en bättre startpunkt för att spåra ett potentiellt dataleveransproblem. Om du märker att antalet unika användare har ökat och att det finns unika användare ombord kan du gå till [!UICONTROL On-boarding Status] rapportera för att se om det uppstod ett problem med en inkommande fil.

**Så här öppnar du kontrollpanelen:**

1. Klicka på **[!UICONTROL Dashboard]**.
2. *Valfritt* Välj önskad tidsram från det sista rapporteringsdatumet i listrutan (7 dagar, 14 dagar (standard), 30 dagar eller 60 dagar).

   Beroende på vald period ändras deltavärdet i [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] och [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] paneler visar förändringen i unika besökare i publiken under perioden som slutar idag jämfört med föregående period av samma längd. Om du till exempel väljer 7 dagar, jämför deltat de unika besökarna under de föregående sju dagarna som slutar i dag med de unika besökarna för de sju dagar som slutade för sju dagar sedan.

   >[!NOTE]
   >
   >Du kan undersöka en deltaändring som verkar ovanlig genom att köra en [!UICONTROL Trend] rapport. Om du till exempel ser en ovanligt stor deltaförändring under de senaste sju dagarna kan du köra en [!UICONTROL Trend] rapportera för de senaste 14 dagarna (2 x 7) för att bättre förstå siffrorna.

   Beroende på den inloggade användarens behörigheter visas följande paneler:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Största egenskaper/De mest förändrade egenskaperna](../reporting/reports-dashboard.md#largest-traits)
   * [Största segment/mest ändrade segment](../reporting/reports-dashboard.md#most-changed-segments)

3. *Valfritt* Klicka **[!UICONTROL Normalize]** över ett diagram för att visa alla data i samma skala. Du kan också föra musen över en datapunkt för att se mer information.

## Partner Uniques {#partner-uniques}

Behörighet krävs för att visa: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Den här panelen visar antalet unika besökare under den angivna tidsramen. Individuella, färgkodade linjer representerar det totala antalet unika besökare och antalet unika besökare som fångas med hjälp av algoritmiska, regelbaserade och inbyggda egenskaper.

>[!NOTE]
>
>Det totala antalet unika besökare representerar besökare som tagits med hjälp av regelbaserade eller inbyggda egenskaper. Det totala antalet unika besökare är dock inte lika med summan av unika besökare som tagits med regelbaserade och inbyggda egenskaper. Samma unika användare kan representeras i någon av dessa två egenskapstyper.

## Största egenskaper/mest förändrade egenskaper {#largest-traits}

Behörighet krävs för att visa: [!UICONTROL View Traits].

![](assets/largest_traits.png)

På den här panelen visas antalet unika besökare som hämtats av olika egenskaper.

Använd **[!UICONTROL Show]** nedrullningsbar lista för att visa information om olika typer av egenskaper: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], eller [!UICONTROL Rule-Based].

Panelen innehåller följande flikar:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabb </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Största egenskaper</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare sorterat efter antal (högsta till lägsta) och visar även deltavärdet för unika besökare under den angivna tidsramen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Mest ändrade egenskaper</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare sorterade efter deltaändringen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Största segment/mest förändrade segment {#most-changed-segments}

Behörighet krävs för att visa: [!UICONTROL View Segments].

![](assets/largest_segments.png)

På den här panelen visas antalet unika besökare som fångats av olika segment i realtid.

Panelen innehåller följande flikar:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tabb </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Största segment</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare och deltavärdet för unika besökare under den angivna tidsramen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Mest ändrade segment</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare sorterade efter deltaändringen. </p> </td> 
  </tr> 
 </tbody> 
</table>
