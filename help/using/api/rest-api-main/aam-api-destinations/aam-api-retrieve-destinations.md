---
description: En GET-metod som returnerar målet för angivet mål-ID.
seo-description: En GET-metod som returnerar målet för angivet mål-ID.
seo-title: Returnera en destination med destinations-ID
solution: Audience Manager
title: Returnera en destination med destinations-ID
uuid: abce7426-55a5-4045-93a7-0487652a7189
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 5%

---


# Returnera en destination med destinations-ID {#return-a-destination-by-destination-id}

En `GET` metod som returnerar destinationen för den angivna `destinationId`.

<!-- r_get_all_destinations_order_id.xml -->

## Begäran

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*

>[!NOTE]
>
>Fylla i `mappings` fältet genom att skicka `includeMappings=true` i URL:en.

## Svar

```
{
   "destinationType":"PUSH",
   "destinationId":314,
   "dataSourceId":null,
   "pid":1099,
   "name":"sample destination",
   "description":"Turn",
   "startDate":null,
   "endDate":null,
   "status":"active",
   "destinationType":"PUSH",
   "createTime":1281997484000,
   "updateTime":1300752888000,
   "crUID":224,
   "upUID":308,
   "domainRestrictions":"ALL_DOMAINS",
   "tagType":0,
   "serializationEnabled":false,
   "urlFormatString":null,
   "secureUrlFormatString":null,
   "delimiter":null,
   "mappings":null
}
```

## Returnera alla mål {#return-all-destinations}

En `GET` metod som returnerar alla mål för den angivna partnern.

<!-- r_get_all_destinations.xml -->

### Begäran

`GET https://api.demdex.com/v1/destinations`

>[!NOTE]
>
>* *(Valfritt)* Skicka in `containsSegment=<sid>` för att returnera en array med alla mål som är mappade till det angivna segmentet. Frågan kan till exempel se ut ungefär så här: `GET .../destinations/?containsSegment=4321`.
   >
   >
* Returnerar inte det fullständiga målobjektet. Hämta målet efter dataordning om du behöver ett fullständigt ifyllt objekt.


### Valfria frågeparametrar

Du kan använda dessa valfria parametrar med API-metoder som returnerar *alla* egenskaper för ett objekt. Ange dessa alternativ i begärandesträngen när du skickar frågan till [!DNL API]. Se [Valfria parametrar](../../../api/rest-api-main/aam-api-getting-started.md#optional-api-query-parameters).

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
   <td colname="col2">Sorterar och returnerar resultat enligt den angivna <span class="keyword"> JSON</span> -egenskapen. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> descending</code> </td>
   <td colname="col2"> Sorterar och returnerar resultat i fallande ordning. Stigande är standard. </td>
  </tr>
  <tr valign="top"> 
   <td colname="col1"><code> search</code> </td>
   <td colname="col2">Returnerar resultat baserat på den angivna strängen som du vill använda som sökparameter. Anta att du vill hitta resultat för alla modeller som har ordet "Test" i något av värdefälten för det objektet. Din exempelbegäran kan se ut så här: <p><code> GET https://api.demdex.com/v1/models/?search=Test</code>. </p> <p>Du kan söka efter alla värden som returneras av en get all-metod. </p> </td>
  </tr>
 </tbody>
</table>

### Svar

```
[
   {
      "destinationId":364,
      "pid":1099,
      "name":"Test",
      "description":"",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1291345192000,
      "updateTime":1291347561000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   },
   {
      "destinationId":369,
      "pid":1099,
      "name":"sample destination",
      "status":"active",
      "destinationType":"PUSH",
      "createTime":1292631706000,
      "updateTime":1292631706000,
      "crUID":262,
      "upUID":262,
      "domainRestrictions":"all_domains"
   }
]
```

## Returnera en målmappning med mappnings-ID {#return-dest-mapping-id}

En `GET` metod som returnerar en enskild målmappning baserad på `mappingId`.

<!-- r_get_destination_trait_data_order.xml -->

### Begäran

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings/`*`<destinationMappingId>`*

### Svar

```
{
"mappingId": 14593,
"traitType": "SEGMENT",
"traitValue": 0,
"destinationId": 314,
"elementName": "sample",
"elementDescription": "Migration Pixel",
"elementStatus": "active",
"createTime": 1281997484000,
"updateTime": 1300752888000,
"crUID": 224,
"upUID": 308,
"sid": 80920,
"startDate": "2010-11-15",
"endDate": null,
"priority": null,
"url": "https://www.adobe.com/send?%ALIAS%",
"secureUrl": "https://www.adobe.com/send?%ALIAS%",
"tagCode": null,
"secureTagCode": null,
"traitAlias": null
}
```

## Returmålsmappningar {#return-dest-mappings}

En `GET` metod som returnerar mappningarna för ett mål.

<!-- r_get_destination_mappings.xml -->

>[!NOTE]
>
>Den returnerade mappningen är specifik för måltypen och konfigurationen.

### Begäran

`GET https://api.demdex.com/v1/destinations/`*`<destinationId>`*`/mappings`

>[!NOTE]
>
>Stöder sidindelningsparametrar.

### Svar

```
{
   "total":354,
   "page":0,
   "pageSize":2,
   "list":[
      {
         "destinationMappingId":14395,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":224,
         "upUID":308,
         "sid":80920,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
      {
         "destinationMappingId":15934,
         "traitType":"SEGMENT",
         "traitValue":0,
         "destinationId":314,
         "elementName":"sample pixel",
         "elementDescription":"Migration Pixel",
         "elementStatus":"active",
         "createTime":1281997484000,
         "updateTime":1300752888000,
         "crUID":242,
         "upUID":803,
         "sid":90820,
         "startDate":"2010-11-15",
         "endDate":null,
         "priority":null,
         "url":"https://www.adobe.com/send?%ALIAS%",
         "secureUrl":"https://www.adobe.com/send?%ALIAS%",
         "tagCode":null,
         "secureTagCode":null,
         "traitAlias":null
      }
   ]
{
```

## Returnera alla tillgängliga målplattformar {#return-dest-platforms}

En `GET` metod som returnerar alla tillgängliga enhetsplattformar för destinationer.

<!-- r_get_dest_platforms.xml -->

### Begäran

`GET /destinations/configurations/available-platforms/`

### Svar

```
[
BROWSER, ANDROID, iOS, ALL
]
```

## Returnera jobbhistorik för S2S- och S2S-måljobb {#return-job-history}

En `GET` metod som returnerar historikinformation för utgående jobb [!UICONTROL Server-to-Server] ( [!UICONTROL S2S]) och [!UICONTROL S2S] bulkdestinationsjobb.

<!-- r_get_job_history.xml -->

### Begäran

`GET https://api.demdex.com/v1/destinations/655/history/outbound?startDate=1000000000&endDate=1403034473000`

Obligatoriska frågeparametrar: `startDate` = *&lt;`epochtime`>* och `endDate` = *&lt;`epochtime`>*.

### Svar

```
[
{
      "pushID":34090,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337292466000,
      "endTime":1337292466000,
      "dataFileName":"ftp_655_269_iter_1337229891903.sync",
      "success":true
   },
   {
      "pushID":34104,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337346397000,
      "endTime":1337346397000,
      "dataFileName":"ftp_655_269_iter_1337285714581.sync",
      "success":true
   },
   {
      "pushID":34124,
      "orderID":655,
      "dataProviderID":269,
      "syncType":1,
      "fullPublish":false,
      "receivedRecords":1,
      "attemptedRecords":1,
      "successRecords":1,
      "startTime":1337396811000,
      "endTime":1337396812000,
      "dataFileName":"ftp_655_269_iter_1337338243600.sync",
      "success":true
   }
]
```
