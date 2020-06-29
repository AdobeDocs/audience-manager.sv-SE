---
description: Lägg till en if-programsats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.
seo-description: Lägg till en if-programsats för att kontrollera om det finns Audience Manager-cookies innan du anropar Google Publisher-taggen .setTargeting-metoden.
seo-title: Ändra GPT-API-anropet setTargeting
solution: Audience Manager
title: Ändra GPT-API-anropet setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---


# Ändra GPT- `setTargeting` API-anropet {#modify-the-gpt-settargeting-api-call}

Lägg till en if-sats för att kontrollera om det finns Audience Manager-cookies innan du anropar [!DNL Google Publisher Tag]`.setTargeting` metoden.

## Sök efter Audience Manager Cookies med en `IF` programsats

Metoden hämtar data från målcookien för Audience Manager och den unika användar-ID-cookien ( `.setTargeting` `aam_uuid`). Om `.setTargeting` anropas innan dessa cookies [!UICONTROL DIL] skrivs, eller om cookies är tomma, kan du se fel när sidan läses in. Du kan undvika detta genom att omsluta metoden i en `.setTargeting` `if` programsats som söker efter dessa cookies. Om de inte är angivna förhindrar den här programsatsen `.setTargeting` att anropa `AamGpt` funktionen.

### `IF` Exempel på utdragskod

I det här exemplet är målcookie-namnet för Audience Manager `Sample`. Du anger det här namnet när du skapar målcookien i användargränssnittet i Audience Manager. [!UICONTROL DIL] anger cookie-filen och namnet kan inte ändras `aam_uuid` .

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
>Beroende på hur du vill integrera med [!DNL DFP]behöver du bara några av raderna i kodexemplet ovan:
>
>* Integrering på klientsidan: använder endast raderna 1-3.
>* Integrering på serversidan: ingen av raderna behövs.
>* Infoga [!DNL DFP] loggfiler för rapportering i [!DNL Audience Manager]: använder endast raderna 4-6. Den här koden infogar värdet för `aam_uuid` cookien i loggarna så att de kan importeras för rapportering.


### `AamGpt` Funktioner och datatyper

Definierar de nyckelvariabler som används i `if` programsatsen .

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
   <td colname="col3"> <p>Returnerar nyckeln i nyckelvärdessegmentparet. Om nyckelvärdepar till exempel består av <code> color=blue </code>, returneras <code> color </code>. </p> </td> 
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
>* [Skapa ett GPT-mål](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager Code for Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

