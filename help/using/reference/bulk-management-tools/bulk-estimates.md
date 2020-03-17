---
description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-title: Massuppskattningar
solution: Audience Manager
title: Massuppskattningar
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Massuppskattningar{#bulk-estimates}

En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] stöds inte *av* [!DNL Audience Manager]. Det här verktyget finns endast till för att underlätta och för att underlätta. För större förändringar rekommenderar vi att du arbetar med API:erna [för](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager i stället. [RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Om du vill göra större uppdateringar öppnar du [!UICONTROL Bulk Management Tools] kalkylbladet och:

1. Klicka på **[!UICONTROL Headers]** fliken och kopiera [!UICONTROL Estimate Segment Size] rubriken.
1. Klicka på **[!UICONTROL Estimate]** fliken.
1. Klistra in uppskattningsrubriken i den första raden i uppskattningskalkylbladet.
1. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
1. Klicka i verktygsfältet för kalkylblad på knappen Skapa som matchar det objekt du uppdaterar.
Den här åtgärden öppnar [!UICONTROL Account Information] dialogrutan.

1. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

Den här åtgärden skapar en [!UICONTROL Response] kolumn i kalkylbladet som innehåller information om uppskattad segmentstorlek. Innan du anger data bör kalkylbladet för bulkberäkning se ut ungefär så här:

![](assets/estimate.png)
Om en satsvis uppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).

