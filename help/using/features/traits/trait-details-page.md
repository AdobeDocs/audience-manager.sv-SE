---
description: Detaljsidan för en enskild trait innehåller en översikt över information som trait name, ID, performance metrics, expressions som definierar trait, segments som den tillhör och trait Audit log. Om du vill visa den här informationen går du till Målgruppsdata > Traits och klickar på namnet på den trait du vill arbeta med.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Informationssida för traits
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Uppdelning av identitetstyp, identitetsuppdelning, rapportering av målgruppsidentitet, enhets-ID, enhets-ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] Detaljsida {#trait-details-page}

Informationssidan för en enskild person [!UICONTROL trait] innehåller en översikt över [!UICONTROL trait] information, t.ex. [!UICONTROL trait] name, ID, performance metrics, expressions that define the [!UICONTROL trait], segment som det tillhör och [!UICONTROL trait] granskningslogg. Om du vill visa den här informationen går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** och klicka på namnet på [!UICONTROL trait] du vill arbeta med.

## [!UICONTROL Trait] Hanteringsverktyg {#trait-management-tools}

Överst på [!UICONTROL trait] informationssidan innehåller de verktyg du kan använda för att hantera dina [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Använd det här alternativet för att skapa nya [!UICONTROL rule-based], [!UICONTROL algorithmic], eller [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Använd det här alternativet om du vill ändra konfigurationen för den aktuella [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Använd det här alternativet om du vill ta bort den aktuella [!UICONTROL trait] från ditt Audience Manager-konto.
4. **[!UICONTROL Marketplace Recommendations]**: Använd det här alternativet för att hitta liknande [!UICONTROL traits] till den du tittar på, från [!UICONTROL Audience Marketplace] avgifter som du inte prenumererar på. Se [Audience Marketplace för datainköpare](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) för att lära dig navigera i [!UICONTROL Marketplace] och hitta liknande egenskaper.

![grundläggande information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Information {#basics}

The [!UICONTROL Trait Information] -avsnittet innehåller information om obligatoriska och valfria fält som du slutförde när du skapade [!UICONTROL trait]. Detta inkluderar saker som [!UICONTROL trait] text, [!UICONTROL trait] ID, beskrivning, [!UICONTROL data source]och andra metadata. Vilka uppgifter som visas varierar beroende på [!UICONTROL trait] text ([!UICONTROL folder], [!UICONTROL onboarded], eller [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

The [!UICONTROL Trait Graph] ger överskådliga prestandamått för det du valt [!UICONTROL trait]. Håll markören över en trendlinje om du vill se ytterligare data för den markerade [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] representerar ett antal unika användare som har lagt till det här [!UICONTROL trait] till deras profil inom det angivna tidsintervallet. The [!UICONTROL Total Trait Population] anger antalet unika användare som för närvarande är kvalificerade för detta [!UICONTROL trait].

För [!UICONTROL rule-based traits], [!UICONTROL trait] kvalificering sker i realtid, eftersom användarna kvalificerar sig för [!UICONTROL trait] i webbläsaren.

För [!UICONTROL onboarded traits], [!UICONTROL trait] -kvalificeringen inträffar efter att en inkommande fil har bearbetats, dvs. den inkommande filen [matad i Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när [!UICONTROL trait] kvalificeringen sker.

The [!UICONTROL Trait Graph] visar följande information:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: välj det här alternativet om du vill se resultat för [!UICONTROL traits] som samlar in data för autentiserade profiler. När du väljer det här alternativet visas endast data på [!UICONTROL Cross-Device ID] och inga data kommer att finnas i [!UICONTROL Device ID] rapport.
   * **[!UICONTROL Device ID]**: välj det här alternativet om du vill se resultat för [!UICONTROL traits] som samlar in data för enhetsprofiler. När du väljer det här alternativet visas endast data på [!UICONTROL Device ID] och inga data kommer att finnas i [!UICONTROL Cross-Device ID] rapport.

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Antal unika användare som har lagt till detta [!UICONTROL trait] till deras profil inom det angivna tidsintervallet.
* **[!UICONTROL Total Trait Population]**: Antalet unika användare som är kvalificerade för detta [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: De tre första posterna visar de tre översta [!UICONTROL cross-device data sources] med det högsta antalet populationer som har kvalificerat sig för [!UICONTROL trait], i fallande ordning. Den fjärde posten visar summan av alla andra [!DNL DPUUIDs] ([!DNL CRM IDs]) som är kvalificerad för [!UICONTROL trait], från [!UICONTROL cross-device data sources] som inte finns i de tre översta. Den här rapporten visas bara om du väljer [!UICONTROL Cross-device ID] i [!UICONTROL Show Results By] nedrullningsbar meny längst upp till höger på sidan. Standardalternativet är [!UICONTROL Device ID], där den här rapporten inte visas.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager visar endast [!UICONTROL Identity Type Breakdown] rapportera om du har [!UICONTROL cross-device] ID:n som är kvalificerade för [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Uttryck {#trait-expression}

The [!UICONTROL Trait Expression] visas vilka kriterier som användarna måste uppfylla för att kvalificera sig för [!UICONTROL trait]. Dessa regler anges när du [skapa eller redigera ett varumärke](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segment  {#trait-segments}

The [!UICONTROL Segments with this Trait] i listas alla segment i det markerade [!UICONTROL trait] tillhör. Du kan klicka på ett segmentnamn om du vill se information om det segmentet.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Gransknings-/historiklogg {#trait-audit-history}

För [!UICONTROL rule-based] och [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] visar de 10 senaste ändringarna av [!UICONTROL trait] uttrycksregler och vem som gjorde dem. Om [!UICONTROL trait] har fler än 10 ändringar, klicka **[!UICONTROL Export to CSV]** om du vill hämta hela granskningsloggen. Granskningsloggen är inte tillgänglig för [!UICONTROL folder] eller [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] i [!UICONTROL By User] kolumn betyder att kontot för den användaren har tagits bort.

![](assets/traitHistory.png)
