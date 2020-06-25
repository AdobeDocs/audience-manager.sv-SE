---
description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-title: Massbegäranden
solution: Audience Manager
title: Massbegäranden
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%

---


# Massbegäranden{#bulk-requests}

En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Kalkylbladet har ingen egen uppsättning kolumnrubriker och du behöver inte kopiera ID:n till någon av kolumnerna. [!UICONTROL Request] Instead, it returns data based on the action button you click in the toolbar. And, an optional reporting feature returns a frequency count for pixel fires and unique user count for several fixed time intervals.

To make bulk requests, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Klicka på **[!UICONTROL Request]** fliken.
2. In the tool bar at the top of the worksheet, click a request button corresponding to the data you want to work with. You can request:

   * Algoritmiska modeller
   * Datakällor
   * Härledda signaler
   * Målmappningar
   * Algoritmiska, regelbaserade och ombord-anpassade egenskaper
   * Segment
   * ID för trait- och segmentmapp
   API:t [!DNL Audience Manager] skriver massdata tillbaka till [!UICONTROL Request] kalkylbladet.

>[!NOTE]
>
>Resultatet blir att kolumnerna `createTime` och `updateTime` kolumnerna returnerar data med exponentiell notation. De underliggande datum-/tidsstämplarna registreras i UNIX UTC-tid. För närvarande kan kalkylbladet inte returnera datum-/tidsstämplar i läsbart format.

Om en satsvis uppdatering returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
