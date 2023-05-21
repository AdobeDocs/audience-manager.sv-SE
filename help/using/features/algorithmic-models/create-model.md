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
source-wordcount: '629'
ht-degree: 1%

---

# Skapa en look-alike-modell {#create-an-algorithmic-model}

Beskriver de obligatoriska och valfria stegen som gör att du kan skapa en [!UICONTROL Look-Alike Model].

## Model Builder-avsnitt

[!UICONTROL Model Builder] består av [!UICONTROL Basic Information] och [!UICONTROL Configuration] -avsnitt. Om du vill skapa en modell fyller du i de obligatoriska fälten i dessa två avsnitt. Spara modellen för att starta algoritmen. [!DNL Audience Manager] skickar ett automatiskt meddelande när den första datakörningen har slutförts. När du har fått e-postmeddelandet kan du gå till [Trait Builder](../../features/traits/about-trait-builder.md) och skapa algoritmiska egenskaper.

>[!NOTE]
>
>* Modelleringsprocessen körs bara en gång om du skapar en modell och inte skapar några egenskaper med den.
>* Skapa modeller från datakällor som innehåller meningsfull information. Modeller med otillräckliga data kommer att köras, men de kommer inte att returnera några resultat.
>* *Gör inte* skapa modeller med andra algoritmiska egenskaper eller segment.
>* Det automatiska e-postmeddelandet skickas endast en gång (efter den första datakörningen).


## Bygg modellen

Följ stegen nedan för att skapa en [!UICONTROL Look-Alike Model]:

1. Gå till **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** och klicka **[!UICONTROL Add New]** i [!UICONTROL Look-Alike Modeling] -avsnitt.
   ![look-alike-add](assets/look-alike-add.png)
1. I [Grundläggande information](../../features/algorithmic-models/create-model.md#basic-information) section
   * Ge modellen ett namn.
   * *(Valfritt)* Ge en kort beskrivning av modellen.
   * Ange modellens status till **[!UICONTROL Active]** eller **[!UICONTROL Inactive]**. Inaktiva modeller kommer inte att köras och kommer inte att generera några data.
      ![look-alike-basic](assets/look-alike-basic.png)
1. I [Konfiguration](../../features/algorithmic-models/create-model.md#configuration) avsnitt:
   * Klicka **[!UICONTROL Browse All Traits]** eller **[!UICONTROL Browse All Segments]** för att markera ett trait eller segment som du vill modellera mot. Sök efter egenskaper efter namn, ID, beskrivning eller datakälla. Klicka på en mapp medan du söker för att begränsa resultatet till den mappen och dess undermappar. Du kan också filtrera egenskaper efter traits-typ ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]och [!UICONTROL Algorithmic]) eller populationstyp ([Enhets-ID](../../reference/ids-in-aam.md) och [Enhets-ID](../../reference/ids-in-aam.md)).
      ![browse-traits](assets/browse-traits.png)
   * Välj en 30-, 60- eller 90-dagars summeringsperiod. Detta anger ett tidsintervall för modellen.
   * The [!UICONTROL TraitWeight] som standard är algoritmen vald.
   * Välj en datakälla på menyn [!UICONTROL Available Data] lista.
   * Klicka **[!UICONTROL Save]** när det är klart.
      ![look-alike-configuration](assets/look-alike-configuration.png)

Titta på videon nedan för att få en detaljerad bild av hur enhetsövergripande mätvärden fungerar.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Grundläggande information för algoritmiska modeller {#basic-information}

<!-- r_model_basic.xml -->

I [!UICONTROL Model Builder], [!UICONTROL Basic Information] gör att du kan skapa nya eller redigera befintliga modeller. Om du vill skapa en ny modell anger du ett namn och går vidare till [!UICONTROL Configuration] inställningar. Beskrivningsfältet är valfritt.

| Fält | Beskrivning |
|---|---|
| **[!UICONTROL Name]** | Ge modellen ett kort logiskt namn som beskriver dess funktion eller syfte. Undvik förkortningar, specialtecken och accenttecken. |
| **[!UICONTROL Description]** | Ett fält för ytterligare beskrivande information om modellen. |
| **[!UICONTROL Status]** | Aktiverar eller inaktiverar modellen (aktiv som standard). |

## Konfiguration {#configuration}

I [!UICONTROL Model Builder], [!UICONTROL Configuration] kan du lägga till egenskaper eller segment i modellen. I det här avsnittet väljer du ett baslinjetrafik eller segment, en summeringsperiod och data från första och tredje parts datakällor.

<!-- r_model_configuration.xml -->

### Förutsättningar

Fyll i de obligatoriska fälten i [!UICONTROL Basic Information] -avsnittet först.

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
   <td colname="col2"> <p>Klicka på trait- eller segment-knappen för att visa en lista över alla egenskaper och segment. Ditt valda segment eller egenskaper blir baslinjen som systemalgoritmerna använder för modellering. </p> <p> <p><b>Anteckning</b>: Välj en fördel, en regelbaserad egenskap eller ett segment som baslinje. Annars körs inte modellerna. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Välj bakåtperiod (2)</b> </p> </td> 
   <td colname="col2"> <p>Anger ett tidsintervall för modellen. Beroende på vad du väljer innehåller och utvärderar algoritmen data från de senaste 30, 60 eller 90 dagarna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Välj algoritm (3)</b> </p> </td> 
   <td colname="col2"> <p>Just nu fungerar Model Builder tillsammans med våra egna <span class="keyword"> Tågbredd</span> Endast algoritm. <span class="keyword"> Audience Manager</span> kan lägga till andra algoritmiska funktioner i efterföljande versioner. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Välj modelldata från datakälla (4)</b> </p> </td> 
   <td colname="col2"> <p>Gör att du kan välja den första och tredje parts datakälla som du vill använda i modellen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Undantag (5)</b> </p> </td> 
   <td colname="col2"> <p>Du kan utesluta egenskaper från de datakällor som du har valt för modellering. Använd <span class="wintitle"> Undantag</span> lista och läsa <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algoritmiska modeller: Uteslutning av trait</a> om du vill veta mer. </p> </td>
  </tr> 
 </tbody>
</table>

Titta på videon nedan för att lära dig hur du skapar en modell som ser likadan ut som hos första part, så att du kan hitta fler egna besökare som ser ut som dina konverterare.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [TraitWeight - introduktion](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

