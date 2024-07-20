---
description: Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.
seo-description: Bulk delete lets you remove multiple segments, traits, folders, derived signals, data sources, models, and destinations with a single operation. Follow these instructions to make a bulk delete request.
seo-title: Bulk Delete
solution: Audience Manager
title: Massborttagning
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
feature: BAAAM
exl-id: 3ff530dd-66d0-4dd3-a6e6-afe4a9cb5ba4
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%

---

# Massborttagning{#bulk-delete}

Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.

>[!IMPORTANT]
>
>Masshanteringsverktygen är inte ett officiellt Adobe-erbjudande som stöds. Felsökning och support via kundtjänst hanteras från fall till fall.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i användargränssnittet för [!DNL Audience Manager] respekteras i [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>En massborttagning för målmappningar misslyckas om du har segment mappade till målet. Ta bort dina segment från den destinationen i användargränssnittet innan du försöker att ta bort mål gruppvis. Dessutom måste trait- och segmentmappar vara tomma innan du kan ta bort dem.

Om du vill ta bort flera objekt öppnar du kalkylbladet [!UICONTROL Bulk Management Tools] och:

1. Klicka på fliken **[!UICONTROL Headers]** och kopiera rubrikerna för det objekt som du vill lägga till.
2. Klicka på fliken **[!UICONTROL Delete]**.
3. Klistra in borttagningsrubrikerna på den första raden i uppdateringskalkylbladet.
4. Klistra in eller skriv in ID:n för de objekt som du vill ta bort i kolumnen nedanför rubriken.
5. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

   Kalkylbladet skapar en [!UICONTROL Results]-kolumn. Kolumnen [!UICONTROL Results] returnerar ett meddelande som anger om objektet har tagits bort eller ett felmeddelande.
Innan du anger data bör kalkylbladet för bulkuppdatering se ut ungefär så här:

![](assets/delete.png)

Om gruppuppdateringen returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
