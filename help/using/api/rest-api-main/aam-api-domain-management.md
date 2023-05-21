---
description: Domänhanteringsmetoder som gör att du kan skapa och hantera domäner som du vill skicka data till (endast för cookie-mål).
seo-description: Domain management methods that let you create and manage the domains to which you want to send data (for cookie destinations only).
seo-title: Domain Management API Methods
solution: Audience Manager
title: API-metoder för domänhantering
uuid: f2f08bc5-ea42-4171-9a43-0b20976f0cb0
feature: API
exl-id: f9907f6e-d553-4771-945b-2fddb3c9ce2f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# API-metoder för domänhantering {#domain-management-api-methods}

Domänhanteringsmetoder som gör att du kan skapa och hantera domäner som du vill skicka data till (endast för cookie-mål).

<!-- c_partner_site.xml -->

## Skapa en ny domän {#create-new-domain}

A `POST` metod som gör att du kan skapa en ny domän för (endast cookie-mål).

<!-- r_post_new_partner_site.xml -->

### Begäran

`POST` `https://api.demdex.com/v1/partner-sites/`

### Exempelbegäran

```
{
   "url":"example1.com"
}
```

### Svar

Ett godkänt svar returnerar `201 created` och partnerwebbplatsen, inklusive dess unika ID.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Ta bort en domän {#delete-domain}

A `DELETE` metod som gör att du kan ta bort en domän (endast för cookie-mål).

<!-- r_delete_partner_site.xml -->

### Begäran

`DELETE` `https://api.demdex.com/v1/partner-sites/`*`<site-Id>`*

### Svar

Ett godkänt svar returnerar `204 no content`. Returnerar `404 not found` om partnerwebbplatsen inte kan hittas.

## Returnera egenskaper för en domän {#return-props-domain}

A `GET` metod som returnerar information om den angivna domänen (endast för cookie-mål).

<!-- r_get_partner_site.xml -->

### Begäran

`GET` `https://api.demdex.com/v1/partner-sites/`*`<siteId>`*

### Svar

Ett godkänt svar returnerar `200 OK` och data enligt exemplet nedan. Returnerar `404 Not found` om plats-ID:t eller partnern inte hittas.

```
{
    "pid": 1111,
    "siteId": 111,
    "url": "example1.com"
}
```

## Returnera egenskaper för alla domäner {#return-props-all-domains}

A `GET` metod som returnerar information om alla dina domäner (endast för cookie-mål).

<!-- r_get_partner_sites.xml -->

### Begäran

`GET https://api.demdex.com/v1/partner-sites/`

### Valfria frågeparametrar

Du kan använda de här valfria parametrarna med [!DNL API] metoder som returnerar *alla* egenskaper för ett objekt. Ange dessa alternativ i begärandesträngen när frågan skickas till [!DNL API]. Se [Valfria parametrar](../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

<table id="table_B05A8EE22C9A4C72B84A8479E1AB7D0A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"><code> page</code> </td> 
   <td colname="col2"> Returnerar resultat per sidnummer. Numreringen börjar vid 0. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code> pageSize</code> </td> 
   <td colname="col2"> Anger antalet svarsresultat som returneras av begäran (10 är standard). </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> sortBy</code> </td> 
   <td colname="col2"> Sorterar och returnerar resultat enligt den angivna JSON-egenskapen. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sorterar och returnerar resultat i fallande ordning. Stigande är standard. </td>
  </tr>
  <tr valign="top">
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Returnerar resultat baserat på den angivna strängen som du vill använda som sökparameter. Anta att du vill hitta resultat för alla modeller som har ordet "Test" i något av värdefälten för det objektet. Din exempelbegäran kan se ut så här: <p><code> `GET` `https://api.demdex.com/v1/models/?search=Test`</code>. </p> <p>Du kan söka efter alla värden som returneras av en get all-metod. </p> </td>
  </tr> 
 </tbody> 
</table>

### Svar

Ett godkänt svar returnerar `200 OK` och data i en array enligt exemplet nedan. Returnerar `404 Not found` om plats-ID:t eller partnern inte hittas.

```
[
    {
        "pid": 1111,
        "siteId": 111,
        "url": "example1.com"
    },
    {
        "pid": 2222,
        "siteId": 222,
        "url": "example2.com"
    },
    {
        "pid": 3333,
        "siteId": 333,
        "url": "example3.com"
    }
]
```
