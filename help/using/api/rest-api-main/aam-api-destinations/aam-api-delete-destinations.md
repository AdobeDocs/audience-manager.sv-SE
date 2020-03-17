---
description: Metoderna DELETE och POST som gör att du kan ta bort mål- och segmentmappningar.
seo-description: Metoderna DELETE och POST som gör att du kan ta bort mål- och segmentmappningar.
seo-title: Ta bort mål
solution: Audience Manager
title: Ta bort mål
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# Ta bort mål {#delete-destinations}

`DELETE` och `POST` metoder som gör att du kan ta bort mål- och segmentmappningar.

<!-- r_delete_destinations_all.xml -->

## Ta bort ett mål

En `DELETE` metod som tar bort ett mål.

>[!NOTE]
>
>Du måste ta bort alla segmentkopplingar innan du kan ta bort ett mål.

* Begäran: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Svar: Returnerar koden `204 No Content` om den lyckas.

## Ta bort mål gruppvis

Ta bort flera mål med den här `POST` metoden. Skicka mål-ID:n ( `destinationId`) med en array i begärandetexten.

* Begäran: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Svar: Returnerar koden `204 No Content` om den lyckas.

## Ta bort målmappningar efter segmentmappnings-ID

En `POST` metod som tar bort målmappningar enligt angivet segment-ID.

* Begäran: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Svar: Returnerar koden `204 No Content` om den lyckas.