---
description: Använd Dashboard för att visa information om partners unika antal besökare, uppdelade efter trait-typer och segment, för en viss tidsram.
seo-description: Använd Dashboard för att visa information om partners unika antal besökare, uppdelade efter trait-typer och segment, för en viss tidsram.
seo-title: Kontrollpanel för rapporter
solution: Audience Manager
title: Kontrollpanel för rapporter
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Rapporteringsreferens
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Kontrollpanel för rapporter {#reports-dashboard}

Använd Dashboard för att visa information om antalet besökare som är unika, uppdelade efter trait-typer och segment, under en angiven tidsram.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] använder  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]) för att utöka användargruppsbehörigheter till  [!UICONTROL Dashboard]. Användarna kan bara se information på kontrollpanelen som de har behörighet att visa. [!UICONTROL RBAC] kan ni styra vilka rapportdata som interna team kan visa.

En byrå som till exempel hanterar olika annonsörkonton kan konfigurera användargruppbehörigheter så att ett team som hanterar Advertiser A:s konto inte kan se annonsörens B:s rapportdata. Den här instrumentpanelen kan användas för att felsöka dataleveransproblem.

Om du t.ex. märker en dip, eller spike, för totalt antal unika användare med en uppdelning av typ av unik användare (regelbaserad kontra ombord), har du en bättre startpunkt för att spåra ett potentiellt dataleveransproblem. Om du märker att antalet unika användare har minskat och att det finns unika användare ombord kan du gå till [!UICONTROL On-boarding Status]-rapporten och se om det har uppstått ett problem med en inkommande fil.

**Så här öppnar du kontrollpanelen:**

1. Klicka på **[!UICONTROL Dashboard]** i den övre navigeringsmenyn.
2. *Valfritt* Välj önskad tidsram från det senaste rapportdatumet i listrutan (7 dagar, 14 dagar (standard), 30 dagar eller 60 dagar).

   Beroende på vilken period som är markerad visar förändringen av delta i panelerna [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] och [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] förändringen av unika besökare i målgruppen under perioden som slutar idag jämfört med föregående period av samma längd. Om du till exempel väljer 7 dagar jämför Delta de unika besökarna under de senaste sju dagarna som slutar idag mot de unika besökarna under de sju dagar som slutade för sju dagar sedan.

   >[!NOTE]
   >
   >Du kan undersöka en delta-ändring som verkar vara ur gängse synvinkel genom att köra en [!UICONTROL Trend]-rapport. Om du till exempel ser en ovanligt stor delta-förändring under de senaste sju dagarna kan du köra en [!UICONTROL Trend]-rapport under de senaste 14 dagarna (2 x 7) för att bättre förstå siffrorna.

   Beroende på den inloggade användarens behörigheter visas följande paneler:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Största egenskaper/De mest förändrade egenskaperna](../reporting/reports-dashboard.md#largest-traits)
   * [Största segment/mest ändrade segment](../reporting/reports-dashboard.md#most-changed-segments)

3. ** ValfrittKlicka  **[!UICONTROL Normalize]** ovanför ett diagram om du vill visa alla data i samma skala. Du kan också föra musen över en datapunkt för att se mer information.

## Partner Uniques {#partner-uniques}

Behörighet krävs för att visa: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

På den här panelen visas antalet unika besökare under den angivna tidsramen. Enskilda färgkodade linjer representerar det totala antalet unika besökare och antalet unika besökare som tagits med algoritmiska, regelbaserade och onboardbaserade egenskaper.

>[!NOTE]
>
>Det totala antalet unika besökare representerar besökare som tagits med regelbaserade eller ombord-anpassade egenskaper. Det totala antalet unika besökare motsvarar dock inte summan av unika besökare som tagits med hjälp av regelbaserade och anpassade egenskaper. Samma unika användare kan representeras i någon av dessa två trait-typer.

## Största antal traits/De mest ändrade traits {#largest-traits}

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
   <td colname="col1"> <p><span class="wintitle"> Största egenskaper</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare sorterade efter nummer (högst upp till lägst) och visar även förändringen av unika besökares delta under den angivna tidsramen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> De mest förändrade egenskaperna</span> </p> </td> 
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
   <td colname="col1"> <p><span class="wintitle"> Största segment</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare och förändringen av unika besökare under den angivna tidsramen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> De mest ändrade segmenten</span> </p> </td> 
   <td colname="col2"> <p>Visar information om antalet unika besökare som sorterats efter förändringen i delta. </p> </td> 
  </tr> 
 </tbody> 
</table>
