---
description: Detaljsidan för en enskild trait innehåller en översikt över information som trait name, ID, performance metrics, expressions som definierar trait, segments som den tillhör och trait Audit log. Om du vill visa den här informationen går du till Målgruppsdata > Traits och klickar på namnet på den trait du vill arbeta med.
seo-description: Detaljsidan för en enskild trait innehåller en översikt över information som trait name, ID, performance metrics, expressions som definierar trait, segments som den tillhör och trait Audit log. Om du vill visa den här informationen går du till Målgruppsdata > Traits och klickar på namnet på den trait som du vill arbeta med.
seo-title: Anpassa detaljsida
solution: Audience Manager
title: Anpassa detaljsida
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
translation-type: tm+mt
source-git-commit: 3b56d7ecdef4375bf3b007fa9b325618c701c174
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 0%

---


# Anpassa detaljsida {#trait-details-page}

Detaljsidan för en enskild trait innehåller en översikt över trait-informationen, t.ex. trait name, ID, performance metrics, expressions that define the trait, segment it tillhör och trait Audit log. Om du vill visa den här informationen går du till **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** och klickar på namnet på den egenskap du vill arbeta med.

## Trait Management Tools {#trait-management-tools}

Överst på sidan med trait details finns verktyg som du kan använda för att hantera dina egenskaper:

1. **[!UICONTROL Add New]**: Använd det här alternativet om du vill skapa nya regelbaserade, algoritmiska eller anpassade egenskaper.
2. **[!UICONTROL Edit]**: Använd det här alternativet om du vill ändra konfigurationen för den aktuella egenskapen.
3. **[!UICONTROL Delete]**: Använd det här alternativet om du vill ta bort den aktuella egenskapen från ditt Audience Manager-konto.
4. **[!UICONTROL Marketplace Recommendations]**: Använd det här alternativet för att hitta liknande egenskaper som den du visar, från [!UICONTROL Audience Marketplace] datarvoden som du inte prenumererar på. Se [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om du vill lära dig navigera på Marketplace och hitta liknande egenskaper.

![grundläggande information](assets/basic-trait-information.png)

## Trait Information {#basics}

I avsnittet visas information om obligatoriska och valfria fält som du har fyllt i när du skapade egenskapen. [!UICONTROL Trait Information] Detta inkluderar egenskaper som trait-typ, trait-ID, beskrivning, datakälla och andra metadata. De här detaljerna varierar beroende på trait-typ (mapp, introduktion eller regelbaserad).

## Trait Graph {#trait-graph}

Här [!UICONTROL Trait Graph] finns en överskådlig prestandamätning för det valda trait-objektet. Håll markören över en trendlinje om du vill se ytterligare data för den valda egenskapen.

[!UICONTROL Unique Trait Realizations] representerar ett antal unika användare som har lagt till den här egenskapen i sin profil under det angivna tidsintervallet. Anger [!UICONTROL Total Trait Population] antalet unika användare som för närvarande är kvalificerade för den här egenskapen.

När det gäller regelbaserade egenskaper sker en kvalificering i realtid, eftersom användarna kvalificerar sig för en egenskap i sina webbläsare.

För praktik som introduceras sker en trait-kvalificering efter att en inkommande fil har bearbetats, dvs. den inkommande filen [matas in i Audience Manager](../../faq/faq-inbound-data-ingestion.md) och det är när trait-kvalificeringen görs.

Följande information [!UICONTROL Trait Graph] visas:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Välj det här alternativet om du vill se resultat för egenskaper som samlar in data för autentiserade profiler. När du väljer det här alternativet visas bara data i [!UICONTROL Cross-Device ID] rapporten, och inga data kommer att finnas under [!UICONTROL Device ID] rapporten.
   * **[!UICONTROL Device ID]**: Välj det här alternativet om du vill se resultat för egenskaper som samlar in data för enhetsprofiler. När du väljer det här alternativet visas bara data i [!UICONTROL Device ID] rapporten, och inga data kommer att finnas under [!UICONTROL Cross-Device ID] rapporten.

      ![trait-graph](assets/trait-summary.png)

* **[!UICONTROL Unique Trait Realizations]**: Antal unika användare som har lagt till den här egenskapen i sin profil under det angivna tidsintervallet.
* **[!UICONTROL Total Trait Population]**: Antalet unika användare som är kvalificerade för den här egenskapen.

* **[!UICONTROL Identity Type Breakdown]**: De första tre posterna visar de tre viktigaste datakällorna för olika enheter med det högsta antalet populationer som har kvalificerat sig för egenskapen, i fallande ordning. Den fjärde posten visar summan av alla andra [!DNL DPUUIDs] ([!DNL CRM IDs]) som kvalificerar sig för egenskapen, från datakällor mellan enheter som inte finns i de tre översta. Den här rapporten visas bara om du väljer Enhets-ID i den [!UICONTROL Show Results By] nedrullningsbara menyn längst upp till höger på sidan. Standardalternativet är [!UICONTROL Device ID]där den här rapporten inte visas.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager visar bara rapporten om du har ett ID-nummer mellan olika enheter som är kvalificerat för egenskapen. [!UICONTROL Identity Type Breakdown]

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## Trait-uttryck {#trait-expression}

I avsnittet visas [!UICONTROL Trait Expression] vilka kriterier som användarna måste uppfylla för att kvalificera sig för egenskapen. Dessa regler anges när du [skapar eller redigerar en egenskap](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

I [!UICONTROL Segments with this Trait] avsnittet visas alla segment som den valda egenskapen tillhör. Du kan klicka på ett segmentnamn om du vill se information om det segmentet.

![](assets/traitSegments.png)

## Gransknings-/historiklogg {#trait-audit-history}

För regelbaserade och onboardbaserade egenskaper visas de 10 senaste ändringarna av reglerna för [!UICONTROL Trait Expression Change History] anpassade uttryck och vem som gjorde dem. Om ditt varumärke innehåller fler än 10 ändringar klickar du på **[!UICONTROL Export to CSV]** för att hämta hela granskningsloggen. Granskningsloggen är inte tillgänglig för mappar eller algoritmiska egenskaper.

>[!NOTE]
>
>[!UICONTROL Not Available] i [!UICONTROL By User] kolumnen betyder att kontot för den användaren har tagits bort.

![](assets/traitHistory.png)