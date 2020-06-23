---
description: Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet Profile Link, Adobe Experience Cloud Device Co-op och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt fyra regler för profilsammanslagning.
seo-description: Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet Profile Link, Adobe Experience Cloud Device Co-op och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt fyra regler för profilsammanslagning.
seo-title: Alternativ för profilkopplingsregel definierade
solution: Audience Manager
title: Alternativ för profilkopplingsregel definierade
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 0%

---


# [!UICONTROL Profile Merge Rules] Alternativ definierade {#profile-merge-rule-options-defined}

Med [!UICONTROL profile merge rule] alternativen kan du styra vilken typ av data som [!DNL Audience Manager] används för segmentering. Ett [!UICONTROL profile merge rule] program kan innehålla enhetsprofiler som mappats av [!UICONTROL Profile Link] enhetsdiagrammet, [!UICONTROL Adobe Experience Cloud Device Co-op]och/eller andra tredjepartsdiagramleverantörer som är integrerade med [!DNL Audience Manager]. Du kan skapa maximalt 4 [!UICONTROL Profile Merge Rules]. Den fjärde [!UICONTROL Profile Merge Rule] är exklusivt tillgänglig för kunder som köpt [!UICONTROL People-Based Destinations] tillägget.

Du skapar en [!UICONTROL Profile Merge Rule] genom att göra ett val bland alternativen som beskrivs nedan [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Alternativöversikt {#overview}

[!UICONTROL Profile Merge Rules] möjliggör ett antal kombinationer av regler, som var och en är inriktad på specifika användningsområden. Se tabellen nedan för mer ingående information om när varje regelkombination ska användas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Tillgänglighet | Utvärderingstyp | [!UICONTROL Audience Lab] Support | Användningsexempel |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alla kunder | Realtid och batch | Ja | [Målinriktning](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] (inkluderar [!UICONTROL Co-op Device Graph]) | Alla kunder | Realtid och batch | Nej | [Utökad målinriktning](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alla kunder | Endast i realtid | Nej | [Delad enhetsinriktning](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alla kunder | Realtid och batch | Ja | [Online-/offlinemål](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alla kunder | Realtid och batch | Ja | [Målinriktning på flera enheter](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] (inkluderar [!UICONTROL Co-op Device Graph]) | Alla kunder | Realtid och batch | Nej | [Avancerad målgruppsanpassning mellan enheter](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | Ej tillämpligt | Endast för [personbaserade](../destinations/people-based-destinations-overview.md) destinationskunder | Endast batch | Nej | [Målgruppsanpassning för personbaserade destinationer](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Utvärdering {#segment-evaluation}

Beroende på din [!UICONTROL Profile Merge Rules] konfiguration [!DNL Audience Manager] kan utföra [!UICONTROL segment] utvärderingen i realtid, i batch eller både och.

* Vid [!UICONTROL segment] utvärdering i realtid måste besökarna [!DNL DCS] se era digitala resurser i realtid för att kvalificera sig för [!UICONTROL segment].
* Batchutvärderingen [!UICONTROL segment] utförs mot tidigare kvalificerade [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] som stöder både realtids- och batchutvärdering kombinerar besökaraktiviteten i realtid med tidigare kvalificerad [!UICONTROL segment] aktivitet [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Svarstid för rapportering {#reporting-latency}

Realtidsutvärderingen [!UICONTROL segment] återspeglas omedelbart i [!UICONTROL Profile Merge Rules] rapporterna.

Det kan ta upp till 24 timmar att [!UICONTROL segment] utvärdera grupper för att spegla i [rapporter](profile-link-metrics.md)om regler för profilsammanslagning.

## [!UICONTROL Cross-Device Options] {#auth-options}

Med [!UICONTROL Cross-Device Options] verktyget kan du välja autentiserade och oautentiserade användare och använda deras enhetsövergripande profil för segmentering. Dessa alternativ hjälper dig att identifiera och nå specifika användare på en delad enhet. Mer information om anonyma och autentiserade användare finns i Autentiseringstillstånd för [besökare i Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att inte använda uppgifter som samlats in från autentiserade användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuella autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa och skriva data till den autentiserade profilen om en besökare har loggat in på din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Senaste autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa data från den autentiserade profilen för den användare som senast loggade in på enheten. </p> <p>När du väljer det här alternativet skriver inte <span class="keyword"> Audience Manager</span> nya trait-data till den autentiserade profilen om användaren är anonym. Vid autentisering skrivs nya trait-data till användarens autentiserade profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alla enhetsövergripande profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar Audience Manager att läsa data från alla enhetsövergripande profiler, oavsett autentiseringsstatus. Det här alternativet är endast tillgängligt för Audience Manager-kunder som har köpt tillägget Personer-baserade destinationer.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

I [!UICONTROL Cross-Device Profile Options] listorna [!UICONTROL cross-device data sources]. Dessa alternativ använder de namn du angav när du skapade en [!UICONTROL cross-device] fil [!UICONTROL data source] (se [Skapa en datakälla](merge-rules-start.md#create-data-source)för olika enheter). Du kan välja upp till 3 [!UICONTROL cross-device data sources] för varje profilregel. De [!UICONTROL Authenticated Profile Options] är tillgängliga när du väljer **[!UICONTROL Current Authenticated Profiles]** eller **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

Med den här ikonen kan du [!UICONTROL Device Options] välja vilken typ av *`device profile`* som används av en [!UICONTROL Profile Merge Rule]. En enhetsprofil har skapats utifrån [!UICONTROL traits] en anonym surfningsaktivitet. Som ett minimum [!UICONTROL profile merge rule] innehåller en [!UICONTROL authenticated option] och en [!UICONTROL device option].

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
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa profilerna från den aktuella enheten och upp till 100 andra enheter som användaren har autentiserat från. Det här enhetsdiagrammet bygger på egna data från första part i <span class="keyword"> Audience Manager</span>. Det är idealiskt för kunder som har en hög autentiseringsnivå över sina digitala resurser. Enhetsdiagrammet <span class="wintitle"> Profile Link</span> uppdateras i realtid. Det här alternativet är tillgängligt när du väljer <b><span class="uicontrol"> Aktuell autentiserad profil</span></b> eller <b><span class="uicontrol"> Senaste autentiserade profil</span></b>. När du använder det här alternativet kan du bara välja en enda autentiserad profil (<span class="keyword"> Audience Manager</span> gråskalar automatiskt ut de andra). Se även, <a href="profile-link-use-case.md"> Profile Link Device Graph Use Case</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Co-op Device Graph</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa profilerna från den aktuella enheten och upp till 100 andra enheter med hjälp av länkarna från <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Experience Cloud Device Co-op</a>. </p> <p>Device Co-op <span class="keyword"></span> är ett digitalt samarbete där deltagande kunder delar information om enhetslänkar. Device Co-op <span class="keyword"> bearbetar dessa data i ett</span> enhetsdiagram <span class="term"></span>. Ett enhetsdiagram länkar samman enheter från enhetsgrupper. Länkarna bygger på <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/links.html" format="https" scope="external"> sannolikhetsdata och deterministiska data</a>. Klustren representerar en grupp enheter som används av en okänd person. Device Co-op <span class="keyword"></span> delar dessa kluster bland sina medlemmar, vilket hjälper dem att leverera värdefulla och enhetliga upplevelser på olika enheter till sina kunder. </p> <p> Mer information om Device Co-op <span class="wintitle"></span>finns i: </p> <p> 
     <ul id="ul_8EDA7D092ECD444C8C19CDC7534D84DE"> 
      <li id="li_323BC5993D6A4BA3962169BF0ED37C55"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/home.html" format="https" scope="external"> Device Co-op - översikt</a> </li> 
      <li id="li_0BDB2144EC584002B3B9F1D64B6CD580"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/requirements.html" format="https" scope="external"> Krav för medlemskap</a> </li> 
      <li id="li_632D1014909146758F07CFAC79B90CFE"> <a href="https://docs.adobe.com/content/help/en/device-co-op/using/device-graph/device-graph-overview.html" format="https" scope="external"> Enhetsdiagram: Interna processer och utdata</a> </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Alternativ</b> för tredjepartsdiagram (person och hushåll) </p> </td>
   <td colname="col2"> <p>Med dessa alternativ kan du skapa sammanfogningsregler som baseras på enhetsgraferingsteknik från en tredjepartsleverantör. Ett enhetsdiagram från tredje part innehåller: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Sannolikhetsdata och/eller deterministiska data. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Uppgifter på individ- eller hushållsnivå. </li> 
     </ul> </p> <p>Om du vill använda dessa alternativ måste du vara kund till en enhetsdiagram som redan är integrerad med <span class="keyword"> Audience Manager</span>. Kontakta din kontoansvarige om du vill ha mer information eller vill komma igång. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Målgruppssegment som automatiskt skapats från andra [!DNL Experience Cloud] lösningar, baserat på sammanfogningsregler som definierats utanför [!DNL Audience Manager], markeras som om de använder en [!UICONTROL External Merge Policy]. Se till exempel [Målgruppsdelning mellan Audience Manager och Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning](../../faq/faq-profile-merge.md)

