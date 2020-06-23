---
description: Målgruppsoptimering för annonsörer kan hjälpa er att identifiera potentiella prestationsmöjligheter för segment i Audience Manager i era betalmediekampanjer. Dessa rapporter kombinerar kampanjdata på loggnivå med Audience Manager segmentstatistik för att kunna skapa segmentbaserade optimeringar och en effektiv kanalmix.
seo-description: Målgruppsoptimering för annonsörer kan hjälpa er att identifiera potentiella prestationsmöjligheter för segment i Audience Manager i era betalmediekampanjer. Dessa rapporter kombinerar kampanjdata på loggnivå med Audience Manager segmentstatistik för att kunna skapa segmentbaserade optimeringar och en effektiv kanalmix.
seo-title: Målgruppsoptimering för annonsörer
solution: Audience Manager
title: Målgruppsoptimering för annonsörer
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: 9326b61f27f6c529567ab9b26694998f0b5dafb3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---


# [!UICONTROL Audience Optimization] för annonsörer{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] för annonsörer kan hjälpa er att identifiera potentiella prestationsmöjligheter för segment i Audience Manager i era betalda mediekampanjer. Dessa rapporter kombinerar kampanjdata på loggnivå med Audience Manager- [!UICONTROL segment] statistik för att kunna skapa segmentbaserade optimeringar och en effektiv kanalmix.

## Metoder för datainmatning {#data-ingestion-methods}

Du kan skicka data till [!DNL Audience Manager] för användning i dessa rapporter på något av följande sätt. Ibland skickar kunderna data på båda sätten. Detta säkerställer att era rapporter innehåller den mest omfattande och korrekta informationen om besökaren. Om du vill använda [!UICONTROL Audience Optimization] rapporterna måste dina händelseanrop innehålla *alla* parametrar som anges i dokumentationen [Översikt och Mappningar för metadatafiler](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) . Du kan skicka data via följande metoder som listas nedan.

* Pixelanrop: Om du vill skicka de metadataparametrar som krävs för att [!DNL Audience Manager] se [Hämta kampanjklickdata via pixelanrop](../../../integration/media-data-integration/click-data-pixels.md) och [Hämta kampanjkomprimeringsdata via pixelanrop](../../../integration/media-data-integration/impression-data-pixels.md).

* Datafiler: Om du vill använda dessa rapporter för att analysera dina egna data eller data från en källa som inte är integrerad med [!DNL Audience Manager]måste du skapa och överföra data och metadatafiler för dessa data. Mer information finns i [Datafiler för målgruppsoptimeringsrapporter](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) och [data- och metadatafiler för målgruppsoptimeringsrapporter](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Vilken typ av rapporter du kan visa beror på vilken [!UICONTROL RBAC] grupp du har tilldelats. Mer information finns i [Administration](../../../features/administration/administration-overview.md) och [Skapa en grupp](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] grupper måste ha vissa datakällor konfigurerade för att kunna visa [!UICONTROL Audience Optimization] rapporterna. Din [!DNL Audience Manager] konsult kommer att konfigurera dessa [!UICONTROL data sources] åt dig. Ju mer i varje [!UICONTROL data sources] [!UICONTROL RBAC] användargrupp, desto mer data har dessa gruppmedlemmar åtkomst till. Din konsult kommer att skapa minst en av dessa [!UICONTROL data sources]:

* Annonsör [!UICONTROL data source ]
* Varumärke [!UICONTROL data source]
* Platform [!UICONTROL data source]

Användare som tillhör mer än en [!UICONTROL RBAC] användargrupp kan växla mellan varje grupps vy. De data som visas uppdateras för att motsvara den valda gruppen. Om ditt företag inte använder [!UICONTROL RBAC]får alla användare administratörsbehörighet och åtkomst till alla [!UICONTROL data sources] (konverteringsgrupper).

## Konverteringsgrupper {#conversion-groups}

I [!UICONTROL Audience Optimization] rapporterna **[!UICONTROL Conversion Groups]** är synonyma med [!UICONTROL data sources] som innehåller minst en konverteringsegenskap. [!UICONTROL Data sources] som inte innehåller minst en konverteringsegenskap visas inte i [!UICONTROL Audience Optimization] rapporterna. Du kan visa konverteringsegenskaperna för konverteringsgrupper i rapporten [Rapporterade konverteringsegenskaper](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) .
