---
description: Innan Audience Manager kan aktivera Audience Optimization för utgivare måste du se till att alla krav som beskrivs i den här artikeln uppfylls. Kontakta kundtjänst när du har kontrollerat alla krav.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importera Google Ad Manager-datafiler till Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Importera Google Ad Manager-datafiler (tidigare DFP) till Audience Manager{#import-dfp-data-files-into-audience-manager}

Innan Audience Manager kan aktivera Audience Optimization för utgivare måste du se till att alla krav som beskrivs i den här artikeln uppfylls. Kontakta kundtjänst när du har kontrollerat alla krav.

## Förutsättningar för logginmatning i Google Ad Manager {#prereqs-dfp-ingestion}

Observera att den process som beskrivs i det här avsnittet måste slutföras *innan* du går vidare till förutsättningarna för aktivering av inloggningsinformation.

För att kunna använda loggfiler för [!DNL Google Ad Manager] (tidigare Google DFP) i [!DNL Audience Manager] måste du först ange ditt [Audience Manager-unika användar-ID (UUID)](../../../reference/ids-in-aam.md) i annonstagganropet. På så sätt inkluderas vårt ID i [!DNL Google Ad Manager]-loggarna och vi kan matcha ID:n mellan [!DNL Google Ad Manager] och [!DNL Audience Manager]. Använd [!DNL Audience Manager] [!UICONTROL DIL]-koden eller [!UICONTROL Audience Management Module] för att ange [!DNL Audience Manager] UID i en cookie för första part.

Så här anger du ID:t för [!DNL Audience Manager] i annonstagganropet, vilket förklaras i vår dokumentation:

* [Via Google Publisher-tagg (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via ett cookie-mål](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Du måste ange [!DNL Audience Manager]-ID:t själv och kan arbeta med [!DNL Audience Manager]-konsulter för att kontrollera om allt fungerar. Du har angett [!DNL Audience Manager]-ID korrekt om:

* `'aamid'` är nyckeln som används som identifierare.
* Värdet för användar-ID är korrekt formaterat som [!DNL Audience Manager] UUID, vilket beskrivs i [Index för ID:n i Audience Manager](../../../reference/ids-in-aam.md).
* Du har inkluderat [!DNL Audience Manager]-UUID i ett definierat fält i [!DNL Google Ad Manager]-loggarna (t.ex. CustomTargeting).

## Krav för aktivering av logginmatning {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Steg </th> 
   <th colname="col2" class="entry"> Information </th> 
   <th colname="col3" class="entry"> Ägare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Steg 1 </p> </td> 
   <td colname="col2"> <p>Bekräfta att de nödvändiga stegen för att ange UUID för <span class="keyword"> Audience Manager </span> (se ovan) har slutförts innan du går till steg 2 </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> kundtjänst eller konsulttjänster </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Steg 2 </p> </td> 
   <td colname="col2"> <p>Din Google Ad Manager-administratör skapar: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Ett tjänstkonto för inhämtning av Google Ad Manager loggar in på <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nya autentiseringsuppgifter. <p>Obs! Detta kan kräva en unik e-postadress som är specifik för det här projektet och kommer att användas vid etablering av åtkomst till Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">En privat nyckel (JSON-baserade autentiseringsuppgifter) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Din Google Ad Manager-administratör </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Steg 3 </p> </td> 
   <td colname="col2"> <p>Din Google Ad Manager-administratör beviljar API-åtkomst till tjänstkontot. I det här steget får du tillgång till metadata som identifierar dimensioner (radartiklar, order, kreatörer). <p>Obs! Använd e-poståtkomsten till tjänstkontot som du konfigurerade i steg 2 för att ge behörighet att komma åt API:t. </p> </p> </td> 
   <td colname="col3"> <p>Din Google Ad Manager-administratör </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Steg 4 </p> </td> 
   <td colname="col2"> <p>Din Google Ad Manager-administratör upprättar åtkomst till Google Storage Bucket. Kom ihåg: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Detta kan göras via en Google-grupp. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Associera den unika e-postadressen som tilldelats tjänstkontot med lagringskassetten. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Din Google Ad Manager-administratör </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Steg 5 </p> </td> 
   <td colname="col2"> <p>Din Google Ad Manager-administratör tillhandahåller Google Ad Manager-nätverks-ID. Detta gör att vi kan skicka in nätverks-ID när vi anropar API:t. </p> </td> 
   <td colname="col3"> <p>Din Google Ad Manager-administratör </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Steg 6 </p> </td> 
   <td colname="col2"> <p>Kompilera förutsättningarna och öppna en supportanmälan genom att följa instruktionerna som beskrivs <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">här</a> för att starta loggningsprocessen. </p> </td> 
   <td colname="col3"> <p>Du eller <span class="keyword"> Audience Manager</span> konsulting å dina vägnar </p> </td> 
  </tr> 
 </tbody> 
</table>
