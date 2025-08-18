---
description: Audience Optimization for Advertisers kan hjälpa er att identifiera potentiella prestandamöjligheter för Audience Manager-segment i era betalda mediekampanjer. Dessa rapporter kombinerar kampanjresultatdata på log-nivå med Audience Manager segmentstatistik för att skapa segmentbaserade optimeringar och en effektiv kanalmix.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization for Advertisers
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] för annonsörer{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] för annonsörer kan hjälpa dig att identifiera potentiella prestandamöjligheter för Audience Manager-segment i dina betalda mediekampanjer. Dessa rapporter kombinerar kampanjresultatdata på loggnivå med Audience Manager [!UICONTROL segment]-statistik för att informera segmentbaserade optimeringar och en effektiv kanalmix.

## Metoder för dataöverföring {#data-ingestion-methods}

Du kan skicka data till [!DNL Audience Manager] för användning i dessa rapporter på något av följande sätt. Ibland skickar kunderna data på båda sätten. Detta bidrar till att säkerställa att era rapporter innehåller den mest omfattande och korrekta informationen om besökaren. Om du vill använda [!UICONTROL Audience Optimization]-rapporterna måste dina händelseanrop innehålla *all* av de parametrar som anges i [Översikt och mappningar för metadatafiler](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) -dokumentationen. Du kan skicka data via följande metoder som listas nedan.

* Pixelanrop: Information om hur du skickar de nödvändiga metadataparametrarna till [!DNL Audience Manager] finns i [Hämta kampanjklicksdata via pixelanrop](../../../integration/media-data-integration/click-data-pixels.md) och [Hämta kampanjkomprimeringsdata via pixelanrop](../../../integration/media-data-integration/impression-data-pixels.md).

* Datafiler: Om du vill använda dessa rapporter för att analysera dina egna data eller data från en källa som inte är integrerad med [!DNL Audience Manager] måste du skapa och överföra data och metadatafiler för dessa data. Mer information finns i [Datafiler för Audience Optimization-rapporter](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) och [Data- och metadatafiler för Audience Optimization-rapporter](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Vilken typ av rapporter du kan visa beror på gruppen [!UICONTROL RBAC] som du är tilldelad till. Mer information finns i [Administration](../../../features/administration/administration-overview.md) och [Skapa en grupp](../../../features/administration/administration-overview.md#create-group).

[!UICONTROL RBAC] grupper måste ha vissa datakällor konfigurerade för att kunna visa [!UICONTROL Audience Optimization]-rapporter. Din [!DNL Audience Manager]-konsult kommer att konfigurera dessa [!UICONTROL data sources] åt dig. Ju mer [!UICONTROL data sources] i varje [!UICONTROL RBAC]-användargrupp, desto mer data har dessa gruppmedlemmar åtkomst till. Din konsult kommer att konfigurera minst en av dessa [!UICONTROL data sources]:

* Annonsör [!UICONTROL data source]
* Märke [!UICONTROL data source]
* Plattform [!UICONTROL data source]

Användare som tillhör mer än en [!UICONTROL RBAC]-användargrupp kan växla mellan varje grupps vy. De data som visas uppdateras för att motsvara den valda gruppen. Om ditt företag inte använder [!UICONTROL RBAC] får alla användare administratörsbehörighet och åtkomst till alla [!UICONTROL data sources] (konverteringsgrupper).

## Konverteringsgrupper {#conversion-groups}

I [!UICONTROL Audience Optimization]-rapporterna är **[!UICONTROL Conversion Groups]** synonymt med [!UICONTROL data sources] som innehåller minst en konverteringsegenskap. [!UICONTROL Data sources] som inte innehåller minst en konverteringsegenskap visas inte i [!UICONTROL Audience Optimization]-rapporterna. Du kan visa konverteringsegenskaperna för konverteringsgrupper i rapporten [Rapporterade konverteringsegenskaper](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md).
