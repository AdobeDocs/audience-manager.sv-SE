---
description: Med Skapa gruppvis kan du skapa flera datakällor, härledda signaler, segment, egenskaper och andra objekt med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om att skapa en grupp.
seo-description: Med Skapa gruppvis kan du skapa flera datakällor, härledda signaler, segment, egenskaper och andra objekt med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om att skapa en grupp.
seo-title: Skapa satsvis
solution: Audience Manager
title: Skapa satsvis
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Skapa satsvis{#bulk-create}

Med Skapa gruppvis kan du skapa flera datakällor, härledda signaler, segment, egenskaper och andra objekt med en enda åtgärd. Följ de här instruktionerna för att göra en begäran om att skapa en grupp.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] stöds inte *av* [!DNL Audience Manager]. Det här verktyget finns endast till för att underlätta och för att underlätta. För större förändringar rekommenderar vi att du arbetar med API:erna [för](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager i stället. [RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Blanda inte objekttyper i en gruppskapandebegäran. Rubrikerna för varje objekt är unika och kan inte kombineras. Rensa kalkylbladet och gör en separat begäran för olika objekt.

Om du vill skapa flera objekt samtidigt öppnar du [!UICONTROL Bulk Management Tools] kalkylbladet och:

1. Klicka på **[!UICONTROL Headers]** fliken och kopiera de nya rubrikerna för objektet som du vill lägga till.
1. Klicka på **[!UICONTROL Create]** fliken.
1. Klistra in de skapade rubrikerna på den första raden i uppdateringskalkylbladet.
1. Klistra in eller skriv in data som du vill ändra i en motsvarande kolumn baserat på rubriketiketten.
1. Klicka i verktygsfältet för kalkylblad på knappen Skapa som matchar det objekt du uppdaterar.
Den här åtgärden öppnar [!UICONTROL Account Information] dialogrutan.

1. Ange nödvändig [inloggningsinformation](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) och klicka på **[!UICONTROL Submit]**.

Kalkylbladet skapar en [!UICONTROL Results] kolumn. Kolumnen returnerar JSON-svaret för en slutförd åtgärd. [!UICONTROL Results] Se exempel på [REST API](../../api/rest-api-main/rest-api-main.md) . Innan du anger data bör kalkylbladet som du skapar gruppvis se ut som i följande exempel. Observera att alla olika skapandealternativ inte visas här. Här finns information som hjälper dig förstå hur ett ifyllt kalkylblad kan se ut.

![](assets/cretetraits.png)

Om en satsvis uppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
