---
description: Med alternativen för regler för profilsammanslagning kan ni utöka eller öka målgruppernas fokus på specifika målgrupper baserat på verksamhetens behov eller mål. De här allmänna användningsexemplen utforskar hur du använder tillgängliga alternativ och skapar kopplingsregler för målinriktning individuellt, för hushåll och på olika enheter.
seo-description: Profile Merge Rules options let you expand or tighten audience focus on specific audiences based on business needs or goals. These general use cases explore how to use available options and create merge rules for individual, household, and cross-device targeting.
seo-title: General Use Cases for Profile Merge Rules
solution: Audience Manager
title: Allmänna användningsexempel för profilkopplingsregler
uuid: c9eb41c8-fe19-45f8-9ff1-552c11ef08da
feature: Profile Merge
exl-id: 66341736-4f61-4306-b9f4-1b37dc7ce0ff
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '894'
ht-degree: 1%

---

# Allmänna användningsexempel för profilkopplingsregler {#general-use-cases-for-profile-merge-rules}

Med alternativen för [!UICONTROL Profile Merge Rules] kan du utöka eller öka målgruppens fokus på specifika målgrupper baserat på affärsbehov eller verksamhetsmål. De här allmänna användningsexemplen utforskar hur du använder tillgängliga alternativ och skapar kopplingsregler för målinriktning individuellt, för hushåll och på olika enheter. [!UICONTROL Profile Merge Rules] arbetar med mål i realtid och batchvis.

>[!TIP]
>
>Definitioner och beskrivningar av de här [!UICONTROL Merge Rule] inställningarna finns i [Alternativ för profilkopplingsregel definierade](merge-rule-definitions.md).

## Målinriktning {#device-personalization}

Detta scenario gäller för marknadsförare som vill utvärdera en enda enhetsprofil för ett målgruppssegment som definieras i Audience Manager, för att leverera en enhetlig upplevelse till enheten med målplattformar som stöder enhets-ID (DSP, platspersonaliseringsplattformar och andra enhetsbaserade målinriktningsplattformar) utan att ta hänsyn till användarautentisering.

Om du vill skapa en regel som endast har enhetsprofiler som mål väljer du **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]**.

![endast enhet](assets/device-only.png)

Låt oss säga att John äger tre smarttelefoner. Två av dem är iPhone 7s i dataabonnemang A, och en av dem är Samsung i dataabonnemang B. John&#39;s mobiloperatör vill inte ta hänsyn till sin autentiserade status på någon av de tre enheterna, utan bara erbjuda honom en uppgradering av en dataplan, utan bara för iPhone 7-enheter som kan köras med Data Plan A.

Genom att använda regeln **[!UICONTROL No Cross-Device Profile]** + **[!UICONTROL Device Profile]** kvalificerar [!DNL Device 1] och [!DNL Device 3] båda för segmentet, medan Device 2 ignoreras.

![endast enhet](assets/device-management.png)

## Delad enhetsinriktning {#target-shared-devices}

Säg att John och hans fru Jane använder samma bärbara dator för att besöka en webbutik och beställa olika artiklar.

John använder sitt eget konto för att boka resebiljetter och specialerbjudanden, medan Jane använder sitt eget konto för att handla musik och filmer.

Butikens marknadsföringsteam kan använda regeln **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** för att rikta sig till John och Jane med specifika avtal, baserat enbart på deras autentiserade aktivitet.

![current-no-device](assets/current-no-device.png)

Genom att använda den här regeln ignorerar Audience Manager helt enhetsprofilen, kvalificerar Johns CRM-ID för segmentet och kvalificerar inte Jane CRM-ID.

![shared-device-targeting](assets/shared-device-targeting.png)

## Online-/offlinemål {#device-household-targeting}

Detta användningsfall omfattar identitetshantering för hushåll. Ett företag kan sammanfoga en enskild enhetsprofil med den senaste profilen som autentiserats på den enheten med hjälp av regeln **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Device Profile]**.

![last-device-profile](assets/last-device-profile.png)

Låt oss titta på ett segment som består av hushåll med inkomster över 100 000 USD/år, som innehåller minst en enhet som är en [!DNL iPhone 7] på [!DNL Data Plan B]. Vi har två profiler för hemmabruk (profiler som fungerar på olika enheter), var och en anslutna till två olika enhetsprofiler. De egenskaper som krävs för att kvalificera sig för segmentet fördelas över enhets- och enhetsprofilerna.

Audience Manager sammanfogar alla enheter + profilpar för olika enheter för att se om den sammanfogade uppsättningen egenskaper kvalificerar sig för segmentet. Eftersom Audience Manager utvärderar alla profiler som ingick i sammanslagningen kan både en enhetsprofil och en hushållsprofil segmenteras.

Med länken mellan enheten och hushållsprofilen kan Audience Manager kvalificera [!DNL Household 2] för segmentet, men inte [!DNL Household 1]. Från [!DNL Household 2] är det bara [!DNL Device 3] som kvalificerar för segmentet. Detta [!UICONTROL Profile Merge Rule] har gjort det möjligt för marknadsföraren att leverera ett konsekvent marknadsföringsmeddelande till en enskild enhet ([!DNL Device 3]) och ett större hushåll ([!DNL Household 2]).

![Hushållshantering](assets/household-management.png)

## Målgruppsanpassning för personbaserade destinationer {#all-cross-device}

>[!IMPORTANT]
>
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

Det här målscenariot är bara tillgängligt för kunder som har köpt tillägget [!DNL People-Based Destinations]. Med den här regeln kan marknadsförarna nå kunder utifrån sina egna autentiserade data.

En webbutik vill nå befintliga kunder via sociala plattformar och visa dem personaliserade erbjudanden baserat på deras tidigare order. Med [!UICONTROL People-Based Destinations] kan de importera hashade e-postadresser från sina egna [!DNL CRM] till Audience Manager, skapa segment från offlinedata och skicka dessa segment till de sociala plattformar som de vill annonsera på, med hjälp av den hashade identifieraren, vilket optimerar deras annonsutgifter.

Mer information om det här alternativet finns i [Personbaserade mål](../destinations/people-based-destinations-overview.md).

![all-cross-device](assets/all-cross-device.png)

## Alternativ för enhetsdiagram {#device-graph-options}

Om du väljer ett [!UICONTROL device graph]-alternativ för en [!UICONTROL Profile Merge]-regel beror på villkor som är unika för dina digitala egenskaper och affärsmål. Dessa allmänna riktlinjer kan hjälpa dig att förstå när du ska använda en typ av diagram jämfört med en annan. Observera att du måste ha ett avtalsförhållande med ett externt enhetsdiagram för att kunna använda dessa alternativ. Se tabellen nedan för allmänna riktlinjer om när du ska välja ett alternativ för enhetsdiagram. Specifika användningsexempel finns i [Användningsexempel för länkad enhetsgrafik](profile-link-use-case.md) och [Användningsexempel för extern enhetsgrafik](external-graph-use-cases.md).

<table id="table_66D9152D4FF040A186003272D456625D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Typ av enhetsdiagram </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profile Link Device Graph </span> </p> </td> 
   <td colname="col2"> <p><span class="wintitle">-profilsammanfogningsregler</span> som skapats med alternativet <span class="wintitle"> Profillänk </span> är idealiska för: </p> <p> 
     <ul id="ul_FF44FA894BB2448887C8EDA9C8407EF9"> 
      <li id="li_E22505210C664FE6A9AA7C61244B36DA">Digitala egenskaper som har en hög nivå av kundautentisering. </li> 
      <li id="li_BE7112EE611E4DEB95B5C0A2852BFA97">Fokuserade kampanjer med låg räckvidd. Enhetsdiagrammet <span class="wintitle"> Profile Link</span> är baserat på deterministiska data. Den här poolen med enhetsprofiler är alltid mindre i förhållande till poolen med oautentiserade användare och enheter. </li> 
      <li id="li_5FD9E936A72A4EFE80E694FA2E08E385">Använd fall där kunderna måste vara i ett autentiserat tillstånd för att vara kvalificerade för segmentering. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alternativ för externt enhetsdiagram </p> </td> 
   <td colname="col2"> <p><span class="wintitle">-profilsammanfogningsregler</span> som har skapats med externa enhetsdiagram som är integrerade med <span class="keyword"> Audience Manager </span> är idealiska för: </p> <p> 
     <ul id="ul_D76D773988604A619FA4A3BF37F910F0"> 
      <li id="li_969A0755A9E34CBEB2F7331C137B9A26">Digitala egenskaper som har låg nivå av kundautentisering. </li> 
      <li id="li_AC78C8B4AD5340FFAC44FE851096C6A6">Breda, heltäckande varumärkeskampanjer. </li> 
      <li id="li_14AEC54CE34440889A3A36324EC6F497">Användningsexempel där kunderna inte behöver vara i ett autentiserat tillstånd för att vara kvalificerade för segmentering. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

I videon nedan visas en översikt över möjliga användningsfall för [!UICONTROL Profile Merge Rules].

>[!VIDEO](https://video.tv.adobe.com/v/28975/)

>[!MORELIKETHIS]
>
>* [Användningsexempel för enhetsdiagram för profillänk](profile-link-use-case.md)
>* [Användningsexempel för externt enhetsdiagram](external-graph-use-cases.md)
>* [Regler för profilsammanslagning - frågor och svar](../../faq/faq-profile-merge.md)
