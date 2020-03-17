---
description: Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet Profile Link, Adobe Experience Cloud Device Co-op och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt fyra regler för profilsammanslagning.
seo-description: Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet Profile Link, Adobe Experience Cloud Device Co-op och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt fyra regler för profilsammanslagning.
seo-title: Alternativ för profilkopplingsregel definierade
solution: Audience Manager
title: Alternativ för profilkopplingsregel definierade
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: e27ce2f607cadd7318a171359a5ae4daa071c486

---


# Alternativ för profilkopplingsregler definierade {#profile-merge-rule-options-defined}

Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som mappats av enhetsdiagrammet, [!UICONTROL Profile Link] enhetsdiagrammet [!UICONTROL Adobe Experience Cloud Device Co-op]och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt 4 [!UICONTROL Profile Merge Rules]. Den fjärde [!UICONTROL Profile Merge Rule] är exklusivt tillgänglig för kunder som köpt [!UICONTROL People-Based Destinations] tillägget.

Du skapar en [!UICONTROL Profile Merge Rule] genom att göra ett val bland alternativen som beskrivs nedan [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## Översikt över alternativ för sammanslagningsregel för profil {#overview}

Regler för profilsammanfogning tillåter ett antal regelkombinationer, som var och en är inriktad på specifika användningsfall. Se tabellen nedan för mer ingående information om när varje regelkombination ska användas.

| Alternativ för flera enheter | Enhetsalternativ | Tillgänglighet | Utvärderingstyp | Stöd för Audience Lab | Användningsexempel |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| Ingen enhetsprofil | Enhetsprofil | Alla kunder | Realtid och batch | Ja | [Målinriktning](merge-rule-targeting-options.md#device-personalization) |
| Ingen enhetsprofil | Externt enhetsdiagram (inkluderar enhetsdiagram för Co-op) | Alla kunder | Realtid och batch | Nej | [Utökad målinriktning](external-graph-use-cases.md#audience-expansion) |
| Aktuella autentiserade profiler | Ingen enhetsprofil | Alla kunder | Endast i realtid | Nej | [Delad enhetsinriktning](merge-rule-targeting-options.md#target-shared-devices) |
| Senaste autentiserade profiler | Enhetsprofil | Alla kunder | Realtid och batch | Ja | [Online-/offlinemål](merge-rule-targeting-options.md#device-household-targeting) |
| Senaste autentiserade profiler | Enhetsdiagram för profillänk | Alla kunder | Realtid och batch | Ja | [Målinriktning på flera enheter](profile-link-use-case.md#cross-device-personalization) |
| Senaste autentiserade profiler | Externt enhetsdiagram (inkluderar enhetsdiagram för Co-op) | Alla kunder | Realtid och batch | Nej | [Avancerad målgruppsanpassning mellan enheter](external-graph-use-cases.md#advanced-graph-expansion) |
| Alla enhetsövergripande profiler | Ej tillämpligt | Endast för [personbaserade](../destinations/people-based-destinations-overview.md) destinationskunder | Endast batch | Nej | [Målgruppsanpassning för personbaserade destinationer](merge-rule-targeting-options.md#all-cross-device) |

## Utvärdering av sammanslagningsregelsegment för profil {#segment-evaluation}

Beroende på din [!UICONTROL Profile Merge Rules] konfiguration kan Audience Manager utföra segmentutvärderingen i realtid, i batch eller både och.

* Vid utvärdering av segment i realtid måste besökarna [!DNL DCS] se era digitala resurser i realtid för att kvalificera sig för segmentet.
* Utvärdering av batchsegment görs mot tidigare kvalificerade egenskaper.
* [!UICONTROL Profile Merge Rules] som stöder både utvärdering i realtid och gruppsegmentsutvärdering kombinerar besökaraktiviteten i realtid med tidigare kvalificerade egenskaper.

## Rapporteringsfördröjning för profilkopplingsregler {#reporting-latency}

Utvärderingen av segment i realtid återspeglas direkt i [!UICONTROL Profile Merge Rules] rapporterna.

Det kan ta upp till 24 timmar att utvärdera batchsegment för att spegla dem i [profilkopplingsregelrapporter](profile-link-metrics.md).

## Alternativ för olika enheter {#auth-options}

Med [!UICONTROL Cross-Device Options] verktyget kan du välja autentiserade och oautentiserade användare och använda deras enhetsövergripande profil för segmentering. Dessa alternativ hjälper dig att identifiera och nå specifika användare på en delad enhet. Mer information om anonyma och autentiserade användare finns i [Autentiseringstillstånd för besökare i Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Alternativ för flera enheter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ingen enhetsprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att inte använda data som samlats in från autentiserade användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuella autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa och skriva data till den autentiserade profilen om en besökare har loggat in på din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Senaste autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa data från den autentiserade profilen för den användare som senast loggade in på enheten. </p> <p>När detta är markerat skriver inte Audience Manager <span class="keyword"></span> nya egenskapsdata till den autentiserade profilen om användaren är anonym. Vid autentisering skrivs nya trait-data till användarens autentiserade profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alla enhetsövergripande profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar Audience Manager att läsa data från alla enhetsövergripande profiler, oavsett autentiseringsstatus. Det här alternativet är endast tillgängligt för Audience Manager-kunder som har köpt tillägget Folk-baserade destinationer.</p> </td>
  </tr>
 </tbody>
</table>

## Profilalternativ för olika enheter {#profile-options}

I [!UICONTROL Cross-Device Profile Options] listan visas datakällor mellan olika enheter. Dessa alternativ använder de namn du angav när du skapade en datakälla för olika enheter (se [Skapa en datakälla](merge-rules-start.md#create-data-source)för olika enheter). Du kan välja upp till tre datakällor för olika enheter som ska användas med varje profilregel. De [!UICONTROL Authenticated Profile Options] är tillgängliga när du väljer **[!UICONTROL Current Authenticated Profiles]** eller **[!UICONTROL Last Authenticated Profiles]**.

## Enhetsalternativ {#device-options}

Med den här ikonen kan du [!UICONTROL Device Options] välja vilken typ av *`device profile`* som används av en [!UICONTROL Profile Merge Rule]. En enhetsprofil byggs utifrån egenskaper som samlats in från anonym surfningsaktivitet. En regel för profilsammanslagning innehåller åtminstone ett autentiserat alternativ och ett enhetsalternativ.

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Enhetsalternativ </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ingen enhetsprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att inte använda de egenskaper som ingår i den anonyma profilen för segmentering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Enhetsprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att använda den anonyma enhetsprofilen för segmentering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Enhetsdiagram för profillänk</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar Audience Manager <span class="keyword"></span> att läsa profilerna från den aktuella enheten och upp till 100 andra enheter som användaren har autentiserat från. Det här enhetsdiagrammet bygger på egna data från första part i <span class="keyword"> Audience Manager</span>. Det är idealiskt för kunder som har en hög autentiseringsnivå över sina digitala resurser. Enhetsdiagrammet <span class="wintitle"> Profile Link</span> uppdateras i realtid. Det här alternativet är tillgängligt när du väljer <b><span class="uicontrol"> Aktuell autentiserad profil</span></b> eller <b><span class="uicontrol"> Senaste autentiserade profil</span></b>. När du använder det här alternativet kan du bara välja en autentiserad profil (<span class="keyword"> Audience Manager</span> gör de andra automatiskt gråtonade). Se även, <a href="profile-link-use-case.md"> Profile Link Device Graph Use Case</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar Audience Manager <span class="keyword"> att läsa profilerna från den aktuella enheten och upp till 100 andra enheter med hjälp av länkarna i</span> Experience Cloud Device Co-op <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/" format="https" scope="external"></a>. </p> <p>Device Co-op <span class="keyword"></span> är ett digitalt samarbete där deltagande kunder delar information om enhetslänkar. Device Co-op <span class="keyword"> bearbetar dessa data i ett</span> enhetsdiagram <span class="term"></span>. Ett enhetsdiagram länkar samman enheter från enhetsgrupper. Länkarna bygger på <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-links.html" format="https" scope="external"> sannolikhetsdata och deterministiska data</a>. Klustren representerar en grupp enheter som används av en okänd person. Device Co-op <span class="keyword"></span> delar dessa kluster bland sina medlemmar, vilket hjälper dem att leverera värdefulla och enhetliga upplevelser på olika enheter till sina kunder. </p> <p> Mer information om Device Co-op <span class="wintitle"></span>finns i: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-overview.html" format="https" scope="external"> Device Co-op - översikt</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-requirements.html" format="https" scope="external"> Krav för medlemskap</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html" format="https" scope="external"> Enhetsdiagram: Interna processer och utdata</a> </li> 
      <li id="li_9DF8876BFBC043948D3E82BD081AAF9F"><a href="https://marketing.adobe.com/resources/help/en_US/aam/downloads/AAM_Device_Graphs.pdf" format="https" scope="external"> Audience Manager och External Device Graphs</a> (PDF-nedladdning). </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Alternativ</b> för tredjepartsdiagram (person och hushåll) </p> </td>
   <td colname="col2"> <p>Med dessa alternativ kan du skapa sammanfogningsregler som baseras på enhetsgraferingsteknik från en tredjepartsleverantör. Ett enhetsdiagram från tredje part innehåller: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Sannolikhetsdata och/eller deterministiska data. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Uppgifter på individ- eller hushållsnivå. </li> 
     </ul> </p> <p>För att kunna använda dessa alternativ måste du vara kund till en enhetsgraf som redan är integrerad med <span class="keyword"> Audience Manager</span>. Kontakta din kontoansvarige om du vill ha mer information eller vill komma igång. </p> </td>
  </tr>
 </tbody>
</table>

## Principer för extern sammanslagning {#external-merge-policies}

Målgruppssegment som automatiskt skapats från andra Experience Cloud-lösningar, baserat på kopplingsregler som definierats utanför Audience Manager, markeras som om de använder en [!UICONTROL External Merge Policy]. Se till exempel [Målgruppsdelning mellan Audience Manager och Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning](../../faq/faq-profile-merge.md)

