---
description: Lägg till en if-programsats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.
seo-description: Lägg till en if-programsats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.
seo-title: Ändra API-anropet GPT setTargeting
solution: Audience Manager
title: Ändra API-anropet GPT setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 8%

---


# Ändra GPT-API-anropet `setTargeting` {#modify-the-gpt-settargeting-api-call}

Lägg till en if-programsats för att kontrollera om det finns Audience Manager-cookies innan du anropar [!DNL Google Publisher Tag] `.setTargeting`-metoden.

## Sök efter Audience Manager Cookies med en `IF`-sats

Metoden `.setTargeting` hämtar data från målcookien för Audience Manager och den unika cookien för användar-ID ( `aam_uuid`). Om `.setTargeting` anropas innan [!UICONTROL DIL] skriver dessa cookies, eller om cookies är tomma, kan det uppstå fel när sidan läses in. Du kan undvika detta genom att omsluta metoden `.setTargeting` i en `if`-sats som söker efter dessa cookies. Om de inte anges förhindrar den här programsatsen `.setTargeting` från att anropa funktionen `AamGpt`.

### `IF` Exempel på utdragskod

I det här exemplet är målcookie-namnet för Audience Manager `Sample`. Du anger det här namnet när du skapar målcookien i användargränssnittet i Audience Manager. [!UICONTROL DIL] anger  `aam_uuid` cookien och namnet kan inte ändras.

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
>* Integrering på klientsidan: använder endast raderna 1-3.
>* Integrering på serversidan: ingen av raderna behövs.
>* Infoga [!DNL Google Ad Manager]-loggfiler för rapportering i [!DNL Audience Manager]: använder endast raderna 4-6. Den här koden infogar värdet för `aam_uuid`-cookien i loggarna så att de kan importeras för rapportering.


### `AamGpt` Funktioner och datatyper

Definierar de nyckelvariabler som används i `if`-satsen.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry">  -funktion </th> 
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

