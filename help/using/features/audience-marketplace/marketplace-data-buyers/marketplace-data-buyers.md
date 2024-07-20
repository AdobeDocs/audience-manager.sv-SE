---
description: Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace för datainköpare
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 0%

---

# [!UICONTROL Audience Marketplace] för datainköpare {#audience-marketplace-for-data-buyers}

Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån [!DNL Audience Manager].

>[!NOTE]
>[Rollbaserade behörigheter](../../../reporting/reports-dashboard.md) styr åtkomsten till funktioner i [!UICONTROL Audience Marketplace].
>
>* Administratörer kan skapa dataflöden, hantera prenumeranter och prenumerera på dataflöden.
>* Användarna kan bara söka efter och visa feeds.

## [!UICONTROL Marketplace]: Om {#about-marketplace}

[!UICONTROL Marketplace] är en [!DNL Audience Manager]-funktion för datainköpare som listar dataflöden som du kan prenumerera på. Den innehåller en lista över fasta datahastigheter, [!DNL CPM] och privata datautflöden. Dessa feeds tillhandahålls av tredjepartsleverantörer som använder [!DNL Audience Manager] för att sälja data.

I [!UICONTROL Marketplace] kan du med rapportverktygen spåra flödeanvändningen och överlappningen mellan [!UICONTROL traits] och de i en prenumererad datafeed. Med [!UICONTROL Audience Marketplace] hanterar [!DNL Adobe] slutligen fakturor och avgiftsbetalningar (även om du måste rapportera användningen själv när du prenumererar på en [!DNL CPM]-feed). Med dessa funktioner kan ni hitta effektiva datakällor utan att slösa tid på att leta efter en DataProvider.

>[!TIP]
>
>Använd **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** för att hitta högkvalitativa dataflöden som du kan prenumerera på. Gå sedan tillbaka till användargränssnittet för [!DNL Audience Manager] eller använd API:t för [Audience Marketplace Buyer](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) för att prenumerera på de feeds du har hittat.

![purchase-marketplace-overview](assets/buyer-marketplace-overview.png)

Listan [!UICONTROL Marketplace] innehåller information som du kan sortera och söka efter för att hitta den datafeed som passar dig. Objekten i köparlistan för [!UICONTROL Marketplace] omfattar:

* **[!UICONTROL Search]**: Sök efter datafeeds efter namn eller textbeskrivning.
* **[!UICONTROL Similar Traits]**: Visar antalet liknande [!UICONTROL traits] från en datafeed. Den här kolumnen visas när du har angett en [!UICONTROL trait] eller [!UICONTROL segment] att filtrera efter i avsnittet **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Dataflödets namn.
* **[!UICONTROL Description]**: Information om innehållet i en datafeed.
* **[!UICONTROL Provider]**: Dataleverantörens namn.
* **[!UICONTROL Traits]**: Antalet [!UICONTROL traits] i en datafeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Antalet unika användare som har setts under de senaste 30 dagarna.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Antalet användare i ditt konto som överlappar användarna i leverantörens konto.
* **[!UICONTROL Feed Overlap]**: Det 30-dagars överlappade uniques-värdet, i procent, beräknat som: Datainköpare (30 dagar överlappade uniques/Datainköpare (30 dagars uniques) x 100.
* **[!UICONTROL Private Feeds]**: Se [Privata datafeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Antalet prenumerationer som du har hos en DataProvider.

 

Använd följande filter till vänster på sidan [!UICONTROL Marketplace] för att enkelt hitta de bästa dataflödena för dina behov:

* **[!UICONTROL Similarity To]**: Filtrera datafeeds baserat på deras likhet med antingen en [!UICONTROL trait] eller [!UICONTROL segment] som du väljer. När du anger det [!UICONTROL trait] eller segment som du vill jämföra med kan du använda ID:t [!UICONTROL trait] eller [!UICONTROL segment], eller deras respektive namn.
* **[!UICONTROL Similarity Cutoff]**: Dra i skjutreglaget för att filtrera dataflödena baserat på hur lika deras [!UICONTROL traits] är med din [!UICONTROL trait] eller [!UICONTROL segment]. Mer information om [!UICONTROL trait] likhetspoäng finns i [Spåra likhetspoäng](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrera dataflödena baserat på din prenumerationsstatus.
* **[!UICONTROL Plan Use Case]**: Filtrera datafeeds baserat på vilka användningsfall som stöds: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** och **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrera datafeeds baserat på deras pristyp.

## Söker efter liknande [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] ger dig möjlighet att hitta [!UICONTROL traits] från olika dataflöden utifrån deras likhet med dina befintliga [!UICONTROL traits] eller segment. Så här gör du:

1. Gå till **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Använd **[!UICONTROL Similarity To]**-väljaren för att välja mellan filtrering baserat på en [!UICONTROL trait] eller [!UICONTROL segment]. Du kan filtrera baserat på [!UICONTROL trait]/[!UICONTROL segment]-ID eller namn. I sökrutan visas automatiskt förslag som baseras på dina indata.
3. När du har identifierat den egenskap eller det segment som du vill filtrera efter klickar du på den i listan med förslag.
4. Om du vill begränsa resultaten kan du använda skjutreglaget **[!UICONTROL Similarity Cutoff]** för att gå från mindre liknande [!UICONTROL traits] till mer liknande.

När filtreringen är klar visas en ny kolumn på resultatsidan: **[!UICONTROL Similar Traits]**. I den här kolumnen visas antalet [!UICONTROL traits] som liknar den du filtrerade efter, från varje datafeed som uppfyller filtervillkoren.

Om du vill visa en fullständig lista över liknande egenskaper klickar du på siffran i kolumnen **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> Audience Marketplace visar de 500 mest likartade [!UICONTROL trait] resultaten från alla dataflöden.

I videon nedan visas en fullständig översikt över hur du hittar liknande [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privata datafeeds {#private-data-feeds}

I listan [!UICONTROL Marketplace] markeras ibland providerns namn och [!UICONTROL trait]-data som privata. Detta indikerar en [privat datafeed](../../../features/audience-marketplace/marketplace-private-feeds.md). Med ett privat dataflöde kan säljarna begränsa köparåtkomsten till sina data. Säljarna kan göra feeds privata när de erbjuder specialerbjudanden, rabatter eller när sekretess och åtkomstkontroll är viktigt för dem. Som köpare måste du skicka en prenumerationsförfrågan till säljaren om du vill ha tillgång till en privat feed. Mer information finns i [Prenumerera på en privat datafeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

>[!MORELIKETHIS]
>
>* [Förstå sidan med avtalsinformation i Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatter för datainköpare](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)
