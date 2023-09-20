---
description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Satsvisa förfrågningar
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 1%

---

# Satsvisa förfrågningar{#bulk-requests}

En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.

>[!IMPORTANT]
>
>Masshanteringsverktygen är inte ett officiellt Adobe-erbjudande som stöds. Felsökning och support via kundtjänst hanteras från fall till fall.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som har tilldelats i [!DNL Audience Manager] Gränssnittet respekteras i [!UICONTROL Bulk Management Tools].

The [!UICONTROL Request] kalkylbladet har ingen egen uppsättning kolumnrubriker och du behöver inte kopiera ID:n till någon av kolumnerna. I stället returneras data baserat på den åtgärdsknapp du klickar på i verktygsfältet. Och en valfri rapportfunktion returnerar en frekvens för pixelbränder och ett unikt antal användare för flera fasta tidsintervall.

Öppna [!UICONTROL Bulk Management Tools] och:

1. Klicka på **[!UICONTROL Request]** -fliken.
2. Klicka på en begärandeknapp som motsvarar de data du vill arbeta med i verktygsfältet högst upp i kalkylbladet. Du kan begära:

   * Algoritmiska modeller
   * Datakällor
   * Härledda signaler
   * Målmappningar
   * Algoritmiska, regelbaserade och ombord-anpassade egenskaper
   * Segment 
   * ID:n för trait- och segmentmapp

   The [!DNL Audience Manager] API skriver massdata tillbaka till [!UICONTROL Request] kalkylblad.

>[!NOTE]
>
>I resultatet `createTime` och `updateTime` kolumner returnerar data med exponentiell notation. De underliggande datum-/tidsstämplarna registreras i UNIX UTC-tid. För närvarande kan kalkylbladet inte returnera datum-/tidsstämplar i läsbart format.

Om gruppuppdateringen returnerar ett fel eller misslyckas finns mer information i [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
