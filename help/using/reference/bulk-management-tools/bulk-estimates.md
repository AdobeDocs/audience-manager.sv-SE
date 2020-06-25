---
description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-title: Massuppskattningar
solution: Audience Manager
title: Massuppskattningar
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 0%

---


# Massuppskattningar{#bulk-estimates}

En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Om du vill göra större uppdateringar öppnar du [!UICONTROL Bulk Management Tools] kalkylbladet och:

1. Klicka på **[!UICONTROL Headers]** fliken och kopiera [!UICONTROL Estimate Segment Size] rubriken.
2. Klicka på **[!UICONTROL Estimate]** fliken.
3. Klistra in uppskattningsrubriken i den första raden i uppskattningskalkylbladet.
4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka i verktygsfältet för kalkylblad på knappen Skapa som matchar det objekt du uppdaterar.
Den här åtgärden öppnar [!UICONTROL Account Information] dialogrutan.
6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

Den här åtgärden skapar en [!UICONTROL Response] kolumn i kalkylbladet som innehåller information om den uppskattade segmentstorleken. Innan du anger data bör kalkylbladet för bulkberäkning se ut ungefär så här:

![](assets/estimate.png)
Om en satsvis uppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).

