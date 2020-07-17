---
description: Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.
keywords: baaam
seo-description: Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.
seo-title: Satsvisa uppdateringar
solution: Audience Manager
title: Satsvisa uppdateringar
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---


# Satsvisa uppdateringar{#bulk-updates}

Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Om du vill göra större uppdateringar öppnar du [!UICONTROL Bulk Management Tools] kalkylbladet och:

1. Klicka på **[!UICONTROL Headers]** fliken och kopiera uppdateringshuvuden för objektet som du vill redigera.
2. Klicka på **[!UICONTROL Update]** fliken.
3. Klistra in uppdateringshuvuden i den första raden i uppdateringskalkylbladet. Observera följande:

   * När du uppdaterar en mapp krävs alla sidhuvuden.
   * När du uppdaterar segment eller egenskaper behöver du bara segmentets ID (SID) och rubrikelementet som behöver ändras. Ta bort rubriker som inte används.

4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka på en uppdateringsknapp som matchar det objekt du uppdaterar i verktygsfältet för kalkylblad.
Den här åtgärden öppnar [!UICONTROL Account Information] dialogrutan.

6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

   Kalkylbladet skapar en [!UICONTROL Results] kolumn. Kolumnen returnerar JSON-svaret för en slutförd åtgärd. [!UICONTROL Results] Se exempel på [REST API](../../api/rest-api-main/rest-api-main.md) . Innan du anger data bör kalkylbladet för bulkuppdatering se ut ungefär så här:

![](assets/update.png)

Om en satsvis uppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
