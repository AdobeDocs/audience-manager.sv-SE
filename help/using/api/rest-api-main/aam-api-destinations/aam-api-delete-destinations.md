---
description: DELETE och POST-metoder där du kan ta bort mål- och segmentmappningar.
seo-description: DELETE och POST-metoder där du kan ta bort mål- och segmentmappningar.
seo-title: Ta bort destinationer
solution: Audience Manager
title: Ta bort destinationer
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 5%

---


# Ta bort destinationer {#delete-destinations}

`DELETE` och  `POST` metoder som gör att du kan ta bort mål- och segmentmappningar.

<!-- r_delete_destinations_all.xml -->

## Ta bort ett mål

En `DELETE`-metod som tar bort ett mål.

>[!NOTE]
>
>Du måste ta bort alla segmentkopplingar innan du kan ta bort ett mål.

* Begäran: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Svar: Returnerar koden `204 No Content` om den lyckas.

## Ta bort mål gruppvis

Ta bort flera mål med den här `POST`-metoden. Skicka mål-ID:n ( `destinationId`) med en matris i begärandetexten.

* Begäran: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Svar: Returnerar koden `204 No Content` om den lyckas.

## Ta bort målmappningar efter segmentmappnings-ID

En `POST`-metod som tar bort målmappningar enligt angivet segment-ID.

* Begäran: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Svar: Returnerar koden `204 No Content` om den lyckas.