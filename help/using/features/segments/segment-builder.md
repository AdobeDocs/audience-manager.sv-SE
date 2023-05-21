---
description: Beskriver hur du skapar segment med Segment Builder.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Beskriver obligatoriska och valfria steg som skapar ett segment i [!UICONTROL Segment Builder].

## Videodemonstration

Börja med att titta på [Skapa segment i Audience Manager-video](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). Videon visar hur du skapar segment. Läs avsnitten nedan för mer information.

## Skapa en [!UICONTROL Segment] {#create-segment}

### Segmentbyggaravsnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] består av tre separata avsnitt: [!UICONTROL Basic Information], [!UICONTROL Traits]och [!UICONTROL Destinations Mapping]. Skapa en [!UICONTROL segment]fyller du i de obligatoriska fälten i [!UICONTROL Basic Information] och [!UICONTROL Traits] -avsnitt. [!UICONTROL Destinations Mapping] inställningarna är valfria. Se instruktionerna nedan för ytterligare hjälp.

1. I [Grundläggande information](../../features/segments/segment-builder.md#segment-builder-controls-basics) avsnitt:

   ![create-segment](assets/create-segment.png)

   * Namnge [!UICONTROL segment]. Maximala längden för en [!UICONTROL segment] namnet är 255 tecken.
   * Ange [!UICONTROL segment] status (active is default).
   * Välj en [!UICONTROL data source]. Använd den första listrutan för att filtrera mellan Audience Manager [!UICONTROL data sources], Adobe Analytics eller båda. Använd sedan den andra listrutan för att välja [!UICONTROL data source]. Om du inte använder Adobe Analytics rapporteringsprogram kan du [!UICONTROL data source] typväljaren är inaktiverad och standardinställningen är endast Audience Manager datakällor.
   * Välj en [!UICONTROL profile merge rule] att använda för [!UICONTROL segment] kvalificering.
   * Tilldela [!UICONTROL segment] till en lagringsmapp.

1. I [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) avsnitt:
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Sök efter [!UICONTROL trait] du vill lägga till i ett segment och klicka på **[!UICONTROL Add Trait]**. Lägg till ytterligare [!UICONTROL trait] för att skapa en [!UICONTROL trait] grupp.
   * Ta fram [!UICONTROL Advanced Search] spärra/knip genom att klicka **[!UICONTROL Browse All Traits]**. Sök efter [!UICONTROL traits] efter namn, ID, beskrivning eller [!UICONTROL data source]. Klicka på en mapp medan du söker för att begränsa resultatet till den mappen och dess undermappar. Du kan också filtrera [!UICONTROL traits] av [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]och [!UICONTROL Algorithmic]) eller populationstyp ([Enhets-ID](../../reference/ids-in-aam.md) och [Enhets-ID](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Visa live [rekommendationer för egenskaper](trait-recommendations.md) när du bygger [!UICONTROL segment].
   * Klicka och dra [!UICONTROL traits] för att skapa separata grupper.
   * Hovra mellan grupper för att ange relationer med Boolean [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] värden.
   * Håll pekaren över klockikonen för att lägga till [senaste och frekvenser](../../features/segments/recency-and-frequency.md) regler för [!UICONTROL trait].
   * Visa segmentpopulationsdata när du lägger till eller tar bort [!UICONTROL traits]. Klicka **[!UICONTROL Calculate Estimates]** för att visa (eller uppdatera) de beräknade populationssiffrorna. Läs mer om [segmentpopulationsdata](../../features/segments/segment-builder-data.md#segment-populations) i [!UICONTROL Segment Builder].
   * Klicka **[!UICONTROL Save]** när det är klart.

1. *(Valfritt)* Karta a [!UICONTROL segment] till [!UICONTROL destination] i [Målmappning](../../features/segments/segment-builder.md#segment-builder-controls-destinations) avsnitt:
   * Sök efter [!UICONTROL destination] och klicka **[!UICONTROL Add Destination]**. Obs! [!UICONTROL destination] måste finnas innan du kan lägga till det i en [!UICONTROL segment].
   * Klicka **[!UICONTROL Save]** när det är klart.

Titta på videon nedan för att få en detaljerad bild av hur enhetsövergripande mätvärden fungerar.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Kontroller: [!UICONTROL Basic Information] Avsnitt {#segment-builder-controls-basics}

I [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] gör att du kan skapa nya eller redigera befintliga egenskaper. Skapa en ny [!UICONTROL segment], ange ett namn, [!UICONTROL data source]och välj en lagringsmapp. Alla andra fält är valfria. Gå vidare till [!UICONTROL Traits] när du är klar.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Fält | Beskrivning |
---------|----------
| **[!UICONTROL Name]** | Ge segmentet ett kort logiskt namn som beskriver dess funktion eller syfte. Undvik förkortningar och specialtecken. Segmentnamnet får innehålla högst 255 tecken. |
| **[!UICONTROL Description]** | Ett fält för ytterligare beskrivande information om segmentet. |
| **[!UICONTROL Integration Code]** | Ett fält för ett användardefinierat ID eller annan företagsspecifik information. |
| **[!UICONTROL Data Source]** | Associerar segmentet med en viss DataProvider. <br> Använd den första listrutan för att filtrera mellan Audience Manager och datakällor, Adobe Analytics rapportsviter eller båda. Använd sedan den andra listrutan för att välja datakälla. <br> Om du inte använder Adobe Analytics rapportprogramsviter är datakälltypväljaren inaktiverad och standardinställningen är endast Audience Manager datakällor. |
| **[!UICONTROL Profile Merge Rule]** | Väljer den profilkopplingsregel som ska användas för segmentkvalificering. |
| **[!UICONTROL Status]** | Aktiverar eller inaktiverar segmentet (aktivt som standard). |
| **Mapplagring** | Avgör vilken lagringsmapp som segmentet tillhör. |

## [!UICONTROL Segment Builder] Kontroller: [!UICONTROL Traits] Avsnitt {#segment-builder-controls-traits}

I [!UICONTROL Segment Builder], [!UICONTROL Traits] kan du hantera [!UICONTROL traits] i en [!UICONTROL segment], skapa [!UICONTROL trait] grupper och ange kvalificeringskriterier. Lägga till en [!UICONTROL trait] till [!UICONTROL segment], skriver du [!UICONTROL trait] namn i sökfältet och klicka på [!UICONTROL Add Trait]. Spara [!UICONTROL trait] (om du är klar) eller gå vidare till [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Förutsättningar:** Fyll i de obligatoriska fälten i [!UICONTROL Basic Information] -avsnitt.

| Fält | Beskrivning |
|--- |--- |
| **[!UICONTROL Basic View]** | I det här avsnittet finns visuella kontroller som du kan använda för att: <ul><li>Bygg nya och hantera befintliga [!UICONTROL segments].</li><li>Ta bort [!UICONTROL traits] från en [!UICONTROL segment].</li><li>Lägg till upp till 50 (max) [!UICONTROL traits] till [!UICONTROL segment].</li><li>Dra och släpp [!UICONTROL traits] för att skapa nya grupper.</li><li>Visa [!UICONTROL traits] och [!UICONTROL trait] grupper i en [!UICONTROL segment].</li><li>Ange kvalificeringskriterier med booleska uttryck, jämförelseoperatorer och inställningar för senaste frekvens/frekvens.</li></ul> |
| **[!UICONTROL Code View]** | Öppnar en utvecklingsmiljö där du kan skapa och hantera [!UICONTROL traits], grupper och kvalificeringskrav med kod i stället för det visuella gränssnittet. Kodvyn är användbar om [!UICONTROL segments]: <ul><li>Innehåller mer än 50 [!UICONTROL traits] på individ [!UICONTROL segment]. Obs! [!UICONTROL Segments] begränsas till 5000 [!UICONTROL traits] (max).</li><li>Innehåller många [!UICONTROL trait] grupper.</li><li>ha komplexa kvalifikationskrav.</li></ul> |
| Sök | Hjälper dig att hitta [!UICONTROL traits] lägga till i en [!UICONTROL segment]. |
| Recommendations | Få live-rekommendationer för liknande [!UICONTROL traits]från din första part [!UICONTROL traits] och [!UICONTROL Audience Marketplace] dataflöden som du prenumererar på. Lägg till dessa rekommendationer i [!UICONTROL segment] för att utöka er målgrupp. Läs mer i [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Få live-rekommendationer för liknande [!UICONTROL traits], från [!UICONTROL Audience Marketplace] dataflöden som du inte prenumererar på. Läs mer i [Trait Recommendations](trait-recommendations.md). |
| Verklig och uppskattad [!UICONTROL Segment] Storleksdata | Se [Trait- och segmentpopulationsdata i Segment Builder](segment-builder-data.md). |

## Ta bort [!UICONTROL Traits] från en [!UICONTROL Segment] {#remove-traits}

Hantera [!UICONTROL traits] i [!UICONTROL segments] är en viktig del av att [!UICONTROL segments] livskraftigt. Följ de här stegen om du behöver ta bort [!UICONTROL traits] från en [!UICONTROL segment].

Ta bort [!UICONTROL traits] från en [!UICONTROL segment]:

1. Gå till **[!UICONTROL Audience Data > Segments]**. Bläddra igenom listan eller använd sökfunktionen för att hitta [!UICONTROL segment] du vill arbeta med.
2. Klicka på [!UICONTROL segment] namn för att öppna [!UICONTROL segment] informationsskärmen.
3. Klicka **Redigera** att öppna [!UICONTROL Segment Builder] och sedan klicka **Traits** för att öppna [!UICONTROL traits] -panelen.
4. Hovra över [!UICONTROL trait] du vill ta bort och sedan klicka på krysset. Den här åtgärden tar omedelbart bort [!UICONTROL trait] från [!UICONTROL segment].

## [!UICONTROL Segment Builder] Kontroller: [!UICONTROL Destinations Mappings] Avsnitt {#segment-builder-controls-destinations}

I [!UICONTROL Segment Builder], det valfria [!UICONTROL Destinations Mapping] kan du skicka [!UICONTROL segment] data till tredje part [!DNL cookie], [!DNL URL], eller [!UICONTROL server-to-server destination]. Lägga till en [!UICONTROL destination], söka (eller bläddra) efter en [!UICONTROL destination], tillhandahålla [!UICONTROL destination] specifik information och klicka på **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Förutsättningar

Fyll i de obligatoriska fälten i [!UICONTROL Basic Information] och [!UICONTROL Traits] -avsnitt. Målet måste också finnas.

### [!UICONTROL Destination Mappings] Sökverktyg

The **[!UICONTROL Destination Mappings]** panelen innehåller sökverktyg enligt beskrivningen i tabellen nedan.

| Söktyp | Beskrivning |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Gör att du kan söka efter en viss [!UICONTROL destination] efter namn. Börja skriva om du vill söka. Fältet fylls i automatiskt baserat på dina sökord. Klicka **[!UICONTROL Add Destination]** när det är klart. |
| **[!UICONTROL Browse All Destinations]** | Bläddra i en lista över *alla* [!UICONTROL destinations] som är tillgängliga för dig. Markera och lägg till [!UICONTROL destinations] till [!UICONTROL segment] från popup-listan. |

## Fält i [!UICONTROL Destination Mappings] Popup-fönster {#fields-in-dest-mappings}

I [!UICONTROL Segment Builder], [!UICONTROL Add Destination] visas när du har valt [!UICONTROL destination]. I det här fönstret visas statisk information om [!UICONTROL destination] och fält som varierar beroende på [!UICONTROL destination] typ. Ange nödvändig information i de tomma fälten för att konfigurera en [!UICONTROL destination mapping].

>[!NOTE]
>
>Publiceringsdatum är valfria. Om det är tomt blir målet aktivt och upphör aldrig att gälla.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Fält

I [!UICONTROL Destination Mapping] fält, ange nyckelvärdepar som används för att skicka data till [!UICONTROL destination]. Ange tangenten i det första fältet och värdena i det andra. Dina [!UICONTROL cookie destination] pop could look similar to this:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Fält

I [!UICONTROL URL] och [!UICONTROL Secure URL] fält, ange den fullständiga standardadressen eller den säkra adressen som används för att skicka data till [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Fält

I [!UICONTROL Destination Value] fältet anger värdet (del av nyckelvärdepar) som används för att skicka data till [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Skapa ett cookie-mål](../../features/destinations/create-cookie-destination.md)
>* [Skapa ett URL-mål](../../features/destinations/create-url-destination.md)

