---
description: Beskriver hur du skapar segment med Segment Builder.
seo-description: Beskriver hur du skapar segment med Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 859e55fa5d93c7c56cef4bf2a112cdd4ff318d97

---


# Segment Builder {#segment-builder}

Beskriver de obligatoriska och valfria stegen som skapar ett segment i [!UICONTROL Segment Builder].

## Videodemonstration

Börja med att titta på videon [](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)Skapa segment i Audience Manager. Videon visar hur du skapar segment. Läs avsnitten nedan för mer information.

## Skapa ett segment {#create-segment}

### Segmentbyggaravsnitt

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] består av tre separata avsnitt: [!UICONTROL Basic Information], [!UICONTROL Traits]och [!UICONTROL Destinations Mapping]. Om du vill skapa ett segment fyller du i de obligatoriska fälten i [!UICONTROL Basic Information] - och [!UICONTROL Traits] -avsnitten. [!UICONTROL Destinations Mapping] inställningarna är valfria. Se instruktionerna nedan för ytterligare hjälp.

1. Under [Grundläggande information](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Namnge segmentet. Segmentnamnet får innehålla högst 255 tecken.
   * Ange segmentstatus (aktiv är standard).
   * Välj en datakälla. Använd den första listrutan för att filtrera mellan datakällor i Audience Manager, rapportsviter i Adobe Analytics eller båda. Använd sedan den andra listrutan för att välja datakälla. Om du inte använder rapportsviter från Adobe Analytics inaktiveras typväljaren för datakällan och används som standard endast för datakällor i Audience Manager.
   * Välj en profilkopplingsregel som ska användas för segmentkvalificering.
   * Tilldela segmentet till en lagringsmapp.

1. I avsnittet [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-traits](assets/segment-builder-traits.png)
   * Sök efter den egenskap som du vill lägga till i ett segment och klicka på **[!UICONTROL Add Trait]**. Lägg till en annan egenskap för att skapa en egen trait-grupp.
   * Visa spärren för avancerad sökning genom att klicka **[!UICONTROL Browse All Traits]**. Sök efter egenskaper efter namn, ID, beskrivning eller datakälla. Klicka på en mapp medan du söker för att begränsa resultatet till den mappen och dess undermappar. Du kan också filtrera egenskaper efter trait-typ ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]och [!UICONTROL Algorithmic]) eller populationstyp ([enhets-ID](../../reference/ids-in-aam.md) och [korsenhets-ID](../../reference/ids-in-aam.md)).
      ![segment-builder-browser-traits](assets/segment-builder-browse-traits.png)
   * Få rekommendationer [för](trait-recommendations.md) aktuella egenskaper när du bygger upp ditt segment.
   * Klicka och dra traits för att skapa separata grupper.
   * Hovra mellan grupper för att ange relationer med booleska värden [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL AND NOT] värden.
   * Håll muspekaren över klockikonen för att lägga till regler för [senaste](../../features/segments/recency-and-frequency.md) och frekvens i egenskapen.
   * Visa segmentpopulationsdata när du lägger till eller tar bort egenskaper. Klicka **[!UICONTROL Calculate Estimates]** för att visa (eller uppdatera) de beräknade populationssiffrorna. Läs mer om [segmentpopulationsdata](../../features/segments/segment-builder-data.md#segment-populations) i Segment Builder.
   * Klicka **[!UICONTROL Save]** när du är klar.

1. *(Valfritt)* Mappa ett segment till ett mål i avsnittet [Målmappning](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * Sök efter målet och klicka på **[!UICONTROL Add Destination]**. Observera att målet måste finnas innan du kan lägga till det i ett segment.
   * Klicka **[!UICONTROL Save]** när du är klar.

Titta på videon nedan för att få en detaljerad bild av hur enhetsövergripande mätvärden fungerar.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Segment Builder Controls: Avsnittet Grundläggande information {#segment-builder-controls-basics}

I [!UICONTROL Segment Builder]kan du [!UICONTROL the Basic Information] skapa nya eller redigera befintliga egenskaper. Om du vill skapa ett nytt segment anger du ett namn, en datakälla och väljer en lagringsmapp. Alla andra fält är valfria. Gå vidare till [!UICONTROL Traits] avsnittet när du är klar.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Namn</b> </td> 
   <td colname="col2"> <p>Ge segmentet ett kort logiskt namn som beskriver dess funktion eller syfte. Undvik förkortningar och specialtecken. Segmentnamnet får innehålla högst 255 tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beskrivning</b> </td> 
   <td colname="col2"> <p>Ett fält för ytterligare beskrivande information om segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integrationskod</b> </td> 
   <td colname="col2"> <p>Ett fält för ett användardefinierat ID eller annan företagsspecifik information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Datakälla</b> </td> 
   <td colname="col2"> <p>Associerar segmentet med en viss DataProvider. <p>Använd den första listrutan för att filtrera mellan datakällor i Audience Manager, rapportsviter i Adobe Analytics eller båda. Använd sedan den andra listrutan för att välja datakälla.</p><p> Om du inte använder rapportsviter från Adobe Analytics inaktiveras typväljaren för datakällan och används som standard endast för datakällor i Audience Manager.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Sammanfogningsregel för profil</b> </td> 
   <td colname="col2"> <p>Väljer den profilkopplingsregel som ska användas för segmentkvalificering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Aktiverar eller inaktiverar segmentet (aktivt som standard). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mapplagring</b> </td> 
   <td colname="col2"> <p>Avgör vilken lagringsmapp som segmentet tillhör. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment Builder Controls: Traits Section {#segment-builder-controls-traits}

I [!UICONTROL Segment Builder][!UICONTROL Traits] avsnittet kan du hantera egenskaper i ett segment, skapa egenskapsgrupper och ange kvalificeringskriterier. Om du vill lägga till en egenskap i ett segment skriver du namnet på egenskapen i sökfältet och klickar på [!UICONTROL Add Trait]. Spara trait (om du är klar) eller gå vidare till [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Förutsättningar:** Fyll i de obligatoriska fälten i [!UICONTROL Basic Information] avsnittet.

| Fält | Beskrivning |
|--- |--- |
| Grundläggande vy | I det här avsnittet finns visuella kontroller som du kan använda för att: <ul><li>Skapa nya och hantera befintliga segment.</li><li>Ta bort egenskaper från ett segment.</li><li>Lägg till upp till 50 (maximalt) egenskaper i ett segment.</li><li>Dra och släpp traits för att skapa nya grupper.</li><li>Visa traits- och trait-grupper i ett segment.</li><li>Ange kvalificeringskriterier med booleska uttryck, jämförelseoperatorer och inställningar för senaste frekvens/frekvens.</li></ul> |
| Kodvyn | Öppnar en utvecklingsmiljö där du kan skapa och hantera egenskaper, grupper och kvalificeringskrav med kod istället för det visuella gränssnittet. Kodvyn är användbar om dina segment: <ul><li>Innehåller mer än 50 egenskaper i ett enskilt segment. Obs! Segmenten är begränsade till 5 000 traits (max).</li><li>Innehåller många egenskapsgrupper.</li><li>ha komplexa kvalifikationskrav.</li></ul> |
| Sök | Hjälper dig att hitta egenskaper att lägga till i ett segment. |
| Rekommendationer | Få live-rekommendationer för liknande egenskaper från era egna egenskaper och [!UICONTROL Audience Marketplace] dataflöden som ni prenumererar på. Lägg till dessa rekommendationer i segmentregeln för att utöka er målgrupp. Läs mer i [Trait Recommendations](trait-recommendations.md). |
| Marketplace-rekommendationer | Få live-rekommendationer för liknande egenskaper från [!UICONTROL Audience Marketplace] dataflöden som du inte prenumererar på. Läs mer i [Trait Recommendations](trait-recommendations.md). |
| Reella och beräknade segmentstorleksdata | Se [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Ta bort egenskaper från ett segment {#remove-traits}

Att hantera egenskaper i era segment är en viktig del av att hålla segment lönsamma. Följ de här stegen om du behöver ta bort egenskaper från ett segment.

Så här tar du bort egenskaper från ett segment:

1. Gå till **Målgruppsdata > Segment**. Bläddra igenom listan eller använd sökfunktionen för att hitta det segment du vill arbeta med.
2. Klicka på segmentnamnet för att öppna segmentinformationsskärmen.
3. Klicka på **Redigera** för att öppna Segmentverktyget och klicka sedan på **Teckningar** för att öppna panelen Egenskaper.
4. Håll muspekaren över det tecken du vill ta bort och klicka sedan på krysset. Den här åtgärden tar omedelbart bort egenskapen från ditt segment.

## Segment Builder Controls: Destinationsmappningsavsnitt {#segment-builder-controls-destinations}

I [!UICONTROL Segment Builder]det valfria [!UICONTROL Destinations Mapping] avsnittet kan du skicka segmentdata till ett mål från tredje part [!DNL cookie][!DNL URL]eller server till server. Om du vill lägga till ett mål söker du efter (eller bläddrar) ett mål, anger målspecifik information och klickar på **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Förutsättningar

Fyll i de obligatoriska fälten i [!UICONTROL Basic Information] - och [!UICONTROL Traits] -avsnitten. Målet måste också finnas.

### Sökverktyg för målmappningar

Panelen innehåller **[!UICONTROL Destination Mappings]** sökverktyg som beskrivs i tabellen nedan.

| Söktyp | Beskrivning |
|---|---|
| **Sök efter målnamn** | Gör att du kan söka efter ett specifikt mål efter namn. Börja skriva om du vill söka. Fältet fylls i automatiskt baserat på dina sökord. Klicka **[!UICONTROL Add Destination]** när du är klar. |
| **Bläddra bland alla mål** | Bläddra i en lista över *alla* destinationer som är tillgängliga för dig. Välj och lägg till mål till ditt segment i popup-listan. |

## Fält i popup-fönstret Målmappningar {#fields-in-dest-mappings}

I [!UICONTROL Segment Builder]visas [!UICONTROL Add Destination] dialogrutan när du har valt ett mål. I det här fönstret visas statisk information om målet och fält som varierar beroende på måltyp. Ange nödvändig information i de tomma fälten för att ställa in en målmappning.

>[!NOTE]
>
>Publiceringsdatum är valfria. Om det är tomt blir målet aktivt och upphör aldrig att gälla.

<!-- r_add_mappings_pop.xml -->

### Cookie-målfält

I [!UICONTROL Destination Mapping] fälten anger du nyckelvärdepar som används för att skicka data till målet. Ange tangenten i det första fältet och värdena i det andra. Din popup-meny för cookie kan se ut ungefär så här:

![](assets/cookie_modal.PNG)

### URL-målfält

I fälten [!UICONTROL URL] och [!UICONTROL Secure URL] anger du den fullständiga standardadress eller den säkra adress som används för att skicka data till målet.

![](assets/url_modal.PNG)

### Målfält för server-till-server

I [!UICONTROL Destination Value] fältet anger du värdet (del av nyckelvärdepar) som används för att skicka data till målet.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Skapa ett cookie-mål](../../features/destinations/create-cookie-destination.md)
>* [Skapa ett URL-mål](../../features/destinations/create-url-destination.md)

