---
description: Med Skapa gruppvis kan du skapa flera datakällor, härledda signaler, segment, egenskaper och andra objekt med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om att skapa en grupp.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Skapa satsvis
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 1%

---

# Skapa satsvis{#bulk-create}

Med Skapa gruppvis kan du skapa flera datakällor, härledda signaler, segment, egenskaper och andra objekt med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om att skapa en grupp.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som har tilldelats i [!DNL Audience Manager] Gränssnittet respekteras i [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Blanda inte objekttyper i en gruppskapandebegäran. Rubrikerna för varje objekt är unika och kan inte kombineras. Rensa kalkylbladet och gör en separat begäran för olika objekt.

Om du vill skapa objekt i grupp öppnar du [!UICONTROL Bulk Management Tools] kalkylblad och:

1. Klicka på **[!UICONTROL Headers]** och kopiera de nya rubrikerna för det objekt som du vill lägga till.
2. Klicka på **[!UICONTROL Create]** -fliken.
3. Klistra in de skapade rubrikerna på den första raden i uppdateringskalkylbladet.
4. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
5. Klicka i verktygsfältet för kalkylblad på knappen Skapa som matchar det objekt du uppdaterar.
Den här åtgärden öppnar [!UICONTROL Account Information] -dialogrutan.
6. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka **[!UICONTROL Submit]**.

Kalkylbladet skapar en [!UICONTROL Results] kolumn. The [!UICONTROL Results] kolumn returnerar JSON-svaret för en slutförd åtgärd. Se [REST API:er](../../api/rest-api-main/rest-api-main.md) till exempel. Innan du anger data bör kalkylbladet som du skapar gruppvis se ut som i följande exempel. Observera att alla olika skapandealternativ inte visas här. Här finns information som hjälper dig förstå hur ett ifyllt kalkylblad kan se ut.

![](assets/cretetraits.png)

Om gruppuppdateringen returnerar ett fel eller misslyckas finns mer information i [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
