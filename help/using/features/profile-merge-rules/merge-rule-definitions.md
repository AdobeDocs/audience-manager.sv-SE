---
description: Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet Profile Link och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt fyra regler för profilsammanslagning.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Alternativ för profilkopplingsregel definierade
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '794'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules] alternativ har definierats {#profile-merge-rule-options-defined}

Med alternativen för [!UICONTROL profile merge rule] kan du styra vilken typ av data som [!DNL Audience Manager] använder för segmentering. En/ett [!UICONTROL profile merge rule] kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet [!UICONTROL Profile Link] och/eller andra tredjepartsdiagramleverantörer som är integrerade med [!DNL Audience Manager]. Du kan skapa högst 4 [!UICONTROL Profile Merge Rules]. Den fjärde [!UICONTROL Profile Merge Rule] är exklusivt tillgänglig för kunder som har köpt tillägget [!UICONTROL People-Based Destinations].

Du skapar en [!UICONTROL Profile Merge Rule] genom att göra ett val bland alternativen som beskrivs nedan i [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Alternativ - översikt {#overview}

[!UICONTROL Profile Merge Rules] tillåter ett antal regelkombinationer, som var och en är inriktad på specifika användningsfall. Se tabellen nedan för mer ingående information om när varje regelkombination ska användas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Tillgänglighet | Utvärderingstyp | [!UICONTROL Audience Lab] support | Användningsexempel |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alla kunder | Realtid och batch | Ja | [Målinriktning för enhet](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Alla kunder | Realtid och batch | Nej | [Utökat enhetsmål](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alla kunder | Endast i realtid | Nej | [Delad målenhet](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alla kunder | Realtid och batch | Ja | [Online-/offlinemål](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alla kunder | Realtid och batch | Ja | [Målinriktning mellan enheter](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Alla kunder | Realtid och batch | Nej | [Avancerad målinriktning mellan enheter](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | Ej tillämpligt | Exklusivt för [personbaserade destinationer](../destinations/people-based-destinations-overview.md)-kunder | Endast batch | Nej | [Målgruppsanpassning för personbaserade mål](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Utvärdering {#segment-evaluation}

Beroende på din [!UICONTROL Profile Merge Rules]-konfiguration kan [!DNL Audience Manager] utföra [!UICONTROL segment]-utvärderingen i realtid, i batch eller båda.

* Utvärderingen av [!UICONTROL segment] i realtid kräver att [!DNL DCS] ser besökarna få åtkomst till dina digitala egenskaper i realtid för att kvalificera sig för [!UICONTROL segment].
* Utvärdering av grupp [!UICONTROL segment] utförs mot tidigare kvalificerad [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] som stöder både realtids- och batchutvärdering [!UICONTROL segment] kombinerar besöksaktiviteten i realtid med tidigare kvalificerad [!UICONTROL traits].

## Svarstid för rapportering för [!UICONTROL Profile Merge Rules] {#reporting-latency}

Realtidsutvärderingen av [!UICONTROL segment] visas omedelbart i [!UICONTROL Profile Merge Rules]-rapporterna.

Utvärderingen av gruppen [!UICONTROL segment] kan ta upp till 24 timmar att reflektera i [rapporter för profilkopplingsregler](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

Med [!UICONTROL Cross-Device Options] kan du välja autentiserade och oautentiserade användare och utnyttja deras enhetsövergripande profil för segmentering. Dessa alternativ hjälper dig att identifiera och nå specifika användare på en delad enhet. Mer information om anonyma och autentiserade användare finns i [Autentiseringstillstånd för besökare i Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Alternativ för flera enheter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Ingen enhetsprofil </span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att inte använda data som samlats in från autentiserade användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> aktuella autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa och skriva data till den autentiserade profilen om en besökare har loggat in på din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> senast autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa data från den autentiserade profilen för den användare som senast loggade in på enheten. </p> <p>Om det här alternativet är markerat skriver <span class="keyword"> Audience Manager</span> inte nya egenskapsdata till den autentiserade profilen om användaren är anonym. Vid autentisering skrivs nya trait-data till användarens autentiserade profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alla enhetsövergripande profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar Audience Manager att läsa data från alla enhetsövergripande profiler, oavsett autentiseringsstatus. Det här alternativet är endast tillgängligt för Audience Manager-kunder som har köpt tillägget Personer-baserade destinationer.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

[!UICONTROL Cross-Device Profile Options] visar din [!UICONTROL cross-device data sources]. De här alternativen använder de namn du angav när du skapade [!UICONTROL cross-device] [!UICONTROL data source] (se [Skapa ett Source för korsenhetsdata](merge-rules-start.md#create-data-source)). Du kan välja upp till 3 [!UICONTROL cross-device data sources] för varje profilregel. [!UICONTROL Authenticated Profile Options] är tillgängligt när du väljer **[!UICONTROL Current Authenticated Profiles]** eller **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

Med [!UICONTROL Device Options] kan du välja vilken typ av *`device profile`* som används av en [!UICONTROL Profile Merge Rule]. En enhetsprofil har skapats från [!UICONTROL traits] som samlats in från anonym surfningsaktivitet. Minst [!UICONTROL profile merge rule] innehåller en [!UICONTROL authenticated option] och en [!UICONTROL device option].

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
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att inte använda de egenskaper som finns i den anonyma profilen för segmentering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Enhetsprofil </span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att använda den anonyma enhetsprofilen för segmentering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Profile Link Device Graph </span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar <span class="keyword"> Audience Manager</span> att läsa profilerna från den aktuella enheten och upp till 100 andra enheter som användaren har autentiserat från. Det här enhetsdiagrammet är baserat på dina egna förstahandsdata i <span class="keyword"> Audience Manager</span>. Det är idealiskt för kunder som har en hög autentiseringsnivå över sina digitala resurser. Enhetsdiagrammet <span class="wintitle"> Profile Link</span> uppdateras i realtid. Det här alternativet är tillgängligt när du väljer <b><span class="uicontrol"> Aktuell autentiserad profil </span></b> eller <b><span class="uicontrol"> Senast autentiserad profil </span></b>. När du använder det här alternativet kan du bara välja en enda autentiserad profil (<span class="keyword"> Audience Manager</span> gör de andra automatiskt gråtonade). Se även <a href="profile-link-use-case.md"> Användningsexempel för profillänksenhetsdiagram </a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Alternativ för enhetsdiagram från tredje part</b> (person och hushåll) </p> </td>
   <td colname="col2"> <p>Med dessa alternativ kan du skapa sammanfogningsregler som baseras på enhetsgraferingsteknik från en tredjepartsleverantör. Ett enhetsdiagram från tredje part innehåller: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Sannolikhetsdata och/eller deterministiska data. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Uppgifter på individ- eller hushållsnivå. </li> 
     </ul> </p> <p>Om du vill använda de här alternativen måste du vara kund till en enhetsdiagram som redan är integrerad med <span class="keyword"> Audience Manager</span>. Kontakta din kontoansvarige om du vill ha mer information eller vill komma igång. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Målgruppssegment som skapades automatiskt från andra [!DNL Experience Cloud]-lösningar, baserat på sammanfogningsregler som definierats utanför [!DNL Audience Manager], markeras som [!UICONTROL External Merge Policy]. Se till exempel [Målgruppsdelning mellan Audience Manager och Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Regler för profilsammanslagning - frågor och svar](../../faq/faq-profile-merge.md)
