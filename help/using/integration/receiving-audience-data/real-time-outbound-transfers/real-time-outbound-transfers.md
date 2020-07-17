---
description: Den utgående dataöverföringsprocessen i realtid returnerar användardata som en serie JSON-objekt som skickas in med en POST-metod.
seo-description: Den utgående dataöverföringsprocessen i realtid returnerar användardata som en serie JSON-objekt som skickas in med en POST-metod.
seo-title: Utgående dataöverföringar i realtid
solution: Audience Manager
title: Utgående dataöverföringar i realtid
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---


# Utgående dataöverföringar i realtid {#real-time-outbound-data-transfers}

Den utgående dataöverföringsprocessen i realtid levererar användardata som en serie [!DNL JSON] formaterade meddelanden till en målplattform.

<!-- c_outbound_json.xml -->

## Rekommendationer

Om du vill använda den här metoden måste målplattformen uppfylla följande krav:

* Det måste tillhandahålla en slutpunkt [!DNL URL] som kan skalas för att kunna ta emot ett stort antal meddelanden från Audience Manager.
* Den skall godta uppgifter i [!DNL JSON] formatet (`Content-type: application/json`).
* Den måste acceptera säkra `HTTPS` dataöverföringar. [!DNL Audience Manager] skickar inte meddelanden via det osäkra `HTTP` protokollet.

## Frekvens

Denna dataöverföringsmetod kan skicka data i nästan realtid när användarna kvalificerar sig för segment. Realtidsmeddelanden levereras endast när användaren är online och aktivt synlig för Audience Manager Edge-nätverket. Den här metoden kan också skicka batchar med offline- eller inbyggda data så ofta som var 24:e timme.

## Batchöverföringar

Både realtids- och batchöverföringar skickas till samma slutpunkt och använder samma meddelandeformat. När batchöverföringar är aktiverade kommer målplattformen att se en ökning av meddelandevolymen medan batchmeddelandena levereras. Många av de segmentkvalifikationer som skickas via realtidsmeddelanden upprepas i gruppmeddelandena. Batchöverföringar omfattar endast de segmentkvalifikationer (eller icke-kvalifikationer) som har ändrats sedan den senaste batchen levererades.

## Hastighetsgränser

Det finns inga hastighetsbegränsningar för flödet av levererade meddelanden. Om du anger hastighetsgränser kan det leda till dataförlust.

## Obligatoriska svar

Som standard måste mottagarservern returnera `200 OK` koden för att ange att inleveransen lyckades. Andra koder tolkas som fel. Detta svar förväntas inom 3 000 millisekunder. Som svar på ett fel görs endast ett försök [!DNL Audience Manager] igen.

## Parametrar

I följande tabell definieras elementen i den datafil som du skickar till målet [!DNL JSON] .

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Datatyper </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Tid då begäran kördes. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Heltal </p> </td> 
   <td colname="col3"> <p>Ett ID som anger vilken typ av enhets-ID som finns i meddelandet, i egenskapen User.DataPartner_UUID. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android ID (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS-ID (IDFA): <code> 20915</code> </li>
     <li>Webb-/cookie-ID: varierar beroende på målplattform</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Representerar målkontot på målplattformen. Detta ID kommer från målplattformen.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Heltal </p> </td> 
   <td colname="col3"> <p>ID:t för Audience Manager-objektet "destination". Detta ID kommer från Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Heltal </p> </td> 
   <td colname="col3"> <p>Totalt antal användare i <code> POST</code> begäran. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>En array med användarobjekt. Som standard kommer varje meddelande att innehålla mellan 1 och 10 användare, vilket ger optimal meddelandestorlek. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>UUID för <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>UUID för målplattform eller det globala enhets-ID:t. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> Det region-ID för <span class="keyword"> Audience Manager</span> där vi har sett den här enheten. Om enheten till exempel har någon aktivitet i Paris (Europa) blir region-ID:t <code> 6</code>. See <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> DCS Region IDs, Locations, and Host Names</a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>En array med segmentobjekt. För realtidsmeddelanden innehåller arrayen alla segment som användaren tillhör. För gruppmeddelanden innehåller arrayen endast segmentändringar sedan den senaste gruppen.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segmnent.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Heltal </p> </td> 
   <td colname="col3"> <p>Identifieraren för segmentet. I de flesta fall är detta det segment-ID som genereras av Audience Manager (ett heltal). I vissa fall, om målplattformen tillåter det, kan kunderna definiera segmentidentifieraren i användargränssnittet i Audience Manager (öppet textfält), som sedan återspeglas i den här egenskapen. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Heltal </p> </td> 
   <td colname="col3"> <p>Definierar statusen för en användare i segmentet. Accepterar följande värden: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Aktiv (standard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Inaktiv, avanmäld eller osegmenterad. </li> 
    </ul> <p>Användarna är osegmenterade när de är: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Borttagen från ett segment baserat på segmentregeln. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Borttagen från ett segment baserat på segmentets tidsintervall <a href="../../../features/traits/segment-ttl-explained.md"></a>. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Flyttad till ett inaktivt läge om de inte har setts de senaste 120 dagarna. </li>
     <li>Borttagen på grund av en begäran om sekretessändring (dvs. <span class="keyword"> GDPR</span>)</li>
    </ul> <p>Alla partner-ID:n som synkroniseras med ett <span class="keyword"> Audience Manager</span> -ID får <code> "Status":"0"</code> flaggan när en användare är osegmenterad. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Den tidpunkt då användarsegmentets kvalifikationer senast verifierades.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Säkerhet

Du kan skydda din utgående dataöverföringsprocess i realtid genom att [signera HTTP-begäranden](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) med privata nycklar eller genom att [!DNL Audience Manager] autentisera via [OAuth 2.0](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) -protokollet.

## Begäran

En begäran i realtid kan se ut ungefär så här:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
