---
description: Med Predictive Audiences kan ni klassificera okända målgrupper i distinkta personas i realtid med datavetenskap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Komma igång med Predictive Audiences
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 4%

---

# Komma igång med Predictive Audiences {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

## Skapa en modell för prediktiva målgrupper {#create-predictive-audiences}

Innan du skapar en [!UICONTROL Predictive Audiences] måste du bestämma vilken datakälla du vill tilldela [!UICONTROL Predictive Audiences] egenskaper och segment till. Du kan använda en befintlig datakälla från första part eller skapa en ny. Se [Hantera datakällor](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) om du vill ha mer information om hur du skapar en ny datakälla från första part.

När du vet vilken datakälla du ska använda följer du stegen nedan.

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. I [!UICONTROL Predictive Audiences] avsnitt, klicka **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definiera sedan de profiler som ni vill klassificera er målgrupp efter. Du kan göra detta genom att välja antingen egenskaper eller segment att bygga profiler från. Använd [!UICONTROL Traits] och [!UICONTROL Segments] i skärmens övre vänstra hörn för att växla mellan trait och segments katalog. När du har identifierat de egenskaper eller segment som du vill använda som profiler klickar du på motsvarande **[!UICONTROL Add]** ikonen i [!UICONTROL Action] kolumn.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >Du måste välja minst två egenskaper eller två segment för baslinjeegenskaperna. Du kan inte använda en kombination av både egenskaper och segment.
1. Klicka **[!UICONTROL Next]** efter att du har definierat din personlighet.
1. Välj sedan den första målgrupp du vill klassificera genom att välja en första parts egenskap eller segment för den här målgruppen. Använd [!UICONTROL Traits] och [!UICONTROL Segments] i skärmens övre vänstra hörn för att växla mellan dina egenskaper och segmentkataloger. Välj den första parts trait eller det segment som du vill använda som målgrupp för att lägga till det i modellen.
   ![smart-persona-select-audition](assets/predictive-audiences-audience.png)
1. Klicka **[!UICONTROL Next]** efter att ni har valt er målgrupp.
1. Fyll i modellinformationen:
   * **[!UICONTROL Model Name]**: Ange ett beskrivande namn för modellen, som hjälper dig att identifiera den senare. Namnen på segmenten som genereras av modellen börjar med modellens namn.
   * **[!UICONTROL Description]**: Ange en beskrivning av modellen som hjälper dig att identifiera dess användningsfall.
   * **[!UICONTROL Data Source]**: Välj den första datakälla du vill använda [!UICONTROL Predictive Audiences] segment från den här modellen som ska tilldelas.
   * **[!UICONTROL Profile Merge Rule]**: Välj [!UICONTROL Profile Merge Rule] tilldelas för alla prediktiva [!UICONTROL segments] som har skapats av den här modellen. Om den valda målgruppen är en [!UICONTROL segment]rekommenderar vi att du väljer samma [!UICONTROL Profile Merge Rule] av målgruppen.
      ![prediktiv målgrupp-spara](assets/predictive-audiences-save.png)
1. Klicka på **[!UICONTROL Save]**.

## Kloning och redigering - prediktiva målgruppsmodeller {#clone-predictive-audiences}

Audience Manager stöder inte redigering av befintliga [!UICONTROL Predictive Audiences] modeller. Om du vill ändra en modells konfiguration kan du skapa en klon av en befintlig modell och redigera den. Så här kan du göra:

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Klicka på namnet på [!UICONTROL Predictive Audiences] modell som du vill klona.
3. Klicka på **[!UICONTROL Clone]** i skärmens övre vänstra sida.
   ![prediktiv-audiences-clone](assets/predictive-audiences-clone.png)
4. När du har klonat modellen tas du till [!DNL Save & Configure] sida för den klonade modellen. På den här sidan kan du ändra [!UICONTROL data source] och de tilldelade[!UICONTROL Profile Merge Rule] av modellen. Om du vill redigera personerna och målgruppen för den klonade modellen använder du [!UICONTROL Back] och [!UICONTROL Next] för att navigera mellan de tre flikarna, eller klicka på de tre fliknamnen

   ![prediktiv-audiences-clone-navigate](assets/predictive-audiences-clone-navigate.png)

5. När du är klar med redigeringen av en modell klickar du på **[!UICONTROL Save]**.

## Ta bort prediktiva målgrupper {#delete-predictive-audiences}

Så här tar du bort en [!UICONTROL Predictive Audiences] modell, gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** söker du efter den modell som du vill ta bort och klickar på **[!UICONTROL Delete]** ikon.
