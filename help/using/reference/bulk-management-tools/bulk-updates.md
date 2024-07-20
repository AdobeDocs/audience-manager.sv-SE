---
description: Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Massuppdateringar
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Massuppdateringar{#bulk-updates}

Med en gruppuppdatering kan du redigera flera segment, egenskaper, modeller, datakällor samt segmentera eller anpassa mappelement i en enda åtgärd. Följ dessa anvisningar för att göra satsvisa uppdateringar.

>[!IMPORTANT]
>
>Masshanteringsverktygen är inte ett officiellt Adobe-erbjudande som stöds. Felsökning och support via kundtjänst hanteras från fall till fall.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i användargränssnittet för [!DNL Audience Manager] respekteras i [!UICONTROL Bulk Management Tools].

Om du vill göra satsvisa uppdateringar öppnar du kalkylbladet [!UICONTROL Bulk Management Tools] och:

1. Klicka på fliken **[!UICONTROL Headers]** och kopiera uppdateringshuvuden för objektet som du vill redigera.
2. Klicka på fliken **[!UICONTROL Update]**.
3. Klistra in uppdateringshuvuden i den första raden i uppdateringskalkylbladet. Observera följande:

   * När du uppdaterar en mapp krävs alla sidhuvuden.
   * När du uppdaterar segment eller egenskaper behöver du bara segmentets ID (SID) och rubrikelementet som behöver ändras. Ta bort rubriker som inte används.

4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka på en uppdateringsknapp som matchar        objekt som du uppdaterar.
Den här åtgärden öppnar dialogrutan [!UICONTROL Account Information].

6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

   Kalkylbladet skapar en [!UICONTROL Results]-kolumn. Kolumnen [!UICONTROL Results] returnerar JSON-svaret för en slutförd åtgärd. Se [REST API:erna](../../api/rest-api-main/rest-api-main.md) för exempel. Innan du anger data bör kalkylbladet för bulkuppdatering se ut ungefär så här:

![](assets/update.png)

Om gruppuppdateringen returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
