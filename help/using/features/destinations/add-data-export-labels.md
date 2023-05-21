---
description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Lägga till dataexportkontroller för en destination
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 5%

---

# Lägg till dataexportetiketter till ett mål {#add-data-export-labels}

[!DNL Data Export Labels] arbeta med [!DNL Export Controls] du anger på en datakälla. [!DNL Data Export Labels] förhindrar att du lägger till begränsade egenskaper i ett segment och inte skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig [!DNL cookie] eller [!DNL URL] mål.

>[!NOTE]
>
>Om du vill lägga till en exportetikett måste du ha administratörsbehörighet *eller* tillräcklig behörighet för att skapa eller redigera ett mål.

<!-- t_export_labels.xml -->

Så här lägger du till exportetiketter till ett mål:

1. Klicka på **[!UICONTROL Audience Data]**:
   * För nya destinationer: Klicka **[!UICONTROL Create New Destination]**. Slutför [!UICONTROL Basic Information] innan du väljer en dataexportetikett. Se [Skapa ett cookie-mål](../../features/destinations/create-cookie-destination.md) eller [Skapa ett URL-mål](../../features/destinations/create-url-destination.md) för information.
   * För befintliga destinationer: Använd [!DNL Search] om du vill hitta målet eller bläddra i listan och klicka på målnamnet för att öppna det.
1. Välj en [!DNL Data Export Label]. Lämna kryssrutorna tomma om du inte vill ange några exportbegränsningar. Exportetiketter innehåller följande alternativ:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Exportbegränsningar fungerar inte om du inte anger en [matchande exportkontroll](../../features/data-export-controls.md) på en datakälla.
1. Klicka på **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Skapa en datakälla](../../features/manage-datasources.md#create-data-source)

