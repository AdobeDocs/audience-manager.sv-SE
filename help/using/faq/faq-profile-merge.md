---
description: Svar på vanliga frågor om profilkopplingsregel och enhetsdiagram.
keywords: Organization ID
seo-description: Svar på vanliga frågor om profilkopplingsregel och enhetsdiagram.
seo-title: Vanliga frågor om regler för profilsammanslagning och enhetsdiagram
solution: Audience Manager
title: Vanliga frågor om regler för profilsammanslagning och enhetsdiagram
uuid: ba7986f1-078f-4162-aef3-b5c8740cebf4
translation-type: tm+mt
source-git-commit: 56a9626b1fa77926bdc31ef72b058d2aa9b58f43
workflow-type: tm+mt
source-wordcount: '1545'
ht-degree: 0%

---


# Vanliga frågor om regler för profilsammanslagning och enhetsdiagram{#profile-merge-rules-and-device-graph-faq}

Svar på vanliga frågor om profilkopplingsregel och enhetsdiagram.

<!-- profile-merge-faq.xml -->

## Grunderna i enhetsdiagram {#device-graph-basics}

**Vad är ett enhetsdiagram?**

Ett enhetsdiagram är en uppsättning ID-mappningar som definierar grupper med anonyma enheter. Den kopplar dessa enheter till en person eller ett hushåll baserat på gemensamma element i de signaler som samlas in från varje enhet. Dessa signaler hjälper till att identifiera enheter på individ- eller hushållsnivå.

 

**Vad är ett externt enhetsdiagram?**

Ett externt enhetsdiagram är ett enhetsdiagram [!DNL Audience Manager] som inte har skapats exklusivt från dina egna datakällor för olika enheter. När du t.ex. skapar en [profilkopplingsregel](../features/profile-merge-rules/merge-rules-start.md) och väljer alternativ för enhetsdiagram [!UICONTROL Co-op Device Graph] eller enhetsdiagram från tredje part, arbetar du med ett externt enhetsdiagram. Se [Enhetsalternativ](../features/profile-merge-rules/merge-rule-definitions.md#device-options).

 

**Vilka är några vanliga användningsområden för ett externt enhetsdiagram i en[!UICONTROL Profile Merge Rule]?**

Det främsta målet med att använda en enhetsgraf i en [!UICONTROL Profile Merge Rule] är att utvärdera och kvalificera flera enheter som tillhör en enskild person eller ett hushåll för ett visst segment. Själva segmentet kan ha flera användningsområden, till exempel för en målgrupp med potentiella kunder med en annons som hanteras av en DSP eller för att personalisera en kunds upplevelse på plats via en personaliseringsplattform på plats. See [External Device Graph Use Cases](../features/profile-merge-rules/external-graph-use-cases.md).

 

**Har Audience Manager globalt stöd för externa enhetsdiagram?**

Nej. Externa enhetsdiagram är endast tillgängliga i USA och Kanada.

 

**Hur ofta uppdateras data i externa enhetsdiagram?[!DNL Audience Manager]**

En gång i veckan.

 

## Enhetsdiagram och sammanfogningsregler för profiler {#device-graph-profile-merge-rules}

**Hur[!DNL Audience Manager]använder jag ett enhetsdiagram?**

I [!DNL Audience Manager]visas enhetsdiagram som konfigurationsalternativ när du [skapar en profilkopplingsregel](../features/profile-merge-rules/merge-rules-start.md). Med hjälp av dina [!UICONTROL Profile Merge Rules]enhetsdiagram kan du [!DNL Audience Manager]göra följande:

* Sammanfoga flera enhetsprofiler. Detta skapar en enda supermängd av egenskaper.
* Utvärdera den anpassade profilen för segmentkvalificering (i stället för att utvärdera varje enhetsprofil individuellt).
* Lägg till kvalificerade enheter i tillgängliga segment.

 

**Hur många[!UICONTROL Profile Merge Rules]kan jag skapa?**

För närvarande kan du skapa maximalt 4 [!UICONTROL Profile Merge Rules]. Den fjärde profilkopplingsregeln ([!UICONTROL All Cross-Device Profiles]) är bara tillgänglig för kunder som köper [!UICONTROL People-Based Destinations] tillägget.

 

**Hur många enhetsprofiler[!DNL Audience Manager]sammanfogas och läses när ett enhetsdiagram används i ett[!UICONTROL Profile Merge Rule]?**

När du kvalificerar en enhet för ett segment med hjälp av en [!UICONTROL Profile Merge Rule], sammanfogar och läser Audience Manager den aktuella enhetsprofilen och maximalt 99 andra enhetsprofiler som är länkade med det valda alternativet för enhetsdiagram.

 

**Vilka enheter kvalificerar sig för ett segment när du använder ett enhetsdiagram i ett[!UICONTROL Profile Merge Rule]?**

Enheterna [!DNL Audience Manager] sammanfogas och läses av samma enheter som är kvalificerade för ett segment.

 

**Var kan[!DNL Audience Manager]skicka segment som har kvalificerats av en[!UICONTROL Profile Merge Rule]som använder ett enhetsdiagram?**

[!DNL Audience Manager] kan skicka segment till ett mål i gruppfiler eller i realtid.

 

## Segment, enhetsdiagram och regler för profilsammanfogning {#segments-device-graphs-rules}

**Hur bryter du segmenteringen av en enhet när den inte längre är kvalificerad för ett segment med en[!DNL Audience Manager][!UICONTROL Profile Merge Rule]enhetsgraf?**

Audience Manager sammanfogar upp till 100 enheter vid utvärdering av segment med en [!UICONTROL Profile Merge Rule] som använder ett enhetsdiagram. Om signalen för att dela upp segment utfärdas kommer den aktuella enheten och upp till 99 ytterligare enheter att tas bort från segmentet i målenheten. Mer information om icke-segmentering finns i [Profilsammanfogningsregler och Avsegmenteringsprocesser](../features/profile-merge-rules/merge-rule-unsegment.md)för enheter.

 

**Om en destination kan dela upp segment i enheter, kommer enheter att tas bort från segment av[!UICONTROL Profile Merge Rules]dem som använder ett enhetsdiagram?**

Ja. Se förklaringen ovan.

 

**Om jag skapar ett segment med ett[!UICONTROL Profile Merge Rule]enhetsdiagram och segmentet använder både realtidsdata och inbyggda data, kommer mitt segment att uppdateras när de inbyggda data ändras?**

Ja.

 

**Omfattar uppskattningar av segmentstorlek enheter som kvalificerar sig för ett segment baserat på anslutningar som tillhandahålls av en enhet[!UICONTROL Profile Merge Rule]som använder ett alternativ för enhetsdiagram?**

Nej. Se definitionerna för [!UICONTROL Estimated Real-Time Population] och [!UICONTROL Estimated Total Population] i [Trait and Segment Population Data i Segment Builder](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/segments/segment-builder-data.html).

 

**Inkluderar[!UICONTROL Addressable Audiences]enheter som kvalificerar sig för ett segment baserat på anslutningar från en enhet[!UICONTROL Profile Merge Rule]som använder ett enhetsdiagramalternativ?**

Ja.

 

**Om ett segment använder en[!UICONTROL Profile Merge Rule]med[!UICONTROL No Cross-Device Profile]och de egenskaper som kvalificerar enheter för segmentet endast lagras i profilen för olika enheter, kommer segmentets totala population att vara 0?**

Ja. Audience Manager räknar inte de egenskaper som lagras i profilen för olika enheter i segmentutvärderingen när profilkopplingsregeln är inställd på [!UICONTROL No Cross-Device Profile].

 

## Trait Frequency, Device Graphs och Profile Merge Rules {#trait-freq-device-rules}

**Hur beräknas trait-frekvensen med en[!DNL Audience Manager][!UICONTROL Profile Merge Rule]som använder ett enhetsdiagram?**

Tågfrekvensen definieras av summan av antalet kvalifikationer för en viss egenskap över flera enheter. Ta en titt på följande användningsexempel för att få en förståelse för detta.

<table id="table_DE7A308705C84B93B3089CAD2228569E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Användningsfall </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Villkor</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_52EA0F142E3F488CAAC7CF541E7F3472"> 
      <li id="li_11228EC0266A4A02BB4057B77FE93A8A">Enhet A och Enhet B är länkade med ett enhetsdiagram. </li> 
      <li id="li_EB90B9D0D3F64A15AB24DA5D000EEBA5">Du har en <span class="wintitle"> profilkopplingsregel</span> som använder ett alternativ för enhetsdiagram. </li> 
      <li id="li_B46C4DE6CBD44D44B0F02EC9987140A5">Ett enskilt segment (segment 1) som består av ett enda drag (spår 1), där Trait 1 har frekvensen 8. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Åtgärder</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> läser och sammanfogar enhetsprofilerna för Device A och Device B. Här ser vi följande: </p> <p> 
     <ul id="ul_7AB307154C034695B4486E68D55CB084"> 
      <li id="li_5760BEE513C94152AA307AEE10894718">Enhet A har kvalificerat för Trait 1 tre gånger. Den har frekvensen 3 för Trait 1. </li> 
      <li id="li_E20BC24CCCEC407C820A8032D56BC3F0">Enhet B har kvalificerat för Trait 1 fem gånger. Den har frekvensen 5 för Trait 1. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultat</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager</span> summerar frekvensen för Trait 1 och använder 8 (3 + 5 = 8) för att bestämma segmentkvalificeringen. Enhet A och enhet B kvalificerar för segment 1 eftersom den har frekvensen 8. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

## Rapporter, enhetsdiagram och regler för profilsammanslagning {#reports-device-graphs-rules}

**Kan jag se hur många enheter som kan nås av en enhet[!UICONTROL Profile Merge Rule]som använder ett enhetsdiagram?**

Ja. Rapporterna returnerar data på [!UICONTROL Profile Merge Rule] nivån. Rapportdata uppdateras dagligen. Data baseras på de enheter som visas i ditt konto, inte på dem som länkas av ett enhetsdiagram. Se [Rapportera mått för profilkopplingsregler](../features/profile-merge-rules/profile-link-metrics.md).

 

**Kan jag se hur många enheter som är kvalificerade för ett visst segment i *realtid*med[!UICONTROL Profile Merge Rules]ett enhetsdiagram?**

Ja. Populationsmåtten för realtid fångar upp segmentens kvalifikationer för den aktuella enheten (enheten visas i realtid) med hjälp av profilerna från alla enheter som är länkade till ett enhetsdiagram.

<table id="table_D37A51E99B314C04A96A084491A5FEC7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Använd skiftlägeselement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Villkor</b> </p> </td> 
   <td colname="col2"> <p>Anta att vi har: </p> <p> 
     <ul id="ul_B8B627FBF6A04C0CAE6C8543EA3EA56D"> 
      <li id="li_2557CE3F109C42DC8CB5E99B93E96265">Segment 1 bygger på följande egenskaper och kvalificeringslogik: Segment 1 = Trait A och Trait B och Trait C. </li> 
      <li id="li_F7D559B3C0CA424DA2C1A0703C1E1717">3 enhetsprofiler: Enhet 1 (aktuell enhet), Enhet 2 (enhetsdiagram), Enhet 3 (enhetsdiagram). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Åtgärder</b> </p> </td> 
   <td colname="col2"> <p>Alla tillgängliga egenskaper är kopplade till en enhet: </p> <p> 
     <ul id="ul_E60A5CBBEC484BB78F2A4AB0D6306019"> 
      <li id="li_26D7300BA0164426949FA43A60AC7023">Enhet 1: Trait A </li> 
      <li id="li_B0C3D7ACC7754ED985974317362AFF85">Enhet 2: Fack B </li> 
      <li id="li_32C32DD0E87F461AA2C7FB77FB35C6DA">Enhet 3: Fack C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultat</b> </p> </td> 
   <td colname="col2"> <p>Med tanke på de föregående elementen är den totala populationen för segment 1 en. </p> <p>I det här fallet används alla enheter och deras egenskaper för att avgöra <span class="wintitle"> segmentkvalificeringen i profilkopplingsregeln</span> . Det innebär att Enheter 1, 2 och 3 kvalificerar sig för Segment 1, men, som det sägs ovan, är det bara Device 1 som ingår i segmentpopulationen i realtid. Detta beror på: </p> <p> 
     <ul id="ul_5958E1A0E1514B6BA31DF5551401AF38"> 
      <li id="li_E4F68B12ED944416ACBEAF7BF61CA4E7">Enhet 1 är den enhet som för närvarande interagerar med Audience Manager <span class="wintitle"> Data Collection Servers</span> (<span class="wintitle"> DCS</span>) i realtid. </li> 
      <li id="li_57165E96289F4E20BF2244BC68B90BA3">Enheter 2 och 3 är kopplade till Device 1 av ett enhetsdiagram, men de interagerar inte med DCS samtidigt som Device 1. </li> 
     </ul> </p> <p>Därför ingår inte enheterna 2 och 3 i populationsmätningen för realtidssegment. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Kan jag se det totala antalet enheter som är kvalificerade för ett specifikt segment med ett enhetsdiagram[!UICONTROL Profile Merge Rule]?**

Ja. Det totala segmentets populationsmått omfattar de ytterligare enheter som har kvalificerat sig för ett segment baserat på anslutningarna från ett enhetsdiagram.

<table id="table_932E61B1D4374DD58F673C3B35C365EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Använd skiftlägeselement </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Villkor</b> </p> </td> 
   <td colname="col2"> <p>Anta att vi har: </p> <p> 
     <ul id="ul_DC0AC0F79323451C8C2480E4A85AE2EB"> 
      <li id="li_790F24FA1F0747F385640EDB1AE9E59E">Segment 1 bygger på följande egenskaper och kvalificeringslogik: Segment 1 = Trait A och Trait B och Trait C. </li> 
      <li id="li_6628727DDD0644BF8F5B6A8A9FA71E67">3 enhetsprofiler: Enhet 1 (aktuell enhet), Enhet 2 (enhetsdiagram), Enhet 3 (enhetsdiagram). </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Associationer</b> </p> </td> 
   <td colname="col2"> <p>Alla tillgängliga egenskaper är kopplade till en enhet: </p> <p> 
     <ul id="ul_FE16B1639D2541009110E77A605D2CE0"> 
      <li id="li_25959C3822384CFAB8B18D3CD80A30DD">Enhet 1: Trait A </li> 
      <li id="li_CDAC38F4CF3A4BEDA49A92BAEC48583E">Enhet 2: Fack B </li> 
      <li id="li_6063A91C482E48FD9FC5C00600B05E31">Enhet 3: Fack C </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Resultat</b> </p> </td> 
   <td colname="col2"> <p>Med hänsyn till de föregående elementen är den totala populationen för segment 1 tre (3). </p> <p>I det här fallet används alla enheter och deras egenskaper för att avgöra <span class="wintitle"> segmentkvalificeringen i profilkopplingsregeln</span> . Detta innebär att Enheter 1, 2 och 3 kvalificerar sig för Segment 1 och alla tre ingår i den totala populationen. </p> </td> 
  </tr> 
 </tbody> 
</table>

 

**Finns det enheter som är kvalificerade för ett segment med ett enhetsdiagram[!UICONTROL Profile Merge Rule]som ingår i[!UICONTROL Interactive]rapporter,[!UICONTROL Overlap]rapporter och[!UICONTROL Audience Optimization]rapporter?**

Nej.

**Varför visas min segmentexport till Adobe Campaign som 0 efter den 16 mars 2020?**

I slutet av 2019 har vi släppt en serie förbättringar av reglerna för profilsammanslagning för att förbättra exaktheten hos gruppfiler som genererats med hjälp av enhets-ID:n. Dessa förbättringar respekteras strikt i Audience Manager-instansen från och med måndagen den 16 mars 2020. Därför kommer segment som mappas till ett mål med hjälp av enhets-ID att sluta producera exporter i vissa konfigurationer av profilkopplingsregler.

För att säkerställa korrekt integrering mellan Audience Manager-instansen och destinationerna med olika enhets-ID:n, som Adobe Campaign, måste du uppfylla följande krav:

1. Granska den profilkopplingsregel som används av de segment som är mappade till ditt deklarerade ID-mål för Adobe Campaign. Regeln för profilsammanfogning måste använda [!UICONTROL Last Authenticated Profile] alternativet så att alla autentiserade profiler kan inkluderas i exporten. Om du använder ett annat alternativ för profilkopplingsregeln växlar du till [!UICONTROL Last Authenticated Profile].
2. Välj datakällan för deklarerat ID i Adobe Campaign i inställningarna för profilkopplingsregel.

>[!NOTE]
>
> Vi har ökat gränsen för profilsammanfogningsregel med 1 för kunder som befinner sig i den här situationen, så att du kan skapa en dedikerad profilsammanfogningsregel för de segment som mappas till det deklarerade ID-målet för Adobe Campaign, utan att ändra reglerna för profilsammanfogning för andra användningsfall.

>[!MORELIKETHIS]
>
>* [Profillänk](../features/profile-merge-rules/profile-link-use-case.md)

