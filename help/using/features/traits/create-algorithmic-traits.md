---
description: Beskriver hur du konfigurerar steg och funktioner som är unika för processen att skapa algoritmiska egenskaper.
seo-description: Beskriver hur du konfigurerar steg och funktioner som är unika för processen att skapa algoritmiska egenskaper.
seo-title: Skapa algoritmiska traits
solution: Audience Manager
title: Skapa algoritmiska traits
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# Skapa algoritmiska traits {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Om du vill skapa en algoritmisk egenskap går du till [!UICONTROL Traits] och följer stegen nedan:

1. Klicka **[!UICONTROL Create New Trait]** och välj **[!UICONTROL Algorithmic]** i listrutan.
1. I avsnittet [Grundläggande information](../../features/traits/create-onboarded-rule-based-traits.md)
   * Ge trait ett namn.
   * Välj en datakälla.
   * Välj en lagringsmapp.
1. Expandera [!UICONTROL Configuration] rutan och klicka **[!UICONTROL Browse All Models]**.
Då öppnas ett nytt fönster där du kan välja den modell som du vill använda med egenskapen.
1. Markera en modell och klicka på **[!UICONTROL Add Selected Model to Trait]**.
När du lägger till modellen visas inställningarna för räckvidd och precision.
1. Välj räckvidd eller precision som mål och välj ett värde i respektive listruta. Klicka **[!UICONTROL Save]** när du är klar.

## Konfigurationsinställningar för algoritmiska egenskaper {#configure-settings}

I [!UICONTROL Trait Builder][!UICONTROL Configuration] avsnittet kan du associera en algoritmisk modell med en egenskap. Slutför processen med att skapa algoritmiska egenskaper genom att markera en modell och välja ett mål för räckvidd eller precision.

### Förutsättningar

<!-- r_algo_trait_config_section.xml -->

* [Skapa en look-alike-modell](../../features/algorithmic-models/create-model.md).
* Vänta på e-postmeddelandet som talar om för dig att körningen av modelldata har slutförts.
* Fyll i de obligatoriska fälten i avsnittet [Grundläggande information](../../features/traits/create-onboarded-rule-based-traits.md) .

### Konfigurationsfält och inställningar

| Gränssnittselement | Förklaring |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Klicka på **[!UICONTROL Update]** knappen för att öppna modellfönstret. I fönstret väljer du den algoritmiska modell som du vill använda för att skapa egenskapen. |
| **[!UICONTROL Select Goal Accuracy]** | Välj det här alternativet om du vill skapa en egenskap baserat på noggrannhet. Noggrannhet är ett poängvärde som anger hur nära en potentiell användare är din baslinje. Precisionsskalan varierar från 0 (minst korrekt) till 1 (mest korrekt). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | I det här avsnittet, som finns till höger, visas upp till 21 rader med numeriska data som visar modellens noggrannhet och målvärden. |
| **[!UICONTROL Reach and Accuracy Slider]** | Längst ned i diagrammet kan du med skjutreglaget ange ett numeriskt värde för räckvidd och precision. Du kan ställa in skjutreglaget och sedan välja målknappen för räckvidd eller precision för att skapa ett drag. |

>[!MORELIKETHIS]
>
>* [Precision och räckvidd](../../features/traits/trait-accuracy-reach.md)

