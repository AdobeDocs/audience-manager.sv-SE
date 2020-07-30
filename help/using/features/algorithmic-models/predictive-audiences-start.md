---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-title: Hantera prediktiva målgrupper
solution: Audience Manager
title: Audience Manager Predictive Audiences
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 71e129a39cf85d5f07979ede8f3aa862f93b6512
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 8%

---


# Komma igång med Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

## Skapa en modell för prediktiva målgrupper {#create-predictive-audiences}

Innan du skapar en [!UICONTROL Predictive Audiences] modell måste du bestämma vilken första parts datakälla du vill tilldela dina [!UICONTROL Predictive Audiences] egenskaper och segment till. Du kan använda en befintlig datakälla från första part eller skapa en ny. Mer information om hur du skapar en ny datakälla finns i [Hantera datakällor](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) .

När du vet vilken datakälla du ska använda följer du stegen nedan.

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klicka i [!UICONTROL Predictive Audiences] avsnittet **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definiera sedan de profiler som ni vill klassificera er målgrupp efter. Du kan göra detta genom att välja antingen egenskaper eller segment att bygga profiler från. Använd flikarna [!UICONTROL Traits] och [!UICONTROL Segments] i skärmens övre vänstra hörn för att växla mellan trait- och segments katalog. När du har identifierat de egenskaper eller segment som du vill använda som profiler klickar du på motsvarande **[!UICONTROL Add]** ikon i [!UICONTROL Action] kolumnen.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Du måste välja minst två egenskaper eller två segment för baslinjeegenskaperna. Du kan inte använda en kombination av både egenskaper och segment.
1. Klicka **[!UICONTROL Next]** när du har definierat dina profiler.
1. Välj sedan den första målgrupp du vill klassificera genom att välja en första parts egenskap eller segment för den här målgruppen. Använd flikarna [!UICONTROL Traits] och [!UICONTROL Segments] längst upp till vänster på skärmen för att växla mellan dina egenskaper och segmentkataloger. Välj den första parts trait eller det segment som du vill använda som målgrupp för att lägga till det i modellen.
   ![smart-persona-select-audition](assets/predictive-audiences-audience.png)
1. Klicka **[!UICONTROL Next]** när du har valt målgrupp.
1. Fyll i modellinformationen:
   * **[!UICONTROL Model Name]**: Ange ett beskrivande namn för modellen, som hjälper dig att identifiera den senare. Namnen på segmenten som genereras av modellen börjar med modellens namn.
   * **[!UICONTROL Description]**: Ange en beskrivning av modellen som hjälper dig att identifiera dess användningsfall.
   * **[!UICONTROL Data Source]**: Välj den första parts datakälla som du vill att segmenten från den här modellen ska tilldelas till [!UICONTROL Predictive Audiences] .
   * **[!UICONTROL Profile Merge Rule]**: Välj den [!UICONTROL Profile Merge Rule] som ska tilldelas för alla prediktiva [!UICONTROL segments] som skapas av den här modellen. Om den valda målgruppen är en [!UICONTROL segment]målgrupp rekommenderar vi att du väljer samma målgrupp [!UICONTROL Profile Merge Rule] .
      ![prediktiv målgrupp-spara](assets/predictive-audiences-save.png)
1. Klicka på **[!UICONTROL Save]**.

## Redigera prediktiva målgrupper {#edit-predictive-audiences}

Audience Manager stöder inte redigering av befintliga [!UICONTROL Predictive Audiences] modeller. Om du vill ändra en modells konfiguration måste du skapa en ny modell. Om du har nått gränsen på 10 [!UICONTROL Predictive Audiences] modeller och behöver redigera någon av modellerna, måste du ta bort en modell och skapa en ny.

## Ta bort prediktiva målgrupper {#delete-predictive-audiences}

Om du vill ta bort en [!UICONTROL Predictive Audiences] modell går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, letar reda på den modell som du vill ta bort och klickar på **[!UICONTROL Delete]** ikonen.
