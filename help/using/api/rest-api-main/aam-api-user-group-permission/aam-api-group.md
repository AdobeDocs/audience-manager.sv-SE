---
description: Resten av API-metoder för att hantera grupper, inklusive att skapa, uppdatera, lista och ta bort grupper.
seo-description: Rest API methods to manage groups, including creating, updating, listing, deleting groups.
seo-title: Group Management API Methods
solution: Audience Manager
title: API-metoder för grupphantering
uuid: fe042eb5-ea12-42fe-be98-d721f987a914
feature: API
exl-id: b43c8404-1853-4306-8f26-96d9191a2548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 0%

---

# API-metoder för grupphantering {#group-management-api-methods}

Återställ [!DNL API] metoder för att hantera grupper, inklusive att skapa, uppdatera, lista och ta bort grupper.

<!-- c_rest_api_user_man_group.xml -->

## Skapa en grupp {#create-group}

En `POST`-metod för att skapa en ny användargrupp.

<!-- r_rest_api_group_create.xml -->

### Begäran

`POST /api/v1/groups/`

### Exempelbegärandebrödtext

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Svar

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Uppdatera en grupp {#update-group}

En `PUT`-metod för att uppdatera en användargrupp.

<!--
r_rest_api_group_update.xml
-->

### Begäran

`PUT /api/v1/groups/`*`<groupId>`*

### Exempelbegärandebrödtext

```
 {
    "name" : <string>,
    "description" : <string_may_be_null>,
 }
```

### Svar

```
  {
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }
```

## Listgrupper {#list-groups}

En `GET`-metod för att lista användargrupper.

<!--
r_rest_api_group_list.xml
-->

### Begäran

`GET /api/v1/groups/`

### Svar

```
[
  { 
    "groupId" : <integer>,
    "pid" : <integer>,
    "name" : <string>,
    "description" : <string_may_be_null>,
    "membershipCount" : <integer>,
    "wildcards" : <list of strings>,
    "users" : <list of user IDs>
  }, ...
]
```

## Ta bort en grupp {#delete-groups}

En `DELETE`-metod som tar bort en användargrupp och alla medlemmar från den gruppen.

<!-- r_rest_api_group_delete.xml -->

### Begäran

`DELETE /api/v1/groups/`*`<groupId>`*

Returnerar `204 No Content` om det lyckas. Om en konflikt skulle returnera `409 Conflict`.

## Ta bort grupper gruppvis {#delete-groups-bulk}

En `DELETE`-metod för att ta bort flera grupper samtidigt och ta bort alla medlemmar från den gruppen.

<!-- r_rest_api_group_delete_bulk.xml -->

### Begäran

`DELETE /api/v1/groups/bulk-delete`

Returnerar `204 No Content` om det lyckas. Om en konflikt skulle returnera `409 Conflict`.

## Visa alla behörigheter för en grupp {#list-permissions-group}

En `GET`-metod för att lista behörighetsobjekten i en grupp.

<!-- r_rest_api_perm_list_group.xml -->

### Begäran

`GET /api/v1/groups/{groupId}/permissions`

### Svar

```
[{
 "objectId" : 34,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },

{
 "objectId" : "234",
 "objectType": "TRAIT",
 "permissions": ["READ", "WRITE", "DELETE", "MAP_TO_MODELS"]
 },
 {
 "objectId" : 277,
 "objectType": "SEGMENT",
 "permissions": ["READ", "WRITE", "MAP_TO_MODELS"]
 }
]
```

Returnerar `400 Bad Request` om gruppen inte är tillgänglig.

## Ange behörigheter för en grupp {#set-permissions-group}

En `PUT`-metod för att uppdatera gruppbehörigheter. Den här metoden skriver över de gamla behörigheterna med de nya behörigheterna.

<!-- r_rest_api_perm_set.xml -->

### Begäran

`PUT /api/v1/groups/{groupId}/permissions/`

### Svar

```
[ 
  { "objectType" : "SEGMENT",
    "objectId" : 563,
    "permissions" : [ "READ", "WRITE"]
  },
  { "objectType" : "SEGMENT",
    "objectId" : 2363,
    "permissions" : [ "CREATE", "WRITE"]
  },
  { "objectType" : "TRAIT",
    "objectId" : 83498,
    "permissions" : [ "READ", "MAP_TO_SEGMENTS"]
  },
  { "objectType" : "DESTINATION",
    "objectId" : 304,
    "permissions" : [ "READ", "WRITE", "CREATE"]
  }
]
```

Exempelsvaret representerar den uppdaterade listan med behörighetsobjekt.

Returnerar `200 OK` om det lyckas. Returnerar `400` om någon angiven behörighet är ogiltig. Kan även returnera `403` om objektet inte är tillgängligt för den inloggade användaren.
