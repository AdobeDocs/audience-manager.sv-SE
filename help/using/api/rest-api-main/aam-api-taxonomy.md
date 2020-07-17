---
description: Metoder som gör att du kan visa den vanliga taxonomin för Audience Manager. Detta valfria klassificeringssystem organiserar egenskaper i branschstandardkategorier.
seo-description: Metoder som gör att du kan visa den vanliga taxonomin för Audience Manager. Detta valfria klassificeringssystem organiserar egenskaper i branschstandardkategorier.
seo-title: Taxonomiska API-metoder
solution: Audience Manager
title: Taxonomiska API-metoder
uuid: 4ee29ba5-e9ba-4498-a6ee-7343227dd7ba
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# Taxonomiska API-metoder {#taxonomic-api-methods}

Metoder som gör att du kan visa den vanliga taxonomin för Audience Manager. Detta valfria klassificeringssystem organiserar egenskaper i branschstandardkategorier.

<!-- c_rest_api_taxonomy.xml -->

>[!NOTE]
>
>Du kan inte skapa nya taxonomiska kategorier eller klassificera egenskaper med dessa metoder. Om du vill klassificera en egenskap anger du lämplig `categoryId` med en egen create- eller update-metod.

## Returnera en specifik taxonomi {#return-specific-taxonomy}

En `GET` metod som returnerar information om den angivna taxonomiska kategorin.

<!-- r_rest_api_taxonomy.xml -->

### Begäran

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*

### Svar

Ett lyckat svar returnerar `200 OK` och kategorin för det angivna ID:t. En misslyckad begäran returnerar `404 No Content` om ID:t inte finns.

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

En `GET` metod som returnerar en lista över kategorierna på den översta nivån i en array.

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

En `GET` metod som returnerar underkategorier för den angivna överordnade kategorin i en array.

<!-- r_rest_api_taxonomy_sub.xml -->

### Begäran

`GET https://api.demdex.com/v1/taxonomies/0/`*`<categoryId>`*`/childCategories/`

### Svar

Ett lyckat svar returnerar `200 OK` och kategorin för det angivna ID:t. En misslyckad begäran returnerar `404 No Content` om ID:t inte finns. Trunkerad för att vara snabb.

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
