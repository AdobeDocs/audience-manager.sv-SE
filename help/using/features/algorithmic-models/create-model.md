---
description: Beskriver de obligatoriska och valfria stegen som gör att du kan skapa en algoritmisk modell i Model Builder.
keywords: algo how works
seo-description: Beskriver de obligatoriska och valfria stegen som gör att du kan skapa en algoritmisk modell i Model Builder.
seo-title: Skapa en algoritmisk modell
solution: Audience Manager
title: Skapa en algoritmisk modell
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
translation-type: tm+mt
source-git-commit: 35bad7e676aa1d4143f5d114a1eff85d6aba5f1d

---


# Skapa en look-Alike-modell {#create-an-algorithmic-model}

Beskriver de obligatoriska och valfria stegen som du kan använda för att skapa en [!UICONTROL Look-Alike Model].

## Model Builder-avsnitt

[!UICONTROL Model Builder] består av avsnitten [!UICONTROL Basic Information] och [!UICONTROL Configuration] . Om du vill skapa en modell fyller du i de obligatoriska fälten i dessa två avsnitt. Spara modellen för att starta algoritmen. [!DNL Audience Manager] skickar ett automatiskt meddelande när den första datakörningen har slutförts. När du har fått e-postmeddelandet kan du gå till [Trait Builder](../../features/traits/about-trait-builder.md) och skapa algoritmiska egenskaper.

>[!NOTE]
>
>* Modelleringsprocessen körs bara en gång om du skapar en modell och inte skapar några egenskaper med den.
>* Skapa modeller från datakällor som innehåller meningsfull information. Modeller med otillräckliga data kommer att köras, men returnerar inga resultat.
>* *Skapa inte* modeller med andra algoritmiska egenskaper eller segment.
>* Det automatiska e-postmeddelandet skickas endast en gång (efter den första datakörningen).


## Bygg modellen

Följ stegen nedan för att skapa en [!UICONTROL Look-Alike Model]:

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** och klicka **[!UICONTROL Add New]** i [!UICONTROL Look-Alike Modeling] avsnittet.
   ![look-alike-add](assets/look-alike-add.png)
1. I avsnittet [Grundläggande information](../../features/algorithmic-models/create-model.md#basic-information)
   * Ge modellen ett namn.
   * *(Valfritt)* Ge en kort beskrivning av modellen.
   * Ange status för modellen till **[!UICONTROL Active]** eller **[!UICONTROL Inactive]**. Inaktiva modeller kommer inte att köras och kommer inte att generera några data.
      ![look-alike-basic](assets/look-alike-basic.png)
1. I avsnittet [Konfiguration](../../features/algorithmic-models/create-model.md#configuration) :
   * Klicka **[!UICONTROL Browse All Traits]** eller **[!UICONTROL Browse All Segments]** för att markera ett spår eller segment som du vill modellera mot. Sök efter egenskaper efter namn, ID, beskrivning eller datakälla. Klicka på en mapp medan du söker för att begränsa resultatet till den mappen och dess undermappar. Du kan också filtrera egenskaper efter trait-typ ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]och [!UICONTROL Algorithmic]) eller populationstyp ([enhets-ID](../../reference/ids-in-aam.md) och [korsenhets-ID](../../reference/ids-in-aam.md)).
      ![browse-traits](assets/browse-traits.png)
   * Välj en 30-, 60- eller 90-dagars summeringsperiod. Detta anger ett tidsintervall för modellen.
   * Algoritmen [!UICONTROL TraitWeight] är markerad som standard.
   * Välj en datakälla i [!UICONTROL Available Data] listan.
   * Klicka **[!UICONTROL Save]** när du är klar.
      ![look-alike-configuration](assets/look-alike-configuration.png)

## Grundläggande information för algoritmiska modeller {#basic-information}

<!-- r_model_basic.xml -->

Med [!UICONTROL Model Builder]inställningarna kan du [!UICONTROL Basic Information] skapa nya eller redigera befintliga modeller. Om du vill skapa en ny modell anger du ett namn och går vidare till [!UICONTROL Configuration] inställningarna. Beskrivningsfältet är valfritt.

| Fält | Beskrivning |
|---|---|
| **[!UICONTROL Name]** | Ge modellen ett kort logiskt namn som beskriver dess funktion eller syfte. Undvik förkortningar, specialtecken och accenttecken. |
| **[!UICONTROL Description]** | Ett fält för ytterligare beskrivande information om modellen. |
| **[!UICONTROL Status]** | Aktiverar eller inaktiverar modellen (aktiv som standard). |

## Konfiguration {#configuration}

I [!UICONTROL Model Builder]avsnittet kan du lägga till egenskaper eller segment i modellen [!UICONTROL Configuration] . I det här avsnittet väljer du ett baslinjetrafik eller segment, en summeringsperiod och data från första och tredje parts datakällor.

<!-- r_model_configuration.xml -->

### Förutsättningar

Fyll i de obligatoriska fälten i [!UICONTROL Basic Information] avsnittet först.

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
   <td colname="col2"> <p>Klicka på trait- eller segment-knappen för att visa en lista över alla egenskaper och segment. Ditt valda segment eller egenskaper blir baslinjen som systemalgoritmerna använder för modellering. </p> <p> <p><b>Obs</b>:  Välj en fördel, en regelbaserad egenskap eller ett segment som baslinje. Annars körs inte modellerna. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Välj bakåtperiod (2)</b> </p> </td> 
   <td colname="col2"> <p>Anger ett tidsintervall för modellen. Beroende på vad du väljer innehåller och utvärderar algoritmen data från de senaste 30, 60 eller 90 dagarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Välj algoritm (3)</b> </p> </td> 
   <td colname="col2"> <p>I nuläget fungerar Model Builder endast med vår egen <span class="keyword"> Trait Weight</span> -algoritm. <span class="keyword"> Audience Manager</span> kan lägga till andra algoritmiska funktioner i efterföljande versioner. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Välj modelldata från datakälla (4)</b> </p> </td> 
   <td colname="col2"> <p>Gör att du kan välja den första och tredje parts datakälla som du vill använda i modellen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Undantag (5)</b> </p> </td> 
   <td colname="col2"> <p>Du kan utesluta egenskaper från de datakällor som du har valt för modellering. Använd listan <span class="wintitle"> Undantag</span> och läs <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> algoritmiska modeller: Uteslutning</a> av trait om du vill veta mer. </p> </td>
  </tr> 
 </tbody>
</table>

Titta på videon nedan för att lära dig hur du skapar en modell som ser likadan ut som hos första part, så att du kan hitta fler egna besökare som ser ut som dina konverterare.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [TraitWeight - introduktion](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

