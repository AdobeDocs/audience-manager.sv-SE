---
description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-description: Dataexportetiketter fungerar med de exportkontroller du anger för en datakälla. Dataexportetiketter förhindrar att du lägger till begränsade egenskaper i ett segment och skickar segmentdata till ett mål. Du kan ange flera exportetiketter till en ny eller befintlig cookie eller URL-adress.
seo-title: Lägg till dataexportkontroller till ett mål
solution: Audience Manager
title: Lägg till dataexportkontroller till ett mål
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---



# Lägg till dataexportetiketter till ett mål {#add-data-export-labels}

[!DNL Data Export Labels] arbeta med den [!DNL Export Controls] du anger för en datakälla. [!DNL Data Export Labels] förhindrar att du lägger till begränsade egenskaper i ett segment och inte skickar segmentdata till ett mål. Du kan ange flera exportetiketter till ett nytt eller befintligt [!DNL cookie] mål eller [!DNL URL] mål.

>[!NOTE]
>
>Om du vill lägga till en exportetikett måste du ha administratörsbehörighet *eller* tillräcklig behörighet för att skapa eller redigera ett mål.

<!-- t_export_labels.xml -->

Så här lägger du till exportetiketter till ett mål:

1. Klicka på **[!UICONTROL Audience Data]**:
   * För nya destinationer: Klicka **[!UICONTROL Create New Destination]**. Slutför [!UICONTROL Basic Information] avsnittet innan du väljer en dataexportetikett. Mer information finns i [Skapa ett cookie-mål](../../features/destinations/create-cookie-destination.md) eller [Skapa ett URL-mål](../../features/destinations/create-url-destination.md) .
   * För befintliga destinationer: Använd [!DNL Search] rutan för att hitta målet eller bläddra igenom listan och klicka på målnamnet för att öppna den.
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