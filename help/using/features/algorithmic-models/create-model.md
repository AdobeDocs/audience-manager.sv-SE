---
description: Beskriver de obligatoriska och valfria stegen som gör att du kan skapa en algoritmisk modell i Model Builder.
keywords: hur fungerar
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Skapa en algoritmisk modell
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# Skapa en lookalike-modell {#create-an-algorithmic-model}

Beskriver de obligatoriska och valfria stegen som gör att du kan skapa en [!UICONTROL Look-Alike Model].

## Model Builder-avsnitt

[!UICONTROL Model Builder] består av avsnitten [!UICONTROL Basic Information] och [!UICONTROL Configuration]. Om du vill skapa en modell fyller du i de obligatoriska fälten i dessa två avsnitt. Spara modellen för att starta algoritmen. [!DNL Audience Manager] skickar ett automatiskt meddelande till dig när den första datakörningen har slutförts. När du har fått e-postmeddelandet kan du gå till [Trait Builder](../../features/traits/about-trait-builder.md) och skapa algoritmiska egenskaper.

>[!NOTE]
>
>* Modelleringsprocessen körs bara en gång om du skapar en modell och inte skapar några egenskaper med den.
>* Skapa modeller från datakällor som innehåller meningsfull information. Modeller med otillräckliga data kommer att köras, men returnerar inga resultat.
>* *Skapa inte* modeller med andra algoritmiska egenskaper eller segment.
>* Det automatiska e-postmeddelandet skickas endast en gång (efter den första datakörningen).

## Bygg modellen

Följ stegen nedan för att skapa en [!UICONTROL Look-Alike Model]:

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** och klicka på **[!UICONTROL Add New]** i avsnittet [!UICONTROL Look-Alike Modeling].
   ![look-alike-add](assets/look-alike-add.png)
1. I avsnittet [Grundläggande information](../../features/algorithmic-models/create-model.md#basic-information)
   * Ge modellen ett namn.
   * *(Valfritt)* Ange en kort beskrivning av modellen.
   * Ange modellens status till **[!UICONTROL Active]** eller **[!UICONTROL Inactive]**. Inaktiva modeller kommer inte att köras och kommer inte att generera några data.
     ![look-alike-basic](assets/look-alike-basic.png)
1. I avsnittet [Konfiguration](../../features/algorithmic-models/create-model.md#configuration):
   * Klicka på **[!UICONTROL Browse All Traits]** eller **[!UICONTROL Browse All Segments]** för att välja ett spår eller segment som du vill modellera mot. Sök efter egenskaper efter namn, ID, beskrivning eller datakälla. Klicka på en mapp medan du söker för att begränsa resultatet till den mappen och dess undermappar. Du kan också filtrera egenskaper efter trait-typ ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded] och [!UICONTROL Algorithmic]) eller populationstyp ([enhets-ID](../../reference/ids-in-aam.md) och [Cross-Device ID](../../reference/ids-in-aam.md)).
     ![browse-traits](assets/browse-traits.png)
   * Välj en 30, 60 eller 90 dagars summeringsperiod. Detta anger ett tidsintervall för modellen.
   * Algoritmen [!UICONTROL TraitWeight] är markerad som standard.
   * Välj en datakälla i listan [!UICONTROL Available Data].
   * Klicka på **[!UICONTROL Save]** när du är klar.
     ![look-alike-configuration](assets/look-alike-configuration.png)

Titta på videon nedan för att få en detaljerad bild av hur enhetsövergripande mätvärden fungerar.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=sv-SE)

## Grundläggande information för algoritmiska modeller {#basic-information}

<!-- r_model_basic.xml -->

I [!UICONTROL Model Builder] kan du med inställningarna för [!UICONTROL Basic Information] skapa nya eller redigera befintliga modeller. Om du vill skapa en ny modell anger du ett namn och går vidare till inställningarna för [!UICONTROL Configuration]. Beskrivningsfältet är valfritt.

| Fält | Beskrivning |
|---|---|
| **[!UICONTROL Name]** | Ge modellen ett kort logiskt namn som beskriver dess funktion eller syfte. Undvik förkortningar, specialtecken och accenttecken. |
| **[!UICONTROL Description]** | Ett fält för ytterligare beskrivande information om modellen. |
| **[!UICONTROL Status]** | Aktiverar eller inaktiverar modellen (aktiv som standard). |

## Konfiguration {#configuration}

I [!UICONTROL Model Builder] kan du med [!UICONTROL Configuration]-avsnittet lägga till egenskaper eller segment i modellen. I det här avsnittet väljer du ett baslinjetrafik eller segment, en summeringsperiod och data från första och tredje parts datakällor.

<!-- r_model_configuration.xml -->

### Förutsättningar

Fyll i de obligatoriska fälten i avsnittet [!UICONTROL Basic Information] först.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fält </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Välj ett baslinjestöd eller segment (1)</b> </p> </td> 
   <td colname="col2"> <p>Klicka på trait- eller segment-knappen för att visa en lista över alla egenskaper och segment. Ditt valda segment eller egenskaper blir baslinjen som systemalgoritmerna använder för modellering. </p> <p> <p><b>Obs!</b>: Välj en fördel, en regelbaserad egenskap eller ett segment som baslinje. Annars körs inte modellerna. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Välj summeringsperiod (2)</b> </p> </td> 
   <td colname="col2"> <p>Anger ett tidsintervall för modellen. Beroende på vad du väljer innehåller och utvärderar algoritmen data från de senaste 30, 60 eller 90 dagarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Välj algoritm (3)</b> </p> </td> 
   <td colname="col2"> <p>För närvarande fungerar Model Builder endast med vår egna <span class="keyword"> Trait Weight </span> -algoritm. <span class="keyword"> Audience Manager</span> kan lägga till andra algoritmiska funktioner i efterföljande versioner. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Välj modelldata från Data Source (4)</b> </p> </td> 
   <td colname="col2"> <p>Gör att du kan välja den första och tredje parts datakälla som du vill använda i modellen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Undantag (5)</b> </p> </td> 
   <td colname="col2"> <p>Du kan utesluta egenskaper från de datakällor som du har valt för modellering. Använd listan <span class="wintitle"> Undantag </span> och läs <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> algoritmiska modeller: Uteslutning av trait </a> om du vill veta mer. </p> </td>
  </tr> 
 </tbody>
</table>

Titta på videon nedan för att lära dig hur du skapar en modell som ser likadan ut som hos första part, så att du kan hitta fler av dina egna besökare som ser ut som dina konverterare.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [Om TraitWeight](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
