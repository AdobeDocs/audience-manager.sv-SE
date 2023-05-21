---
description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-description: A bulk request returns data you can use with the different headers in the Update, Create, Estimate, and Delete worksheets.
seo-title: Bulk Requests
solution: Audience Manager
title: Satsvisa förfrågningar
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---

# Satsvisa förfrågningar{#bulk-requests}

En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som har tilldelats i [!DNL Audience Manager] Gränssnittet respekteras i [!UICONTROL Bulk Management Tools].

The [!UICONTROL Request] kalkylbladet har ingen egen uppsättning kolumnrubriker och du behöver inte kopiera ID:n till någon av kolumnerna. I stället returneras data baserat på åtgärdsknappen som du klickar på i verktygsfältet. Och en valfri rapportfunktion returnerar en frekvens för pixelbränder och ett unikt antal användare för flera fasta tidsintervall.

Om du vill göra gruppförfrågningar öppnar du [!UICONTROL Bulk Management Tools] kalkylblad och:

1. Klicka på **[!UICONTROL Request]** -fliken.
2. Klicka på en begärandeknapp som motsvarar de data du vill arbeta med i verktygsfältet högst upp i kalkylbladet. Du kan begära:

   * Algoritmiska modeller
   * Datakällor
   * Härledda signaler
   * Målmappningar
   * Algoritmiska, regelbaserade och ombord-anpassade egenskaper
   * Segment 
   * ID för trait- och segmentmapp

   The [!DNL Audience Manager] API skriver massdata tillbaka till [!UICONTROL Request] kalkylblad.

>[!NOTE]
>
>I resultatet `createTime` och `updateTime` kolumner returnerar data med exponentiell notation. De underliggande datum-/tidsstämplarna registreras i UNIX UTC-tid. För närvarande kan kalkylbladet inte returnera datum-/tidsstämplar i läsbart format.

Om gruppuppdateringen returnerar ett fel eller misslyckas finns mer information i [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
