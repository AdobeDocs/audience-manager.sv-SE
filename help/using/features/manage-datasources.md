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
source-git-commit: e41dddd022b6fa02cab3e16bd21536d41584975f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# Hantera [!UICONTROL Data Sources] {#manage-data-sources}

## Skapa en [!UICONTROL Data Source] {#create-data-source}

Om du vill skapa en ny [!UICONTROL data source] går du till **[!UICONTROL Audience Data > Data Sources > Add New]** och slutför stegen för varje avsnitt som beskrivs här. Administratörsbehörighet krävs för att skapa en [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Se [Inställningar och menyalternativ för Data Source](../features/datasources-list-and-settings.md#settings-menu-options) för beskrivningar av dessa olika kontroller.

## Information om [!UICONTROL Data Source] {#details}

Så här slutför du avsnittet [!UICONTROL Data Source Details]:

1. Namnge [!UICONTROL data source].
1. *(Valfritt)* Beskriv [!UICONTROL data source]. En kort beskrivning hjälper dig att definiera rollen eller syftet med [!UICONTROL data source].
1. Ange en [!UICONTROL integration code]. I allmänhet är [!UICONTROL integration codes] valfritt. De är obligatoriska när du vill:

   * [Skapa en datakälla för olika enheter](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Använd [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Arbeta med [profilkopplingsregler](../features/profile-merge-rules/merge-rules-start.md).

1. Välj en **[!UICONTROL ID Type]**. [!UICONTROL ID Type] alternativ omfattar:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (krävs för att skapa en [!UICONTROL Profile Merge Rule]). Observera att för vissa kunder visas alternativen för **[!UICONTROL ID Definition]** i det här valet.

   >[!NOTE]
   >
   >För varje organisation som har etablerats för Audience Manager och Experience Platform skapas ett motsvarande [identitetsnamnutrymme](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) i Experience Platform när du skapar en datakälla för olika enheter, även om du inte har segmentdelning mellan de två programmen.

1. Välj ett **[!UICONTROL ID Definition]**-alternativ. Alternativen är:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Dataexportkontroller](../features/data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på [!UICONTROL data source] och [!UICONTROL destination]. De förhindrar dig från att skicka data till en [!UICONTROL destination] när den åtgärden bryter mot en datasekretess eller ett användningsavtal. Hoppa över det här avsnittet om du inte använder [!UICONTROL Data Export Controls].

## Inställningar för [!UICONTROL Data Source] {#settings}

De här inställningarna avgör hur en [!UICONTROL data source] identifieras, används och delas. Du kan även aktivera felrapportering för inkommande datafiler. Så här slutför du avsnittet [!UICONTROL Data Source Settings]:

1. Markera kryssrutan [!UICONTROL Data Source Setting] om du vill använda ett alternativ för [!UICONTROL data source].
2. Klicka på **[!UICONTROL Save]**.

## Ta bort en Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Ta bort en [!UICONTROL data source] som du inte längre behöver.

>[!NOTE]
>
>Observera följande begränsningar:
>
>* Du kan inte ta bort en [aktiv publik eller Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* För kunder som använder Adobe Analytics: Audience Manager tillåter inte att du tar bort datakällor som skapas automatiskt från [!DNL Analytics]-rapportsviterna. Använd [bastjänsten](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) för att ta bort mappningen för dessa datakällor.

1. Klicka på **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Markera kryssrutan bredvid en eller flera datakällor.
Du kan använda rutan [!UICONTROL Search] för att hitta de önskade datakällorna om du har en lång lista.
1. Klicka på ![](assets/icon_trash.png) och bekräfta sedan borttagningen.


>[!MORELIKETHIS]
>
>* [Inställningar och menyalternativ för Data Source](../features/datasources-list-and-settings.md#settings-menu-options)
