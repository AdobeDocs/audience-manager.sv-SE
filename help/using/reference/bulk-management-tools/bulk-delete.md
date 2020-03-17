---
description: Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.
seo-description: Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.
seo-title: Massborttagning
solution: Audience Manager
title: Massborttagning
uuid: 679cde46-09fb-45c6-b84d-47e00e0e7c0a
translation-type: tm+mt
source-git-commit: 30d4cec4502a2cf8b217816ea4ae62eb1b22f641

---


# Massborttagning{#bulk-delete}

Med massborttagning kan du ta bort flera segment, egenskaper, mappar, härledda signaler, datakällor, modeller och mål med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om massborttagning.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] stöds inte *av* [!DNL Audience Manager]. Det här verktyget finns endast till för att underlätta och för att underlätta. För större förändringar rekommenderar vi att du arbetar med API:erna [för](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager i stället. [RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

>[!NOTE]
>
>En massborttagning för målmappningar misslyckas om du har segment mappade till målet. Ta bort dina segment från den destinationen i användargränssnittet innan du försöker att ta bort mål gruppvis. Dessutom måste trait- och segmentmappar vara tomma innan du kan ta bort dem.

Om du vill ta bort flera objekt öppnar du [!UICONTROL Bulk Management Tools] kalkylbladet och:

1. Klicka på **[!UICONTROL Headers]** fliken och kopiera de nya rubrikerna för objektet som du vill lägga till.
2. Klicka på **[!UICONTROL Delete]** fliken.
3. Klistra in borttagningsrubrikerna på den första raden i uppdateringskalkylbladet.
4. Klistra in eller skriv in ID:n för de objekt som du vill ta bort i kolumnen nedanför rubriken.
5. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

   Kalkylbladet skapar en [!UICONTROL Results] kolumn. Kolumnen returnerar ett meddelande som anger om objektet har tagits bort eller ett felmeddelande. [!UICONTROL Results] 
Innan du anger data bör kalkylbladet för bulkuppdatering se ut ungefär så här:

![](assets/delete.png)

Om en satsvis uppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
