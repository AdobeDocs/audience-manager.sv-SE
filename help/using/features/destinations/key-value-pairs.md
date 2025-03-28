---
description: A [!DNL key-value pair] består av [!DNL related elements]. En nyckel, som är en konstant som definierar datauppsättningen (t.ex. kön, färg, pris) och ett värde, vilket är en variabel som tillhör uppsättningen (t.ex. man/kvinna, grön, 100). Destination Builder skickar data formaterade som nyckelvärdepar.
solution: Audience Manager
title: Standard och seriell [!DNL Key-value pairs]
uuid: 43789419-5b3f-4e62-b2e0-2722340bdd41
feature: Destination Basics
exl-id: b37c829b-66be-4c31-8198-bc032371279e
source-git-commit: 0dfe96a4644c61fb5bc22e4791bfd09c574dcf34
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---

# Standardpar och serienyckelvärdepar {#standard-and-serial-key-value-pairs}

Ett nyckelvärdepar består av relaterade element: En nyckel, som är en konstant som definierar datauppsättningen (t.ex. kön, färg, pris) och ett värde, som är en variabel som tillhör uppsättningen (t.ex. man/kvinna, grön, 100). [!UICONTROL Destination Builder] skickar data formaterade som nyckelvärdepar.

## Grundläggande nyckelvärdepar {#basic-key-value-pairs}

En grundläggande uppsättning nyckelvärdepar kan se ut så här:

* `gender = male`
* `color = green`
* `price > 100`

## Standardpar och serienyckelvärdepar {#standard-serial-key-value-pairs}

Destinationer accepterar nyckelvärdesdata i formatet *`standard`* eller *`serialized`*.

* **Standardnyckelvärdepar:** Formaterar måldata i separata nyckelvärdepar. Varje nyckel anges explicit, även om den används igen för att definiera ett annat värde.
* **Serialiserade nyckelvärdepar:** Komprimerar flera värden till ett nyckelvärdepar. I ett serialiserat nyckelvärdepar avgränsar en specialindikator värdena i nyckelvärdesmängden.

Både standardvärden och serialiserade nyckelvärden kan innehålla ett eller flera värden. Följande tabell innehåller exempel på standardformat och serienyckelformat.

<table id="table_7895B1E800934117A19A96380F0CF91B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formatering </th>
   <th colname="col2" class="entry"> Enkla nyckelvärdepar </th>
   <th colname="col3" class="entry"> Flera nyckelvärdepar </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Standard</b> </p> </td>
   <td colname="col2"> <p> <code> x = 1 &amp; x = 2 </code> </p> </td>
   <td colname="col3"> <p> <code> x = 1 &amp; x = 2 &amp; y = 3 &amp; y = 4 </code> </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Serialiserad</b> </p> </td> 
   <td colname="col2"> <p> <code> x = 1 ; 2 </code> </p> </td> 
   <td colname="col3"> <p> <code> x = 1 ; 2 &amp; y = 3 ; 4 </code> </p> </td>
  </tr>
 </tbody>
</table>

## Avgränsare och avgränsare {#delimiters-separators}

Tecknen som avgränsar värden inom och mellan tangenter och värden kallas *`delimiters`* och *`separators`*. Dessa blir särskilt viktiga när du skickar segment till ett mål i ett serieformat. Med serialisering kan du skicka in flera värden med en enda nyckel och kombinera nyckelvärdepar. Avgränsare och avgränsare definieras enligt följande:

* **Nyckelvärdesavgränsare:** Separerar en nyckel och ett värde inom ett nyckelvärdepar.
* **Avgränsare för nyckelvärde:** Separerar uppsättningar av nyckelvärdepar.
* **Seriell avgränsare:** Separerar flera värden i uppsättningar med serialiserade nyckelvärdepar.

## Exempel {#examples}

Med [!UICONTROL Destination Builder] kan du formatera nyckelvärdesdata på flera olika sätt. Låt oss titta på några exempel på varje typ.

<table id="table_C2FBDC887C8C4CC88B1B2A7CF8E2795F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Exempel på nyckelvärdepar </th> 
   <th colname="col2" class="entry"> Exempel </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Enkel standardnyckel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 </code> </p> </td> 
   <td colname="col3"> <p>En enkel uppsättning nyckelvärdepar. Exemplet innehåller följande element: </p> 
    <ul id="ul_28C0CB005B264373926CA5D7418EE845"> 
     <li id="li_B6D300DBA9064F0BA743BA9B04339511">Nyckel: X </li> 
     <li id="li_9A1C98D5C9124FF1B4F032668576C03A">Värden: 1, 2 </li> 
     <li id="li_1D2828328E554176846C94F6140C0CBF">Avgränsare: = </li> 
     <li id="li_0C6A70A0D9534611ACC98A0FD3693587">Avgränsare för nyckelvärde: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Flera nyckelvärdepar</b> (icke-seriella) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 &amp; X = 2 &amp; Y = 3 &amp; Y = 4 </code> </p> </td> 
   <td colname="col3"> <p>En uppsättning med flera nyckelvärdepar som skickar värden med separata nyckelvärdesuppsättningar. Exemplet innehåller följande element: </p> 
    <ul id="ul_7FB22A43B435463D9F209067FF2C3619"> 
     <li id="li_7487657F6C2F48F5A4C4C9F9E8FB3B4B">Tangenter: X, Y </li> 
     <li id="li_B828CF81DAB8443FBB2EDF6538A63B3C">Värden: 1, 2, 3, 4 </li> 
     <li id="li_EA4C95F6C93D435EB79237E38CE6F011">Avgränsare: = </li> 
     <li id="li_45984AE2B581498299054BA5276D461D">Avgränsare för nyckelvärde: &amp; </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Seriell enskild nyckel</b> </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 ; 3 </code> </p> </td> 
   <td colname="col3"> <p>En uppsättning nyckelvärden som skickar in flera värden med en enda nyckel. Eftersom nyckeln har flera värden kallas den för ett serialiserat nyckelvärdepar. Exemplet innehåller följande element: </p> 
    <ul id="ul_69C4C662B9BD4F77BB940D921B316CCF"> 
     <li id="li_718BEC527E69417C9F88D3DBD3357A28">Nyckel: X </li> 
     <li id="li_659DCBBFB4024AC2B9C4E74D2A86648D">Värden: 1, 2, 3 </li> 
     <li id="li_9A890233C6F84085A7BD5EA4D044E3CC">Avgränsare: = </li> 
     <li id="li_AFC0426EA6044F8BAFD915FCB3808FBA">Serieavgränsare: semikolon </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Flera nyckelvärdepar</b> (seriella) </p> </td> 
   <td colname="col2"> <p> <code> X = 1 ; 2 &amp; Y = 3 ; 4 </code> </p> </td> 
   <td colname="col3"> <p>En uppsättning med flera nyckelvärdepar som skickar flera värden på olika nycklar. Exemplet innehåller följande element: </p> 
    <ul id="ul_CB50133B2E944818B9F2A0586EF69774"> 
     <li id="li_FD3D7ECC2BF046E99B1ED0B73EFE341F">Tangenter: X, Y </li> 
     <li id="li_2BADC98C4CE74BBBBA1DC446D24615AC">Värden: 1, 2, 3, 4 </li> 
     <li id="li_4125435175AD4A43A44B980B28F32364">Avgränsare: = </li> 
     <li id="li_48CFC279B2514F4FB2935B05FC7F287A">Avgränsare: &amp; </li> 
     <li id="li_576C731F2FAF47FD92F55345CD6D36A0">Serieavgränsare: semikolon </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Målserialisering {#destination-serialized}

Ett serialiserat mål kombinerar flera egenskaper till en enda sträng och skickar informationen till ett mål.

<!-- c_dest_serialized.xml -->

Serialiserad dataöverföring bidrar till att förbättra effektiviteten eftersom flera trasig branding sker sekventiellt i stället för parallellt. Detta ger målservern tillräckligt med tid för att ta emot, bearbeta och returnera data innan ytterligare förfrågningar besvaras.

### Destinationer som stöds

I [!DNL Audience Manager] kan du serialisera och skicka data till i stort sett alla mål som du vill arbeta med. Innan du använder den här funktionen måste du känna till målet [!DNL URL] och var några obligatoriska eller valfria makron ska placeras. Hämta information om makroplacering från målpartnern. Mer information finns i [Definierade målmakron](../../features/destinations/destination-macros.md#destination-macros-defined).
