---
description: Resten av API-metoder för att hantera behörigheter för objekt och grupper.
seo-description: Resten av API-metoder för att hantera behörigheter för objekt och grupper.
seo-title: API-metoder för behörighetshantering
solution: Audience Manager
title: API-metoder för behörighetshantering
uuid: 111d0f92-d92c-4d4b-b0d6-10dd3fa466ad
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---


# API-metoder för behörighetshantering {#permissions-management-api-methods}

Restmetoder [!DNL API] för att hantera behörigheter för objekt och grupper.

<!-- c_rest_api_perm_man.xml -->

## Visa tillgängliga objekttyper {#list-object-types}

En `GET` metod för att lista tillgängliga objekttyper som rollbaserade åtkomstkontroller kan ställas in på.

<!-- r_rest_api_perm_list.xml -->

### Begäran

`GET /api/v1/permissionable-object-types/`

### Svar

```
[ "SEGMENT", "TRAIT", "DESTINATION", "DERIVED_SIGNALS", "TAGS" ]
```

## Visa tillgängliga behörigheter för en objekttyp {#list-permissions-object-type}

En `GET` metod för att visa tillgängliga behörigheter för en objekttyp.

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