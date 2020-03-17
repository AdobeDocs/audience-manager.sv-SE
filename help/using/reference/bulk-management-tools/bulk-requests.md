---
description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-description: En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.
seo-title: Massbegäranden
solution: Audience Manager
title: Massbegäranden
uuid: 0192d26a-4cea-4e12-9fea-388b92b382f1
translation-type: tm+mt
source-git-commit: cb17d417aa6b3cc213e69c5d71051f235d81c2a5

---


# Massbegäranden{#bulk-requests}

En gruppbegäran returnerar data som du kan använda med de olika rubrikerna i kalkylbladen Uppdatera, Skapa, Beräkna och Ta bort.

<!-- 

t_bulk_requests.xml

 -->

>[!NOTE]
>
>De [!UICONTROL Bulk Management Tools] stöds inte *av* [!DNL Audience Manager]. Det här verktyget finns endast till för att underlätta och för att underlätta. För större förändringar rekommenderar vi att du arbetar med API:erna [för](../../api/rest-api-main/aam-api-getting-started.md) Audience Manager i stället. [RBAC-gruppbehörigheter](../../features/administration/administration-overview.md) som tilldelats i [!DNL Audience Manager] användargränssnittet respekteras i [!UICONTROL Bulk Management Tools].

Kalkylbladet har ingen egen uppsättning kolumnrubriker och du behöver inte kopiera ID:n till någon av kolumnerna. [!UICONTROL Request] I stället returneras data baserat på åtgärdsknappen som du klickar på i verktygsfältet. Och en valfri rapportfunktion returnerar en frekvens för pixelbränder och ett unikt antal användare för flera fasta tidsintervall.

Om du vill göra en gruppbegäran öppnar du [!UICONTROL Bulk Management Tools] kalkylbladet och:

1. Klicka på **[!UICONTROL Request]** fliken.
2. Klicka på en begärandeknapp som motsvarar de data du vill arbeta med i verktygsfältet högst upp i kalkylbladet. Du kan begära:

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
