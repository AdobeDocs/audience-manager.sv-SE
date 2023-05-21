---
description: DELETE och POST-metoder där du kan ta bort mål- och segmentmappningar.
seo-description: DELETE and POST methods that let you remove destinations and segment mappings.
seo-title: Delete Destinations
solution: Audience Manager
title: Ta bort destinationer
uuid: 38fb2228-e564-49a3-9930-3139f8799a8f
feature: API
exl-id: eaac3908-75ab-42d2-93bd-e8979f8b2427
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---

# Ta bort destinationer {#delete-destinations}

`DELETE` och `POST` metoder som gör att du kan ta bort mål- och segmentmappningar.

<!-- r_delete_destinations_all.xml -->

## Ta bort ett mål

A `DELETE` som tar bort ett mål.

>[!NOTE]
>
>Du måste ta bort alla segmentkopplingar innan du kan ta bort ett mål.

* Begäran: `DELETE https://api.demdex.com/v1/destinations/`*`<destinationId>`*
* Svar: Returnerar kod `204 No Content` om det lyckas.

## Ta bort mål gruppvis

Ta bort flera mål med den här `POST` -metod. Skicka in mål-ID:n ( `destinationId`) med en array i begärandetexten.

* Begäran: `POST https://api.demdex.com/v1/destinations/bulk-delete/`
* Svar: Returnerar kod `204 No Content` om det lyckas.

## Ta bort målmappningar efter segmentmappnings-ID

A `POST` som tar bort målmappningar enligt angivet segment-ID.

* Begäran: `DELETE https://api.demdex.com/v1/destinations/` *`<destinationId>`*`/segments/`*`<mappingId>`*
* Svar: Returnerar kod `204 No Content` om det lyckas.
