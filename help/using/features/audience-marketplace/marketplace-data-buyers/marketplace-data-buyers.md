---
description: Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån Audience Manager
seo-description: Overview and workflow for data buyers who want to purchase third-party data from within Audience Manager
seo-title: Audience Marketplace for Data Buyers
solution: Audience Manager
title: Audience Marketplace för dataköpare
uuid: f505b5f4-4231-4e84-993a-cd64128b540f
feature: Audience Marketplace
exl-id: 9d6a7fda-f79f-41ad-9654-3ebcf9028cc2
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 1%

---

# [!UICONTROL Audience Marketplace] för datainköpare {#audience-marketplace-for-data-buyers}

Översikt och arbetsflöde för datainköpare som vill köpa data från tredje part inifrån [!DNL Audience Manager].

>[!NOTE]
>[Rollbaserade behörigheter](../../../reporting/reports-dashboard.md) styra åtkomst till [!UICONTROL Audience Marketplace] funktioner.
>
>* Administratörer kan skapa dataflöden, hantera prenumeranter och prenumerera på dataflöden.
>* Användarna kan bara söka efter och visa feeds.


## The [!UICONTROL Marketplace]: Om {#about-marketplace}

The [!UICONTROL Marketplace] är en [!DNL Audience Manager] för datainköpare som listar dataflöden som du kan prenumerera på. Här anges schablonbelopp. [!DNL CPM]och privata dataflöden. Dessa feeds tillhandahålls av tredjepartsleverantörer som använder [!DNL Audience Manager] för att sälja data.

I [!UICONTROL Marketplace]kan du med rapportverktygen spåra flödeanvändningen och överlappningen mellan [!UICONTROL traits] och de i en prenumererad datafeed. Äntligen med [!UICONTROL Audience Marketplace], [!DNL Adobe] tar hand om fakturor och avgiftsbetalningar (men du måste själv rapportera användningen när du prenumererar på en [!DNL CPM] feed). Med dessa funktioner kan ni hitta effektiva datakällor utan att slösa tid på att leta efter en DataProvider.

>[!TIP]
>
>Använd **[Adobe Audience Finder](https://www.adobe-audience-finder.com/)** för att hitta högkvalitativa dataflöden som du kan prenumerera på. Gå sedan tillbaka till [!DNL Audience Manager] användargränssnittet eller använder [Audience Marketplace Buyer API](https://bank.demdex.com/portal/swagger/index.html#/Audience_Marketplace_Buyer_API) för att prenumerera på de feeds du har hittat.

![customer-marketplace-overview](assets/buyer-marketplace-overview.png)

The [!UICONTROL Marketplace] listan innehåller information som du kan sortera och söka efter för att hitta den datafeed som passar dig. Objekt i [!UICONTROL Marketplace] köparens lista omfattar:

* **[!UICONTROL Search]**: Sök efter datafeeds efter namn eller textbeskrivning.
* **[!UICONTROL Similar Traits]**: Visar antalet liknande [!UICONTROL traits] från en datafeed. Den här kolumnen visas när du har angett en [!UICONTROL trait] eller [!UICONTROL segment] för att filtrera efter **[!UICONTROL Similarity To]** -avsnitt.
* **[!UICONTROL Name]**: Dataflödets namn.
* **[!UICONTROL Description]**: Information om innehållet i en datafeed.
* **[!UICONTROL Provider]**: Dataproviderns namn.
* **[!UICONTROL Traits]**: Antalet [!UICONTROL traits] i en datafeed.
* **[!UICONTROL 30 Day Provider Unique Users]**: Antalet unika användare de senaste 30 dagarna.
* **[!UICONTROL 30 Day Overlapped Uniques]**: Antalet användare på ditt konto som överlappar användarna på leverantörens konto.
* **[!UICONTROL Feed Overlap]**: Det 30-dagars överlappade uniques-värdet, i procent, beräknat som: Uppgiftsköparen (30 dagar) överlappade uniques (unika) / Datamöpares (30 dagar) x 100.
* **[!UICONTROL Private Feeds]**: Se [Privata datafeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).
* **[!UICONTROL Currently Subscribed Plan Count]**: Antalet prenumerationer som du har hos en DataProvider.

 

Använd följande filter till vänster i dialogrutan för att enkelt hitta de bästa dataflödena för dina behov [!UICONTROL Marketplace] sida:

* **[!UICONTROL Similarity To]**: Filtrera dataflöden baserat på deras likhet med antingen en [!UICONTROL trait] eller [!UICONTROL segment] efter eget val. När du anger [!UICONTROL trait] eller segment att jämföra med kan du använda [!UICONTROL trait] eller [!UICONTROL segment] ID eller deras respektive namn.
* **[!UICONTROL Similarity Cutoff]**: Dra skjutreglaget för att filtrera dataflödena baserat på hur lika deras [!UICONTROL traits] är till din valda [!UICONTROL trait] eller [!UICONTROL segment]. Mer information om [!UICONTROL trait] likhetspoäng, se [Spåra likhetsresultat](../../segments/trait-recommendations.md#trait-similarity-score)
* **[!UICONTROL Subscription Status]**: Filtrera dataflödena baserat på din prenumerationsstatus.
* **[!UICONTROL Plan Use Case]**: Filtrera dataflöden baserat på vilka användningsfall som stöds: **[!UICONTROL Activation]**, **[!UICONTROL Segments and Overlap]** och **[!UICONTROL Modelling]**.
* **[!UICONTROL Plan Unit]**: Filtrera dataflöden baserat på deras pristyp.

## Söker efter liknande [!UICONTROL Traits] {#finding-similar-traits}

[!UICONTROL Audience Marketplace] ger dig möjlighet att hitta [!UICONTROL traits] från olika dataflöden, baserat på deras likhet med dina befintliga [!UICONTROL traits] eller segment. Så här gör du:

1. Gå till **[!UICONTROL Audience Marketplace]** > **[!UICONTROL Marketplace]**.
2. Använd **[!UICONTROL Similarity To]** väljer du mellan att filtrera baserat på en [!UICONTROL trait] eller [!UICONTROL segment]. Du kan filtrera baserat på [!UICONTROL trait]/[!UICONTROL segment] ID eller namn. I sökrutan visas automatiskt förslag som baseras på dina indata.
3. När du har identifierat den egenskap eller det segment som du vill filtrera efter klickar du på den i listan med förslag.
4. Om du vill begränsa resultaten använder du **[!UICONTROL Similarity Cutoff]** för att flytta från mindre liknande [!UICONTROL traits], till fler liknande.

När filtreringen är klar visas en ny kolumn på resultatsidan: **[!UICONTROL Similar Traits]**. I den här kolumnen visas antalet liknande [!UICONTROL traits] till den som du filtrerat efter, från varje datafeed som uppfyller filtervillkoren.

Om du vill visa en fullständig lista över liknande egenskaper klickar du på siffran i **[!UICONTROL Similar Traits]** kolumn.

>[!NOTE]
>
> Audience Marketplace visar de 500 översta liknande [!UICONTROL trait] resultat från alla dataflöden.

I videon nedan finns en fullständig översikt över hur du hittar liknande [!UICONTROL traits].

>[!VIDEO](https://video.tv.adobe.com/v/29370/)

## Privata dataflöden {#private-data-feeds}

I [!UICONTROL Marketplace] lista, ibland leverantörens namn och [!UICONTROL trait] data markeras som privata. Detta indikerar en [privat datafeed](../../../features/audience-marketplace/marketplace-private-feeds.md). Med ett privat dataflöde kan säljarna begränsa köparåtkomsten till sina data. Säljarna kan göra feeds privata när de erbjuder specialerbjudanden, rabatter eller när sekretess och åtkomstkontroll är viktigt för dem. Som köpare måste du skicka en prenumerationsförfrågan till säljaren om du vill ha tillgång till en privat feed. Se [Prenumerera på en privat datafeed](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) för mer information.

>[!MORELIKETHIS]
>
>* [Sidan med avtalsinformation i Audience Marketplace](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#marketplace-buyer-details)
>* [Rabatter för datainköpare](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#buyer-discount)

