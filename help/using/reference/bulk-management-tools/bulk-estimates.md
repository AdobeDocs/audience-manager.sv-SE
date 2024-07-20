---
description: En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.
seo-description: A bulk estimate returns segment size data based on segment rules. Follow these instructions to make a bulk estimate request.
seo-title: Bulk Estimates
solution: Audience Manager
title: Massuppskattningar
uuid: 63b2f06a-8ba0-47a2-bd0b-8039b2d4c95d
feature: BAAAM
exl-id: 8da0b48e-6fa4-43c9-a149-a39e465ac366
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 0%

---

# Massuppskattningar{#bulk-estimates}

En bulkuppskattning returnerar segmentstorleksdata baserat på segmentregler. Följ de här instruktionerna för att göra en gruppuppskattning.

>[!IMPORTANT]
>
>Masshanteringsverktygen är inte ett officiellt Adobe-erbjudande som stöds. Felsökning och support via kundtjänst hanteras från fall till fall.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i användargränssnittet för [!DNL Audience Manager] respekteras i [!UICONTROL Bulk Management Tools].

Om du vill göra satsvisa uppdateringar öppnar du kalkylbladet [!UICONTROL Bulk Management Tools] och:

1. Klicka på fliken **[!UICONTROL Headers]** och kopiera rubriken [!UICONTROL Estimate Segment Size].
2. Klicka på fliken **[!UICONTROL Estimate]**.
3. Klistra in uppskattningsrubriken i den första raden i uppskattningskalkylbladet.
4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka i verktygsfältet för kalkylblad på knappen Skapa som matchar det objekt du uppdaterar.
Den här åtgärden öppnar dialogrutan [!UICONTROL Account Information].
6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

Den här åtgärden skapar en [!UICONTROL Response]-kolumn i kalkylbladet som innehåller beräknade segmentstorleksdata. Innan du anger data bör kalkylbladet för bulkberäkning se ut ungefär så här:

![](assets/estimate.png)
Om en gruppuppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md) .
