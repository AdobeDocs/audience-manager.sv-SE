---
description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-title: Lägga till eller redigera segment för server-till-server-destinationer
solution: Audience Manager
title: Lägga till eller redigera segment för server-till-server-destinationer
feature: Destination Basics
translation-type: tm+mt
source-git-commit: 55925e803e16580e0d9357d973405cf39370a8fd
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 8%

---


# Lägga till eller redigera segment för server-till-server-destinationer {#add-edit-segments}

Du kan bara lägga till eller redigera segment för ett server-till-server-mål ([!DNL S2S]). Du kan inte skapa [!DNL S2S]-mål med [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md). Kontakta din konsult för att konfigurera [!DNL S2S]-mål. Följ dessa anvisningar när du vill lägga till eller redigera segment för ett [!DNL S2S]-mål.

<!-- destination-s2s-edit.xml -->

Så här lägger du till eller redigerar segmentmappningar för ett [!DNL S2S]-mål:

1. Gå till **[!UICONTROL Audience Data > Destinations]**. Välj **Integrerade plattformar > Enhetsbaserade** och hitta det [!DNL S2S]-mål som du vill arbeta med.
2. Klicka på pennikonen i kolumnen [!UICONTROL Action] för att redigera målet.
   * I rutan **[!UICONTROL Search and Add Segments]** börjar du skriva namnet på ett segment eller klickar på **[!UICONTROL Browse All Segments]** och bläddrar i en lista över tillgängliga segment.
   * Klicka på **[!UICONTROL Add Selected Segments]** när du hittar det segment du vill använda. Om du lägger till ett segment öppnas fönstret [!UICONTROL Edit Mapping].
   * I [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Ange ett värde för  [nyckelvärdepar ](../../features/destinations/key-value-pairs.md) som används av det här målet.
      * **[!UICONTROL Start Date]** och  **[!UICONTROL End Date]**: Välj ett start- och slutdatum för målet. Om slutdatumet är tomt upphör målet aldrig att gälla.
3. Klicka på **[!UICONTROL Save]** och sedan på **[!UICONTROL Done]**.
