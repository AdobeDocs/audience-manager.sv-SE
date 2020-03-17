---
description: Metoder som gör att du programmässigt kan lista Audience Manager DCS-regioner.
seo-description: Metoder som gör att du programmässigt kan lista Audience Manager DCS-regioner.
seo-title: API-metoder för DCS-region
solution: Audience Manager
title: API-metoder för DCS-region
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# API-metoder för DCS-region {#dcs-region-api-methods}

Metoder som gör att du programmässigt kan lista Audience Manager- [!UICONTROL DCS] regioner.

<!-- c_rest_api_regions.xml -->

En lista med regioner och deras motsvarande heltal finns i [DCS-regions-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista en specifik DCS-region {#list-specific-dcs-region}

En `GET` metod för att lista en viss [!UICONTROL DCS] region.

<!-- r_rest_api_regions_list_specific.xml -->

### Begäran

`GET /v1/dcs-regions/`*`<id>`*

### Exempelsvar

```
{ 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code>",
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  }
```

Returnerar `200 OK` om det lyckas.

En lista med regioner och deras motsvarande heltal finns i [DCS-regions-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista DCS-regioner {#list-dcs-regions}

En `GET` metod för att lista [!UICONTROL DCS] regioner.

<!-- r_rest_api_regions_list.xml -->

### Begäran

`GET /v1/dcs-regions/`

### Exempelsvar

```
[
  { 
    "regionId" : <id>, 
    "location" : "<location>",
    "host" : "<host>",
    "code" : "<code> # APSE, USE, etc,
    "status" : "ACTIVE" | "INACTIVE",
    "createTime" : long of milliseconds since epoch,
    "updateTime" : long of milliseconds since epoch,
    "crUID" : <userId who created>,
    "upUID" : <userId who updated>
  },
  ...
]
```

Returnerar `200 OK` om det lyckas.

En lista med regioner och deras motsvarande heltal finns i [DCS-regions-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
