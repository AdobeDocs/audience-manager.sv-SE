---
description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-title: Satsvisa beräkningar
solution: Audience Manager
title: Satsvisa beräkningar
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 3%

---


# Satsvisa beräkningar{#bulk-estimates}

En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter ](../../features/administration/administration-overview.md) som tilldelats i  [!DNL Audience Manager] användargränssnittet respekteras i  [!UICONTROL Bulk Management Tools].

Om du vill göra satsvisa uppdateringar öppnar du [!UICONTROL Bulk Management Tools]-kalkylbladet och:

1. Klicka på fliken **[!UICONTROL Headers]** och kopiera rubriken [!UICONTROL Estimate Segment Size].
2. Klicka på fliken **[!UICONTROL Estimate]**.
3. Klistra in uppskattningsrubriken i den första raden i uppskattningskalkylbladet.
4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka på knappen Skapa som matchar det objekt du uppdaterar i verktygsfältet för kalkylblad.
Den här åtgärden öppnar dialogrutan [!UICONTROL Account Information].
6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

Den här åtgärden skapar en [!UICONTROL Response]-kolumn i kalkylbladet som innehåller beräknade segmentstorleksdata. Innan du anger data bör kalkylbladet för bulkberäkning se ut ungefär så här:

![](assets/estimate.png)
Om en satsvis uppdatering returnerar ett fel eller misslyckas, se  [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).

