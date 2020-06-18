---
description: Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån Audience Manager
seo-description: Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån Audience Manager
seo-title: Audience Marketplace för datainköpare
solution: Audience Manager
title: Audience Marketplace för datainköpare
topic: DIL API
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '777'
ht-degree: 0%

---


# Audience Marketplace för datainköpare {#audience-marketplace-for-data-buyers}

Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån [!DNL Audience Manager].

>[!NOTE]
>[Rollbaserade behörigheter](../../../reporting/reports-dashboard.md) styr åtkomsten till [!UICONTROL Audience Marketplace] funktioner.
>
>* Administratörer kan skapa dataflöden, hantera prenumeranter och prenumerera på dataflöden.
>* Användarna kan bara söka efter och visa feeds.


## Marketplace: Om {#about-marketplace}

<!-- c_marketplace_about.xml -->

Det [!UICONTROL Marketplace] är en [!DNL Audience Manager] funktion för datainköpare som listar dataflöden som du kan prenumerera på. Här anges schablonbelopp [!DNL CPM]och privata dataflöden. Dessa flöden tillhandahålls av tredjepartsleverantörer som använder [!DNL Audience Manager] för att sälja data.

I [!UICONTROL Marketplace]kan du med rapportverktygen spåra flödeanvändningen och överlappningen mellan egenskaper och egenskaper i en prenumererad datafeed. Slutligen, med [!UICONTROL Audience Marketplace]tar [!DNL Adobe] hand om fakturor och avgiftsbetalningar (även om du måste rapportera användningen själv när du prenumererar på ett [!DNL CPM] flöde). Med dessa funktioner kan ni hitta effektiva datakällor utan att slösa tid på att leta efter en DataProvider.

>[!TIP]
>
>Använd **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)**för att hitta högkvalitativa dataflöden som du kan prenumerera på. Gå sedan tillbaka till[!DNL Audience Manager]användargränssnittet eller använd[Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API)för att prenumerera på de feeds du har hittat.

![customer-marketplace-overview](assets/buyer-marketplace-overview.png)

Listan innehåller information som du kan sortera och söka efter för att hitta den datafeed som passar dig. [!UICONTROL Marketplace] Posterna i [!UICONTROL Marketplace] köparens lista omfattar:

* **[!UICONTROL Search]**: Sök efter datafeeds efter namn eller textbeskrivning.
* **[!UICONTROL Similar Traits]**: Visar antalet liknande egenskaper från en datafeed. Den här kolumnen visas när du har angett ett trait- eller segment som ska filtreras efter i **[!UICONTROL Similarity To]** avsnittet.
* **[!UICONTROL Name]**: Dataflödets namn.
* **[!UICONTROL Description]**: Information om innehållet i en datafeed.
* **[!UICONTROL Provider]**: Dataproviderns namn.
* **[!UICONTROL Traits]**: Antalet egenskaper i en datafeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Antalet unika användare de senaste 30 dagarna.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Antalet användare på ditt konto som överlappar användarna på leverantörens konto.
* **[!UICONTROL Feed Overlap]**: Det 30-dagars överlappade uniques-värdet, i procent, beräknat som: Uppgiftsköparen (30 dagar) överlappade uniques (unika) / Datamöpares (30 dagar) x 100.
* **[!UICONTROL Private Feeds]**: Se [Privata datafeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Antalet prenumerationer som du har hos en DataProvider.

 

Använd följande filter till vänster på [!UICONTROL Marketplace] sidan för att enkelt hitta de bästa dataflödena för dina behov:

* **[!UICONTROL Similarity To]**: Filtrera dataflöden baserat på deras likhet med antingen ett trait-värde eller ett segment som du väljer. När du anger trait eller segment att jämföra med kan du använda trait- eller segment-ID:t eller deras respektive namn.
* **[!UICONTROL Similarity Cutoff]**: Dra skjutreglaget för att filtrera dataflödena baserat på hur deras egenskaper liknar det valda tecknet eller segmentet. Mer information om poäng för trait-likhet finns i [Spåra likhetspoäng](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrera dataflödena baserat på din prenumerationsstatus.
* **[!UICONTROL Plan Use Case]**: Filtrera dataflöden baserat på vilka användningsfall som stöds: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** och **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrera dataflöden baserat på deras pristyp.

## Söka efter liknande egenskaper {#finding-similar-traits}

[!UICONTROL Audience Marketplace] ger dig möjlighet att hitta egenskaper från olika dataflöden utifrån deras likhet med dina befintliga egenskaper eller segment. Så här gör du:

1. Gå till **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Använd väljaren för att välja mellan filtrering baserat på ett trait- eller segment. **[!UICONTROL Similarity To]** Du kan filtrera baserat på trait/segment-ID eller namn. I sökrutan visas automatiskt förslag som baseras på dina indata.
3. När du har identifierat den egenskap eller det segment som du vill filtrera efter klickar du på den i listan med förslag.
4. Om du vill begränsa resultatet kan du använda skjutreglaget för att gå från mindre liknande egenskaper till mer liknande. **[!UICONTROL Similarity Cutoff]**

När filtreringen är klar visas en ny kolumn på resultatsidan: **[!UICONTROL Similar Traits]**. I den här kolumnen visas antalet egenskaper som liknar de som du filtrerade efter, från varje datafeed som uppfyller filtervillkoren.

Om du vill visa en fullständig lista över liknande egenskaper klickar du på siffran i **[!UICONTROL Similar Traits]** kolumnen.

>[!NOTE]
>
> Audience Marketplace visar de 500 vanligaste likartade egenskaperna från dataflödena.

I videon nedan finns en fullständig översikt över hur du hittar liknande egenskaper.

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privata dataflöden {#private-data-feeds}

I [!UICONTROL Marketplace] listan markeras ibland providerns namn och egenskaper som privata. Detta anger en [privat datafeed](../../../features/audience-marketplace/marketplace-private-feeds.md). Med ett privat dataflöde kan säljarna begränsa köparåtkomsten till sina data. Säljarna kan göra feeds privata när de erbjuder specialerbjudanden, rabatter eller när sekretess och åtkomstkontroll är viktigt för dem. Som köpare måste du skicka en prenumerationsförfrågan till säljaren om du vill ha tillgång till en privat feed. Mer information finns i [Prenumerera på en privat datafeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) .

>[!MORELIKETHIS]
>
>* [Sidan med avtalsinformation i Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatter för datainköpare](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

