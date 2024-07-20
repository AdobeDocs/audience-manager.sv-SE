---
description: Valfria metoder som gör att du kan tilldela egenskaper till en användardefinierad typ eller kategori, vanligtvis efter funktion eller för dina egna interna rapporteringsprocesser.
seo-description: Optional methods that let you to assign traits to a user-defined type or category, usually according to function or for your own internal reporting processes.
seo-title: Trait Type Methods
solution: Audience Manager
title: Trait Type-metoder
uuid: 082931d5-457b-4622-817b-86303f38c26a
feature: API
exl-id: d450f9ce-2abb-4a8b-b8db-2962b84fb341
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Trait Type-metoder {#trait-type-methods}

Valfria metoder som gör att du kan tilldela egenskaper till en användardefinierad typ eller kategori, vanligtvis efter funktion eller för dina egna interna rapporteringsprocesser.

<!-- c_rest_api_trait_types_intro.xml -->

>[!NOTE]
>
>Trait-typmetoder tilldelar inte egenskaper till kategorier som används av [Common taxonomy](../../api/rest-api-main/aam-api-taxonomy.md#taxonomic-api-methods). Tänk på dessa som etiketter som är åtskilda från den vanliga taxonomin.

För visuell referens är [!UICONTROL Trait Types] en nedrullningsbar kontroll som finns i [!DNL UI] under **[!UICONTROL Traits > Create new trait > Basic Information]**.

## Skapa en ny dragtyp {#create-trait-type}

En `POST`-metod som gör att du kan skapa en ny trait-typ.

<!-- r_rest_api_create_trait_type.xml -->

### Begäran

`POST https://api.demdex.com/v1/customer-trait-types`

### Exempelbegäran

```
{
"name":"Custom trait type"
}
```

### Svar

```
{
    "pixelType": 34,
    "pid": 1099,
    "name": "Custom type",
    "description": null,
    "crUID": 694,
    "upUID": 694,
    "createTime": 1358297352000,
    "updateTime": 1358297352000
}
```

## Returnera egenskaper för en dragtyp {#return-props}

En `GET`-metod som returnerar information om den angivna trait-typen.

<!-- r_rest_api_get_trait_type.xml -->

### Begäran

`GET https://api.demdex.com/v1/customer-trait-types/`*`<customerTraitTypeId>`*

### Svar

```
{
    "pixelType": 4,
    "pid": 0,
    "name": "Delivery Event",
    "description": "Delivery Event",
    "crUID": 158,
    "upUID": 158,
    "createTime": 1299115496000,
    "updateTime": 1299115496000
}
```

## Returnera egenskaper för alla trait-typer {#return-props-all}

En `GET`-metod som returnerar information om alla dina trait-typer i en array.

<!-- r_rest_api_get_trait_types.xml -->

### Begäran

`GET https://api.demdex.com/v1/customer-trait-types/`

### Svar

```
[
    {
        "pixelType": 200,
        "pid": 1099,
        "name": "Customer Specific Trait Type",
        "description": "Test",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1349990458000,
        "updateTime": 1349990458000
    },
    {
        "pixelType": 1,
        "pid": 0,
        "name": "User Trait",
        "description": "User Trait",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115492000,
        "updateTime": 1299115492000
    },
    {
        "pixelType": 2,
        "pid": 0,
        "name": "Site Visitor",
        "description": "Site Visitor",
        "crUID": 158,
        "upUID": 158,
        "createTime": 1299115493000,
        "updateTime": 1299115493000
    }
]
```
