---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Hantera prediktiva målgrupper
solution: Audience Manager
title: Komma igång med Predictive Audiences
feature: Algoritmiska modeller
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
translation-type: tm+mt
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 7%

---

# Komma igång med Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

## Skapa en prediktiv målgruppsmodell {#create-predictive-audiences}

Innan du skapar en [!UICONTROL Predictive Audiences]-modell måste du bestämma vilken första parts datakälla du vill tilldela dina [!UICONTROL Predictive Audiences]-egenskaper och segment till. Du kan använda en befintlig datakälla från första part eller skapa en ny. Mer information om hur du skapar en ny datakälla finns i [Hantera datakällor](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html).

När du vet vilken datakälla du ska använda följer du stegen nedan.

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klicka på **[!UICONTROL Add New]** i [!UICONTROL Predictive Audiences]-avsnittet.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definiera sedan de profiler som ni vill klassificera er målgrupp efter. Du kan göra detta genom att välja antingen egenskaper eller segment att bygga profiler från. Använd flikarna [!UICONTROL Traits] och [!UICONTROL Segments] i skärmens övre vänstra hörn för att växla mellan trait- och segments katalog. När du har identifierat de egenskaper eller segment som du vill använda som profiler klickar du på motsvarande **[!UICONTROL Add]**-ikon i kolumnen [!UICONTROL Action].
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Du måste välja minst två egenskaper eller två segment för baslinjeegenskaperna. Du kan inte använda en kombination av både egenskaper och segment.
1. Klicka på **[!UICONTROL Next]** när du har definierat dina profiler.
1. Välj sedan den första målgrupp du vill klassificera genom att välja en första parts egenskap eller segment för den här målgruppen. Använd flikarna [!UICONTROL Traits] och [!UICONTROL Segments] i skärmens övre vänstra hörn för att växla mellan dina egenskaper och segmentkataloger. Välj den första parts trait eller det segment som du vill använda som målgrupp för att lägga till det i modellen.
   ![smart-persona-select-audition](assets/predictive-audiences-audience.png)
1. Klicka på **[!UICONTROL Next]** när du har valt målgrupp.
1. Fyll i modellinformationen:
   * **[!UICONTROL Model Name]**: Ange ett beskrivande namn för modellen, som hjälper dig att identifiera den senare. Namnen på segmenten som genereras av modellen börjar med modellens namn.
   * **[!UICONTROL Description]**: Ange en beskrivning av modellen som hjälper dig att identifiera dess användningsfall.
   * **[!UICONTROL Data Source]**: Välj den första parts datakälla som du vill att  [!UICONTROL Predictive Audiences] segmenten från den här modellen ska tilldelas till.
   * **[!UICONTROL Profile Merge Rule]**: Välj det  [!UICONTROL Profile Merge Rule] som ska tilldelas för alla prediktiva  [!UICONTROL segments] som skapas av den här modellen. Om den valda målgruppen är en [!UICONTROL segment] rekommenderar vi att du väljer samma [!UICONTROL Profile Merge Rule] som målgruppen.
      ![prediktiv målgrupp-spara](assets/predictive-audiences-save.png)
1. Klicka på **[!UICONTROL Save]**.

## Prediktiva målgruppsmodeller för kloning och redigering {#clone-predictive-audiences}

Audience Manager stöder inte redigering av befintliga [!UICONTROL Predictive Audiences]-modeller. Om du vill ändra en modells konfiguration kan du skapa en klon av en befintlig modell och redigera den. Så här kan du göra:

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Klicka på namnet på den [!UICONTROL Predictive Audiences]-modell som du vill klona.
3. Klicka på knappen **[!UICONTROL Clone]** längst upp till vänster på skärmen.
   ![prediktiv-audiences-clone](assets/predictive-audiences-clone.png)
4. När du har klonat modellen tas du till sidan [!DNL Save & Configure] i den klonade modellen. På den här sidan kan du ändra [!UICONTROL data source] och den tilldelade[!UICONTROL Profile Merge Rule] modellen. Om du vill redigera personerna och målgruppen för den klonade modellen använder du knapparna [!UICONTROL Back] och [!UICONTROL Next] för att navigera mellan de tre flikarna, eller klickar på de tre fliknamnen

   ![prediktiv-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. När du är klar med redigeringen av en modell klickar du på **[!UICONTROL Save]**.

## Tar bort prediktiva målgrupper {#delete-predictive-audiences}

Om du vill ta bort en [!UICONTROL Predictive Audiences]-modell går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, letar reda på modellen som du vill ta bort och klickar på ikonen **[!UICONTROL Delete]**.
