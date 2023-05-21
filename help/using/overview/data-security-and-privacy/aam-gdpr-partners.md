---
description: På den här sidan beskrivs information som tillhandahålls direkt av våra partner allt eftersom den blir tillgänglig, tillsammans med eventuella konsekvenser för Audience Manager. I främsta hand beror dessa uppdateringar på GDPR (General Data Protection Regulation), som trädde i kraft den 25 maj 2018, och IABs nya GDPR-ramverket för öppenhet och samtycke (IAB Framework).
seo-description: This page outlines information provided directly by our partners, as it becomes available, along with any implications related to your Audience Manager practice. Key implications for partners making these updates are the result of GDPR (General Data Protection Regulation), which went into effect on May 25th, 2018 and the new IAB GDPR Transparency & Consent Framework (IAB Framework).
seo-title: GDPR Considerations for Destinations
solution: Audience Manager
title: GDPR-överväganden för destinationer
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: Data Governance & Privacy
exl-id: ff2aa030-94cd-45dc-a9a2-283b38ab5e46
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 96%

---

# GDPR-överväganden för destinationer{#gdpr-considerations-for-destinations}

På den här sidan beskrivs information som tillhandahålls direkt av våra partner allt eftersom den blir tillgänglig, tillsammans med eventuella konsekvenser för Audience Manager. I främsta hand beror dessa uppdateringar på GDPR (General Data Protection Regulation), som trädde i kraft den 25 maj 2018, och IABs nya GDPR-ramverket för öppenhet och samtycke (IAB Framework).

Adobe-partners äger sina affärsprocesser och kan ibland besluta att uppdatera integreringskraven för Audience Manager. Vi arbetar aktivt med vårt partnersystem i Audience Manager för att hålla kunderna informerade om eventuella ändringar.

<!-- ## Audience Manager Partner Updates - ID Syncs {#partner-updates-id-syncs}

Some partners, as listed in the table below, have changed their integration requirements with Audience Manager to include support based on the IAB Framework, in order to comply with GDPR standards.

<table id="table_335A470D4F10434E9CF587089FB54B0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Partner Name </p> </th> 
   <th colname="col2" class="entry"> <p>Expected Impact </p> </th> 
   <th colname="col3" class="entry"> <p>Status of the change </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Yahoo/Oath/DataX </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Live since May 22nd 2018 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trade Desk </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rubicon </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>LiveRamp </p> </td> 
   <td colname="col2"> <p>ID syncs for users in the European Union are dropped by the partner </p> </td> 
   <td colname="col3"> <p>Not live yet </p> </td> 
  </tr> 
 </tbody> 
</table> -->

## Uppdatering av användargränssnittet i Audience Manager - integrering av Yahoo/Oath/DataX {#ui-update}

Förutom uppdateringarna av IAB Framework som nämns ovan har Yahoo/Oath/DataX lagt till nya parametrar, **gdpr** och **gdpr_mode**, i sina API:er för taxonomi och målgrupp. Dessa parametrar informerar Yahoo/Oath/DataX om att de har rätt att bearbeta ett visst segment som personuppgiftsbiträde eller personuppgiftsansvarig. Därför måste Audience Manager-kunder som skickar segment till en Yahoo/Oath/DataX-destination ange lämplig parameter (biträde eller ansvarig) beroende på kundens avtal med Oath.

Kontakta en rådgivare eller kundtjänsten när du ska ange rätt parameter. Adobe kan bara göra uppdateringen åt kunden om vi får ett skriftligt meddelande som begär det. Kontakta en Yahoo/Oath/DataX-representant för mer information om dessa parametrar.
