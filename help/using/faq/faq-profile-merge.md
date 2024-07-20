---
description: Svar på vanliga frågor om regler för profilsammanslagning och enhetsdiagram.
keywords: Organisations-ID
seo-description: Answers to common Profile Merge Rule and device graph questions.
seo-title: Profile Merge Rules and Device Graph FAQ
solution: Audience Manager
title: Vanliga frågor om regler för profilsammanslagning och enhetsdiagram
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
feature: Profile Merge
exl-id: 03ad79b7-a111-437e-82c5-c7406bd33c39
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1583'
ht-degree: 81%

---

# Vanliga frågor om regler för profilsammanslagning och enhetsdiagram{#profile-merge-rules-and-device-graph-faq}

Svar på vanliga frågor om regler för profilsammanslagning och enhetsdiagram.

<!-- profile-merge-faq.xml -->

## Grunderna i enhetsdiagram {#device-graph-basics}

**Vad är ett enhetsdiagram?**

Ett enhetsdiagram är en uppsättning ID-mappningar som definierar grupper med anonyma enheter. Det kopplar dessa enheter till en person eller ett hushåll baserat på gemensamma element i de signaler som samlas in från varje enhet. Dessa signaler hjälper till att identifiera enheter på individ- eller hushållsnivå.

 

**Vad är ett externt enhetsdiagram?**

Ett externt enhetsdiagram är ett enhetsdiagram i [!DNL Audience Manager] som inte enbart har skapats av era egna enhetsövergripande datakällor. När du t.ex. skapar en [profilkopplingsregel](../features/profile-merge-rules/merge-rules-start.md) och väljer alternativ för enhetsdiagram från tredje part arbetar du med ett externt enhetsdiagram. Se [Enhetsalternativ](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Vilka är några vanliga användningsområden för externa enhetsdiagram i [!UICONTROL Profile Merge Rule]?**

Det främsta målet med att använda ett enhetsdiagram i en [!UICONTROL Profile Merge Rule] är att utvärdera och kvalificera flera enheter som tillhör en enskild person eller ett hushåll för ett visst segment. Själva segmentet kan ha flera användningsområden, till exempel för en målgrupp med potentiella kunder med en annons som betjänas av en DSP eller personalisering av en kunds upplevelse på plats via en personaliseringsplattform på plats. Se [Användningsexempel för externt enhetsdiagram](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Har Audience Manager globalt stöd för externa enhetsdiagram?**

Nej. Externa enhetsdiagram är endast tillgängliga i USA och Kanada.

 

**Hur ofta uppdateras data i externa enhetsdiagram i [!DNL Audience Manager]?**

En gång i veckan.

 

## Enhetsdiagram och sammanfogningsregler för profiler {#device-graph-profile-merge-rules}

**Hur används ett enhetsdiagram i [!DNL Audience Manager]?**

I [!DNL Audience Manager] visas enhetsdiagram som konfigurationsalternativ när du [skapar en regel för profilsammanslagning](../features/profile-merge-rules/merge-rules-start.md). Via [!UICONTROL Profile Merge Rules] kan enhetsdiagram hjälpa [!DNL Audience Manager] att:

* Sammanfoga flera enhetsprofiler. Det skapar en enda överordnad mängd av traits.
* Utvärdera den överordnade mängden med traits för segmentkvalificering (i stället för att utvärdera varje enhetsprofil individuellt).
* Lägga till kvalificerade enheter i tillgängliga segment.

 

**Hur många [!UICONTROL Profile Merge Rules] kan jag skapa?**

För närvarande kan du skapa maximalt 4 [!UICONTROL Profile Merge Rules]. Den fjärde regeln för profilsammanslagning ([!UICONTROL All Cross-Device Profiles]) är bara tillgänglig för kunder som köpt tillägget [!UICONTROL People-Based Destinations].

 

**Hur många enhetsprofiler kan [!DNL Audience Manager] sammanfoga och läsa när ett enhetsdiagram används i en [!UICONTROL Profile Merge Rule]?**

När en enhet kvalificeras för ett segment med en [!UICONTROL Profile Merge Rule], sammanfogar och läser Audience Manager den aktuella enhetsprofilen och maximalt 99 andra enhetsprofiler som är länkade till det valda alternativet för enhetsdiagram.

 

**Vilka enheter kvalificerar för ett segment när ett enhetsdiagram används i en [!UICONTROL Profile Merge Rule]?**

Enheterna som [!DNL Audience Manager] sammanfogar och avläser är samma enheter som är kvalificerade för ett segment.

 

**Var kan [!DNL Audience Manager] skicka segment som har kvalificerats av en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram?**

[!DNL Audience Manager] kan skicka segment till en destination satsvis eller i realtid.

 

## Segment, enhetsdiagram och regler för profilsammanfogning {#segments-device-graphs-rules}

**Hur tas segmenteringen bort i [!DNL Audience Manager] för en enhet när den inte längre kvalificerar för ett segment med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram?**

Audience Manager sammanfogar upp till 100 enheter när segment utvärderas med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram. Om signalen för att ta bort segmentering skickas kommer den aktuella enheten och upp till 99 andra enheter att tas bort från segmentet på destinationen. Mer information om att ta bort segmentering finns i [Regler för profilsammanslagning och Processer för avsegmentering](../features/profile-merge-rules/merge-rule-unsegment.md).

 

**Om en destination kan avsegmentera enheter kommer enheter att tas bort från segment av [!UICONTROL Profile Merge Rules] som använder ett enhetsdiagram?**

Ja. Se förklaringen ovan.

 

**Om jag skapar ett segment med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram och segmentet använder både realtidsdata och registrerade data, kommer mitt segment att uppdateras när registrerade data ändras?**

Ja.

 

**Inkluderar beräknade segmentstorlekar enheter som kvalificerar för ett segment baserat på anslutningar som tillhandahålls av en [!UICONTROL Profile Merge Rule] som använder ett alternativ för enhetsdiagram?**

Nej. Se definitionerna för [!UICONTROL Estimated Real-Time Population] och [!UICONTROL Estimated Total Population] i [Trait- och segmentpopulationsdata i Segment Builder](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**Inkluderar [!UICONTROL Addressable Audiences] enheter som kvalificerar för ett segment baserat på anslutningar som tillhandahålls av en [!UICONTROL Profile Merge Rule] som använder ett alternativ för enhetsdiagram?**

Ja.

 

**Om ett segment använder en [!UICONTROL Profile Merge Rule] med [!UICONTROL No Cross-Device Profile] och de traits som kvalificerar enheter för segmentet endast lagras i den enhetsövergripande profilen kommer den totala populationen för segmentet att vara 0?**

Ja. Audience Manager räknar inte de traits som lagras i den enhetsövergripande profilen i segmentutvärderingen när regeln för profilsammanslagning är inställd på [!UICONTROL No Cross-Device Profile].

 

## Trait Frequency, Device Graphs och Profile Merge Rules {#trait-freq-device-rules}

**Hur beräknar [!DNL Audience Manager] trait-frekvensen med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram?**

Trait-frekvensen definieras av summan av antalet kvalificeringar för ett visst trait på flera enheter. Ta en titt på följande användningsexempel för att förstå detta.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Användningsexempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Villkor</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Enhet A och enhet B är länkade med ett enhetsdiagram. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Du har en <span class="wintitle">regel för profilsammanslagning</span> som använder ett alternativ för enhetsdiagram. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Ett segment (segment 1) består av ett enda trait (trait 1), och trait 1 har frekvensen 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Åtgärder</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> läser och sammanfogar enhetsprofilerna för enhet A och enhet B. Då ser vi följande: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Enhet A har kvalificerat för trait 1 tre gånger. Den har frekvensen 3 för trait 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Enhet B har kvalificerat för trait 1 fem gånger. Den har frekvensen 5 för trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultat</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> lägger ihop frekvensen för trait 1 och använder 8 (3 + 5 = 8) för att bestämma segmentkvalificeringen. Enhet A och enhet B kvalificerar för segment 1 eftersom de har frekvensen 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapporter, enhetsdiagram och regler för profilsammanslagning {#reports-device-graphs-rules}

**Kan jag se hur många enheter som kan nås av en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram?**

Ja. Rapporterna returnerar data på [!UICONTROL Profile Merge Rule]-nivån. Rapportdata uppdateras dagligen. Data baseras på de enheter som visas i ditt konto, inte på de som länkas av ett enhetsdiagram. Se [Rapportmätvärden för regler för profilsammanslagning](../features/profile-merge-rules/profile-link-metrics.md).

 

**Kan jag se hur många enheter som kvalificerat för ett visst segment i *realtid* med en [!UICONTROL Profile Merge Rules] som använder ett enhetsdiagram?**

Ja. Populationsmåtten i realtid fångar upp segmentkvalificering för den aktuella enheten (enheten som visas i realtid) med profilerna från alla enheter som är länkade till ett enhetsdiagram.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element i användningsexempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Villkor</b> </p> </td> 
   <td colname="col2"> <p>Anta att vi har: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 som bygger på följande traits och kvalificeringslogik: Segment 1 = Trait A och trait B och trait C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 enhetsprofiler: Enhet 1 (aktuell enhet), enhet 2 (enhetsdiagram), enhet 3 (enhetsdiagram). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Åtgärder</b> </p> </td> 
   <td colname="col2"> <p>Alla tillgängliga traits är kopplade till en enhet: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Enhet 1: Trait A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Enhet 2: Trait B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Enhet 3: Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultat</b> </p> </td> 
   <td colname="col2"> <p>Med tanke på de föregående elementen är den totala populationen för segment 1 en. </p> <p>I det här fallet använder <span class="wintitle">regeln för profilsammanslagning</span> alla enheter och deras traits för att avgöra segmentkvalificeringen. Det innebär att enhet 1, 2 och 3 kvalificerar för Segment 1, men att det bara är enhet 1 som ingår i segmentpopulationen i realtid. Det beror på: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Enhet 1 är den enhet som för närvarande interagerar med Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) i realtid. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Enhet 2 och 3 är kopplade till enhet 1 av ett enhetsdiagram, men de interagerar inte med DCS samtidigt som enhet 1. </li> 
     </ul> </p> <p>Därför ingår inte enhet 2 och 3 i populationsmåtten för segmentet i realtid. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Kan jag se det totala antalet enheter som är kvalificerade för ett specifikt segment med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram?**

Ja. Segmentets totala populationsmått omfattar andra enheter som har kvalificerat för ett segment baserat på anslutningarna från ett enhetsdiagram.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element i användningsexempel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Villkor</b> </p> </td> 
   <td colname="col2"> <p>Anta att vi har: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 som bygger på följande traits och kvalificeringslogik: Segment 1 = Trait A och trait B och trait C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 enhetsprofiler: Enhet 1 (aktuell enhet), enhet 2 (enhetsdiagram), enhet 3 (enhetsdiagram). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associationer</b> </p> </td> 
   <td colname="col2"> <p>Alla tillgängliga traits är kopplade till en enhet: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Enhet 1: Trait A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Enhet 2: Trait B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Enhet 3: Trait C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultat</b> </p> </td> 
   <td colname="col2"> <p>Med tanke på de föregående elementen är den totala populationen för segment 1 tre (3). </p> <p>I det här fallet använder <span class="wintitle">regeln för profilsammanslagning</span> alla enheter och deras traits för att avgöra segmentkvalificeringen. Det innebär att enhet 1, 2 och 3 kvalificerar för Segment 1 och alla tre ingår i den totala populationen. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Inkluderas enheter som kvalificerar för ett segment med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram i [!UICONTROL Interactive]-rapporter, [!UICONTROL Overlap]-rapporter och [!UICONTROL Audience Optimization]-rapporter?**

Nej.

**Varför ser jag ingen segmentpopulation för segmentexport till Adobe Campaign efter 16 mars 2020?**

I slutet av 2019 har vi släppt en serie förbättringar av reglerna för profilsammanslagning för att förbättra exaktheten hos gruppfiler som genererats med hjälp av enhets-ID:n. Dessa förbättringar respekteras strikt i din Audience Manager-instans från och med måndagen den 16 mars 2020. Därför kommer segment som mappas till ett mål med hjälp av enhets-ID att sluta producera exporter i vissa konfigurationer av profilkopplingsregler.

Kontrollera att du uppfyller följande krav för att se till att Audience Manager-instansen och destinationerna är korrekt integrerade med olika enhets-ID, t.ex. Adobe Campaign:

1. Granska den profilkopplingsregel som används av de segment som är mappade till ditt Adobe Campaign-deklarerade ID-mål. Regeln för profilsammanslagning måste använda alternativet [!UICONTROL Last Authenticated Profile], så alla autentiserade profiler kan inkluderas i exporten. Om din profilkopplingsregel använder ett annat alternativ växlar du till [!UICONTROL Last Authenticated Profile].
2. Markera datakällan för det deklarerade Adobe Campaign-ID:t i inställningarna för profilkopplingsregeln.

>[!NOTE]
>
> Vi har ökat gränsen för profilsammanfogningsregel med 1 för kunder som befinner sig i den här situationen, så att du kan skapa en dedikerad profilsammanfogningsregel för de segment som är mappade till Adobe Campaign deklarerade ID-mål, utan att ändra reglerna för profilsammanfogning för andra användningsfall.

>[!MORELIKETHIS]
>
>* [Profillänk](../features/profile-merge-rules/profile-link-use-case.md)
