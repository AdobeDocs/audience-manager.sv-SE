---
description: Audience Manager kräver att HTTP(S) server-till-server-begäranden signeras digitalt för giltighet. I det här dokumentet beskrivs hur du kan signera HTTP-begäranden med privata nycklar.
seo-description: Audience Manager kräver att HTTP(S) server-till-server-begäranden signeras digitalt för giltighet. I det här dokumentet beskrivs hur du kan signera HTTP(S)-begäranden med privata nycklar.
seo-title: Digitalt signerade HTTP(S)-begäranden
solution: Audience Manager
title: Digitalt signerade HTTP(S)-begäranden
uuid: 1183a70f-0c96-42cf-a4f5-37a83ffa1286
translation-type: tm+mt
source-git-commit: 5dddaaae3a5cb2ce4c4649e2a153edf1992fa964

---


# Digitalt signerade `HTTP(S)` begäranden {#digitally-signed-http-requests}

Audience Manager kräver att begäranden från `HTTP(S)` server till server signeras digitalt för giltighet. I det här dokumentet beskrivs hur du kan signera `HTTP(S)` begäranden med privata nycklar.

## Översikt {#overview}

<!-- digitally_signed_http_requests.xml -->

Med hjälp av en privat nyckel som du tillhandahåller och som delas med [!DNL Audience Manager]kan vi digitalt signera de `HTTP(S)` begäranden som skickas mellan [IRIS](../../../reference/system-components/components-data-action.md#iris) och din HTTP(S)-server. Detta säkerställer att

* **Autenticitet**: endast avsändaren som har den privata nyckeln ([!UICONTROL IRIS]) kan skicka giltiga `HTTP(S)` meddelanden till partnern.
* **Meddelandeintegritet**: Med den här metoden, även `HTTP`i det här fallet, skyddas du från en man i en mittersta attack där budskapen förvrängs.

[!UICONTROL IRIS] har inbyggt stöd för att rotera nycklarna utan driftavbrott, vilket visas i avsnittet [Rotera den privata nyckeln](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#rotate-private-key) nedan.

## Information du behöver ange {#info-to-provide}

Kontakta din `HTTP(S)` [!DNL Audience Manager] konsult och ange följande för en server-till-server-destination i realtid:

* Nyckeln som användes för att signera begäran.
* Namnet på det sidhuvud som ska innehålla den genererade signaturen (X-Signature i exempelrubriken nedan). `HTTP(S)`
* Valfritt: den typ av hash som används för signaturen (md5, sha1, sha256).

```
* Connected to partner.website.com (127.0.0.1) port 80 (#0)
> POST /webpage HTTP/1.1
> Host: partner.host.com
> Accept: */*
> Content-Type: application/json
> Content-Length: 20
> X-Signature: +wFdR/afZNoVqtGl8/e1KJ4ykPU=
POST message content
```

## Så här fungerar det {#how-it-works}

1. [!UICONTROL IRIS] skapar det `HTTP(S)` meddelande som ska skickas till partnern.
1. [!UICONTROL IRIS] skapar en signatur baserat på det `HTTP(S)` meddelande och den privata nyckel som partnern har angett.
1. [!UICONTROL IRIS] skickar begäran `HTTP(S)` till partnern. Det här meddelandet innehåller signaturen och det faktiska meddelandet, vilket visas i exemplet ovan.
1. Partnerservern tar emot `HTTP(S)` begäran. Det läser meddelandetexten och signaturen som tas emot från [!UICONTROL IRIS].
1. Baserat på det mottagna meddelandet och den privata nyckeln beräknar partnerservern om signaturen. Se avsnittet [Hur du beräknar signaturen](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md#calculate-signature) nedan om hur du uppnår detta.
1. Jämför den signatur som skapats på partnerservern (mottagaren) med den som tagits emot från [!UICONTROL IRIS] (avsändaren).
1. Om signaturerna matchar varandra har **autenticiteten** och **meddelandeintegriteten** validerats. Endast avsändaren, som har den privata nyckeln, kan skicka en giltig signatur (autenticitet). Dessutom kan en man i mitten inte ändra meddelandet och generera en ny giltig signatur eftersom de inte har den privata nyckeln (meddelandeintegritet).

![](assets/iris-digitally-sign-http-request.png)

## Så här beräknar du signaturen {#calculate-signature}

[!DNL HMAC] (Hash-baserad meddelandeautentiseringskod) är den metod som används [!UICONTROL IRIS] för meddelandesignering. Implementeringar och bibliotek är tillgängliga i stort sett i alla programmeringsspråk. [!DNL HMAC] har inga kända tilläggsattacker. Se ett exempel [!DNL Java] nedan:

```
// Message to be signed.
// For GET type HTTP(S) destinations, the message used for signing will be the REQUEST_PATH + QUERY_STRING
// For POST type HTTP(S) destinations, the message used for signing will be the REQUEST_BODY.
// String getData = "/from-aam-s2s?sids=1,2,3";
String postData = "POST message content";
// Algorithm used. Currently supported: HmacSHA1, HmacSHA256, HmacMD5.
String algorithm = "HmacSHA1";
// Private key shared between the partner and Adobe Audience Manager.
String key = "sample_partner_private_key";
  
// Perform signing.
SecretKeySpec signingKey = new SecretKeySpec(key.getBytes(), algorithm);
Mac mac = Mac.getInstance(algorithm);
mac.init(signingKey);
byte[] result = mac.doFinal(postData.getBytes());
  
String signature = Base64.encodeBase64String(result).trim(); 
// signature = +wFdR/afZNoVqtGl8/e1KJ4ykPU=
```

RFC för [!DNL HMAC] hash-implementeringen är [https://www.ietf.org/rfc/rfc2104.txt](https://www.ietf.org/rfc/rfc2104.txt). En testplats: [https://asecuritysite.com/encryption/hmac](https://asecuritysite.com/encryption/hmac) (observera att du måste [konvertera](https://tomeko.net/online_tools/hex_to_base64.php?lang=en) hex-kodningen till base64).

## Rotera den privata nyckeln {#rotate-private-key}

Av säkerhetsskäl bör du regelbundet rotera den privata nyckeln. Det är upp till dig att bestämma den privata nyckeln och rotationsperioden. För att uppnå tangentrotationen utan driftstopp har [!UICONTROL IRIS] stöd för att lägga till flera signaturrubriker. En rubrik innehåller signaturen som skapades med den gamla nyckeln, en annan rubrik innehåller signaturen som genererats med den nya privata nyckeln. Se stegen nedan i detalj:

1. Partnern kommunicerar den nya privata nyckeln till [!DNL Adobe Audience Manager].
1. Den gamla nyckeln tas bort från [!DNL Audience Manager] och skickar [!UICONTROL IRIS] bara den nya signaturrubriken. Tangenterna har roterats.

## Data som används för signering {#data-signing}

För `GET` textmål används meddelandet för signering som *REQUEST_PATH + QUERY STRING* (t.ex. */from-aam-s2s?sids=1,2,3*). IRIS tar inte hänsyn till värdnamn eller `HTTP(S)` rubriker - dessa kan ändras/felkonfigureras längs sökvägen eller rapporteras felaktigt.

För `POST` typmål används meddelandet som används för signering *REQUEST BODY*. Även här ignoreras rubriker och andra frågeparametrar.
