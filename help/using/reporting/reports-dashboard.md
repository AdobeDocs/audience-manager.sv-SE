---
description: Använd Dashboard för att visa information om partners unika antal besökare, uppdelade efter trait-typer och segment, för en viss tidsram.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Kontrollpanel för rapporter
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Kontrollpanel för rapporter {#reports-dashboard}

Använd Dashboard för att visa information om antalet besökare som är unika, uppdelade efter trait-typer och segment, under en angiven tidsram.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] använder [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) för att utöka användargruppsbehörigheter till [!UICONTROL Dashboard]. Användarna kan bara se information på kontrollpanelen som de har behörighet att visa. Med funktionen [!UICONTROL RBAC] kan du styra vilka rapportdata interna team kan visa.

En byrå som till exempel hanterar olika annonsörkonton kan konfigurera användargruppbehörigheter så att ett team som hanterar Advertiser A:s konto inte kan se annonsörens B:s rapportdata. Den här instrumentpanelen kan användas för att felsöka dataleveransproblem.

Om du t.ex. märker en dip, eller spike, för totalt antal unika användare med en uppdelning av typ av unik användare (regelbaserad kontra ombord), har du en bättre startpunkt för att spåra ett potentiellt dataleveransproblem. Om du märker en nedgång i det totala antalet unika användare och i unika användare ombord kan du gå till rapporten [!UICONTROL On-boarding Status] och se om det uppstod ett problem med en inkommande fil.

**Så här kommer du åt instrumentpanelen:**

1. Klicka på **[!UICONTROL Dashboard]** i den övre navigeringsmenyn.
2. *Valfritt* Välj önskad tidsram från det senaste rapportdatumet i listrutan (7 dagar, 14 dagar (standard), 30 dagar eller 60 dagar).

   Beroende på vald period visar förändringen av delta i panelerna [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] och [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] förändringen av unika besökare i målgruppen under perioden som slutar idag jämfört med föregående period av samma längd. Om du till exempel väljer 7 dagar jämför Delta de unika besökarna under de senaste sju dagarna som slutar idag mot de unika besökarna under de sju dagar som slutade för sju dagar sedan.

   >[!NOTE]
   >
   >Du kan undersöka en delta-ändring som verkar vara ovanlig genom att köra en [!UICONTROL Trend]-rapport. Om du till exempel ser en ovanligt stor delta-förändring under de senaste sju dagarna, kan du köra en [!UICONTROL Trend]-rapport under de senaste 14 dagarna (2 x 7) för att få en bättre förståelse för siffrorna.

   Beroende på den inloggade användarens behörigheter visas följande paneler:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Största egenskaper/De mest ändrade egenskaperna](../reporting/reports-dashboard.md#largest-traits)
   * [Största segment/mest ändrade segment](../reporting/reports-dashboard.md#most-changed-segments)

3. *Valfritt* Klicka **[!UICONTROL Normalize]** ovanför ett diagram om du vill visa alla data i samma skala. Du kan också föra musen över en datapunkt för att se mer information.

## Partner Uniques {#partner-uniques}

Behörighet krävs för att visa: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

På den här panelen visas antalet unika besökare under den angivna tidsramen. Enskilda färgkodade linjer representerar det totala antalet unika besökare och antalet unika besökare som tagits med algoritmiska, regelbaserade och onboardbaserade egenskaper.

>[!NOTE]
>
>Det totala antalet unika besökare representerar besökare som tagits med regelbaserade eller ombord-anpassade egenskaper. Det totala antalet unika besökare motsvarar dock inte summan av unika besökare som tagits med hjälp av regelbaserade och anpassade egenskaper. Samma unika användare kan representeras i någon av dessa två trait-typer.

## Största egenskaper/De vanligaste förändrade egenskaperna {#largest-traits}

Behörighet krävs för att visa: [!UICONTROL View Traits].

![](assets/largest_traits.png)

På den här panelen visas antalet unika besökare som hämtats av olika egenskaper.

Använd listrutan **[!UICONTROL Show]** för att visa information om olika typer av egenskaper: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] eller [!UICONTROL Rule-Based].

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
   <td colname="col1"> <p><span class="wintitle"> Största egenskaper </span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare sorterade efter nummer (högst upp till lägst) och visar även förändringen av unika besökares delta under den angivna tidsramen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> De mest ändrade egenskaperna </span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare som sorterats efter förändringen i delta. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Största segment/mest ändrade segment {#most-changed-segments}

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
   <td colname="col1"> <p><span class="wintitle"> Största segment </span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare och förändringen av unika besökare under den angivna tidsramen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> De mest ändrade segmenten </span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare som sorterats efter förändringen i delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
