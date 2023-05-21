---
description: Metoder som gör att du kan visa den vanliga taxonomin för Audience Manager. Detta valfria klassificeringssystem organiserar egenskaper i branschstandardkategorier.
seo-description: Methods that let you view the Audience Manager common taxonomy. This optional classification scheme organizes traits into industry standard categories.
seo-title: Taxonomic API Methods
solution: Audience Manager
title: Taxonomiska API-metoder
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
exl-id: 8bc6dcbb-7f5b-4a7b-998d-025eaf76c409
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%

---

# Taxonomiska API-metoder {#taxonomic-api-methods}

Metoder som gör att du kan visa den vanliga taxonomin för Audience Manager. Detta valfria klassificeringssystem organiserar egenskaper i branschstandardkategorier.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Du kan inte skapa nya taxonomiska kategorier eller klassificera egenskaper med dessa metoder. Om du vill klassificera en egenskap anger du lämplig `categoryId` med en egen metod för att skapa eller uppdatera.

## Returnera en specifik taxonomi {#return-specific-taxonomy}

A `GET` metod som returnerar information om den angivna taxonomiska kategorin.

<!-- r_rest_api_taxonomy.xml -->

### Begäran

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Svar

Ett godkänt svar returnerar `200 OK` och kategorin för det angivna ID:t. En misslyckad begäran returnerar `404 No Content` om ID:t inte finns.

```
{
    "crUID": 158,
    "name": "Arts & Entertainment",
    "upUID": 158,
    "description": "Arts & Entertainment",
    "categoryID": 1,
    "parentCategoryID": 0
}
```

## Returnera alla taxonomiska kategorier {#return-all-taxonomy-categories}

A `GET` metod som returnerar en lista över de översta kategorierna i en array.

<!-- r_rest_api_taxonomies.xml -->

### Begäran

`GET https://api.demdex.com/v1/taxonomies/0/`

### Svar

Trunkerad för att vara snabb.

```
[
    {
        "crUID": 158,
        "name": "Arts & Entertainment",
        "upUID": 158,
        "description": "Arts & Entertainment",
        "categoryID": 1,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Automotive",
        "upUID": 158,
        "description": "Automotive",
        "categoryID": 2,
        "parentCategoryID": 0
    },
    {
        "crUID": 158,
        "name": "Business",
        "upUID": 158,
        "description": "Business",
        "categoryID": 3,
        "parentCategoryID": 0
    }
]
```

## Returtaxonomiska underkategorier {#return-taxonomy-sub-categories}

A `GET` metod som returnerar underkategorier för den angivna överordnade kategorin i en array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Begäran

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Svar

Ett godkänt svar returnerar `200 OK` och kategorin för det angivna ID:t. En misslyckad begäran returnerar `404 No Content` om ID:t inte finns. Trunkerad för att vara snabb.

```
[
    {
        "crUID": 158,
        "name": "Books & Literature",
        "upUID": 158,
        "description": "Books & Literature",
        "categoryID": 25,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Celebrity Fan/Gossip",
        "upUID": 158,
        "description": "Celebrity Fan/Gossip",
        "categoryID": 49,
        "parentCategoryID": 1
    },
    {
        "crUID": 158,
        "name": "Fine Art",
        "upUID": 158,
        "description": "Fine Art",
        "categoryID": 72,
        "parentCategoryID": 1
    }
]
```
