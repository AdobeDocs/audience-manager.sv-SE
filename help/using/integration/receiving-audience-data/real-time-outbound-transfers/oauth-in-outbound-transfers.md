---
description: När du publicerar segment till partnermålet via en realtidsintegration mellan server och server, kan Audience Manager konfigureras för autentisering med OAuth 2.0 när begäranden görs. Då kan du skicka autentiserade begäranden från Audience Manager till slutpunkten.
seo-description: When publishing segments to the partner destination via a realtime server-to-server integration, Audience Manager can be set up to authenticate using OAuth 2.0 when making the requests. This presents the ability to issue authenticated requests from Audience Manager to your endpoint.
seo-title: OAuth 2.0 Integration for Real-Time Outbound Transfers
solution: Audience Manager
title: OAuth 2.0-integrering för utgående överföringar i realtid
uuid: a39e370c-b3bd-4b06-a1af-60a024ee7ee4
feature: Outbound Data Transfers
exl-id: eef3a3ae-1a3f-47e9-aab6-abf878e4cb77
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# [!DNL OAuth 2.0]-integrering för utgående överföringar i realtid{#oauth-integration-for-real-time-outbound-transfers}

När du publicerar segment till partnermålet via en server-till-server-integration i realtid, kan Audience Manager konfigureras för autentisering med [!DNL OAuth 2.0] när begäranden görs. Då kan du skicka autentiserade begäranden från Audience Manager till slutpunkten.

## Autentiseringsflöde {#auth-flow}

Autentiseringsimplementeringen av [!DNL Adobe Audience Manager] [OAuth 2.0](https://tools.ietf.org/html/rfc6749#section-4.4) baseras på bidragsflödet för klientautentiseringsuppgifter och följer dessa steg:

1. Du måste ge oss följande:
   * Slutpunkten [!DNL OAuth 2.0] som genererar autentiseringstoken.
   * Autentiseringsuppgifterna som används för att generera en token.
1. En [!DNL Audience Manager]-konsult konfigurerar [destination](../../../features/destinations/destinations.md) med den information du har angett.
1. När ett segment har mappats till det här målet gör vårt dataöverföringssystem i realtid, [IRIS](../../../reference/system-components/components-data-action.md#iris), en `POST`-begäran till tokenslutpunkten för utbyte av autentiseringsuppgifter för en innehavartoken.
1. För varje segmentpubliceringsbegäran till partnerslutpunkten använder [!UICONTROL IRIS] innehavartoken för att autentisera.

![](assets/oauth2-iris.png)

## Krav {#auth-requirements}

Som [!DNL Audience Manager]-partner krävs följande slutpunkter för att ta emot autentiserade begäranden:

### Slutpunkt 1 som används av IRIS för att erhålla en innehavartoken

Den här slutpunkten godkänner inloggningsuppgifterna som anges i steg 1 och genererar en innehavartoken som kommer att användas för efterföljande begäranden.

* Slutpunkten måste acceptera `HTTP POST` begäranden.
* Slutpunkten måste acceptera och titta på rubriken [!DNL Authorization]. Värdet för den här rubriken blir: `Basic <credentials_provided_by_partner>`.
* Slutpunkten måste granska rubriken [!DNL Content-type] och verifiera att dess värde är `application/x-www-form-urlencoded ; charset=UTF-8`.
* Innehållet i begäran blir `grant_type=client_credentials`.

### Exempelbegäran från Audience Manager till partnerslutpunkten för att erhålla en innehavartoken

```
POST /oauth2/token HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Basic zq2LOO1CcYGrODS5nXiNHpEz97eCpVHAoMF8pAgCntXAzxp5uRV7DTAE2qtPLjhMQwrEX3O6MHV4S
Content-Type: application/x-www-form-urlencoded;charset=UTF-8
Content-Length: 29
Accept-Encoding: gzip
  
grant_type=client_credentials
```

### Exempelsvar från partnerslutpunkten

```
HTTP/1.1 200 OK
Status: 200 OK
Content-Type: application/json; charset=utf-8
...
Content-Encoding: gzip
Content-Length: 121
  
{"token_type":"Bearer","access_token":"glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY"}
```

### Slutpunkt 2 som används av IRIS för att publicera segment med hjälp av bearer-token

[!DNL Audience Manager] skickar data till den här slutpunkten i nästan realtid när användare kvalificerar sig för segment. Dessutom kan den här metoden skicka batchar med offline- eller inbyggda data så ofta som var 24:e timme.

Bearer-token som genereras av slutpunkt 1 används för att skicka begäranden till den här slutpunkten. Dataöverföringssystemet [!DNL Audience Manager] i realtid, [IRIS](../../../reference/system-components/components-data-action.md#iris), konstruerar en normal HTTPS-begäran och innehåller en auktoriseringshuvud. Värdet för den här rubriken blir: Bearer `<bearer token from step 1>`.

### Exempelsvar från partnerslutpunkten

```
GET /segments/aam HTTP/1.1
Host: api.partner.com
User-Agent: Adobe Audience Manager Iris
Authorization: Bearer glIbBVohK8d86alDEnllPWi6IpjZvJC6kwBRuuawts6YMkw4tZkt84rEZYU2ZKHCQP3TT7PnzCQPI0yY
Content-Type: application/json
Accept-Encoding: gzip
   
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   }]
}
```

>[!NOTE]
>
>Den här begäran innehåller en standardnyttolast (begärandeinnehåll).

## Viktiga överväganden {#considerations}

### Tokens är lösenord

De autentiseringsuppgifter som anges av partnern och de tokens som erhålls av [!DNL Audience Manager] vid autentisering med [!DNL OAuth 2.0]-flödet är känslig information och får inte delas med tredje parter.

### [!DNL SSL] krävs

[!DNL SSL] måste användas för att upprätthålla en säker autentiseringsprocess. Alla förfrågningar, inklusive de som används för att hämta och använda tokens, måste använda `HTTPS` slutpunkter.
