---
description: Mappa segment till mål med dessa RESTful API-metoder.
seo-description: Mappa segment till mål med dessa RESTful API-metoder.
seo-title: Mappa segment till ett mål
solution: Audience Manager
title: Mappa segment till ett mål
uuid: 35358ace-3082-4e86-a6eb-d77281af6d7e
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---


# Mappa segment till ett mål {#map-segments-to-a-destination}

Mappa segment till mål med dessa [!DNL RESTful API] metoder.

<!-- c_api_map_seg_dest.xml -->

## Måltyper som stöds: Endast URL och cookie

Med de tillgängliga `POST` metoderna kan du mappa segment till [!UICONTROL URL] och [!UICONTROL cookie destinations] endast. För närvarande kan du inte mappa segment till [!UICONTROL server-to-server destinations] med dessa [!DNL REST API] metoder. Använd användargränssnittet i stället. Med de relaterade `GET` målmetoderna kan du emellertid hämta information om [!UICONTROL server-to-server destinations] som har skapats i användargränssnittet.

## Mappa ett segment till ett icke-serialiserat URL-mål {#map-segment-non-serial}

En `POST` metod som gör att du kan mappa ett segment till ett icke-seriellt [!UICONTROL URL] mål.

<!-- r_map_noserial_url.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-07-04"
}
```

### Svar

```
{
   "mappingId":65334,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4033,
   "elementName":"Sample games",
   "elementDescription":"Sample games pixel",
   "elementStatus":"active",
   "createTime":1338940094000,
   "updateTime":1338940094000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"https://adobe.com",
   "secureUrl":null,
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":null
}
```

## Mappa ett segment till ett serialiserat URL-mål {#map-segment-serial}

En `POST` metod som gör att du kan mappa ett segment till ett serialiserat [!UICONTROL URL] mål.

<!-- r_map_serialized_url.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<dataOrderId>`*`/traits/`

### Exempelbegäran

I begäran `traitAlias` motsvarar den nyckeln i ett nyckelvärdepar. Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Svar

```
{
   "mappingId":65335,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4034,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940401000,
   "updateTime":1338940401000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "url":"123",
   "secureUrl":"123",
   "tagCode":null,
   "secureTagCode":null,
   "traitAlias":"123"
}
```

## Mappa ett segment till ett cookie-mål: Enkelnyckel, ej serialiserad {#map-segment-cookie-noserial}

En `POST` metod som gör att du kan mappa ett segment till ett icke-serialiserat [!UICONTROL cookie] mål med enkel tangent.

<!-- r_map_cookie_noserial.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exempelbegäran

I begäran `valueAlias` motsvarar värdet i ett nyckelvärdepar. Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "valueAlias":"123"
}
```

### Svar

```
{
   "destinationMappingId":65336,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4035,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338940704000,
   "updateTime":1338940704000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":null,
   "valueAlias":"123"
}
```

## Mappa ett segment till ett cookie-mål: Flera nycklar, ej serialiserade {#map-segment-cookie-multi-noserial}

En `POST` metod som gör att du kan mappa ett segment till ett icke-serialiserat [!UICONTROL cookie] mål med flera nycklar.

<!-- r_map_cookie_multikey_noserial.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exempelbegäran

I begäran anger `traitAlias` och `valueAlias` anger nyckeln respektive värdet i ett nyckel/värde-par. Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Svar

```
{
   "mappingId":65338,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4037,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941092000,
   "updateTime":1338941092000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":1,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Mappa ett segment till ett cookie-mål: Serialiserad flernyckel {#map-segment-cookie-multi-serial}

En `POST` metod som gör att du kan mappa ett segment till en flernyckelsserialiserad [!UICONTROL cookie destination].

<!-- r_map_cookie_multikey_serialized.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exempelbegäran

I begäran anger `traitAlias` och `valueAlias` anger du nyckeln och värdet i ett nyckel/värde-par. Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"type",
   "valueAlias":"123"
}
```

### Svar

```
{
   "destinationMappingId":65340,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":4038,
   "elementName":"Sample Games",
   "elementDescription":"Migration of Sample Games Pixel",
   "elementStatus":"active",
   "createTime":1338941273000,
   "updateTime":1338941273000,
   "crUID":694,
   "upUID":694,
   "sid":87723,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":2,
   "traitAlias":"type",
   "valueAlias":"123"
}
```

## Mappa ett segment till ett mål för server-till-server {#map-segment-s2s}

En `POST` metod som gör att du kan koppla ett segment till ett befintligt [!UICONTROL server-to-server] mål. Observera dock att du inte kan skapa [!UICONTROL server-to-server] mål med de här tillgängliga [!DNL API] metoderna.

<!-- r_map_segment_s2s.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`

### Exempelbegäran

I begäran `traitAlias` motsvarar den nyckeln i ett nyckelvärdepar. Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid":87723,
   "traitType":"SEGMENT",
   "startDate":"2012-07-04",
   "traitAlias":"123"
}
```

### Svar

```
{
   "destinationMappingId":65341,
   "traitType":"SEGMENT",
   "traitValue":0,
   "destinationId":566,
   "elementName":"Sample",
   "elementDescription":"",
   "elementStatus":"active",
   "createTime":1338942118000,
   "updateTime":1338942118000,
   "crUID":308,
   "upUID":308,
   "sid":84326,
   "startDate":"2012-07-03",
   "endDate":null,
   "priority":null,
   "traitAlias":"123"
}
```

## Skapa målmappningar gruppvis {#bulk-create}

En `POST` metod som gör att du kan skicka en array med [!UICONTROL cookie] - eller [!UICONTROL URL] målmappningar.

<!-- r_bulk_create.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/bulk-create`

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Svar

Ett lyckat svar returnerar arrayen med skapade mappningar.

```
[
    {
        "mappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "mappingId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "orderId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Lägg till flera segment till ett mål {#add-segments-dest}

En `POST` metod som gör att du kan mappa flera segment till ett mål.

<!-- r_add_segments_to_destination.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`*`<destinationId>`*`bulk-create`

### Exempelbegäran

Skapa flera målmappningar i en array. Alla begärandavärden är obligatoriska om inget annat anges.

```
[
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
},
{
   "sid": 121070,
   "traitType":"SEGMENT",
   "url":"https://my.adobeconnect.com",
   "startDate":"2012-11-21"
}
]
```

### Svar

Returnerar en array med skapade mappningar.

```
[
    {
        "destinationMappingId": 103454,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Case of the Mondays",
        "elementDescription": "test",
        "elementStatus": "active",
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 105123,
        "startDate": "2012-11-19",
        "endDate": null,
        "priority": null,
        "url": "https://adobe.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    },
    {
        "traitToDataOrderId": 103455,
        "traitType": "SEGMENT",
        "traitValue": 0,
        "destinationId": 780,
        "elementName": "Test Trait",
        "elementDescription": "This trait",
        "elementStatus": 1,
        "createTime": 1353373234000,
        "updateTime": 1353373234000,
        "crUID": 1065,
        "upUID": 1065,
        "sid": 121070,
        "startDate": "2012-11-20",
        "endDate": null,
        "priority": null,
        "url": "https://my.adobeconnect.com",
        "secureUrl": null,
        "tagCode": null,
        "secureTagCode": null,
        "traitAlias": null
    }
]
```

## Uppdatera ett mål med mål-ID {#update-dest-data-order}

En `PUT` metod som gör att du kan uppdatera ett befintligt mål med `destinationId`.

<!-- r_update_destination_data_order_id.xml -->

### Begäran

`PUT https://api.demdex.com/v1/destinations/`*`<destinationId>`*

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "name":"Updated URL Destination (not serialized)",
   "description":"new description",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Svar

```
{
    "destinationType": "PUSH",
    "destinationId": 780,
    "dataSourceId": null,
    "pid": 1099,
    "name": "Updated URL Destination (not serialized)",
    "description": "new description",
    "startDate": null,
    "endDate": null,
    "status": 1,
    "createTime": 1348851790000,
    "updateTime": 1353372029000,
    "crUID": 884,
    "upUID": 1065,
    "domainRestrictions":"all_domains",
    "tagType": 0,
    "serializationEnabled": false,
    "urlFormatString": null,
    "secureUrlFormatString": null,
    "delimiter": null,
    "mappings": null
}
```

## Uppdatera en mappning till ett mål med mappnings-ID {#update-mapping-dest-id}

En `PUT` metod som gör att du kan uppdatera en mappning till ett mål med den angivna `mappingId`.

<!-- r_update_destination_trait_data_order_id.xml -->

### Begäran

`PUT https://api.demdex.com/v1/destinations/mappings/`*`<mappingId>`*

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{
   "sid": 105123,
   "traitType":"SEGMENT",
   "url":"https://adobe.com",
   "startDate":"2012-11-20"
}
```

### Svar

```
{
    "mappingId": 103453,
    "traitType": "SEGMENT",
    "traitValue": 0,
    "destinationId": 780,
    "elementName": "sample",
    "elementDescription": "test",
    "elementStatus": "active",
    "createTime": 1353373005000,
    "updateTime": 1353373005000,
    "crUID": 1065,
    "upUID": 1065,
    "sid": 105123,
    "startDate": "2012-11-19",
    "endDate": null,
    "priority": null,
    "url": "https://www.adobe.com/send?%ALIAS%",
    "secureUrl": null,
    "tagCode": null,
    "secureTagCode": null,
    "traitAlias": null
}
```

>[!MORELIKETHIS]
>
>* [Mål](../../../features/destinations/destinations.md)
>* [Målserialisering](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Förklaring av nyckelvärdepar](../../../reference/key-value-pairs-explained.md)

