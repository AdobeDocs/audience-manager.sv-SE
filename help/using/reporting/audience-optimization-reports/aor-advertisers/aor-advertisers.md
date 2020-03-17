---
description: Målgruppsoptimering för annonsörer kan hjälpa er att identifiera potentiella prestandamöjligheter för Audience Manager-segment i era betalda mediekampanjer. Dessa rapporter kombinerar kampanjresultatdata på loggnivå med segmentstatistik för Audience Manager som underlag för segmentbaserade optimeringar och en effektiv kanalmix.
seo-description: Målgruppsoptimering för annonsörer kan hjälpa er att identifiera potentiella prestandamöjligheter för Audience Manager-segment i era betalda mediekampanjer. Dessa rapporter kombinerar kampanjresultatdata på loggnivå med segmentstatistik för Audience Manager som underlag för segmentbaserade optimeringar och en effektiv kanalmix.
seo-title: Målgruppsoptimering för annonsörer
solution: Audience Manager
title: Målgruppsoptimering för annonsörer
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

Målgruppsoptimering för annonsörer kan hjälpa er att identifiera potentiella prestandamöjligheter för Audience Manager-segment i era betalda mediekampanjer. Dessa rapporter kombinerar kampanjresultatdata på loggnivå med segmentstatistik för Audience Manager som underlag för segmentbaserade optimeringar och en effektiv kanalmix.

## Metoder för datainmatning {#data-ingestion-methods}

Du kan skicka data till [!DNL Audience Manager] för användning i dessa rapporter på något av följande sätt. Ibland skickar kunderna data på båda sätten. Detta säkerställer att era rapporter innehåller den mest omfattande och korrekta informationen om besökaren. Om du vill använda [!UICONTROL Audience Optimization] rapporterna måste dina händelseanrop innehålla *alla* parametrar som anges i dokumentationen [Översikt och Mappningar för metadatafiler](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) . Du kan skicka data via följande metoder som listas nedan.

* Pixelanrop: Om du vill skicka de metadataparametrar som krävs för att [!DNL Audience Manager] se [Hämta kampanjklickdata via pixelanrop](../../../integration/media-data-integration/click-data-pixels.md) och [Hämta kampanjkomprimeringsdata via pixelanrop](../../../integration/media-data-integration/impression-data-pixels.md).

* Datafiler: Om du vill använda dessa rapporter för att analysera dina egna data eller data från en källa som inte är integrerad med [!DNL Audience Manager]måste du skapa och överföra data och metadatafiler för dessa data. Mer information finns i [Datafiler för målgruppsoptimeringsrapporter](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) och [data- och metadatafiler för målgruppsoptimeringsrapporter](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## Rollbaserade åtkomstkontroller (RBAC) {#rbac}

Vilken typ av rapporter du kan visa beror på vilken [!UICONTROL RBAC] grupp du har tilldelats. Mer information finns i [Administration](../../../features/administration/administration-overview.md) och [Skapa en grupp](../../../features/administration/administration-overview.md#create-group) .

[!UICONTROL RBAC] grupper måste ha vissa datakällor konfigurerade för att kunna visa [!UICONTROL Audience Optimization] rapporterna. Din [!DNL Audience Manager] konsult kommer att konfigurera dessa datakällor åt dig. Ju fler datakällor i varje [!UICONTROL RBAC] användargrupp, desto mer data har dessa gruppmedlemmar åtkomst till. Din konsult kommer att skapa minst en av dessa datakällor:

* Advertiser, datakälla
* Varumärkesdatakälla
* Plattformsdatakälla

Användare som tillhör mer än en [!UICONTROL RBAC] användargrupp kan växla mellan varje grupps vy. De data som visas uppdateras för att motsvara den valda gruppen. Om ditt företag inte använder [!UICONTROL RBAC]får alla användare administratörsbehörighet och åtkomst till alla datakällor (konverteringsgrupper).

## Konverteringsgrupper {#conversion-groups}

I [!UICONTROL Audience Optimization] rapporterna **[!UICONTROL Conversion Groups]** är synonyma med datakällor som innehåller minst en konverteringsegenskap. Datakällor som inte innehåller minst en konverteringsegenskap visas inte i [!UICONTROL Audience Optimization] rapporterna. Du kan visa konverteringsegenskaperna för konverteringsgrupper i rapporten [Rapporterade konverteringsegenskaper](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) .
