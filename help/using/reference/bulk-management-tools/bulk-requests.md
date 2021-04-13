---
description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-title: Satsvisa förfrågningar
solution: Audience Manager
title: Satsvisa förfrågningar
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
feature: BAAAM
exl-id: a0597bf4-79c8-404d-ba3b-a92c6b5c9c06
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 3%

---

# Satsvisa förfrågningar{#bulk-requests}

En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>[RBAC-gruppbehörigheter ](../../features/administration/administration-overview.md) som tilldelats i  [!DNL Audience Manager] användargränssnittet respekteras i  [!UICONTROL Bulk Management Tools].

Kalkylbladet [!UICONTROL Request] har ingen egen uppsättning kolumnrubriker och du behöver inte kopiera ID:n till någon av kolumnerna. I stället returneras data baserat på åtgärdsknappen som du klickar på i verktygsfältet. Och en valfri rapportfunktion returnerar en frekvens för pixelbränder och ett unikt antal användare för flera fasta tidsintervall.

Om du vill göra gruppförfrågningar öppnar du [!UICONTROL Bulk Management Tools]-kalkylbladet och:

1. Klicka på fliken **[!UICONTROL Request]**.
2. Klicka på en begärandeknapp som motsvarar de data du vill arbeta med i verktygsfältet högst upp i kalkylbladet. Du kan begära:

   * Algoritmiska modeller
   * Datakällor
   * Härledda signaler
   * Målmappningar
   * Algoritmiska, regelbaserade och ombord-anpassade egenskaper
   * Segment 
   * ID för trait- och segmentmapp

   API:t [!DNL Audience Manager] skriver massdata tillbaka till kalkylbladet [!UICONTROL Request].

>[!NOTE]
>
>I resultatet returnerar kolumnerna `createTime` och `updateTime` data i exponentiell notation. De underliggande datum-/tidsstämplarna registreras i UNIX UTC-tid. För närvarande kan kalkylbladet inte returnera datum-/tidsstämplar i läsbart format.

Om gruppuppdateringen returnerar ett fel eller misslyckas, se [Felsökning för grupphanteringsverktyg](../../reference/bulk-management-tools/bulk-troubleshooting.md).
