---
description: Visar makron som du kan använda för att skapa utgående mallar. Bland dessa finns filnamnsmakron, huvudmakron och innehållsmakron.
seo-description: Lists the macros you can use to create outbound templates. These include file name macros, header macros, and content macros.
seo-title: Outbound Template Macros
solution: Audience Manager
title: Utgående mallmakron
uuid: dec082d3-306b-4ff5-afb2-418bd543d8d0
feature: Outbound Data Transfers
exl-id: 6988d0e5-7a99-4291-91d3-bcd3a15630fd
source-git-commit: d76505fda1ba448a1aaa3a756ef3bcf193a2718a
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 2%

---

# Utgående mallmakron {#outbound-template-macros}

Visar makron som du kan använda för att skapa utgående mallar. Bland dessa finns filnamnsmakron, huvudmakron och innehållsmakron.

## Makron för filnamn och filhuvud {#file-name-header-macros}

Tabellen visar och beskriver makrona som du kan använda i filnamnet och för att definiera rubrikfält. För kodexempel, se [Exempel på utgående makro](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_C353AF028E0A4944A8727FD01C94FDB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ASCII_SOH </code> </p> </td> 
   <td colname="col2"> <p>Ett ASCII-tecken som inte skrivs ut. Det anger början på en rad eller ett avsnitt med innehåll. Den kan också användas för att avgränsa datakolumner i en fil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>DataProvider-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MASTER_DPID </code> </p> </td> 
   <td colname="col2"> <p>Nyckelproviderns ID för användar-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NEW_LINE </code> </p> </td> 
   <td colname="col2"> <p> Gör det möjligt att skapa flerradiga rubriker för utgående order. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Order-/mål-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID_ALIAS </code> </p> </td> 
   <td colname="col2"> <p>Ett alias för ett order-/mål-ID. </p> <p>Aliaset anges i administratörsgränssnittet. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> SPLITNUM </code> </p> </td> 
   <td colname="col2"> <p>Anger delning av utgående filer i flera delar. Ersätt delen SPLITNUM i filnamnet med artikelnumret föregånget av nollor, så att minst tre tecken för delen SPLITNUM anges.</p>
   <p>SPLITNUM-makrot behöver inte omges av &lt;&gt; tecken.</p><p>Exempel på: <code>&lt;SYNC_TYPE&gt;_&lt;ORDER_ID&gt;_&lt;DPID&gt;_&lt;SYNC_MODE&gt;_&lt;TIMESTAMP&gt;SPLITNUM.csv</code>
<p>s3_123456_9999_full_1566906141001.csv</p> 
<p>s3_123456_9999_full_1566906141002.csv</p> 
<p>s3_123456_9999_full_1566906141003.csv</p> 
<p>De tre sista siffrorna (001,002,003) i exemplen ovan är SPLITNUM-identifierarna.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Anger synkroniseringstyp och inkluderar: </p> 
    <ul id="ul_CA5057DA18144AB8BC17B3EB79891B25"> 
     <li id="li_6DFEE438860D4DB18EF831E3AF525F1E"> <code> full </code>: Fullständig synkronisering. </li> 
     <li id="li_1A7BBBB40AD94FC39B06F4FC49586595"> <code> iter </code>: Inkrementell synkronisering. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Anger dataöverföringsmetod och innehåller: </p> 
    <ul id="ul_24DD8DCA18B34A8590FC66431FD720AB"> 
     <li id="li_88EC08F7406641698920F879EB5E9520"> <code> ftp </code> </li> 
     <li id="li_188CE2FDA31949BBB141F57B574301BC"> <code> http </code> </li> 
     <li id="li_0649D3F0F3BE405D89118A7F6F4D8082"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Makrot används som avgränsare och infogar en tabb mellan fält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TIMESTAMP </code> </p> </td> 
   <td colname="col2"> <p>En 10-siffrig UTC-, Unix-tidsstämpel. </p> <p>Den kan också formateras som <code> &lt;TIMESTAMP; format="YYYYMMDDhhmmss"&gt; </code> följa formateringsregler för Java-datum/tidsstämpel. </p> </td> 
  </tr>

</tbody> 
</table>

## Innehållsmakron {#content-macros}

Makron som används för att formatera innehållet i en datafil. För kodexempel, se [Exempel på utgående makro](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md).

<table id="table_5C6F9678CFF34C5EB67BA1DEA0479F1D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> CLOSE_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Infogar en avslutande klammerparentes <code>}</code> tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="term"> Unik användaridentifierare för dataprovider </span>. </p> <p>Det här är ID:t för den datapartent som du skickar data till i en utgående fil. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DP_UUID_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returnerar en lista som innehåller flera ID:n för en datapartner. Detta är användbart om du har en stor organisation med flera indelningar eller andra organisationsgrupper som du kan dela data med. Detta makro returnerar en lista över ID:n för de underordnade grupperna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPID </code> </p> </td> 
   <td colname="col2"> <p>DataProvider-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> DPUUIDS </code> </p> </td> 
   <td colname="col2"> <p>Utdata för det här makrot mappar DataProvider ID (DPID) till relaterade unika användar-ID:n (DPUID). Detta makro måste ha en formateringssträng för att styra utdata. Exempelutdata skulle se ut ungefär så här: </p> <p> <code> "dpids=dpid1,dpid2,...dpid n|maxMappings= n|format=json" </code> </p> <p>The <code> maxMappings </code> anger hur många mappningar du vill att makrot ska returnera. När <code> maxMappings=0 </code>returnerar det här makrot alla mappningar för varje angivet DPID. Data sorteras efter tidsstämpel (senaste först) och returnerar resultat med den största tidsstämpeln först. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> if(SEGMENT_LIST &amp;&amp; REMOVED_SEGMENT_LIST)endif </code> </p> </td> 
   <td colname="col2"> <p>Den här kombinationen av makron skapar en villkorssats som listar de segment som användarna tillhör och har tagits bort från. Den returnerar en tom sträng om båda villkoren inte uppfylls eller om det inte finns några data. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MCID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Adobe Experience Cloud ID.</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPEN_CURLY_BRACKET </code> </p> </td> 
   <td colname="col2"> <p>Infogar en öppen klammerparentes <code>{</code> tecken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OPT_OUT </code> </p> </td> 
   <td colname="col2"> <p>Föråldrat. Skall ej användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ORDER_ID </code> </p> </td> 
   <td colname="col2"> <p>Order- eller mål-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Föråldrat. Skall ej användas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> OUTPUT_ATTRIBUTE_VALUE </code> </p> </td> 
   <td colname="col2"> <p>Returnerar <code> 1 </code> som ett statiskt, hårdkodat värde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PID </code> </p> </td> 
   <td colname="col2"> <p>Partner-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> PIDALIAS </code> </p> </td> 
   <td colname="col2"> <p>Ett alias för ett order-/mål-ID. </p> <p>Aliaset anges i administratörsgränssnittet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> REMOVED_SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returnerar en lista med eventuella segment som har tagits bort. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SEGMENT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returnerar en lista med segment i en lista. Accepterar följande valfria argument: </p> 
    <ul id="ul_B111AA0D6C18445598A1444B8B7E9325"> 
     <li id="li_8603B40229624856AF1FBC434DB8F16A"> <code> segmentId </code>: Segment-ID. Föråldrat. Använd <code> sid </code>. </li> 
     <li id="li_1EF40DDCA3C5447586904CF021D8F912"> <code> csegid </code>: Kundsegment-ID. Föråldrat. Använd <code> sid </code>. </li> 
     <li id="li_D85F0A5D16AE4DAFB55C17DBB35EA66E"> <code> sid </code>: Segment-ID </li> 
     <li id="li_9BE103EFD8384464B46FAC00422431DB"> <code> type </code>: Returnerar <code> 5 </code>, ett statiskt, hårdkodat värde som identifierar data som segmentdata. </li> 
     <li id="li_FE5049089F2944FA9DB9F9D546DBA167"> <code> alias </code>: Föråldrat. Skall ej användas. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD27"> <code> lastUpdateTime </code>: En Unix-tidsstämpel som anger att segmentets senaste medlemskapsstatus uppdaterades. </li>
     <li id="li_DD778AA2D1DB4D409CF5026B5D9DBD28"> <code> lastRealizationTime </code>: En Unix-tidsstämpel som anger när ett segment senast realiserades. </li>
    </ul> <p>Placera dessa variabler inom klammerparentes efter makrot. I den här koden avgränsas resultatet med ett vertikalstreck (|): <code> &lt;SEGMENT_LIST:{seg|&lt;seg.type&gt;,&lt;seg.sid&gt;}; separator=","&gt; </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SET_ATTRIBUTES </code> </p> </td> 
   <td colname="col2"> <p>Returnerar <code> 1 </code>, som ett statiskt, hårdkodat värde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_MODE </code> </p> </td> 
   <td colname="col2"> <p>Anger synkroniseringstyp och inkluderar: </p> 
    <ul id="ul_A3ADC37E66F043DABDA9C4066024B6C1"> 
     <li id="li_A1859F63ACF24618884C41F2DAB19ABB"> <code> full </code>: Fullständig synkronisering. </li> 
     <li id="li_520DDED3662B428DB9DB55D494221D97"> <code> iter </code>: Inkrementell synkronisering. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> SYNC_TYPE </code> </p> </td> 
   <td colname="col2"> <p>Anger dataöverföringsmetod och innehåller: </p> 
    <ul id="ul_13BE35BBBF7C4C67AEFC514C5D192902"> 
     <li id="li_195FE9B4C5494600BD17D7172A8FB630"> <code> ftp </code> </li> 
     <li id="li_751AD59C4C934D66BC530D9806B500AF"> <code> http </code> </li> 
     <li id="li_4638AF7D1FB54E2C890045048B85309C"> <code> s3 </code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Makrot används som avgränsare och infogar en tabb mellan fält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TRAIT_LIST </code> </p> </td> 
   <td colname="col2"> <p>Returnerar en lista med egenskaper. Accepterar följande valfria argument: </p> 
    <ul id="ul_E9CDC4DD47B9435086FF42143D9E8177"> 
     <li id="li_4BBC57F0D7874F8EA8C6D39DB3572257"> <code> type </code>: Identifierar trait-typer efter numeriskt ID. Returnerar: 
      <ul id="ul_D2357E6CF47B4EBC8D3772D17B2EADA3"> 
       <li id="li_C6C2A019FCD945E085E1ABB564C4EDAD"> <code> 10 </code> som identifierar en DPM-egenskap (offline, tilldelad av ett inkommande jobb). </li> 
       <li id="li_7AFF8A1D0E1140459CC95CF43A97B9B6"> <code> 3 </code> som identifierar ett regelbaserat beteende (realtid, som introduceras via DCS). </li> 
      </ul> </li> 
     <li id="li_1DDE25334CF9479A8C4738F3CB3C40AA"> <code> traitId </code>: trait-ID. </li> 
     <li id="li_DCB89F2A40BB43C98EE3C84B5B3CDD33"> <code> lastRealized </code>: Senaste gången trait realiserades. Unix tidsstämpel. </li> 
    </ul> <p>Placera dessa variabler inom klammerparentes efter makrot. I den här koden avgränsas resultatet med ett vertikalstreck (|): <code> &lt;TRAIT_LIST:{trait|&lt;trait.Id&gt;,&lt;trait.lastRealized&gt;};separator="," </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> UUID </code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> användar-ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Exempel på utgående makron](../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-macro-examples.md)

