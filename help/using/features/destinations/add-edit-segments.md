---
description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-title: Lägg till eller redigera segment för server-till-server-mål
solution: Audience Manager
title: Lägg till eller redigera segment för server-till-server-mål
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# Lägg till eller redigera segment för server-till-server-mål {#add-edit-segments}

Du kan bara lägga till eller redigera segment för ett server-till-server-mål ([!DNL S2S]). Du kan inte skapa [!DNL S2S] mål med [!UICONTROL [Destination Builder](/help/using/features/destinations/destination-builder.md)]. Kontakta din konsult för att konfigurera [!DNL S2S] destinationer. Följ dessa anvisningar när du vill lägga till eller redigera segment för ett [!DNL S2S] mål.

<!-- destination-s2s-edit.xml -->

Så här lägger du till eller redigerar segmentmappningar för ett [!DNL S2S] mål:

1. Gå till **[!UICONTROL Audience Data > Destinations]**. Välj **Integrerade plattformar > Enhetsbaserade** och hitta den [!DNL S2S] destination du vill arbeta med.
2. Klicka på pennikonen i [!UICONTROL Action] kolumnen för att redigera målet.
   * I **[!UICONTROL Search and Add Segments]** rutan börjar du skriva namnet på ett segment eller klicka på **[!UICONTROL Browse All Segments]** bläddra i en lista över tillgängliga segment.
   * Klicka **[!UICONTROL Add Selected Segments]** när du hittar det segment du vill använda. När du lägger till ett segment öppnas [!UICONTROL Edit Mapping] fönstret.
   * I [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Ange ett värde för [nyckelvärdepar](../../features/destinations/key-value-pairs.md) som används av det här målet.
      * **[!UICONTROL Start Date]** och **[!UICONTROL End Date]**: Välj ett start- och slutdatum för målet. Om slutdatumet är tomt upphör målet aldrig att gälla.
3. Click **[!UICONTROL Save]** and then click **[!UICONTROL Done]**.