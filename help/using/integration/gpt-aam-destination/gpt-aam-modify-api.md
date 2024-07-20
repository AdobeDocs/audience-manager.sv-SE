---
description: Lägg till en if-sats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Ändra GPT-API-anropet setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 4%

---

# Ändra GPT-API-anropet `setTargeting` {#modify-the-gpt-settargeting-api-call}

Lägg till en if-sats som ska kontrolleras för Audience Manager-cookies innan du anropar metoden [!DNL Google Publisher Tag] `.setTargeting`.

## Sök efter Audience Manager-cookies med en `IF`-sats

Metoden `.setTargeting` hämtar data från målcookien för Audience Manager och den unika cookien för användar-ID ( `aam_uuid`). Om `.setTargeting` anropas innan [!UICONTROL DIL] skriver dessa cookies, eller om cookies är tomma, kan du se fel när sidan läses in. Du kan undvika detta genom att kapsla in metoden `.setTargeting` i en `if` -sats som söker efter dessa cookies. Om de inte anges förhindrar den här programsatsen `.setTargeting` från att anropa funktionen `AamGpt`.

### Exempel på programsats `IF`

I det här exemplet är målcookie-namnet för Audience Manager `Sample`. Du anger det här namnet när du skapar målcookien i användargränssnittet i Audience Manager. [!UICONTROL DIL] anger cookien `aam_uuid` och det går inte att ändra namnet.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Beroende på hur du vill integrera med [!DNL Google Ad Manager] behöver du bara några av raderna i kodexemplet ovan:
>
>* Integrering på klientsidan: använd endast raderna 1-3.
>* Integrering på serversidan: inga av raderna behövs.
>* Infoga [!DNL Google Ad Manager] loggfiler för rapportering i [!DNL Audience Manager]: Använd endast raderna 4-6. Den här koden infogar värdet för cookien `aam_uuid` i loggarna så att de kan importeras för rapportering.

### `AamGpt` funktioner och datatyper

Definierar de nyckelvariabler som används i programsatsen `if`.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>Sträng </p> </td> 
   <td colname="col3"> <p>Returnerar nyckeln i nyckelvärdessegmentparet. Om nyckelvärdepar till exempel bestod av <code> color=blue </code> returneras <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Array med strängar </p> </td> 
   <td colname="col3"> <p>Returnerar värden i en array, t.ex. <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Returnerar användar-ID för Audience Manager, t.ex. <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Skapa en GPT-destination](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-kod för Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)
