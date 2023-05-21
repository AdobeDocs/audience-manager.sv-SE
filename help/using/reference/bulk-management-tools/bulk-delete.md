---
description: Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Satsvis radering
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 1%

---

# Satsvis radering{#bulk-delete}

Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som har tilldelats i [!DNL Audience Manager] Gränssnittet respekteras i [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>En massborttagning för målmappningar misslyckas om du har segment mappade till målet. Ta bort dina segment från den destinationen i användargränssnittet innan du försöker att ta bort mål gruppvis. Dessutom måste trait- och segmentmappar vara tomma innan du kan ta bort dem.

Om du vill ta bort flera objekt öppnar du [!UICONTROL Bulk Management Tools] kalkylblad och:

1. Klicka på **[!UICONTROL Headers]** och kopiera de nya rubrikerna för det objekt som du vill lägga till.
2. Klicka på **[!UICONTROL Delete]** -fliken.
3. Klistra in borttagningsrubrikerna på den första raden i uppdateringskalkylbladet.
4. Klistra in eller skriv in ID:n för de objekt som du vill ta bort i kolumnen nedanför rubriken.
5. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka **[!UICONTROL Submit]**.

   Kalkylbladet skapar en [!UICONTROL Results] kolumn. The [!UICONTROL Results] kolumn returnerar ett meddelande som anger om objektet har tagits bort eller ett felmeddelande.
Innan du anger data bör kalkylbladet för bulkuppdatering se ut ungefär så här:

![](assets/delete.png)

Om gruppuppdateringen returnerar ett fel eller misslyckas finns mer information i [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
