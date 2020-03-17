---
description: Exempel på hur några av de vanliga makrona används för att skapa utgående filmallar.
seo-description: Exempel på hur några av de vanliga makrona används för att skapa utgående filmallar.
seo-title: Exempel på utgående makron
solution: Audience Manager
title: Exempel på utgående makron
uuid: 823d85d4-d683-45cf-9e60-c12b7d52a498
translation-type: tm+mt
source-git-commit: 3d14d58b9cb66faf506ab729e7ff85dc1818d37e

---


# Exempel på utgående makron {#outbound-macro-examples}

Exempel på hur några av de vanliga makrona används för att skapa utgående filmallar.

>[!NOTE]
>
>I tabellerna används **fet** stil för att identifiera varje makro med tillhörande utdata. För formatexemplen har symbolerna `<` `>` lagts till för att hjälpa till att visuellt separera varje makro.

## Filnamnsmakron {#file-name-macros}

En lista med tillgängliga makron och definitioner finns i [Utgående mallmakron](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_B5073597219B470298EE614902DACAE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Exempel på format och utdata </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_ &lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Utdata: <code> ftp_215_ 888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;MASTER_DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Utdata: <code> ftp_215_888_ 20915_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_ &lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Utdata: <code> ftp_ 215_888_iter_1449756724.sync </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_ &lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Utdata: </p> <p> 
     <ul id="ul_F63D7B78AF1246639D6ED85C1621B17C"> 
      <li id="li_4D0D7B4D047345FE861FCBA2BD0408ED">Fullständig: <code> ftp_215_888_ full_1449756724.sync </code> </li> 
      <li id="li_23F4D1F6B2784E599EDA29AA457327E6">Inkrementell: <code> ftp_215_888_ iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;.sync </code> </p> <p>Utdata: </p> <p> 
     <ul id="ul_11B14E740E40474F8302BDB809C428FE"> 
      <li id="li_54A3EAA468B44AC8B2528F855E03D04B">FTP: <code> ftp_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_93468C56B661463CA7F62B1F5D3A53FF">https: <code> http_215_888_iter_1449756724.sync </code> </li> 
      <li id="li_8A204C7BEDBC41C096FE953B5F827DEC">S3: <code> s3_215_888_iter_1449756724.sync </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_ &lt;TIMESTAMP&gt;_&lt;admin&gt;&lt;.sync&gt; </code> </p> <p>Utdata: <code> ftp_215_888_iter_ 1449756724.sync </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Makron för rubrikrad {#header-macros}

En lista med tillgängliga makron och definitioner finns i [Utgående mallmakron](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_ABC31B3D660D47969E111EBC734D5BBC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Exempel på format och utdata </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;ORDER_ID&gt; &lt;TAB&gt;&lt;SYNC_TYPE&gt; </code> </p> <p>Utdata: <code> 888 full.sync </code> </p> <p>I utdata separerar tabbtecknet som inte skrivs ut varje element. </p> </td>
  </tr>
 </tbody>
</table>

## Filinnehållsmakron {#file-content-macros}

En lista med tillgängliga makron och definitioner finns i [Utgående mallmakron](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md).

<table id="table_408C6DD2B9D54550B003EAC93562E64F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Exempel på format och utdata </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt; &lt;UUID&gt; </code> </p> <p>Utdata: <code> 123456 07955261652886032950143702505894272138 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;UUID&gt;&lt;TAB&gt; &lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Utdata: <code> 07955261652886032950143702505894272138 DP_UUID1 DP_UUID2 DP_UUID3 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Se det separata avsnittet nedan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;REMOVED_SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Utdata: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt; &lt;SEGMENT_LIST;separator=" "&gt; </code> </p> <p>Utdata: <code> 123456 105955 101183 101180 101179 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p><b>Format:</b> </p> <p> 
     <code>
       {"AdvertiserId":"&lt;PIDALIAS&gt;",&nbsp;"DataCenterId":&nbsp;2,"TDID":"&lt;DP_UUID&gt;", "Data":[&lt;SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;"&lt;CLOSE_CURLY_BRACKET&gt;}; separator=","&gt;&lt;if(SEGMENT_LIST&nbsp;&amp;&amp;&nbsp;REMOVED_SEGMENT_LIST)&gt;&lt;COMMA&gt;&lt;endif&gt; &lt;REMOVED_SEGMENT_LIST:{seg|&lt;OPEN_CURLY_BRACKET&gt;"Name":"&lt;seg.alias&gt;", "TtlInMinutes":0&lt;CLOSE_CURLY_BRACKET&gt;};&nbsp;separator=","&gt;]}
     </code></p><p><b>Utdata:</b></p> <p>
     <code>//First&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2, "TDID":"dfd215e4-8d6b-4fdb-90b9-fab4456f2c9d","Data":[{"Name":"4321"}]} //Second&nbsp;example {"AdvertiserId":"12345",&nbsp;"DataCenterId":&nbsp;2,"TDID":"9099e8fe-abab-5114-abaa-28bdaa0539ca","Data":[{"Name":"4321"},{"Name":"987","TtlInMinutes":0}, {"Name":"654","TtlInMinutes":0}]} 
     </code></p> <p> <p>Obs!  I det första exemplet returnerar makrot bara data för <code> SEGMENT_LIST </code> eftersom <code> REMOVED_SEGMENT_LIST </code> är tomt. Det andra exemplet returnerar data för båda makrona. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Format: </p> <p> <code> &lt;PID&gt;&lt;TAB&gt;&lt;UUID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt; &lt;SET_ATTRIBUTES&gt;&lt;TAB&gt;&lt;OPT_OUT&gt;&lt;TAB&gt;&lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.alias&gt;,&lt;OUTPUT_ATTRIBUTE_VALUE&gt;,&lt;seg.lastUpdateTime&gt;&amp;}&gt; </code> </p> <p>Utdata: </p> <p> <code> 1159 00088008579683653741516297509717335000 17t0aj01b120hp 1 0 5,103714,1,1344114661000&amp;5,103713,1,1343250661000 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;DP_UUID&gt;&lt;TAB&gt;&lt;DP_UUID_LIST;separator=TAB&gt; </code> </p> <p>Utdata: <code> 123456 UUID1 UUID2 UUID3 </code> </p> <p>I utdata separerar tabbtecknet som inte skrivs ut varje element. </p> </td> 
  </tr>
  <tr>
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Format: <code> &lt;PID&gt;&lt;TAB&gt;&lt;DP_UUID&gt;&lt;TAB&gt;&lt;SET_ATTRIBUTES&gt;&lt;TAB&gt; &lt;TRAIT_LIST;separator="|"&gt; </code> </p> <p>Utdata: <code> 1131 12345 1 123|456|789 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

### `DPUUID` Exempel

För att du ska förstå hur makrot `DPUUID` genererar data kan vi anta att vi har två `DPID`som `DPUUID`är mappade enligt nedan:

* DPID `1111` mappar till DPUID `AAAA` (tidsstämpel = 1) och `BBBB` (tidsstämpel = 2).
* DPID `2222` mappar till DPUUID `CCCC`.

Under dessa förhållanden räknar följande tabell upp några möjliga formatsträngar och deras utdata.

<table id="table_6A6D94F994C1475BB09126BA0B815B1F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mappningsvillkor </th> 
   <th colname="col2" class="entry"> Makroformat </th> 
   <th colname="col3" class="entry"> Utdata </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Returnera alla mappningar för ett enda DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111|maxMappings=0|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","AAAA"],["1111","BBBB"]] </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Returnera maximalt 1 mappning för alla DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=1111,2222|maxMappings=1|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["1111","BBBB"],["2222","CCCC"]] </code> </p> <p>För DPID <code> 1111 </code>mappas makrot till DPUID <code> BBBB </code> endast eftersom det ID:t har den större tidsstämpeln. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Returnera maximalt 2 mappningar för ett enskilt DPID </p> </td> 
   <td colname="col2"> <p> <code> &lt;DPUUIDS; format="dpids=2222|maxMappings=2|format=json"&gt; </code> </p> </td> 
   <td colname="col3"> <p> <code> [["2222","CCCC"]] </code> </p> <p>Trots <code> maxMappings=2 </code>det returnerar det här makrot endast 1 DPID till DPUID-mappning eftersom det angivna DPID bara har ett DPUID. </p> </td> 
  </tr> 
 </tbody> 
</table>

[Utgående mallmakron](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-template-macros.md)