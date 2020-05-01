---
description: Visar och beskriver syntaxen och de attribut (eller nyckelvärdepar) som stöds och som du kan skicka in till datainsamlingsservrarna (DCS). Den här informationen kan hjälpa dig att formatera dina DCS-begäranden och förstå de parametrar som returneras av systemet.
seo-description: Visar och beskriver syntaxen och de attribut (eller nyckelvärdepar) som stöds och som du kan skicka in till datainsamlingsservrarna (DCS). Den här informationen kan hjälpa dig att formatera dina DCS-begäranden och förstå de parametrar som returneras av systemet.
seo-title: Attribut som stöds för DCS API-anrop
solution: Audience Manager
title: Attribut som stöds för DCS API-anrop
keywords: d_caller, d_cb, d_cid, d_cid_ic, d_coppa, d_cts=1, d_cts=2, d_tdpid, d_dst=1, d_dst_filter, d_mid, d_ptfm, d_nsid, d_rs, d_rtbd=json, d_tdpid_ic
uuid: 0b98ed11-314b-4500-afde-45a041112150
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Attribut som stöds för DCS API-anrop {#supported-attributes-for-dcs-api-calls}

Visar och beskriver syntaxen och de attribut (eller nyckelvärdepar) som stöds och som du kan skicka till [!UICONTROL Data Collection Servers] ([!UICONTROL DCS]). Den här informationen kan hjälpa dig att formatera dina [!UICONTROL DCS] förfrågningar och förstå de parametrar som returneras av systemet.

## Attributprefix {#attribute-prefixes}

De [!UICONTROL DCS] förlitar sig på specifika prefix som läggs till nycklarna i nyckelvärdepar för att klassificera den typ av data som du skickar in.

<table id="table_23B7E15EC13749E9A245DFB543822DB7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckelprefix </th> 
   <th colname="col2" class="entry"> Reserverad för </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> c_</code> </p> </td> 
   <td colname="col2"> <p>Kunddefinierade attribut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_</code> </p> </td> 
   <td colname="col2"> <p><span class="keyword"> Audience Manager</span> -attribut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> h_</code> </p> </td> 
   <td colname="col2"> <p>HTTP-rubrikdata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> p_</code> </p> </td> 
   <td colname="col2"> <p>Privata, kunddefinierade attribut. </p> <p> DCS accepterar egna, privata data när nyckeln har ett <code> p_</code> prefix. Privata data används för utvärdering av egenskaper, men de kommer inte att loggas eller lagras i vårt system. Anta till exempel att du har en egenskap definierad som <code> customers = p_age&lt;25</code> och att du skickar in <code> p_age=23</code> i ett händelseanrop. Med dessa villkor kvalificerar den användare som uppfyller de åldersbaserade kvalificeringskriterierna sig för egenskapen, men nyckelvärdepar tas bort efter att <span class="keyword"> Audience Manager</span> har tagit emot begäran och inte loggats. </p> </td>
  </tr> 
 </tbody> 
</table>

## d_Attribut {#d-attributes}

Alla dessa är valfria, såvida du inte vill ha ett svar från [!UICONTROL DCS]. Om du vill [!UICONTROL DCS] att användaren ska returnera ett svar `d_rtbd=json` måste du göra det.

<table id="table_FCCE4F9D796648899772A191981EFDE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribut </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> d_caller</code> </p> </td> 
   <td colname="col2"> <p>Används för att identifiera anroparen som anropar <span class="wintitle"> DCS</span> API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cb</code> </p> </td> 
   <td colname="col2"> <p>Anger en JavaScript-funktion som du vill köra med <span class="wintitle"> DCS</span> -svaret som en funktionsparameter för callback-funktionen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_cid</code> </p> </td> 
   <td colname="col2"> <p>Innehåller ett eller flera par av ID:n (<code> DPID</code>) för dataleverantörer och användar-ID:n (<code> DPUUID</code>) för dataleverantörer som tilldelats av <span class="keyword"> Audience Manager</span>. Om du använder flera par med <code> DPID</code>s och <code> DPUUID</code>s separerar du varje par med tecknet som inte skrivs ut <code> %01</code>. Exempel: <code><i>DPID</i>%01<i>DPUUUID</i></code>. </p> <p><code> d_cid</code> ersätts <code> d_dpid</code> och <code> d_dpuuid</code>, som är borttagna men fortfarande stöds. Se <a href="../../../reference/cid.md"> CID ersätter DPID och DPUUID</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cid_ic</code> </p> </td> 
   <td colname="col2"> <p>Innehåller en integreringskod och ett associerat unikt användar-ID i ett enda nyckelvärdepar. </p> <p><code> d_cid_ic</code> ersätts <code> d_dpid</code> och <code> d_dpuuid</code>, som är borttagna men fortfarande stöds. Se <a href="../../../reference/cid.md"> CID ersätter DPID och DPUUID</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_coppa</code> </p> </td> 
   <td colname="col2"> <p>Inaktivera användning av cookies från tredje part för att uppfylla regler för skydd av barn. Den här parametern ställs in dynamiskt av Adobe Experience Platform Identity Service och beror på <code> idSyncDisable3rdPartySyncing</code> konfigurationen. Se <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/coppa.html" format="https" scope="external"> COPPA-stöd i Adobe Experience Platform Identity Service</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><code> d_cts=1</code> </p> <p><code> d_cts=2</code> </p> </td> 
   <td colname="col2"> <p>Valfritt. Aktiverad på kundens begäran. Kontakta din Adobe Audience Manager-konsult eller kundtjänst. </p> <p>Anger att egenskaper och segment ska returneras inuti <code> JSON</code> svaret. </p> <p> 
     <ul id="ul_8B936ACB18724681B959783421ACF026"> 
      <li id="li_792A6248F49141C0B4B214C754D5F5C5"> <p><code> d_cts=1</code> returnerar <a href="../../../reference/ids-in-aam.md"> äldre segment-ID</a> för segmenten. </p> </li>
      <li id="li_F304CA651F3C444A9A24576726925D87"> <p><code> d_cts=2</code> returnerar segment-ID:n för segmenten. </p> </li>
     </ul> </p> <p>Ett exempelsvar kan se ut som det nedan: </p> <p>
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"07955261652886032950143702505894272138",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"traits":&nbsp;[420020,&nbsp;5421506],
      &nbsp;&nbsp;&nbsp;&nbsp;"segments":&nbsp;[984263,&nbsp;985264],
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpid</code> </p> </td> 
   <td colname="col2"> <p>Föråldrat. Se <code> d_cid</code> och <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dpuuid</code> </p> </td> 
   <td colname="col2"> <p>Föråldrat. Se <code> d_cid</code> och <code> d_cid_ic</code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst=1</code> </p> </td> 
   <td colname="col2"> <p>Returnerar URL-måldata i <code> JSON</code> svaret. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_dst_filter</code> </p> </td> 
   <td colname="col2"> <p><code> d_dst_filter</code> är ett reserverat attribut som används i integrationen mellan Adobe Analytics och Audience Manager. </p> <p>Vi rekommenderar att du inte skapar egenskaper som använder reserverade attribut. Adobe kan när som helst ändra reserverade attribut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_jsonv=1|0</code> </p> </td> 
   <td colname="col2"> <p>Anger vilken <code> JSON</code> version som ska användas i svaret. Normalt bör du ange det här till <code> d_jsonv=1</code>. Inställningen <code> d_jsonv=0</code> inaktiverar ID-synkronisering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_mid</code> </p> </td> 
   <td colname="col2"> <p>Anger Experience Cloud ID-uppsättningen och som används av <span class="keyword"> Experience Cloud</span> ID-tjänsten. Mer information om ECID finns i <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies och Experience Cloud Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_nsid</code> </p> </td> 
   <td colname="col2"> <p>Namnområdes-ID. Anger vilken JavaScript-behållare som används. Används av <span class="wintitle"> DIL</span> för ID-synkronisering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_ptfm </code> </p> </td> 
   <td colname="col2"> <p>Gör att Audience Manager kan skilja på mobilförfrågningar och datorförfrågningar. Värden som stöds är: </p> <p> 
     <ul id="ul_A01D4B15C89F4713A39E08377924D632"> 
      <li id="li_E17CC839265B4EB9AC44A3DA31A23857"> <code> ios</code> </li> 
      <li id="li_468F5903CD3048B5AE02A3FDA9B3C4F1"> <code> android</code> </li> 
      <li id="li_57090DAC3BDA41DFB4BA0DD328754D55"> <code> browser</code> </li> 
      <li id="li_DA4E93A831FE4FD8971CECD508AF992F"> <code> all</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rs</code> </p> </td> 
   <td colname="col2"> <p>Föråldrat. <code> d_rs</code> är ett reserverat attribut som används i den äldre integreringen mellan <span class="keyword"> Adobe Analytics</span> och <span class="keyword"> Audience Manager</span>. </p> <p>Vi rekommenderar att du inte skapar egenskaper som använder reserverade attribut. Adobe kan när som helst ändra reserverade attribut. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_rtbd=json</code> </p> </td> 
   <td colname="col2"> <p>Krävs om du vill ha ett <code> JSON</code> svar från <span class="wintitle"> DCS</span>. </p> <p> 
     <ul id="ul_9EA00BD822504BCA8ECB59C1634DB91A"> 
      <li id="li_7CB890F92C4A4C6AA8B4EE32E1AD4564">Om du utelämnar detta returnerar <span class="wintitle"> DCS</span> en pixel i sidhuvudet. </li> 
      <li id="li_824C23B4C7AA4B5EBADF73D26016A18E">Om du tar med det här returnerar <span class="wintitle"> DCS</span> ett <code> JSON</code> objekt i svarstexten. Se exemplet nedan. Svaret kan vara mer komplext. </li> 
     </ul> </p> <p> 
     <code class="syntax javascript">
      {
      &nbsp;&nbsp;&nbsp;&nbsp;"stuff":&nbsp;[],
      &nbsp;&nbsp;&nbsp;&nbsp;"uuid":&nbsp;"22920112968019678612904394744954398990",
      &nbsp;&nbsp;&nbsp;&nbsp;"dcs_region":&nbsp;7,
      &nbsp;&nbsp;&nbsp;&nbsp;"tid":&nbsp;"ss3OTqPiQp0="
      }
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_sid</code> </p> </td> 
   <td colname="col2"> <p><code> SID</code> står för <span class="term"> score ID</span>. Detta är ett unikt ID för ett trait eller segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid</code> </p> </td> 
   <td colname="col2"> <p>Skickar en datakälla för utvärdering av egenskaper. Endast egenskaper från den här datakällan utvärderas. </p> <p>Anta till exempel att du har: </p> <p> 
     <ul id="ul_6230777E16C14DCB83025A101A4ECA14"> 
      <li id="li_71F3970417BC4B93881A3E12DADE4120"><b>Trait T1</b> with: </li> 
      <li id="li_66125E035F524A958C6F4BFAABA2A0D2">Trait-regel: "<code> key1 == val1</code>" </li> 
      <li id="li_4EE486E02CF54AEA876ABC005094E9E4">Datakälla (<a href="../../../reference/ids-in-aam.md"> DPID</a>): 1 </li> 
      <li id="li_3E6BBDEAE5C644C6A96CB49766CDA988">Integrationskod för DPID: ic1 </li> 
     </ul> 
     <ul id="ul_0C30A8AE349D43A08490DA76CB4B06FA"> 
      <li id="li_F1E8DB26168B471FA35D82F4DD3AC601"><b>Trait T2</b> with: </li> 
      <li id="li_1C943F84A4A149A0A86ABC92761D3E9E">Trait-regel: "<code> key2 == val2</code>" </li> 
      <li id="li_F2AA086C87B7484F8BFE1D5C09E8EBDF">Datakälla (DPID): 2 </li> 
      <li id="li_877CAAAE996A4707BEE74F7042708481">Integrationskod för DPID: ic2 </li> 
     </ul> </p> <p>I ett samplingsanrop <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid=1</code>returneras endast trait T1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_tdpid_ic</code> </p> </td> 
   <td colname="col2"> <p>Syftet är identiskt med den <code> d_tdpid</code> parameter som beskrivs ovan. I det här fallet skickas datakällan med integreringskoden. </p> <p>Behåll de egenskaper som beskrivs ovan, överväg att genomföra stickprovet: </p> <p>För <code>yourcompany.demdex.net/event?key1=val1&amp;key2=val2&amp;d_tdpid_ic=ic2</code>det returneras endast egenskapen T2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> d_uuid</code> </p> </td> 
   <td colname="col2"> <p>Unikt användar-ID. Identifierar en besökare när det här värdet inte är tillgängligt från en cookie. </p> </td> 
  </tr>
 </tbody>
</table>