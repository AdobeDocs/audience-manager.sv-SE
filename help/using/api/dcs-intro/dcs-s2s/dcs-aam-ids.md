---
description: I det här avsnittet beskrivs hur du tolkar ett DCS-svar för att hämta de besökar- och region-ID som krävs för att göra realtidsanrop till DCS.
seo-description: This section describes how to parse a DCS response to retrieve the visitor and region IDs required to make real-time calls to the DCS.
seo-title: Get User IDs and Regions From a DCS Response
solution: Audience Manager
title: Hämta användar-ID:n och regioner från ett DCS-svar
uuid: 08036045-3b26-4d40-8e94-7d0884048683
feature: DCS
exl-id: 3c0c5e57-2d59-4938-9bbd-761495142c31
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 8%

---

# Hämta användar-ID:n och regioner från ett DCS-svar {#get-user-ids-and-regions-from-a-dcs-response}

I det här avsnittet beskrivs hur du tolkar en [!DNL DCS] svar på hämtning av besökar- och region-ID:n som krävs för att göra realtidsanrop till [!DNL DCS].

## Användar- och regions-ID {#user-region-ids}

A [!DNL DCS] svaret innehåller data om besökarna på webbplatsen. Du behöver besökar-ID:t och region-ID:t innan du kan göra server-till-server-anrop till [!DNL DCS].

* Användar-ID krävs för att identifiera och koppla data till en viss besökare.
* Regionens ID krävs eftersom det är knutet till ett regionalt servernamn som du måste skicka data till [!DNL DCS]. The [!DNL DCS] lagrar information i datacenter som är geografiskt närmast besökarna. Se [DCS-region-ID, -platser och -värdnamn](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

Dessa parametrar beskrivs nedan. Kod i *kursiv* representerar en variabelplatshållare.

<table id="table_822C02D5978348DCB7153001882D397C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Datatyp </th> 
   <th colname="col3" class="entry"> Exempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code>"uuid": <i>user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p> <code> "uuid":"123456789"</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>"dcs_region":<i>region ID</i></code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p> <code> "dcs_region":9</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelsvar {#sample-response}

Det här enkla svaret visar `UUID` och region `ID`. Observera att detta endast är exempeldata. Dina loggfiler kan vara längre och mer komplexa.

```js
{
    "stuff": [],
    "uuid": "22920112968019678612904394744954398990",
    "dcs_region": 7,
    "tid": "31ZpxW5bQGc="
}
```

## Nästa steg {#next-steps}

När du har ett användar-ID och ett regionalt servernamn kan du börja skicka och ta emot [!DNL DCS] data. Se [Göra DCS API-anrop](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
