---
description: Om du vill skapa en ny datakälla går du till Målgruppsdata > Datakällor > Lägg till ny och slutför stegen för varje avsnitt som beskrivs här. Administratörsbehörighet krävs för att skapa en datakälla.
keywords: data sources;manage data source;audience manager data source
seo-description: Om du vill skapa en ny datakälla går du till Målgruppsdata > Datakällor > Lägg till ny och slutför stegen för varje avsnitt som beskrivs här. Administratörsbehörighet krävs för att skapa en datakälla.
seo-title: Skapa en datakälla
solution: Audience Manager
title: Hantera datakällor
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Hantera [!UICONTROL Data Sources] {#manage-data-sources}

## Skapa en [!UICONTROL Data Source] {#create-data-source}

Om du vill skapa en ny [!UICONTROL data source]sida går du till **[!UICONTROL Audience Data > Data Sources > Add New]** och slutför stegen som beskrivs här. Administratörsbehörighet krävs för att skapa en [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Mer information om de olika kontrollerna finns i Inställningar för [datakälla och Menyalternativ](../features/datasources-list-and-settings.md#settings-menu-options) .

## [!UICONTROL Data Source] Detaljer {#details}

Så här slutför du [!UICONTROL Data Source Details] avsnittet:

1. Namnge [!UICONTROL data source].
1. *(Valfritt)* Beskriv [!UICONTROL data source]. En kortfattad beskrivning hjälper dig att definiera rollen eller syftet med [!UICONTROL data source].
1. Ange en [!UICONTROL integration code]. Vanligtvis är [!UICONTROL integration codes] de valfria. De krävs när du vill:

   * [Skapa en datakälla](../features/profile-merge-rules/merge-rules-start.md#create-data-source)för olika enheter.
   * Använd [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * Arbeta med [profilkopplingsregler](../features/profile-merge-rules/merge-rules-start.md).

1. Välj en **[!UICONTROL ID Type]**. [!UICONTROL ID Type] bland annat:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Krävs för att skapa en [!UICONTROL Profile Merge Rule]). Observera att för vissa kunder visar det här valet **[!UICONTROL ID Definition]** alternativen.

1. Välj ett **[!UICONTROL ID Definition]** alternativ. Alternativen är:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Dataexportkontroller](../features/data-export-controls.md) är valfria klassificeringsregler som du kan tillämpa på en [!UICONTROL data source] och [!UICONTROL destination]. De förhindrar dig från att skicka data till en [!UICONTROL destination] när den åtgärden bryter mot en datasekretess eller användaravtal. Hoppa över det här avsnittet om du inte använder det [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Inställningar {#settings}

Dessa inställningar avgör hur en bild [!UICONTROL data source] identifieras, används och delas. Du kan även aktivera felrapportering för inkommande datafiler. Så här slutför du [!UICONTROL Data Source Settings] avsnittet:

1. Markera en [!UICONTROL Data Source Setting] kryssruta om du vill använda ett alternativ på din [!UICONTROL data source].
2. Klicka på **[!UICONTROL Save]**.

## Ta bort en datakälla {#delete-data-source}

<!-- t_datasource_delete.xml -->

Ta bort en [!UICONTROL data source] som du inte längre behöver.

>[!NOTE]
>
>Observera följande begränsningar:
>
>* Du kan inte ta bort en [aktiv publik eller en synkroniserad egenskap](../features/traits/client-activity-synced-audience-traits.md)för datakälla.
>* För kunder som använder Adobe Analytics: Audience Manager tillåter inte att du tar bort datakällor som skapats automatiskt från dina [!DNL Analytics] rapportsviter. Använd [bastjänsten](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) för att ta bort mappningen för dessa datakällor.


1. Klicka på **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Markera kryssrutan bredvid en eller flera datakällor.
Du kan använda [!UICONTROL Search] rutan för att hitta de önskade datakällorna om du har en lång lista.
1. Klicka ![](assets/icon_trash.png)och bekräfta sedan borttagningen.


>[!MORELIKETHIS]
>
>* [Inställningar för datakälla och menyalternativ](../features/datasources-list-and-settings.md#settings-menu-options)