---
description: I Destination Builder innehåller konfigurationsavsnittet fälten Cookie-domän och Publish Data To. Med dessa kan du skapa regler som avgör om en destination ställer in en cookie eller returnerar en cookie. Cookie Domain och Publish Data Att arbeta oberoende av varandra och är valfritt. Du kan skapa en cookie-destination utan att använda någon av dem.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Valfria inställningar för cookie-mål
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Valfria inställningar för cookie-mål {#optional-settings-cookies}

I [!UICONTROL Destination Builder] innehåller [!UICONTROL Configuration section] fälten [!UICONTROL Cookie Domain] och [!UICONTROL Publish Data To]. Med dessa kan du skapa regler som avgör om en destination ställer in en cookie eller returnerar en cookie. [!UICONTROL Cookie Domain] och [!UICONTROL Publish Data To] fungerar oberoende av varandra och är valfria. Du kan skapa en cookie-destination utan att använda någon av dem.

## Cookie-domän: Syntax och exempel {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie-domän </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Syntax</b> </p> </td> 
   <td colname="col2"> <p>Fältet <span class="wintitle"> Cookie-domän </span> accepterar en enkel textsträng som gör att du kan ange cookies på en angiven domän eller alla domäner. När du använder den här funktionen: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Ange endast en domän för varje cookie-mål. Ange inte flera domäner i fältet <span class="wintitle"> Cookie-domän </span>. Skapa ett annat <span class="wintitle">-mål </span> i stället. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Använd inte jokertecken. </li> 
     </ul> </p> <p> Lämna fältet <span class="wintitle"> Cookie-domän </span> tomt om du vill ange en cookie för alla domäner. Det här är standardinställningen. </p> <p>Så här anger du cookies för en specifik domän och underdomäner: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Skriv namnet på domänen i fältet <span class="wintitle"> Cookie-domän </span>. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Starta domännamnet med en punkt. Exempel: <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Prefixet <code> https://www</code> krävs inte. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Exempel</b> </p> </td> 
   <td colname="col2"> <p>Ett enkelt exempel: vi har en fiktiv webbplats som heter sports.com. Sports.com har domäner för golf, baseboll och fotboll. Om du vill ange en cookie i alla sportdomäner skriver du den i rutan <span class="wintitle"> Cookie-domän </span> enligt nedan: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Detta anger för <span class="keyword"> Audience Manager</span> att ange en cookie i en domän som innehåller mönstret <code><i>something</i></code>.sports.com. Nedan finns en mer komplex uppsättning exempel. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exempel på komplexa cookie-domäner

De här exemplen visar om [!DNL Audience Manager] kommer att ange en cookie utifrån hur alternativet [!UICONTROL Cookie Domain] är konfigurerat.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Webbplats </th> 
   <th colname="col2" class="entry">Cookie-domän: .sports.com <p>Cookie-uppsättning </p> </th> 
   <th colname="col3" class="entry">Cookie-domän: .golf.sports.com <p>Cookie-uppsättning </p> </th> 
   <th colname="col4" class="entry">Cookie-domän: Tom <p>Cookie-uppsättning </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sport.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nej </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sport.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Ja </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sport.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nej </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sport.golf.com</b> </p> </td> 
   <td colname="col2"> Nej </td> 
   <td colname="col3"> Nej </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
 </tbody> 
</table>

## Publish-data till {#publish-data-to}

[!UICONTROL Publish Data To]-inställningarna returnerar en cookie om domänen uppfyller villkoren som anges i de alternativ du väljer. Alternativen är:

* **[!UICONTROL All of our domains]**: (Standard) Returnerar [!DNL cookie] för alla domäner.
* **[!UICONTROL Only the selected domains]**: Returnerar endast en cookie för de domäner som har valts i domänlistan.
* **[!UICONTROL All of our domains except the selected domains]**: Förhindrar att markerade domäner tar emot en [!DNL cookie]. Alla andra domäner kan ta emot en [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Skapa ett cookie-mål](../../features/destinations/create-cookie-destination.md)
