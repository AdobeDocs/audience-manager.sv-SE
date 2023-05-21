---
description: Resten av API-metoder för att hantera behörigheter för objekt och grupper.
seo-description: Rest API methods to manage permissions for objects and groups.
seo-title: Permissions Management API Methods
solution: Audience Manager
title: API-metoder för behörighetshantering
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
exl-id: 7aac8ea8-4120-4c6b-88a6-30e8aa727dc8
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 8%

---

# API-metoder för behörighetshantering {#permissions-management-api-methods}

Vila [!DNL API] metoder för att hantera behörigheter för objekt och grupper.

<!-- c_rest_api_perm_man.xml -->

## Visa tillgängliga objekttyper {#list-object-types}

A `GET` metod för att lista tillgängliga objekttyper som rollbaserade åtkomstkontroller kan ställas in på.

<!-- r_rest_api_perm_list.xml -->

### Begäran

`GET /api/v1/permissionable-object-types/`

### Svar

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Visa tillgängliga behörigheter för en objekttyp {#list-permissions-object-type}

A `GET` metod för att lista tillgängliga behörigheter för en objekttyp.

<!-- r_rest_api_perm_list_perms.xml -->

### Begäran

`GET /api/v1/permissionable-object-types/SEGMENT/`

### Svar

```
{ 
 "wildcard" : [ "VIEW_ALL_SEGMENTS", "EDIT_ALL_SEGMENTS", "CREATE_ALL_SEGMENTS", "DELETE_ALL_SEGMENTS", "MAP_ALL_SEGMENTS_TO_MODELS", "MAP_ALL_TO_DESTINATIONS" ], 
 "perObject" : [ "READ", "WRITE", "CREATE", "DELETE", "MAP_TO_MODELS", "MAP_TO_DESTINATION" ]
}
```

>[!NOTE]
>
>Objekttyperna TAGS och DERIVED SIGNALS har inga vanliga behörigheter att använda. Kontrollerna för de här objekttyperna ändras endast av behörigheterna Alla eller Inget jokertecken.
