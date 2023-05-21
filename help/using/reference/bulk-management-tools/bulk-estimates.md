---
description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Satsvisa beräkningar
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---

# Satsvisa beräkningar{#bulk-estimates}

En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som har tilldelats i [!DNL Audience Manager] Gränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Om du vill göra satsvisa uppdateringar öppnar du [!UICONTROL Bulk Management Tools] kalkylblad och:

1. Klicka på **[!UICONTROL Headers]** och kopiera [!UICONTROL Estimate Segment Size] header.
2. Klicka på **[!UICONTROL Estimate]** -fliken.
3. Klistra in uppskattningsrubriken i den första raden i uppskattningskalkylbladet.
4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka i verktygsfältet för kalkylblad på knappen Skapa som matchar det objekt du uppdaterar.
Den här åtgärden öppnar [!UICONTROL Account Information] -dialogrutan.
6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka **[!UICONTROL Submit]**.

Den här åtgärden skapar en [!UICONTROL Response] i kalkylbladet som innehåller information om uppskattad segmentstorlek. Innan du anger data bör kalkylbladet för bulkberäkning se ut ungefär så här:

![](assets/estimate.png)
Om gruppuppdateringen returnerar ett fel eller misslyckas finns mer information i [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
