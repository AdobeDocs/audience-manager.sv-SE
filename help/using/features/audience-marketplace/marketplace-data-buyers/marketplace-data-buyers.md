---
description: Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån Audience Manager
seo-description: Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån Audience Manager
seo-title: Audience Marketplace för dataköpare
solution: Audience Manager
title: Audience Marketplace för dataköpare
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 2%

---


# [!UICONTROL Audience Marketplace] för datainköpare  {#audience-marketplace-for-data-buyers}

Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån [!DNL Audience Manager].

>[!NOTE]
>[Rollbaserade behörigheter](../../../reporting/reports-dashboard.md) styr åtkomsten till [!UICONTROL Audience Marketplace]-funktioner.
>
>* Administratörer kan skapa dataflöden, hantera prenumeranter och prenumerera på dataflöden.
>* Användarna kan bara söka efter och visa feeds.


## [!UICONTROL Marketplace]: Om {#about-marketplace}

[!UICONTROL Marketplace] är en [!DNL Audience Manager]-funktion för datainköpare som listar dataflöden som du kan prenumerera på. Här anges schablonbelopp, [!DNL CPM] och privata dataflöden. Dessa flöden tillhandahålls av tredjepartsleverantörer som använder [!DNL Audience Manager] för att sälja data.

I [!UICONTROL Marketplace] kan du med rapportverktygen spåra flödeanvändningen och överlappningen mellan [!UICONTROL traits] och de i en prenumererad datafeed. Med [!UICONTROL Audience Marketplace] tar [!DNL Adobe] hand om fakturor och avgiftsbetalningar (men du måste själv rapportera användningen när du prenumererar på ett [!DNL CPM]-flöde). Med dessa funktioner kan ni hitta effektiva datakällor utan att slösa tid på att leta efter en DataProvider.

>[!TIP]
>
>Använd **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** för att hitta högkvalitativa dataflöden som du kan prenumerera på. Gå sedan tillbaka till [!DNL Audience Manager]-användargränssnittet eller använd [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) för att prenumerera på de feeds du har hittat.

![customer-marketplace-overview](assets/buyer-marketplace-overview.png)

Listan [!UICONTROL Marketplace] innehåller information som du kan sortera och söka efter för att hitta den datafeed som passar dig. Objekten i listan [!UICONTROL Marketplace]-köpare är:

* **[!UICONTROL Search]**: Sök efter datafeeds efter namn eller textbeskrivning.
* **[!UICONTROL Similar Traits]**: Visar antalet liknande  [!UICONTROL traits] data från en datafeed. Den här kolumnen visas efter att du har angett en [!UICONTROL trait] eller [!UICONTROL segment] att filtrera efter i avsnittet **[!UICONTROL Similarity To]**.
* **[!UICONTROL Name]**: Dataflödets namn.
* **[!UICONTROL Description]**: Information om innehållet i en datafeed.
* **[!UICONTROL Provider]**: Dataproviderns namn.
* **[!UICONTROL Traits]**: Antalet  [!UICONTROL traits] i en datafeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Antalet unika användare de senaste 30 dagarna.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Antalet användare på ditt konto som överlappar användarna på leverantörens konto.
* **[!UICONTROL Feed Overlap]**: Det 30-dagars överlappade uniques-värdet, i procent, beräknat som: Uppgiftsköparen (30 dagar) överlappade uniques (unika) / Datamöpares (30 dagar) x 100.
* **[!UICONTROL Private Feeds]**: Se  [Privata datafeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Antalet prenumerationer som du har hos en DataProvider.

 

Använd följande filter till vänster på [!UICONTROL Marketplace]-sidan för att enkelt hitta de bästa dataflödena för dina behov:

* **[!UICONTROL Similarity To]**: Filtrera dataflöden baserat på deras likhet med antingen en  [!UICONTROL trait] eller  [!UICONTROL segment] en av dem du väljer. När du anger det [!UICONTROL trait] eller segment att jämföra med kan du använda ID:t [!UICONTROL trait] eller [!UICONTROL segment] eller deras respektive namn.
* **[!UICONTROL Similarity Cutoff]**: Dra i skjutreglaget för att filtrera dataflödena baserat på hur lika de  [!UICONTROL traits] är för det markerade  [!UICONTROL trait] eller  [!UICONTROL segment]det markerade objektet. Mer information om [!UICONTROL trait]-likhetspoäng finns i [Spåra likhetspoäng](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrera dataflödena baserat på din prenumerationsstatus.
* **[!UICONTROL Plan Use Case]**: Filtrera dataflöden baserat på vilka användningsfall som stöds:  **[!UICONTROL Activation]**,  **[!UICONTROL Segments and Overlap]** och  **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrera dataflöden baserat på deras pristyp.

## Söker efter liknande [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] ger dig möjlighet att hitta  [!UICONTROL traits] från olika dataflöden utifrån deras likhet med befintliga  [!UICONTROL traits] eller befintliga segment. Så här gör du:

1. Gå till **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Använd **[!UICONTROL Similarity To]**-väljaren för att välja mellan filtrering baserad på en [!UICONTROL trait] eller [!UICONTROL segment]. Du kan filtrera baserat på ID eller namn för [!UICONTROL trait]/[!UICONTROL segment]. I sökrutan visas automatiskt förslag som baseras på dina indata.
3. När du har identifierat den egenskap eller det segment som du vill filtrera efter klickar du på den i listan med förslag.
4. Om du vill begränsa resultaten använder du reglaget **[!UICONTROL Similarity Cutoff]** för att gå från mindre liknande [!UICONTROL traits] till mer liknande.

När filtreringen är klar visas en ny kolumn på resultatsidan: **[!UICONTROL Similar Traits]**. I den här kolumnen visas antalet [!UICONTROL traits] som liknar det du filtrerade efter, från varje datafeed som uppfyller filtervillkoren.

Om du vill visa en fullständig lista över liknande egenskaper klickar du på siffran i kolumnen **[!UICONTROL Similar Traits]**.

>[!NOTE]
>
> Audience Marketplace visar de 500 mest likartade [!UICONTROL trait] resultaten från alla dataflöden.

I videon nedan visas en fullständig översikt över hur du hittar liknande [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privata dataflöden {#private-data-feeds}

I listan [!UICONTROL Marketplace] markeras ibland providerns namn och [!UICONTROL trait]-data som privata. Detta indikerar en [privat datafeed](../../../features/audience-marketplace/marketplace-private-feeds.md). Med ett privat dataflöde kan säljarna begränsa köparåtkomsten till sina data. Säljarna kan göra feeds privata när de erbjuder specialerbjudanden, rabatter eller när sekretess och åtkomstkontroll är viktigt för dem. Som köpare måste du skicka en prenumerationsförfrågan till säljaren om du vill ha tillgång till en privat feed. Mer information finns i [Prenumerera på en privat datafeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

>[!MORELIKETHIS]
>
>* [Sidan med avtalsinformation i Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatter för datainköpare](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

