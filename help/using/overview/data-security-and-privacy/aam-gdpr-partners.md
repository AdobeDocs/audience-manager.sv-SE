---
description: På den här sidan finns information som våra partners lämnar direkt, allt eftersom den blir tillgänglig, tillsammans med eventuella konsekvenser för er praxis i Audience Manager. De viktigaste konsekvenserna för partner som gör dessa uppdateringar är resultatet av GDPR (General Data Protection Regulation), som trädde i kraft den 25 maj 2018, och den nya IAB GDPR-ramen för öppenhet och samtycke (IAB Framework).
seo-description: På den här sidan finns information som våra partners lämnar direkt, allt eftersom den blir tillgänglig, tillsammans med eventuella konsekvenser för er praxis i Audience Manager. De viktigaste konsekvenserna för partner som gör dessa uppdateringar är resultatet av GDPR (General Data Protection Regulation), som trädde i kraft den 25 maj 2018, och den nya IAB GDPR-ramen för öppenhet och samtycke (IAB Framework).
seo-title: GDPR-överväganden för destinationer
solution: Audience Manager
title: GDPR-överväganden för destinationer
uuid: e8a40060-086c-4f03-b48c-9c903acb7891
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 0%

---


# GDPR-överväganden för destinationer{#gdpr-considerations-for-destinations}

På den här sidan finns information som våra partners lämnar direkt, allt eftersom den blir tillgänglig, tillsammans med eventuella konsekvenser för er praxis i Audience Manager. De viktigaste konsekvenserna för partner som gör dessa uppdateringar är resultatet av GDPR (General Data Protection Regulation), som trädde i kraft den 25 maj 2018, och den nya IAB GDPR-ramen för öppenhet och samtycke (IAB Framework).

Adobe-partners äger sina affärsprocesser och kan besluta att uppdatera integrationskraven med Audience Manager då och då. Vi arbetar aktivt med vårt partnerekosystem i Audience Manager för att hålla våra kunder informerade om förändringar.

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

Förutom uppdateringarna av IAB Framework som nämns ovan har Yahoo/Oath/DataX lagt till nya parametrar, **gdpr** och **gdpr_mode**, i sina API:er för taxonomi och Audience. Deras parametrar informerar Yahoo/Oath/DataX om att de har behörighet att bearbeta ett visst segment som en dataprocessor eller som en Data Controller. Därför måste Audience Manager-kunder som skickar segment till ett Yahoo/Oath/DataX-mål ange lämplig parameter (processor eller styrenhet) utifrån deras avtal med Oath.

Kontakta din konsult eller kundtjänst för att ställa in rätt parameter. Adobe kan inte göra denna uppdatering för en kunds räkning om vi inte får skriftlig korrespondens som begär denna uppdatering. Kontakta din Yahoo/Oath/DataX-representant för att få en förståelse för den fullständiga definitionen av dessa parametrar.
