---
description: Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.
keywords: baaam
seo-description: Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.
seo-title: Satsvisa uppdateringar
solution: Audience Manager
title: Satsvisa uppdateringar
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 2%

---

# Satsvisa uppdateringar{#bulk-updates}

Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter ](../../features/administration/administration-overview.md) som tilldelats i  [!DNL Audience Manager] användargränssnittet respekteras i  [!UICONTROL Bulk Management Tools].

Om du vill göra satsvisa uppdateringar öppnar du [!UICONTROL Bulk Management Tools]-kalkylbladet och:

1. Klicka på fliken **[!UICONTROL Headers]** och kopiera uppdateringshuvuden för objektet som du vill redigera.
2. Klicka på fliken **[!UICONTROL Update]**.
3. Klistra in uppdateringshuvuden i den första raden i uppdateringskalkylbladet. Observera följande:

   * När du uppdaterar en mapp krävs alla sidhuvuden.
   * När du uppdaterar segment eller egenskaper behöver du bara segmentets ID (SID) och rubrikelementet som behöver ändras. Ta bort rubriker som inte används.

4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka på en uppdateringsknapp som matchar        objekt som du uppdaterar.
Den här åtgärden öppnar dialogrutan [!UICONTROL Account Information].

6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

   Kalkylbladet skapar en [!UICONTROL Results]-kolumn. Kolumnen [!UICONTROL Results] returnerar JSON-svaret för en slutförd åtgärd. Se [REST API:er](../../api/rest-api-main/rest-api-main.md) för exempel. Innan du anger data bör kalkylbladet för bulkuppdatering se ut ungefär så här:

![](assets/update.png)

Om gruppuppdateringen returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
