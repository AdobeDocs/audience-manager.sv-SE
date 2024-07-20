---
description: Beskriver hur du konfigurerar steg och funktioner som är unika för processen att skapa algoritmiska egenskaper.
seo-description: Describes set up steps and features unique to the algorithmic trait creation process.
seo-title: Create Algorithmic Traits
solution: Audience Manager
title: Skapa algoritmiska egenskaper
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
exl-id: dc799688-e38b-469b-bc55-507df0d28f43
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 0%

---

# Skapa algoritmiska egenskaper {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Om du vill skapa en algoritmisk egenskap går du till [!UICONTROL Traits] och följer stegen nedan:

1. Klicka på **[!UICONTROL Create New Trait]** och välj **[!UICONTROL Algorithmic]** i listrutan.
1. I avsnittet [Grundläggande information](../../features/traits/create-onboarded-rule-based-traits.md)
   * Ge trait ett namn.
   * Välj en datakälla.
   * Välj en lagringsmapp.
1. Expandera rutan [!UICONTROL Configuration] och klicka på **[!UICONTROL Browse All Models]**.
Då öppnas ett nytt fönster där du kan välja den modell som du vill använda med egenskapen.
1. Välj en modell och klicka på **[!UICONTROL Add Selected Model to Trait]**.
När du lägger till modellen visas inställningarna för räckvidd och precision.
1. Välj räckvidd eller precision som mål och välj ett värde i respektive listruta. Klicka på **[!UICONTROL Save]** när du är klar.

## Konfigurationsinställningar för algoritmiska egenskaper {#configure-settings}

I [!UICONTROL Trait Builder] kan du associera en algoritmisk modell med en egenskap i avsnittet [!UICONTROL Configuration]. Slutför processen med att skapa algoritmiska egenskaper genom att markera en modell och välja ett mål för räckvidd eller precision.

### Förutsättningar

<!-- r_algo_trait_config_section.xml -->

* [Skapa en look-Alike-modell](../../features/algorithmic-models/create-model.md).
* Vänta på e-postmeddelandet som talar om för dig att körningen av modelldata har slutförts.
* Fyll i de obligatoriska fälten i avsnittet [Grundläggande information](../../features/traits/create-onboarded-rule-based-traits.md).

### Konfigurationsfält och inställningar

| Gränssnittselement | Förklaring |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Klicka på knappen **[!UICONTROL Update]** för att öppna modellfönstret. I fönstret väljer du den algoritmiska modell som du vill använda för att skapa egenskapen. |
| **[!UICONTROL Select Goal Accuracy]** | Välj det här alternativet om du vill skapa en egenskap baserat på noggrannhet. Noggrannhet är ett poängvärde som anger hur nära en potentiell användare är din baslinje. Precisionsskalan varierar från 0 (minst korrekt) till 1 (mest korrekt). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | I det här avsnittet, som finns till höger, visas upp till 21 rader med numeriska data som visar modellens noggrannhet och målvärden. |
| **[!UICONTROL Reach and Accuracy Slider]** | Längst ned i diagrammet kan du med skjutreglaget ange ett numeriskt värde för räckvidd och precision. Du kan ställa in skjutreglaget och sedan välja målknappen för räckvidd eller precision för att skapa ett drag. |

>[!MORELIKETHIS]
>
>* [Precision och räckvidd](../../features/traits/trait-accuracy-reach.md)
