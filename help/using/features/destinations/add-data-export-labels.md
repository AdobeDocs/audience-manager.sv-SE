---
description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie-fil eller URL-adress.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Lägg till dataexportkontroller till ett mål
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Lägg till dataexportetiketter till ett mål {#add-data-export-labels}

[!DNL Data Export Labels] arbetar med [!DNL Export Controls] som du anger för en datakälla. [!DNL Data Export Labels] hindrar dig från att lägga till begränsade egenskaper i ett segment och från att skicka segmentdata till ett mål. Du kan ange flera exportetiketter till ett nytt eller befintligt [!DNL cookie]- eller [!DNL URL]-mål.

>[!NOTE]
>
>Om du vill lägga till en exportetikett måste du ha administratörsbehörighet *eller* för att skapa eller redigera ett mål.

<!-- t_export_labels.xml -->

Så här lägger du till exportetiketter till ett mål:

1. Klicka på **[!UICONTROL Audience Data]**:

   * För nya mål: Klicka på **[!UICONTROL Create New Destination]**. Fyll i avsnittet [!UICONTROL Basic Information] innan du väljer en dataexportetikett. Mer information finns i [Skapa ett cookie-mål](../../features/destinations/create-cookie-destination.md) eller [Skapa ett URL-mål](../../features/destinations/create-url-destination.md).
   * För befintliga mål: Använd rutan [!DNL Search] för att hitta ditt mål eller bläddra igenom listan och klicka på målnamnet för att öppna det.

1. Välj en [!DNL Data Export Label]. Lämna kryssrutorna tomma om du inte vill ange några exportbegränsningar. Exportetiketter innehåller följande alternativ:

   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Exportbegränsningar fungerar inte om du inte anger en [matchande exportkontroll](../../features/data-export-controls.md) för en datakälla.

1. Klicka på **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Skapa en datakälla](../../features/manage-datasources.md#create-data-source)
