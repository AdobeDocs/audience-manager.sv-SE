---
description: Uppdatera koden så att d_cid eller d_cid_ic används i stället för d_pid och d_dpuuid. DPID- och DPUID-variablerna fortsätter att fungera, men du bör tänka på att de är inaktuella. Detta inkluderar DPID- och DPUID-varianter utan d_prefixet.
seo-description: Update your code to use d_cid or d_cid_ic instead of d_dpid and d_dpuuid. The DPID and DPUUID variables will continue to work, but you should consider them deprecated. This includes DPID and DPUUID variants without the d_ prefix.
seo-title: CID Replaces DPID and DPUUID
solution: Audience Manager
title: CID ersätter DPID och DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: Reference
exl-id: 18e6b1db-fe51-4560-9458-8d65474d2506
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '606'
ht-degree: 0%

---

# CID ersätter DPID och DPUUID{#cid-replaces-dpid-and-dpuuid}

Uppdatera koden så att den använder `d_cid` eller `d_cid_ic` i stället för `d_dpid` och `d_dpuuid`. DPID- och DPUID-variablerna fortsätter att fungera, men du bör tänka på att de är inaktuella. Detta inkluderar DPID- och DPUID-varianter utan `d_ prefix`.

## DPID och DPUID: En granskning {#dpid-dpuuid-review}

DPID och DPUID är nyckelvärdepar som innehåller ett dataleverantörs-ID och ett användar-ID. Dessa nyckelvärdepar länkar leverantörs-ID:n till användar-ID:n. De skickar in data under händelseanrop, för inkommande synkroniseringshändelser och för ID-anrop. Utan dem skulle [!DNL Audience Manager] och andra tjänster eller funktioner inte ha något sätt att matcha och synkronisera ID:n. Dessa variabler uttrycks ibland med eller utan prefixet `d_`, vilket visas nedan. Observera att *italics* i koden anger en variabelplatshållare.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Syntax </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data Provider ID (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dataproviderns unika användar-ID (DPUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Dessa nyckelvärdepar fungerar fortfarande, men de är föråldrade. Du bör uppdatera koden så att den använder CID eller CID_IC i stället.

## CID och CID_IC: Om {#cid-cidic-about}

Nyckelvärdepar för CID och CID_IC ersätter DPID och DPUID. De har samma funktioner som DPID och DPUUID, men de är mer effektiva eftersom de innehåller data provider-ID (eller integrationskod) och användar-ID i ett enda nyckel-värde-par. I varje nyckelvärdepar:

* Symbolen = skiljer nyckeln från dess relaterade värden.
* ASCII-tecknet %01 som inte skrivs ut skiljer värdena åt.

`d_cid` och `d_cid_ic` använder syntaxen som visas nedan. Observera att *italics* i koden anger en variabelplatshållare.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Syntax </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Kund-ID (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Kund-ID-integreringskod (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> En <span class="term">-integrationskod </span> är ett alternativt ID som du kan använda i stället för det Data Source ID som tilldelats av <span class="keyword"> Audience Manager</span>. Se <a href="../features/manage-datasources.md#create-data-source"> Skapa en Data Source</a> om du behöver konfigurera en integreringskod. </p> </td> 
  </tr> 
 </tbody> 
</table>

Se även [URL-variabler och syntax för deklarerade ID:n](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>Du kan använda integrationskoder för dina egna datakällor och för globala [delade datakällor](../features/datasources-list-and-settings.md#settings-menu-options) som du har åtkomst till. Du kan till exempel använda integreringskoder när du arbetar med datakällor för mobila identifierare. Använd följande integrationskoder, exakt som anges nedan:

* **DSID_20914** för GAID, som representerar enheter som kör Android operativsystem.
* **DSID_20915** för IDFA, som representerar enheter som kör iOS operativsystem.

**Exempel**

Följande tabell innehåller exempel per händelsetyp.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Händelsetyp </th> 
   <th colname="col2" class="entry"> Exempel </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Händelse </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Nytt: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Föråldrat: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inkommande synkronisering (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Nytt: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Föråldrat: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Generera Audience Manager UID (ID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Nytt: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Föråldrat: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Varje anrop kan även innehålla flera `d_cid`- och `d_cid_ic`-nyckelvärdepar enligt följande:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Viktiga överväganden för utvecklingsteamen {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Objekt </p> </th> 
   <th colname="col2" class="entry"> <p>Beskrivning </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL-kodning </p> </td> 
   <td colname="col2"> <p>Utvecklingsteamen <i>måste</i> tillämpa URL-kodning på följande variabler i nyckelvärdepar för CID: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Obs! Du måste URL-koda användar-ID:t och integrationskoden <i> innan</i> sammanfogar dem i en sträng. Detta beror på att ASCII-tecknet %01 som avgränsar de två variablerna inte får fångas in i URL-kodningen. </p> </p> <p>Med URL-kodning säkerställs att dina användar-ID:n och integreringskoder som innehåller reserverade eller osäkra tecken som, men inte begränsade till, + eller = överförs korrekt till våra servrar. </p> <p>Använd ASCII-kodningstabellen <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> </a> som referens. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Använda integreringskoder för globala delade datakällor </p> </td> 
   <td colname="col2"> <p>Du kan använda integrationskoder för dina egna datakällor och för globala <a href="../features/datasources-list-and-settings.md#settings-menu-options"> delade datakällor</a> som du har åtkomst till. Du kan till exempel använda integreringskoder när du arbetar med datakällor för mobila identifierare. Använd följande integrationskoder, exakt som anges nedan: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> för GAID, som representerar enheter som kör Android operativsystem. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> för IDFA, som representerar enheter som kör iOS operativsystem. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
