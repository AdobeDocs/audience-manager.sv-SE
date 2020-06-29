---
description: Metoder som gör att du programmässigt kan lista Audience Manager DCS-regioner.
seo-description: Metoder som gör att du programmässigt kan lista Audience Manager DCS-regioner.
seo-title: API-metoder för DCS-region
solution: Audience Manager
title: API-metoder för DCS-region
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# API-metoder för DCS-region {#dcs-region-api-methods}

Metoder som gör att du programmässigt kan lista Audience Manager- [!DNL DCS] regioner.

<!-- c_rest_api_regions.xml -->

En lista med regioner och deras motsvarande heltal finns i [DCS-regions-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista en specifik DCS-region {#list-specific-dcs-region}

En `GET` metod för att lista en viss [!DNL DCS] region.

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

En `GET` metod för att lista [!DNL DCS] regioner.

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
