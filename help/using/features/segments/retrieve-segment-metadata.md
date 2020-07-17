---
description: När Audience Manager skickar segmentinformation till en datapartner identifieras dessa objekt med numeriska ID:n. När du som datapartner delar informationen med dina kunder (eller arbetar med den själv) ger ett faktiskt namn och en beskrivning en bättre upplevelse för kunderna i rapporter, instrumentpaneler eller andra användargränssnitt. Data partners kan göra dessa egna namn tillgängliga för sina kunder med antingen de manuella eller automatiserade metoder som beskrivs i detta avsnitt.
seo-description: När Audience Manager skickar segmentinformation till en datapartner identifieras dessa objekt med numeriska ID:n. När du som datapartner delar informationen med dina kunder (eller arbetar med den själv) ger ett faktiskt namn och en beskrivning en bättre upplevelse för kunderna i rapporter, instrumentpaneler eller andra användargränssnitt. Data partners kan göra dessa egna namn tillgängliga för sina kunder med antingen de manuella eller automatiserade metoder som beskrivs i detta avsnitt.
seo-title: Hämta segmentmetadata
solution: Audience Manager
title: Hämta segmentmetadata
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# Hämta segmentmetadata {#retrieving-segment-metadata}

När Audience Manager skickar segmentinformation till en datapartner identifieras dessa objekt med numeriska ID:n. När du som datapartner delar informationen med dina kunder (eller arbetar med den själv) ger ett faktiskt namn och en beskrivning en bättre upplevelse för kunderna i rapporter, instrumentpaneler eller andra användargränssnitt ([!DNL UI]). Data partners kan göra dessa egna namn tillgängliga för sina kunder med antingen de manuella eller automatiserade metoder som beskrivs i detta avsnitt.

## Manuell metod {#manual-method}

Som datapartent är ni antagligen vana att hämta målgruppsmetadata från era kunder via manuella processer. Detta kan omfatta filer som bifogats e-postmeddelanden eller från kunder som lägger till dessa data via ett program som [!DNL UI] du har skapat och underhållet för detta ändamål. Dessa processer fungerar, men de är ofta krångliga och tidskrävande och kan kräva manuell datainmatning. Dessa metoder används ofta för att snabbt få igång en integrering, men de ger inte den bästa kundupplevelsen i längden. Du kan också använda alternativet för [!DNL Audience Manager] [!DNL API] att hämta segmentmetadata automatiskt.

## Automatiserad metod {#automated-method}

[!DNL Audience Manager] innehåller en uppsättning [REST-API:er](../../api/rest-api-main/rest-api-main.md) som gör att du kan hämta segmentmetadata automatiskt. Med [!DNL API]kan du skapa jobb som hämtar segmentmetadata vid schemalagda intervaller eller automatiskt när du bearbetar [!DNL Audience Manager] data och hittar ett nytt segment-ID. Se stegen nedan för mer information.

### Steg 1: Granska API:erna för Audience Manager

Avsnittet [Komma igång med REST API:er](../../api/rest-api-main/aam-api-getting-started.md) innehåller information om allmänna krav, autentisering, tillgängliga metoder osv. Det här är en bra plats att börja på om du inte har arbetat med [!DNL Audience Manager] det [!DNL API] förut.

### Steg 2: Begär autentiseringsuppgifter för OAuth2-åtkomst

Du behöver ett klient-ID och en hemlighet för att ringa [!DNL API] samtal. Du kan få ett klient-ID och en hemlighet från din integreringsspecialist under konfigurationsprocessen. Du kan även skicka en e-postförfrågan till [!UICONTROL Audience Manager Customer Care] på [!DNL amsupport@adobe.com].

### Steg 3: Samla in kundspecifik information från varje integrerad kund

Begär följande från varje integrerad kund:

* Användarnamn: Detta är för en begränsad användare som har skrivskyddade behörigheter för det mål som är associerat med en viss integrering.
* Lösenord: Användarlösenordet.
* Mål-ID: Detta är det ID (ett heltal) som är associerat med målet som skapas för den specifika server-till-server-integreringen.

### Steg 4: Hämta segmentmetadata med ett API-anrop

När du har slutfört de föregående stegen kan du använda en `GET` metod för att hämta segmentmetadata. Ett exempel på begäran och svar finns i [Returmålsmappningar](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Det här anropet returnerar segmentdata som är formaterade som nyckelvärdepar i ett [!DNL JSON] objekt. Vissa viktiga segmentattribut som returneras i svaret visas i följande tabell.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>Segmentets-ID <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>Segmentnamnet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Viss text som kortfattat beskriver segmentet. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>Segmentmappningens aktuella status. Alternativ för returstatus är: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>