---
description: Om du vill skapa en ny datakälla går du till Målgruppsdata > Datakällor > Lägg till ny och slutför stegen för varje avsnitt som beskrivs här. Administratörsbehörighet krävs för att skapa en datakälla.
keywords: datakällor;hantera datakälla;målgruppshanterarens datakälla
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Hantera datakällor
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Hantera [!UICONTROL Data Sources] {#manage-data-sources}

## Skapa en [!UICONTROL Data Source] {#create-data-source}

Skapa en ny [!UICONTROL data source], gå till **[!UICONTROL Audience Data > Data Sources > Add New]** och slutföra stegen för varje avsnitt som beskrivs här. Administratörsbehörighet krävs för att skapa en [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Se [Inställningar för datakälla och menyalternativ](../features/datasources-list-and-settings.md#settings-menu-options) för beskrivningar av dessa olika kontroller.

## [!UICONTROL Data Source] Detaljer {#details}

Slutför [!UICONTROL Data Source Details] avsnitt:

1. Namnge [!UICONTROL data source].
1. *(Valfritt)* Beskriv [!UICONTROL data source]. En kortfattad beskrivning hjälper dig att definiera rollen eller syftet med [!UICONTROL data source].
1. Ange en [!UICONTROL integration code]. I allmänhet [!UICONTROL integration codes] är valfria. De krävs när du vill:

   * [Skapa en datakälla för olika enheter](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Använd [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Arbeta med [Regler för profilsammanslagning](../features/profile-merge-rules/merge-rules-start.md).

1. Välj en **[!UICONTROL ID Type]**. [!UICONTROL ID Type] bland annat:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Krävs för att skapa en [!UICONTROL Profile Merge Rule]). Observera att för vissa kunder visas **[!UICONTROL ID Definition]** alternativ.

   >[!NOTE]
   >
   >För varje organisation som har etablerats för Audience Manager och Experience Platform, även om du inte har segmentdelning mellan de två apparna, när du skapar en datakälla för olika enheter, en motsvarande [identity namespace](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) skapas i Experience Platform.

1. Välj en **[!UICONTROL ID Definition]** alternativ. Alternativen är:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Dataexportkontroller](../features/data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på [!UICONTROL data source] och [!UICONTROL destination]. De förhindrar att du skickar data till en [!UICONTROL destination] när den åtgärden bryter mot en datasekretess eller ett användningsavtal. Hoppa över det här avsnittet om du inte använder det [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Inställningar {#settings}

Dessa inställningar avgör hur [!UICONTROL data source] identifieras, används och delas. Du kan även aktivera felrapportering för inkommande datafiler. Slutför [!UICONTROL Data Source Settings] avsnitt:

1. Välj en [!UICONTROL Data Source Setting] kryssruta för att använda ett alternativ på [!UICONTROL data source].
2. Klicka på **[!UICONTROL Save]**.

## Ta bort en datakälla {#delete-data-source}

<!-- t_datasource_delete.xml -->

Ta bort en [!UICONTROL data source] som du inte längre behöver.

>[!NOTE]
>
>Observera följande begränsningar:
>
>* Du kan inte ta bort en [Synkroniserat varumärke för aktiv publik eller datakälla](../features/traits/client-activity-synced-audience-traits.md).
>* För kunder som använder Adobe Analytics: Audience Manager tillåter inte att du tar bort datakällor som skapats automatiskt från [!DNL Analytics] rapportsviter. Använd [Bastjänst](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) för att ta bort mappningen för dessa datakällor.


1. Klicka på **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Markera kryssrutan bredvid en eller flera datakällor.
Du kan använda [!UICONTROL Search] för att hitta de önskade datakällorna om du har en lång lista.
1. Klicka  ![](assets/icon_trash.png)bekräftar du sedan borttagningen.


>[!MORELIKETHIS]
>
>* [Inställningar för datakälla och menyalternativ](../features/datasources-list-and-settings.md#settings-menu-options)

