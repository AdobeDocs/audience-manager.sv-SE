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
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
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

Fyll i följande fält för att slutföra avsnittet [!UICONTROL Data Source Details]:

1. **[!UICONTROL Name]**: Ange ett namn för datakällan.
1. **[!UICONTROL Description]** (valfritt): Ange en beskrivning för datakällan som hjälper dig att definiera rollen eller syftet med datakällan.
1. **[!UICONTROL Integration Code]** (valfritt): Ange en integreringskod. Dessa koder är obligatoriska när du vill:
   * [Skapa en datakälla för olika enheter](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Använd [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE).
   * Arbeta med [profilkopplingsregler](../features/profile-merge-rules/merge-rules-start.md).
1. **[!UICONTROL Namespace]** (skrivskyddad): Det här fältet är skrivskyddat och genereras automatiskt när du sparar datakällan. Om du vill exportera segment från Audience Manager till Experience Platform måste du skapa ett motsvarande [identitetsnamnutrymme](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=sv-SE#manage-namespaces) i Experience Platform och använda det automatiskt genererade värdet som namnutrymmets [identitetssymbol](https://experienceleague.adobe.com/sv/docs/experience-platform/identity/features/namespaces#components-of-a-namespace) i Experience Platform.
1. **[!UICONTROL ID Type]**: Välj vilken typ av ID som den här datakällan ska innehålla:
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (krävs för att skapa en [!UICONTROL Profile Merge Rule]). Observera att för vissa kunder visas alternativen för **[!UICONTROL ID Definition]** i det här valet.
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
>* För kunder som använder Adobe Analytics: Audience Manager tillåter inte att du tar bort datakällor som skapats automatiskt från [!DNL Analytics]-rapportsviterna. Använd [bastjänsten](https://experienceleague.adobe.com/sv/docs/core-services/interface/services/customer-attributes/attributes) för att ta bort mappningen för dessa datakällor.

1. Klicka på **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Markera kryssrutan bredvid en eller flera datakällor.
Du kan använda rutan [!UICONTROL Search] för att hitta de önskade datakällorna om du har en lång lista.
1. Klicka på ![](assets/icon_trash.png) och bekräfta sedan borttagningen.


>[!MORELIKETHIS]
>
>* [Inställningar och menyalternativ för Data Source](../features/datasources-list-and-settings.md#settings-menu-options)
