---
description: Detaljsidan för en enskild trait innehåller en översikt över information som trait name, ID, performance metrics, expressions som definierar trait, segments som den tillhör och trait Audit log. Om du vill visa den här informationen går du till Målgruppsdata > Traits och klickar på namnet på den trait som du vill arbeta med.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Anpassa detaljsida
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Uppdelning av identitetstyp, identitetsuppdelning, rapportering av målgruppsidentitet, enhets-ID, enhets-ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait] informationssida {#trait-details-page}

Informationssidan för en enskild [!UICONTROL trait] ger en översikt över [!UICONTROL trait]-informationen, t.ex. [!UICONTROL trait]-namnet, ID:t, prestandamätningar, uttryck som definierar [!UICONTROL trait], segment som den tillhör och [!UICONTROL trait]-granskningsloggen. Om du vill visa den här informationen går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** och klickar på namnet på [!UICONTROL trait] som du vill arbeta med.

## Hanteringsverktyg för [!UICONTROL Trait] {#trait-management-tools}

Den övre delen av informationssidan för [!UICONTROL trait] innehåller verktyg som du kan använda för att hantera din [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Använd det här alternativet om du vill skapa nya [!UICONTROL rule-based], [!UICONTROL algorithmic] eller [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Använd det här alternativet om du vill ändra konfigurationen för aktuell [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Använd det här alternativet om du vill ta bort den aktuella [!UICONTROL trait] från ditt Audience Manager-konto.
4. **[!UICONTROL Marketplace Recommendations]**: Använd det här alternativet för att hitta liknande [!UICONTROL traits] som den du visar, från [!UICONTROL Audience Marketplace] dataavgifter som du inte prenumererar på. Mer information om hur du navigerar i [&#x200B; och hittar liknande egenskaper finns i &#x200B;](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)Audience Marketplace for Data Buyers[!UICONTROL Marketplace] .

![grundläggande-trait-information](assets/basic-trait-information.png)

## Information om [!UICONTROL Trait] {#basics}

Avsnittet [!UICONTROL Trait Information] innehåller information om obligatoriska och valfria fält som du slutförde när du skapade [!UICONTROL trait]. Detta inkluderar saker som typen [!UICONTROL trait], [!UICONTROL trait] ID, beskrivning, [!UICONTROL data source] och andra metadata. De här detaljerna varierar beroende på [!UICONTROL trait]-typ ([!UICONTROL folder], [!UICONTROL onboarded] eller [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph] innehåller snabböverskådliga prestandamått för din valda [!UICONTROL trait]. Håll markören över en trendlinje om du vill se ytterligare data för den markerade [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] representerar ett antal unika användare som har lagt till den här [!UICONTROL trait] i sin profil under det angivna tidsintervallet. [!UICONTROL Total Trait Population] anger antalet unika användare som för närvarande är kvalificerade för [!UICONTROL trait].

För [!UICONTROL rule-based traits] sker [!UICONTROL trait]-kvalificering i realtid eftersom användare kvalificerar sig för en [!UICONTROL trait] i sin webbläsare.

För [!UICONTROL onboarded traits] inträffar [!UICONTROL trait]-kvalificeringen efter att en inkommande fil har bearbetats, dvs. den inkommande filen [matas in i Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när [!UICONTROL trait]-kvalificeringen inträffar.

[!UICONTROL Trait Graph] visar följande information:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: välj det här alternativet om du vill visa resultat för [!UICONTROL traits] som samlar in data för autentiserade profiler. När du väljer det här alternativet ser du bara data i [!UICONTROL Cross-Device ID]-rapporten och inga data kommer att finnas i [!UICONTROL Device ID]-rapporten.
   * **[!UICONTROL Device ID]**: välj det här alternativet om du vill visa resultat för [!UICONTROL traits] som samlar in data för enhetsprofiler. När du väljer det här alternativet ser du bara data i [!UICONTROL Device ID]-rapporten och inga data kommer att finnas i [!UICONTROL Cross-Device ID]-rapporten.

     ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Antal unika användare som har lagt till [!UICONTROL trait] i sin profil under det angivna tidsintervallet.
* **[!UICONTROL Total Trait Population]**: Antalet unika användare som för närvarande är kvalificerade för [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: De tre första posterna visar de tre [!UICONTROL cross-device data sources] som har högst populationsantal, i fallande ordning. [!UICONTROL trait] Den fjärde posten visar summan av alla andra [!DNL DPUUIDs] ([!DNL CRM IDs]) som är kvalificerade för [!UICONTROL trait], från [!UICONTROL cross-device data sources] som inte finns i de tre översta. Den här rapporten visas bara om du väljer [!UICONTROL Cross-device ID] i listrutan [!UICONTROL Show Results By] längst upp till höger på sidan. Standardalternativet är [!UICONTROL Device ID], där den här rapporten inte visas.

  ![trait-graph](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager visar bara rapporten [!UICONTROL Identity Type Breakdown] om du har [!UICONTROL cross-device] ID:n som är kvalificerade för [!UICONTROL trait].

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait]-uttryck {#trait-expression}

Avsnittet [!UICONTROL Trait Expression] visar vilka villkor som användare måste uppfylla för att kvalificera sig för [!UICONTROL trait]. Dessa regler anges när du [skapar eller redigerar en egenskap](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] segment {#trait-segments}

I avsnittet [!UICONTROL Segments with this Trait] visas alla segment som den markerade [!UICONTROL trait] tillhör. Du kan klicka på ett segmentnamn om du vill se information om det segmentet.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Granska/historiklogg {#trait-audit-history}

För [!UICONTROL rule-based] och [!UICONTROL onboarded traits] visar [!UICONTROL Trait Expression Change History] de senaste 10 ändringarna av [!UICONTROL trait]-uttrycksreglerna och vem som gjorde dem. Om [!UICONTROL trait] har fler än 10 ändringar klickar du på **[!UICONTROL Export to CSV]** för att hämta hela granskningsloggen. Granskningsloggen är inte tillgänglig för [!UICONTROL folder] eller [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] i kolumnen [!UICONTROL By User] innebär att kontot för den användaren har tagits bort.

![](assets/traitHistory.png)
