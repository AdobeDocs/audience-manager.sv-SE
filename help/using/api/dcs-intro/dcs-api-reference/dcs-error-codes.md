---
description: Felkoder och meddelanden som genereras av datainsamlingsservrarna (DCS) listas i numerisk ordning efter kod-ID.
title: Felkoder, meddelanden och exempel för DCS
uuid: d3290038-567b-4c00-bc95-2cec683da5ec
feature: DCS
exl-id: 485e5ce2-143e-4d18-b157-c243c5a510ad
source-git-commit: 2012c244f6fa5ca01c7e2719ce621214cb22f93e
workflow-type: tm+mt
source-wordcount: '1517'
ht-degree: 2%

---

# Felkoder, meddelanden och exempel för DCS {#dcs-error-codes-messages-and-examples}

Felkoder och meddelanden som genereras av [!UICONTROL Data Collection Servers] ([!DNL DCS]) listas i numerisk ordning efter kod-ID.

I tabellerna nedan representerar *kursiv* en variabelplatshållare.

## Systemfelskoder {#system-error-codes}

| Felkod | Felmeddelande | Beskrivning |
|---|---|---|
| 0 | Ospecificerat fel | Detta är ett catch-all-fel som hanterar händelser som inte täcks av de andra felhanterarna. Det är svårt att felsöka det här felet. Den kan orsakas av en mängd okända åtgärder eller händelser. Om du får det här felet kan du försöka med din [!DNL DCS]-begäran igen. Kontakta din [!DNL Adobe]-representant om problemet kvarstår. |
| 1 | Det gick inte att hitta konfigurationen för värdnamnet: `hostname` | Värdnamnet som skickades i begäran har inte konfigurerats av vårt team för partneretablering. Kontakta din [!DNL Adobe]-representant om det här felmeddelandet visas. |
| 2 | Ogiltigt `d_orgid`-värde (det gick inte att hitta någon konfiguration för detta organisations-ID): `ID` | Organisations-ID:t är felaktigt. Kontrollera ditt ID och försök igen. Om du inte känner till eller har ditt företags-ID kan du läsa avsnittet Administrationssida [Organisationer och kontolänkning](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=sv-SE) för mer information om hur du hittar det. |
| 10 | Det går inte att utvärdera egenskaper | Förfrågans egenskaper har antingen utvärderats delvis eller inte utvärderats alls. Kontakta din [!DNL Adobe]-representant om problemet kvarstår. |

## Felkoder för integrering {#integration-error-codes}

| Felkod | Felmeddelande | Beskrivning |
|---|---|---|
| 100 | Det gick inte att hämta värdnamnet för begäran | Ett [!DNL API]-anrop skickade inte värdhuvudet [!DNL HTTP] i begäran. Lägg till värdhuvudet i samtalet och försök igen. De flesta webbläsare och [!DNL API]-klienter gör detta automatiskt. |
| 101 | Ogiltigt [!DNL Experience Cloud]-ID skickades i `ID` | Anropet [!DNL DCS] innehåller ett ogiltigt [!DNL Experience Cloud]-ID. Kontrollera nyckelvärdepar `d_mid=` i rubriksträngen. Kontrollera att du skickar rätt [!DNL Experience Cloud]-ID och försök igen. |
| 102 | Ogiltig [!DNL AAM ID] skickades i begäran `ID` | Anropet [!DNL DCS] innehåller ett ogiltigt [!DNL Audience Manager]-ID. Kontrollera nyckelvärdepar `d_uuid=` i rubriksträngen. Kontrollera att du skickar rätt [!DNL Audience Manager]-ID och försök igen. |
| 104 | Alla kund-ID:n är ogiltiga | Alla kund-ID:n i samtalet är ogiltiga. Kontrollera dina ID:n och försök igen. |
| 109 | Referenten `HTTP referer` tillåts inte för partnern `Partner ID` | Huvudet `HTTP referer` i samtalet tillåts inte för partner-ID:t i samtalet. Kontrollera att rubriken `HTTP referer` är korrekt. |
| 111 | Ogiltig `IMS`-token har tagits emot | Returnerad för [!DNL Audience Manager] - [!DNL Adobe Target] integreringar. Felet genereras när ett anrop görs till [!DNL DCS], som innehåller en ogiltig [!DNL IMS]-token. Token kan ha fel format, ha upphört att gälla eller så har användaren inte behörighet att komma åt den nödvändiga resursen. |

## Felkoder för avanmälan {#opt-out-error-codes}

<table id="table_A50C284AB84F48A79B01223D991884A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kod-ID </th> 
   <th colname="col2" class="entry"> Meddelande </th> 
   <th colname="col3" class="entry"> Beskrivning </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>171 </p> </td> 
   <td colname="col2"> <p>En avanmälningstagg för ID <code><i>ID</i></code> påträffades </p> </td> 
   <td colname="col3"> <p>En kund har valt att inte ta emot intressebaserad annonsering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>172 </p> </td> 
   <td colname="col2"> <p>Blockerade cookies </p> </td> 
   <td colname="col3"> <p>Returneras när användarens webbläsare blockerar cookies från tredje part.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>173 </p> </td> 
   <td colname="col2"> <p>Påträffade betrodd relation via <a href="https://www.networkadvertising.org/" format="http" scope="external"> NAI</a> </p> </td> 
   <td colname="col3"> <p>Användaren har initierat en avanmälningsprocess via NAI. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>198 </p> </td> 
   <td colname="col2"> <p>Begäranden från det här landet blockeras av partnern </p> </td> 
   <td colname="col3"> <p>Baserat på IP-adressen blockerar <span class="wintitle"> DCS</span> begäranden från länder där partnern avsiktligt har begränsat trafiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>199 </p> </td> 
   <td colname="col2"> <p>Begäranden från det här landet tillåts inte </p> </td> 
   <td colname="col3"> <p>Baserat på IP-adressen blockerar <span class="wintitle"> DCS</span> begäranden från följande länder: </p> <p> 
     <ul id="ul_4017A7D074064FE7A8B5618AFCFA4E28"> 
      <li id="li_EE65DEC3C64F4522B214C503DC754DC1">Kuba </li> 
      <li id="li_EDE8B304D35A41458DCFF11E9328802A">Iran (IR) </li> 
      <li id="li_36664315A06540E0BE024EE60638D5DC">Nordkorea (KP) </li> 
      <li id="li_B508A5FF173E491AAE41334C074D9DED">Sudan (SD) </li> 
      <li id="li_0875540C20204158ADBD92698CEB10EA">Syrien (SY) </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Felkoder för profilhämtning {#profile-retrieval-error-codes}

<table id="table_CFF2252A3CC54960802905454A867D7A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kod-ID </th> 
   <th colname="col2" class="entry"> Meddelande </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>200 </p> </td> 
   <td colname="col2"> <p> Det går inte att läsa egenskaper från profilcache för ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returneras när en användarprofil inte kan läsas från vår interna lagring. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>201 </p> </td> 
   <td colname="col2"> <p> Det går inte att läsa enhets-ID från profilcache för kund-ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returneras när enhets-ID <a href="../../../reference/ids-in-aam.md"> </a> inte kan hämtas för en sammanslagningsregel för profillänkar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>202 </p> </td> 
   <td colname="col2"> <p>Det går inte att läsa relaterad kund för enhets-ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returneras när det <a href="../../../reference/ids-in-aam.md"> kund-ID (UUID)</a> som är kopplat till ett enhets-ID inte kan hämtas för en senast autentiserad kopplingsregel från vår interna lagring. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>203 </p> </td> 
   <td colname="col2"> <p> Det går inte att läsa enhetskluster för ID: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Det går inte att returnera de länkade enhets-ID:n från samma enhetsdiagramkluster för det här enhets-ID:t. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>204 </p> </td> 
   <td colname="col2"> <p>Det gick inte att utföra migreringen eftersom profilläsningen misslyckades för den primära enheten </p> </td> 
   <td colname="col3"> <p>Om du får det här felet kan det uppstå skalbarhetsproblem i vårt datalager (<span class="wintitle"> PCS</span>). Kontakta Adobe om problemet kvarstår. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>205 </p> </td> 
   <td colname="col2"> <p>Det gick inte att utföra migrering från <code><i>ID</i></code> till <code><i>ID</i></code> eftersom profilläsningen misslyckades för <code><i>ID</i></code> </p> </td>
   <td colname="col3"> <p>Om du får det här felet kan det uppstå skalbarhetsproblem i vårt datalager (<span class="wintitle"> PCS</span>). Kontakta Adobe om problemet kvarstår. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Varningskoder för integrering {#integration-warning-codes}

<table id="table_31F1593C46804DDBA2E9BEDE83F2417F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kod-ID </th> 
   <th colname="col2" class="entry"> Meddelande </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>300 </p> </td> 
   <td colname="col2"> <p>Ogiltigt kund-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Kund-ID är ogiltigt (värden saknas för datakälla, integreringskoder saknas, ogiltigt format för datakällor, blockerat kund-ID, tomt kund-ID, oauktoriserat åtkomstförsök till en datakälla som inte tillhör partnern). </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>301 </p> </td> 
   <td colname="col2"> <p>Det högsta antalet kund-ID:n har överskridits. Högsta tillåtna antal är <code><i>maximum allowed</i></code>. <code><i>maximum found</i></code> hittades.</p> </td> 
   <td colname="col3"> <p>Antalet kund-ID:n som är associerade med en datakälla mellan olika enheter överskrider det tillåtna antalet korsenhets-ID:n per begäran. Dessa ID:n omfattar enhets-, mobil- eller cookie-ID:n. Gränsen är för närvarande 10. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>302 </p> </td> 
   <td colname="col2"> <p>Oauktoriserat kund-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returneras när kundens ID-datakälla inte ägs av det aktuella organisations-ID:t. Om du inte känner till eller har ditt företags-ID kan du läsa avsnittet Hitta ditt företags-ID i <a href="https://experiencecloud.adobe.com/resources/help/en_US/mcloud/organizations.html" format="https" scope="external"> Organisationer och Kontolänkning </a> för mer information om hur du hittar det. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>303 </p> </td> 
   <td colname="col2"> <p>Blockerat kund-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returneras när kund-ID:t har identifierats som skadligt och har lagts till i en blockeringslista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>304 </p> </td> 
   <td colname="col2"> <p>ID för blockerad datakälla: <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Returneras när datakällans ID har identifierats som skadligt och har lagts till i en blockeringslista </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>306 </p> </td> 
   <td colname="col2"> <p>Blockerat deklarerat enhets-ID <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>Enhets-ID:t har identifierats som skadligt och har lagts till i en blockeringslista Det här kan hända om vi får ett mycket stort antal <span class="wintitle"> DCS</span>-begäranden som innehåller det här enhets-ID:t på kort tid. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>307 </p> </td> 
   <td colname="col2"> <p>Åtgärd för blockerad profil för <code><i>ID</i></code> </p> </td> 
   <td colname="col3"> <p>En läs-/skrivåtgärd har blockerats eftersom ett ID har identifierats som skadligt och har lagts till i blockeringslista Se felkod 306. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>309 </p> </td> 
   <td colname="col2"> <p>Kund-ID:t <code><i>ID</i></code> ignorerades eftersom det överskred gränsen för deklarerade kund-ID:n per begäran </p> </td> 
   <td colname="col3"> <p>Relaterat till fel 301. Det här felet anger vilket kund-ID som ignorerades eftersom gränsen överskreds. </p> <p>Om till exempel 12 kund-ID har deklarerats för <span class="wintitle"> DCS</span> -anropet, kommer två av dem att ignoreras. För att kunna meddela vilka som har ignorerats visas det här felet två gånger i svaret (en gång för varje ignorerat kund-ID). </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p>310 </p> </td> 
   <td colname="col2"> <p>Kund-ID ignorerades eftersom det överskred gränsen för ett givet namnutrymme. Namnområdes-ID är <code><i>ID</i></code>, kund-ID är <code><i>ID</i></code>. </p> </td> 
   <td colname="col3"> <p>Den här felkoden returneras om fler än tre kund-ID har deklarerats för samma namnområde (<code> DPID</code>) i ett <span class="wintitle"> DCS</span> -anrop. </p> <p><code> https://partner.demdex.net/event?d_rtbd=json&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one&d_cid_ic=one </code> </p> <p>I det här exemplet på <span class="wintitle"> DCS</span>-begäran finns det 4 ID:n deklarerade för samma namnutrymme (med integreringskoden 1). Ett av ID:na ignoreras och fel 310 returneras. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>311 </p> </td> 
   <td colname="col2"> <p>Begäran innehåller ogiltiga parametrar </p> </td> 
   <td colname="col3"> <p><span class="wintitle"> DCS</span> returnerar den här felkoden när minst en URL-parameter inte är korrekt kodad. I det här fallet ignorerar <span class="wintitle"> DCS</span> hela begäran. </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%esid!&amp;d_creative=%ecid!&amp;d_adgroup=%eaid!&amp;d_placement=%epid!&amp;d_campaign=%ebuy!&amp;d_adsrc=48123</code> </p> <p>I exempelbegäran ovan är sekvensen <code> %</code> felaktigt kodad. Därför ignorerar <span class="wintitle"> DCS</span> den. </p> <p>Det korrekt kodade exemplet ska se ut så här: </p> <p><code>http(s)://partner.demdex.net/event?d_event=imp&amp;d_rtbd=json&amp;d_src=38454&amp;d_site=%25esid!&amp;d_creative=%25ecid!&amp;d_adgroup=%25eaid!&amp;d_placement=%25epid!&amp;d_campaign=%25ebuy!&amp;d_adsrc=48123</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>312 </p> </td> 
   <td colname="col2"> <p>Begäran innehåller ett ogiltigt globalt enhets-ID </p> </td> 
   <td colname="col3"> <p><span class="wintitle">DCS</span> returnerar den här felkoden när begäran innehåller ett ogiltigt globalt enhets-ID. DCS ignorerar det ogiltiga ID:t och genererar ett 312-fel tillsammans med de specifika felen för det ogiltiga ID:t. Se <a href="../../../features/global-data-sources.md" format="dita" scope="local">Globala datakällor</a> och <a href="../../../reference/ids-in-aam.md" format="dita" scope="local">Index med ID:n i Audience Manager</a> för detaljerad information om rätt ID-format för enhetsannonsering och motsvarande globala datakällor.</p>
   <p>Exempel på ett felaktigt anrop: <code>"http://partner.demdex.net/event?d_rtbd=json&d_cid=20915%01a53cc5a2-6aa1-4210-8ded-a88b29b6212z"</code></p>
   <p>Förklaring: En <span class="keyword">IDFA (DPID 20915)</span> måste vara ett versalt ID. ID:t som angavs i begäran är gemener.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>313 </p> </td> 
   <td colname="col2"> <p>CMP ID finns inte i GCL</p> </td> 
   <td colname="col3"> <p>När <code>gdpr=1</code> och IAB TC-strängen genereras av ett CMP-ID som inte finns i Audience Manager cachelagrade version av den globala CMP-listan vid tidpunkten för utvärderingen, tar Audience Manager-plugin-programmet för IAB TCF bort IAB TC-strängen och bearbetar begäran som vanligt. IAB TCF v2.2 ${GDPR}-makrot är inställt på 0 och ${GDPR_CONSENT_XXX}-makrot är tomt.</p>
   </td>
  </tr>
   <tr> 
   <td colname="col1"> <p>314 </p> </td> 
   <td colname="col2"> <p>CMP ID har markerats som borttaget i GCL</p> </td> 
   <td colname="col3"> <p>När <code>gdpr=1</code> och IAB TC-strängen genereras av en CMP som har markerats som borttagen i vår cachelagrade version av Global CMP-listan, ignorerar Audience Manager-plugin-programmet för IAB TCF TC-strängen och bearbetar begäran som vanligt, om utvärderingstiden är förbi raderingstiden från den globala CMP-listan. IAB TCF v2.2 ${GDPR}-makrot är inställt på 0 och ${GDPR_CONSENT_XXX}-makrot är tomt.</p></td>
  </tr>
   <tr> 
   <td colname="col1"> <p>315 </p> </td> 
   <td colname="col2"> <p>Godkännandesträngen anger inget samtycke</p> </td> 
   <td colname="col3"> <p>När inget medgivande ges, kommer Audience Manager-plugin-programmet för IAB TCF att stoppa användaren från ytterligare datainsamling eller helt koppla från samtalet om inget partnersammanhang hittas.</p>
   </td>
  </tr>
 </tbody>
</table>

## Exempel på felkodmeddelanden {#sample-error-codes}

[!DNL DCS] returnerar felkoder och meddelanden i ett [!DNL JSON]-objekt eller i ett X-huvud i HTTP-svarssträngen.

### Exempel på DCS-felkod och -meddelande

```
{ 
   "errors":[ 
      { 
         "code":101,
         "msg":"Invalid Experience Cloud id passed in"
      },
      { 
         "code":102,
         "msg":"Invalid aam id passed in request"
      }
   ]
}
```

### X-Error

Felkoder som har hämtats av X-header visas i URL-strängen så här: `X-Error: 101,102`.

[Ansiktsvillkor och felhantering](../../../api/dcs-intro/dcs-api-reference/dcs-race-conditions.md)
