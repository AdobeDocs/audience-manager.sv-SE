---
description: Metoder som gör att du programmässigt kan lista Audience Manager DCS-regioner.
seo-description: Methods that let you programmatically list Audience Manager DCS regions.
seo-title: DCS Region API Methods
solution: Audience Manager
title: API-metoder för DCS-region
uuid: 00b70927-b3b7-46bb-8be1-37c6100ecf80
feature: API
exl-id: 3cd1700e-6914-46be-a0be-a870c472343e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

---

# API-metoder för DCS-region {#dcs-region-api-methods}

Metoder som du kan använda för att programmässigt lista Audience Manager [!DNL DCS] regioner.

<!-- c_rest_api_regions.xml -->

En lista med regioner och deras motsvarande heltal finns på [DCS-region-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista en specifik DCS-region {#list-specific-dcs-region}

A `GET` metod för att lista en viss [!DNL DCS] region.

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

En lista med regioner och deras motsvarande heltal finns på [DCS-region-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

## Lista DCS-regioner {#list-dcs-regions}

A `GET` metod att lista [!DNL DCS] regioner.

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

En lista med regioner och deras motsvarande heltal finns på [DCS-region-ID, -platser och -värdnamn](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
