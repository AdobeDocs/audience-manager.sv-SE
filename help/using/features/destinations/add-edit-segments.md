---
description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie-fil eller URL-adress.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Lägg till eller redigera segment för server-till-server-mål
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# Lägg till eller redigera segment för server-till-server-mål {#add-edit-segments}

Du kan bara lägga till eller redigera segment för ett server-till-server-mål ([!DNL S2S]). Du kan inte skapa [!DNL S2S] mål med [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Kontakta din konsult för att konfigurera [!DNL S2S] mål. Följ de här instruktionerna för att lägga till eller redigera segment för ett [!DNL S2S]-mål.

<!-- destination-s2s-edit.xml -->

Så här lägger du till eller redigerar segmentmappningar för ett [!DNL S2S]-mål:

1. Gå till **[!UICONTROL Audience Data > Destinations]**. Välj **Integrerade plattformar > Enhetsbaserade** och hitta det [!DNL S2S]-mål som du vill arbeta med.
2. Klicka på pennikonen i kolumnen [!UICONTROL Action] för att redigera målet.
   * I rutan **[!UICONTROL Search and Add Segments]** börjar du skriva namnet på ett segment eller klickar på **[!UICONTROL Browse All Segments]** för att bläddra i en lista över tillgängliga segment.
   * Klicka på **[!UICONTROL Add Selected Segments]** när du hittar det segment du vill använda. Om du lägger till ett segment öppnas fönstret [!UICONTROL Edit Mapping].
   * I [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Ange ett värde för det [nyckel/värde-par](../../features/destinations/key-value-pairs.md) som används av det här målet.
      * **[!UICONTROL Start Date]** och **[!UICONTROL End Date]**: Välj ett start- och slutdatum för målet. Om slutdatumet är tomt upphör målet aldrig att gälla.
3. Klicka på **[!UICONTROL Save]** och sedan på **[!UICONTROL Done]**.
