---
description: Detaljsidan för en enskild trait innehåller en översikt över information som trait name, ID, performance metrics, expressions som definierar trait, segments som den tillhör och trait Audit log. Om du vill visa den här informationen går du till Målgruppsdata > Traits och klickar på namnet på den trait som du vill arbeta med.
seo-description: Detaljsidan för en enskild trait innehåller en översikt över information som trait name, ID, performance metrics, expressions som definierar trait, segments som den tillhör och trait Audit log. Om du vill visa den här informationen går du till Målgruppsdata > Traits och klickar på namnet på den trait du vill arbeta med.
seo-title: Anpassa detaljsida
solution: Audience Manager
title: Anpassa detaljsida
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---


# [!UICONTROL Trait] Detaljsida {#trait-details-page}

Detaljsidan för en enskild person [!UICONTROL trait] innehåller en översikt över [!UICONTROL trait] detaljer, t.ex. [!UICONTROL trait] namn, ID, prestandamått, uttryck som definierar [!UICONTROL trait], segment som den tillhör och [!UICONTROL trait] granskningsloggen. Om du vill visa den här informationen går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** och klickar på namnet på det [!UICONTROL trait] du vill arbeta med.

## [!UICONTROL Trait] Hanteringsverktyg {#trait-management-tools}

Den översta delen av informationssidan innehåller de verktyg som du kan använda för att hantera dina [!UICONTROL trait] [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Använd det här alternativet om du vill skapa nytt [!UICONTROL rule-based], [!UICONTROL algorithmic]eller [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Använd det här alternativet om du vill ändra konfigurationen för aktuell [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Använd det här alternativet om du vill ta bort den aktuella filen [!UICONTROL trait] från ditt Audience Manager-konto.
4. **[!UICONTROL Marketplace Recommendations]**: Använd det här alternativet för att hitta liknande [!UICONTROL traits] den som du visar, från [!UICONTROL Audience Marketplace] dataavgifter som du inte prenumererar på. Mer information om hur du navigerar i [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) finns i [!UICONTROL Marketplace] .

![grundläggande information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Information {#basics}

I avsnittet visas information om obligatoriska och valfria fält som du har fyllt i när du skapade [!UICONTROL Trait Information] [!UICONTROL trait]. Detta inkluderar exempelvis [!UICONTROL trait] typ, [!UICONTROL trait] ID, beskrivning [!UICONTROL data source]och andra metadata. Dessa detaljer varierar beroende på [!UICONTROL trait] typ ([!UICONTROL folder], [!UICONTROL onboarded]eller [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Här [!UICONTROL Trait Graph] finns en överskådlig prestandamätning för det du valt [!UICONTROL trait]. Håll markören över en trendlinje om du vill se ytterligare data för den markerade [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] representerar ett antal unika användare som har lagt till det här [!UICONTROL trait] i sin profil under det angivna tidsintervallet. Anger [!UICONTROL Total Trait Population] antalet unika användare som för närvarande är kvalificerade för detta [!UICONTROL trait].

För [!UICONTROL rule-based traits]detta sker [!UICONTROL trait] kvalificeringen i realtid eftersom användarna kvalificerar sig för en [!UICONTROL trait] i sina webbläsare.

Det [!UICONTROL onboarded traits]innebär att [!UICONTROL trait] kvalificeringen sker efter att en inkommande fil har bearbetats, dvs. den inkommande filen [matas in i Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när [!UICONTROL trait] kvalificeringen görs.

Följande information [!UICONTROL Trait Graph] visas:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Välj det här alternativet om du vill se resultat för [!UICONTROL traits] att samla in data för autentiserade profiler. När du väljer det här alternativet visas bara data i [!UICONTROL Cross-Device ID] rapporten, och inga data kommer att finnas under [!UICONTROL Device ID] rapporten.
   * **[!UICONTROL Device ID]**: Välj det här alternativet om du vill se resultat för [!UICONTROL traits] att samla in data för enhetsprofiler. När du väljer det här alternativet visas bara data i [!UICONTROL Device ID] rapporten, och inga data kommer att finnas under [!UICONTROL Cross-Device ID] rapporten.

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Antal unika användare som har lagt till detta [!UICONTROL trait] i sin profil under det angivna tidsintervallet.
* **[!UICONTROL Total Trait Population]**: Antalet unika användare som för närvarande är kvalificerade för detta [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: De första tre posterna visar de tre översta [!UICONTROL cross-device data sources] med det högsta populationsantalet som har kvalificerat för [!UICONTROL trait], i fallande ordning. Den fjärde posten visar summan av alla andra [!DNL DPUUIDs] ([!DNL CRM IDs]) som är kvalificerade för [!UICONTROL trait], från [!UICONTROL cross-device data sources] som inte finns i de tre översta. Den här rapporten visas bara om du väljer [!UICONTROL Cross-device ID] i den [!UICONTROL Show Results By] nedrullningsbara menyn längst upp till höger på sidan. Standardalternativet är [!UICONTROL Device ID]där den här rapporten inte visas.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager visar bara [!UICONTROL Identity Type Breakdown] rapporten om du har [!UICONTROL cross-device] ID:n som är kvalificerade för [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Uttryck {#trait-expression}

I det här [!UICONTROL Trait Expression] avsnittet visas vilka villkor som användarna måste uppfylla för att kvalificera sig för [!UICONTROL trait]. Dessa regler anges när du [skapar eller redigerar en egenskap](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segment {#trait-segments}

I [!UICONTROL Segments with this Trait] avsnittet visas alla segment som det markerade [!UICONTROL trait] tillhör. Du kan klicka på ett segmentnamn om du vill se information om det segmentet.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Gransknings-/historiklogg {#trait-audit-history}

För [!UICONTROL rule-based] och [!UICONTROL onboarded traits]visar [!UICONTROL Trait Expression Change History] den senaste 10 ändringen av [!UICONTROL trait] uttrycksregler och vem som gjorde dem. Om du har [!UICONTROL trait] fler än 10 ändringar klickar du på **[!UICONTROL Export to CSV]** för att hämta hela granskningsloggen. Granskningsloggen är inte tillgänglig för [!UICONTROL folder] eller [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] i [!UICONTROL By User] kolumnen betyder att kontot för den användaren har tagits bort.

![](assets/traitHistory.png)