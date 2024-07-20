---
description: Skapa mål med dessa RESTful API-metoder.
seo-description: Create destinations with these RESTful API methods.
seo-title: Create Destinations
solution: Audience Manager
title: Skapa destinationer
uuid: 12f04151-ad0e-4cb6-8f3b-b5c427dc2cef
feature: API
exl-id: bae0f304-0ff3-4c5f-b432-19aef61d9d10
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 1%

---

# Skapa destinationer {#create-destinations}

Skapa mål med dessa [!UICONTROL RESTful API]-metoder.

<!-- c_create_destinations.xml -->

## Måltyper som stöds: Endast URL och cookie

Med de tillgängliga `POST`-metoderna kan du bara skapa [!UICONTROL URL] och [!UICONTROL cookie destinations]. Du kan för närvarande inte skapa [!UICONTROL server-to-server destinations] med dessa [!DNL REST API]-metoder. Med de relaterade målmetoderna `GET` kan du hämta information om [!UICONTROL server-to-server destinations] som har skapats i användargränssnittet.

## Skapa ett icke-seriellt URL-mål {#create-nonserial-dest}

En `POST`-metod som gör att du kan skapa ett mål som accepterar segment som består av nyckelvärdepar (t.ex. `gender=male` eller `gender=female`).

<!-- r_create_nonserial_destination.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`

### Exempelbegäran

Denna begäran skapar ett enda mål. Alla begärandavärden är obligatoriska om inget annat anges.

```
{ 
   "name":"Sample URL Destination (not serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":false
}
```

### Svar

En lyckad begäran returnerar `201 created` och målet.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4033, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (not serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"ACTIVE", 
   "destinationType":"PUSH", 
   "createTime":1338937116000, 
   "updateTime":1338937116000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":false, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "delimiter":null,
   "mappings":null
} 
```

## Skapa ett serialiserat URL-mål {#create-serial-url-dest}

En `POST`-metod som gör att du kan skapa ett mål som accepterar flera värden som är kopplade till en enskild nyckel (t.ex. `color=blue, red, green`).

<!-- r_create_serial_url_destination.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`

### Exempelbegäran

Ange säker [!DNL URL] och avgränsare för nyckelvärdepar som skickas till målet. Alla begärandavärden är obligatoriska om inget annat anges.

```
{ 
   "name":"Sample URL Destination (Serialized)",
   "description":"",
   "destinationType":"PUSH",
   "serializationEnabled":true,
   "urlFormatString":"https://www.adobe.com/send?data=%ALIAS%",
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%",
   "delimiter":","
}
```

### Svar

En uppdatering returnerar svarskoden `201 created` och målet.

```
{ 
   "destinationType":"PUSH", 
   "destinationId":4034, 
   "dataSourceId":null, 
   "pid":1099, 
   "name":"Sample URL Destination (Serialized)", 
   "description":"", 
   "startDate":null, 
   "endDate":null, 
   "status":"active", 
   "destinationType":"PUSH", 
   "createTime":1338937420000, 
   "updateTime":1338937420000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "tagType":0, 
   "serializationEnabled":true, 
   "urlFormatString":"https://www.adobe.com/send?%ALIAS%", 
   "secureUrlFormatString":"https://www.adobe.com/%ALIAS%", 
   "delimiter":"-", 
   "mappings":null 
}
```

## Skapa ett cookie-mål: En nyckel, icke-serialiserad {#create-cookie-dest-single}

En `POST`-metod som gör att du kan skapa en [!UICONTROL cookie destination] som accepterar segment som består av nyckelvärdepar (t.ex. `gender=male` eller `gender=female`).

<!-- r_cookie_destination_singlekey_noserial.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{ 
   "name":"Cookie Destination Single Key Not Serialized",
   "destinationType":"ADS",
   "adServerTypeID":1,
   "cookieName":"adobe",
   "cnameDomain":"adobe.com",
   "maxSize":"2048",
   "ttl":"0",
   "domainRestrictions":"inclusion",
   "siteIDs":[
      312
   ],
   "formatType":"single_key",
   "singleKey":"key",
   "keySeparator":"=",
   "valueSeparator":",",
   "serializationEnabled":false
}
```

### Svar

En uppdatering returnerar svarskoden `201 created` och målet.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4035, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Not Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338937984000, 
   "updateTime":1338937984000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"inclusion", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"key", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
      312 
   ], 
   "uparamEnabled":false
} 
```

## Skapa ett cookie-mål: En nyckel, serialiserad {#create-cookie-dest-single-serial}

En `POST`-metod som gör att du kan skapa ett mål som accepterar flera värden som är kopplade till en enskild nyckel (t.ex. `color=blue, red, green`).

<!-- r_cookie_destination_singlekey_serial.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{ 
   "name":"Cookie Destination Single Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
 
   ], 
   "formatType":"single_key", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Svar

En uppdatering returnerar svarskoden `201 created` och målet.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4036, 
   "pid":1099, 
   "name":"Cookie Destination Single Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938329000, 
   "updateTime":1338938329000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "singleKey":"k", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"single_key", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false
}
```

## Skapa en cookie-destination: flernyckelslicens, icke-serialiserad {#create-cookie-dest-multi}

En `POST`-metod som låter dig skapa ett mål som accepterar segment som innehåller flera nycklar med olika värden (t.ex. `gender=male; gender=female; color=blue; color=red`).

<!-- r_create_cookie_multikey_noserial.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{ 
   "name":"Ad Server Multi-Key Not Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains", 
   "siteIDs":[ 
  
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":false 
}
```

### Svar

En uppdatering returnerar svarskoden `201 created` och målet.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4037, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Not Serialized", 
   "status":1, 
   "destinationType":"ADS", 
   "createTime":1338938666000, 
   "updateTime":1338938666000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":false, 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
  
   ], 
   "uparamEnabled":false 
}
```

## Skapa ett cookie-mål: Serialiserad flernyckelsmodell {#create-cookie-dest-multi-serial}

En `POST`-metod där du kan skapa ett mål som accepterar segment som innehåller flera nycklar och värden (t.ex. `gender=male, female; color=blue, red, green`).

<!-- r_cookie_destination_multikey_serial.xml -->

### Begäran

`POST https://api.demdex.com/v1/destinations/`

### Exempelbegäran

Alla begärandavärden är obligatoriska om inget annat anges.

```
{ 
   "name":"Cookie Destination Multi-Key Serialized", 
   "destinationType":"ADS", 
   "adServerTypeID":1, 
   "cookieName":"adobe", 
   "cnameDomain":"adobe.com", 
   "maxSize":"2048", 
   "ttl":"0", 
   "domainRestrictions":"all_domains",
   "siteIDs":[ 
 
   ], 
   "formatType":"key_value", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "serializationEnabled":true, 
   "serializationSeparator":"#" 
}
```

### Svar

En uppdatering returnerar svarskoden `201 created` och målet.

```
{ 
   "destinationType":"ADS", 
   "destinationId":4038, 
   "pid":1099, 
   "name":"Ad Server Multi-Key Serialized", 
   "status":"active", 
   "destinationType":"ADS", 
   "createTime":1338938872000, 
   "updateTime":1338938872000, 
   "crUID":694, 
   "upUID":694, 
   "domainRestrictions":"all_domains", 
   "cnameDomain":"adobe.com", 
   "cookieName":"adobe", 
   "keySeparator":"=", 
   "valueSeparator":",", 
   "formatType":"key_value", 
   "transferMethod":0, 
   "serializationEnabled":true, 
   "serializationSeparator":"#", 
   "maxSize":2048, 
   "ttl":0, 
   "siteIDs":[ 
 
   ], 
   "uparamEnabled":false 
}
```

>[!MORELIKETHIS]
>
>* [Mål](../../../features/destinations/destinations.md)
>* [Målserialisering](../../../features/destinations/key-value-pairs.md#destination-serialized)
>* [Förklaring av nyckelvärdespar](../../../reference/key-value-pairs-explained.md)
