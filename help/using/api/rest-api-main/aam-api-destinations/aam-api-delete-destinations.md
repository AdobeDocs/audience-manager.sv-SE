---
description: DELETE och POST-metoder som gör att du kan ta bort mål- och segmentmappningar.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Ta bort mål
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

---

# Ta bort mål {#delete-destinations}

`DELETE`- och `POST`-metoder som gör att du kan ta bort mål- och segmentmappningar.

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
