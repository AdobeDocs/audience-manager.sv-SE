---
description: Med alternativen för sammanfogningsregeln kan du styra vilken typ av data Audience Manager använder för segmentering. En sammanfogningsregel kan innehålla enhetsprofiler som har mappats av enhetsdiagrammet Profile Link och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med Audience Manager. Du kan skapa maximalt fyra regler för profilsammanslagning.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Beskrivning av alternativen för regler för profilsammanslagning
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Alternativ definierade {#profile-merge-rule-options-defined}

The [!UICONTROL profile merge rule] kan du styra datatypen [!DNL Audience Manager] för segmentering. A [!UICONTROL profile merge rule] kan innehålla enhetsprofiler som mappats av [!UICONTROL Profile Link] enhetsdiagram och/eller andra tredjepartsleverantörer av enhetsdiagram som är integrerade med [!DNL Audience Manager]. Du kan skapa maximalt 4 [!UICONTROL Profile Merge Rules]. Den fjärde [!UICONTROL Profile Merge Rule] finns endast för kunder som köpt [!UICONTROL People-Based Destinations] tillägg.

Du bygger en [!UICONTROL Profile Merge Rule] genom att göra ett val bland alternativen som beskrivs nedan, i [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Alternativöversikt {#overview}

[!UICONTROL Profile Merge Rules] möjliggör ett antal kombinationer av regler, som var och en är inriktad på specifika användningsområden. Se tabellen nedan för mer ingående information om när varje regelkombination ska användas.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Tillgänglighet | Utvärderingstyp | [!UICONTROL Audience Lab] Support | Användningsexempel |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alla kunder | Realtid och batch | Ja | [Målinriktning](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Alla kunder | Realtid och batch | Nej | [Utökad målgruppsanpassning för enheter](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alla kunder | Endast i realtid | Nej | [Delad enhetsinriktning](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alla kunder | Realtid och batch | Ja | [Online-/offlinemål](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alla kunder | Realtid och batch | Ja | [Målinriktning på flera enheter](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Alla kunder | Realtid och batch | Nej | [Avancerad målgruppsanpassning mellan enheter](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | Ej tillämpligt | Exklusivt för [Personbaserade mål](../destinations/people-based-destinations-overview.md) kunder | Endast batch | Nej | [Målgruppsanpassning för personbaserade destinationer](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Utvärdering {#segment-evaluation}

Beroende på din [!UICONTROL Profile Merge Rules] konfiguration, [!DNL Audience Manager] kan utföra [!UICONTROL segment] utvärdering i realtid, i batch, eller både och.

* Realtid [!UICONTROL segment] utvärderingen kräver [!DNL DCS] för att se besökarna få tillgång till era digitala resurser i realtid, för att kvalificera sig för [!UICONTROL segment].
* Grupp [!UICONTROL segment] utvärdering utförs mot tidigare kvalificerade [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] som stöder både realtid och batch [!UICONTROL segment] utvärderingen kombinerar besöksaktiviteten i realtid med tidigare kvalificerad [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Svarstid för rapportering {#reporting-latency}

Realtid [!UICONTROL segment] utvärderingen återspeglas omedelbart i [!UICONTROL Profile Merge Rules] rapporter.

Grupp [!UICONTROL segment] kan ta upp till 24 timmar att tänka på i [Regelrapporter för profilsammanslagning](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

The [!UICONTROL Cross-Device Options] gör att du kan välja autentiserade och oautentiserade användare och använda deras enhetsövergripande profil för segmentering. Dessa alternativ hjälper dig att identifiera och nå specifika användare på en delad enhet. Mer information om anonyma och autentiserade användare finns i [Autentiseringstillstånd för besökare i Audience Manager](../../reference/visitor-authentication-states.md).

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
   <td colname="col2"> <p>Teller <span class="keyword"> Audience Manager</span> inte använda data som samlats in från autentiserade användare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuella autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Teller <span class="keyword"> Audience Manager</span> för att läsa och skriva data till den autentiserade profilen om en besökare har loggat in på din webbplats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Senaste autentiserade profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Teller <span class="keyword"> Audience Manager</span> för att läsa data från den autentiserade profilen för den användare som senast loggade in på enheten. </p> <p>När du har valt <span class="keyword"> Audience Manager</span> skriver inte nya egenskapsdata till den autentiserade profilen om användaren är anonym. Vid autentisering skrivs nya trait-data till användarens autentiserade profil. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alla enhetsövergripande profiler</span></b> </p> </td> 
   <td colname="col2"> <p>Uppmanar Audience Manager att läsa data från alla enhetsövergripande profiler, oavsett autentiseringsstatus. Det här alternativet är endast tillgängligt för Audience Manager-kunder som har köpt tillägget Personer-baserade destinationer.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

The [!UICONTROL Cross-Device Profile Options] listor [!UICONTROL cross-device data sources]. Dessa alternativ använder de namn du angav när du skapade en [!UICONTROL cross-device] [!UICONTROL data source] (se [Skapa en datakälla för olika enheter](merge-rules-start.md#create-data-source)). Du kan välja upp till 3 [!UICONTROL cross-device data sources] som ska användas med varje profilregel. The [!UICONTROL Authenticated Profile Options] är tillgängliga när du väljer **[!UICONTROL Current Authenticated Profiles]** eller **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

The [!UICONTROL Device Options] låter dig välja typ av *`device profile`* används av [!UICONTROL Profile Merge Rule]. En enhetsprofil byggs från [!UICONTROL traits] samlas in från anonym surfaktivitet. Minst en [!UICONTROL profile merge rule] innehåller [!UICONTROL authenticated option] och [!UICONTROL device option].

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
   <td colname="col2"> <p>Teller <span class="keyword"> Audience Manager</span> inte använda de egenskaper som ingår i den anonyma profilen för segmentering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Enhetsprofil</span></b> </p> </td> 
   <td colname="col2"> <p>Teller <span class="keyword"> Audience Manager</span> om du vill använda den anonyma enhetsprofilen för segmentering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Enhetsdiagram för profillänk</span></b> </p> </td> 
   <td colname="col2"> <p>Teller <span class="keyword"> Audience Manager</span> för att läsa profilerna från den aktuella enheten och upp till 100 andra enheter som användaren har autentiserat från. Det här enhetsdiagrammet bygger på egna data från första part i <span class="keyword"> Audience Manager</span>. Det är idealiskt för kunder som har en hög autentiseringsnivå över sina digitala resurser. The <span class="wintitle"> Profillänk</span> enhetsdiagram uppdateras i realtid. Det här alternativet är tillgängligt när du väljer <b><span class="uicontrol"> Aktuell autentiserad profil</span></b> eller <b><span class="uicontrol"> Senaste autentiserade profil</span></b>. När du använder det här alternativet kan du bara välja en autentiserad profil (<span class="keyword"> Audience Manager</span> gråtonar ut de andra automatiskt). Se även <a href="profile-link-use-case.md"> Användningsexempel för profillänkens enhetsdiagram</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Alternativ för enhetsdiagram från tredje part</b> (Person och hushåll) </p> </td>
   <td colname="col2"> <p>Med dessa alternativ kan du skapa sammanfogningsregler som baseras på enhetsgraferingsteknik från en tredjepartsleverantör. Ett enhetsdiagram från tredje part innehåller: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Sannolikhetsdata och/eller deterministiska data. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Uppgifter på individ- eller hushållsnivå. </li> 
     </ul> </p> <p>Om du vill använda dessa alternativ måste du vara kund till ett enhetsdiagram som redan är integrerat med <span class="keyword"> Audience Manager</span>. Kontakta din kontoansvarige om du vill ha mer information eller vill komma igång. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

Målgruppssegment som automatiskt skapats från andra [!DNL Experience Cloud] lösningar, baserade på kopplingsregler som definierats utanför [!DNL Audience Manager], markeras som om en [!UICONTROL External Merge Policy]. Se till exempel [Målgruppsdelning mellan Audience Manager och Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Vanliga frågor om regler för profilsammanslagning](../../faq/faq-profile-merge.md)

