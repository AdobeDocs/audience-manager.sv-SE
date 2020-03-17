---
description: På sidan för segmentsammanfattning visas information som namn, egenskaper i segmentet, regler, prestandadata och målmappningsinformation.
seo-description: På sidan för segmentsammanfattning visas information som namn, egenskaper i segmentet, regler, prestandadata och målmappningsinformation.
seo-title: Sidan Segmentinformation
solution: Audience Manager
title: Sidan Segmentinformation
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# Sidan Segmentinformation {#segment-summary-view}

Detaljsidan för ett enskilt segment innehåller en översikt över segmentinformationen, t.ex. segmentnamn, ID, prestandamått, regler som definierar segmentet och målmappningarna. Om du vill visa den här informationen går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** och klickar på namnet på segmentet som du vill arbeta med.

## Segmenthanteringsverktyg {#segment-management-tools}

Överst på sidan med segmentinformation finns verktyg som du kan använda för att hantera dina segment:

1. **[!UICONTROL Add New]**: Använd det här alternativet om du vill aktivera [!UICONTROL Segment Builder] och skapa nya segment.
2. **[!UICONTROL Edit]**: Använd det här alternativet om du vill ändra konfigurationen för det aktuella segmentet.
3. **[!UICONTROL Duplicate]**: Använd det här alternativet om du vill skapa en kopia av det aktuella segmentet.
4. **[!UICONTROL Delete]**: Använd det här alternativet om du vill ta bort det aktuella segmentet från ditt Audience Manager-konto.
5. **[!UICONTROL Marketplace Recommendations]**: Använd det här alternativet för att hitta liknande segment som den du visar, från [!UICONTROL Audience Marketplace] dataflöden som du inte prenumererar på. Se [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om du vill veta hur du navigerar på Marketplace och hittar liknande segment.

![grundläggande segmentinformation](assets/basic-segment-information.png)

## Segmentinformation {#basics}

Under segmenthanteringsverktygen finns följande segmentinformation:

1. **[!UICONTROL Basic Information]:**Visar obligatorisk och valfri information som angavs när segmentet skapades. Se[Segment Builder](segment-builder.md)för en detaljerad översikt över vad dessa fält betyder.
2. **[!UICONTROL Segment Graph]:**Visar prestandadata grafiskt och för fasta 1-, 7-, 14-, 30-, 60- och 90-dagarsintervall. Vi förklarar antalet populationer i segment i en[separat artikel](../../features/segments/segment-builder-data.md).

   ![segment-graph](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:**Rapporten visar antalet personer eller hushåll som är kvalificerade för ett segment genom att räkna antalet enhets-ID och/eller externa enhetsgraf-ID som är kopplade till de enheter som är kvalificerade för segmentet (visas av[!UICONTROL Total Segment Population]). De olika enhets-ID:n och externa enhetsgraf-ID:n som visas i den här rapporten används för att sammanfoga profiler med den profilsammanfogningsregel som segmentet använder. Den här rapporten visas bara om du har valt en datakälla för olika enheter eller ett externt enhetsdiagram i den profilkopplingsregel som segmentet använder.

   ![segment-graph](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager visar bara rapporten om du har ett enhets-ID som är kvalificerat för segmentet [!UICONTROL Identity Type Breakdown] .

   I videon nedan visas en översikt över [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:**Visar egenskaper i segmentet tillsammans med kvalificeringsregler.
5. **[!UICONTROL Destination Mappings]:**Visar målmappningar för segmentet.
6. **[!UICONTROL Management Tools]:**Kontroller som gör att du kan skapa, redigera, klona och ta bort segment.