---
description: Obligatoriska fält, syntax och regler som du ska följa när du formaterar en inkommande trait-datafil.
seo-description: Obligatoriska fält, syntax och regler som du ska följa när du formaterar en inkommande trait-datafil.
seo-title: Innehållssyntax för inkommande datafil, ogiltiga tecken, variabler och exempel
solution: Audience Manager
title: Innehållssyntax för inkommande datafil, ogiltiga tecken, variabler och exempel
uuid: 88699b29-1502-4183-a9a4-be70692a02bb
feature: Inbound Data Transfers
exl-id: 894f1923-6c78-41d2-b6a2-eebf56eaa29e
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '1196'
ht-degree: 1%

---

# Innehåll i inkommande datafil: Syntax, ogiltiga tecken, variabler och exempel {#inbound-data-file-contents-syntax-invalid-characters-variables-and-examples}

Obligatoriska fält, syntax och regler som du ska följa när du formaterar en inkommande trait-datafil.

## Filinnehållssyntax {#file-content-syntax}

Fälten i den inkommande datafilen måste visas i den ordning som visas nedan. I det här exemplet har `<` `>`-symbolerna lagts till för att hjälpa till att skilja ut varje element visuellt. Du behöver inte inkludera dessa i datafilen.

```
<user ID><TAB><trait ID>,<trait ID>,<trait ID>,...
```

Information om andra godkända filinnehållsformat finns i [Anpassade partnerintegreringar](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>Vi har en gräns på 200 rader som vi kan behandla för varje användar-ID som skickas i den inkommande datafilen. Om du till exempel skickar 300 rader för ett användar-ID behålls de första 200 raderna och de ytterligare 100 raderna tas bort. I exemplet nedan är du bra eftersom du skickar tre rader vardera för användar-ID 1 och användar-ID 2. Vi har ingen begränsning för hur många traits- eller key-value-par du får med på en rad.
>
>
```
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID1><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
><user ID2><TAB><trait ID>,<trait ID>,<trait ID>
>```

## Filvariabler definierade {#file-variables-defined}

Tabellen listar och definierar de variabler som används i en korrekt formaterad inkommande datafil. *En* variabelplatshållare anges med kursiv stil.

<table id="table_FE043CE392B34D5194111188E5C39671"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>User ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Ett användar-ID kan vara: </p> <p> 
     <ul id="ul_25168355353545A9A049D0083403025E"> 
      <li id="li_23829FE2F6464E33859B3E388FCD106B">Ett unikt användar-ID som tilldelats av <span class="keyword"> Audience Manager </span> ( <a href="../../../reference/ids-in-aam.md"> Audience Manager UID </a>). </li> 
      <li id="li_76961F20DD3F4554AD2ADFB773F975DB">Ett unikt användar-ID som tilldelats i CRM-systemet ( <a href="../../../reference/ids-in-aam.md"> DPUID, i Audience Manager </a>). </li> 
      <li id="li_52ABF6CCBCD147E2BD84D056F7461BA0">Ett mobilt Android- eller iOS-enhets-ID i dess ursprungliga oförändrade form som det visas i det mobila operativsystemet. </li> 
     </ul> </p> <p>För mobil-ID: </p> <p> 
     <ul id="ul_717A17E11565427E9E2D9D7554BB231B"> 
      <li id="li_83BC5EA1E0294651A1F11D7E78EBCE98">IDFA-format: ID:n måste vara versaler och inte hash. Exempel, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_27F298E62A1E46F88ECF52A01B752D3A">Android-format: ID:n måste vara gemena och inte hashas. Exempel, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p>Avgränsa användar-ID och trait-ID:n med en enda tabbavgränsare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>trait ID </i> </code> </p> </td> 
   <td colname="col2"> <p>Audience Manager <span class="keyword">-trait-ID:t </span>. Vi ber dig att endast inkludera <i>medföljande egenskaper</i> i inkommande datafiler. Vi bearbetar inga andra typer av egenskaper vid inkommande dataöverföring. </p> <p> <p>Obs!  Du kan hitta ditt Trait ID med hjälp av metoden GET som returnerar information om alla dina egenskaper. Mer information finns i <a href="../../../api/rest-api-main/api-traits.md">-API-metoder för spår </a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formaterar [!UICONTROL Trait IDs] {#formatting-trait-ids}

I följande tabell beskrivs de prefix som identifierar [!UICONTROL trait]-namn eller ID:n i en inkommande datafil. Se [exempelfilerna](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#data-file-examples) för exempel.

<table id="table_AD54B3E5487E47C481A4E5FD3A93FDA5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Prefix </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_sid= </code> </p> </td> 
   <td colname="col2"> <p><code> d_sid </code>-prefixet talar om för vårt system att ID:t är ett <span class="keyword"> Audience Manager </span> trait ID. Detta är samma ID som visas i användargränssnittet. Du kan också returnera trait-ID:n med API-metoden <code> GET </code>. Se <a href="../../../api/rest-api-main/api-traits.md"> API-metoder för spår </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_unsid= </code> </p> </td> 
   <td colname="col2"> <p>Data som har prefixats med <code> d_unsid </code> tar bort användare från den egenskapen. <code> d_unsid </code>-prefixet ignoreras i en <code> overwrite </code>-fil. </p> <p><code> d_unsid= </code>-prefixet talar om för vårt system att ID:t är ett <span class="keyword"> Audience Manager </span> trait ID. Detta är samma ID som visas i användargränssnittet. Du kan också returnera trait-ID:n med API-metoden <code> GET </code>. Se <a href="../../../api/rest-api-main/api-traits.md"> API-metoder för spår </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ic= </code> </p> </td> 
   <td colname="col2"> <p> <a href="../../../features/traits/manage-trait-rules.md#managing-trait-rules"> Med svällningsregler  </a> kan du ange kriterier för kvalificering av egenskaper. Om du formaterar en trait-regel som <code> ic == trait ID </code> kan du skicka in egenskaper i en enkel kommaformaterad lista. </p> <p>Exempel: du skapar följande 3-trait-regler: </p> <p> 
     <ul class="simplelist"> 
      <li> <code> ic == "123" </code> </li>
      <li> <code> ic == "456" </code> </li>
      <li> <code> ic == "789" </code> </li>
     </ul> </p> <p>Dessa egenskaper är kopplade till <code> ic </code>-tangenten. På så sätt kan du skapa en enklare lista över egenskaper i datafilen. Du behöver inte ta med prefixet <code> ic </code>. Innehållet i datafilen kan därför se ut så här: </p> <p>
     <code> 
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 
      <i>user ID</i>&nbsp;&lt;TAB&gt;&nbsp;123,456,789 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nyckelvärdepar </p> </td> 
   <td colname="col2"> <p>Fackdata kan formateras som nyckelvärdepar med alfanumeriska strängar. Det finns flera sätt att formatera nyckelvärdepar, vilket visas nedan: </p> <p> 
     <ul id="ul_D4F5A97FE0444AC6B7D8D4DAEDD3EAF2"> 
      <li id="li_07B893AA8EB24F34B70F8DA06E87EAB3"> <code> key = value </code> </li> 
      <li id="li_1F3ACA27C5794931B430298B27AB8BCC"> <code> "key" = value </code> </li> 
      <li id="li_8910539EB4F0431E8CF63983D30D9B08"> <code> key = "value" </code> </li> 
      <li id="li_DCECE281D245438FB01F8D0BA932B3CC"> <code> "key" = "value" </code> </li> 
     </ul><code> "age"="32" </code> ,  <code> "gender"=m </code> ,  <code> model = "pickup truck" </code> är alla  <code> product = tablet </code> exempel på korrekt formaterade nyckelvärdepar. </p> </td> 
  </tr>
 </tbody>
</table>

## Ogiltiga tecken i [!UICONTROL Trait IDs], [!UICONTROL User IDs] och Key-Value-paren {#invalid-chars}

### [!UICONTROL Trait IDs]

[!UICONTROL Trait IDs] består endast av numeriska tecken. Vi ber dig att endast inkludera *[!UICONTROL onboarded traits]* i inkommande datafiler. Inga andra [!UICONTROL trait]-typer bearbetas i den inkommande dataöverföringen.

### [!UICONTROL User IDs]

<table id="table_8C5C7271B813441EA2D45CA2FE2A6C59"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-typ </th> 
   <th colname="col2" class="entry"> Krav </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>DPUUID </p> </td> 
   <td colname="col2"> <p><i>Använd </i> inte kodat kolon (  <code> %3A </code>) eller okodat kolon (: ) i DPUID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID för mobila iOS-enheter (IDFA) eller Android-enheter </p> </td> 
   <td colname="col2"> <p>ID:n för mobila enheter måste vara strikt formaterade så som visas här: </p> <p> 
     <ul id="ul_6AEFB6CFA54444D9B75F03BCE7916696"> 
      <li id="li_45B272D5EEE944FC9D5C89A0924465F7">IDFA-format: ID:n måste vara versaler och inte hash. Exempel, <code> 6D92078A-8246-4BA4-AE5B-76104861E7DC </code> </li> 
      <li id="li_2DA0347293814C70ADCD253BF01A81F5">Android-format: ID:n måste vara gemena och inte hashas. Exempel, <code> 97987bca-ae59-4c7d-94ba-ee4f19ab8c21 </code> </li> 
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### Nyckelvärdepar

Felaktigt formaterade värdenamn i nyckelvärdepar orsakar också problem. Följ dessa regler när du skapar eller namnger värdet i ett nyckelvärdepar:

<table id="table_41A4991090A64DEFA9AF704164B26DBB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tecken </th> 
   <th colname="col2" class="entry"> Krav </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Citattecken (") </p> </td> 
   <td colname="col2"> <p>Du kan använda citattecknet i tangenten och i värdedelen av nyckelvärdepar, som i: </p> <p> 
     <ul id="ul_3447A913203647A8A9A1A5D14B1A19FE"> 
      <li id="li_B19B56CE8D4449B881B912E74809E00D"> <p> <code> d_city = "New York", d_city = "San Francisco" </code> </p> </li> 
      <li id="li_895380BB35B4498091928F75F0BB6A45"> <p> <code> "d_city" = "New York", "d_city" = "San Francisco" </code> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Streck (-) </p> </td> 
   <td colname="col2"> <p>Vi ignorerar strecktecken i början av nycklarna. Till exempel tolkas <code> -product = camera </code> som <code> product = camera </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TAB </code> </p> </td> 
   <td colname="col2"> <p><i>Använd </i> inte  <code> TAB </code> i stället för tomma värden i nyckelvärdepar. Använd bara <code> TAB </code> för att separera variabler i den inkommande datafilen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> \n, \t </code> </p> </td> 
   <td colname="col2"> <p>Använd inte de nya rad- eller tabbtecknen ( <code> \n, \t </code>) i nycklar eller i värden. </p> </td> 
  </tr>
 </tbody>
</table>

## Exempel på datafiler {#data-file-examples}

<table id="table_8017E070F7A54143A82CA153CBAEB5DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datafilformat </th> 
   <th colname="col2" class="entry"> Beskrivning och exempel </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Med <code> d_sid </code> eller <code> d_unsid </code> </p> </td> 
   <td colname="col2"> <p>Den här datafilen visar en användare som är kvalificerad för traits 24, 26, 27 och som har tagits bort från trait 28 och 29. </p> <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;&amp;nbsp;d_sid=24,d_sid=26,d_sid=27,d_unsid=28,d_unsid=29 
     </code> </p> <p>Obs!  <p>I stället för att använda d_unsid kan du ta bort egenskaper från användarprofiler med följande syntax: </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:0,&amp;nbsp;29:0 
      </code> </p> <p> 
      <code>
        59767559181262060060278870901087098252&amp;nbsp;28:-1,&amp;nbsp;29:-1 
      </code> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Med <code> ic== </code> </p> </td> 
   <td colname="col2"> <p>Dessa egenskaper har lagts till i en trait-regel med prefixet <code> ic </code>. Därför kan du lägga till dem i datafilen avgränsade med kommatecken. En flik skiljer UUID och trait ID:n. <code> ic </code>-prefixet krävs inte i filen. </p> <p><b>Numeriska ID:n</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;30608,50354,50338,50352,30626 
     </code> </p> <p><b>Sträng-ID</b> </p> <p> 
     <code>
       DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1&amp;nbsp;&amp;nbsp;ic=52,ic=55 
     </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Med nyckelvärdepar </p> </td> 
   <td colname="col2"> Dessa fildata använder nyckelvärdepar för att skicka data till <span class="keyword"> Audience Manager </span>. <p> 
     <code>
       59767559181262060060278870901087098252&amp;nbsp;“gender”=”female”,“luxury_shopper”=”yes” 
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

[Hämta ](assets/ftp_dpm_1234_1445374061.overwrite) exempeldatafilen om du behöver fler exempel. Den hämtade filen har filtillägget `.overwrite`. Du kan öppna den med en enkel textredigerare.

## Exempelmatris {#examples-matrix}

Diagrammet nedan visar exempel på rätt sätt att formatera dina inkommande filer, beroende på typen [av ID:n](../../../reference/ids-in-aam.md) och den metod som du vill lägga till [!UICONTROL traits] till profiler med.

<table id="table_FE6D97A1F5074E4A8EFC723AF0C5E707"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID-typ/åtgärd </th> 
   <th colname="col2" class="entry"> Använd d_sid för att lägga till egenskaper i en användarprofil </th> 
   <th colname="col3" class="entry"> Använd d_unsid för att ta bort egenskaper från en användarprofil </th> 
   <th colname="col4" class="entry"> Skicka i nyckelvärdepar för att lägga till egenskaper i en användarprofil </th> 
   <th colname="col5" class="entry"> Använd prefixet ic för att lägga till egenskaper i en användarprofil </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Audience Manager UUID </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-1"> Exempel 1  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-2"> Exempel 2  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-3"> Exempel 3  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-4"> Exempel 4  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Google Advertising ID for Android Devices </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-5"> Exempel 5  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-6"> Exempel 6  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-7"> Exempel 7  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-8"> Exempel 8  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apple IDFA för iOS-enheter </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-9"> Exempel 9  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-10"> Exempel 10  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-11"> Exempel 11  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-12"> Exempel 12  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ditt eget CRM-ID (DPUID) </p> </td> 
   <td colname="col2"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-13"> Exempel 13  </a> </p> </td> 
   <td colname="col3"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-14"> Exempel 14  </a> </p> </td> 
   <td colname="col4"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-15"> Exempel 15  </a> </p> </td> 
   <td colname="col5"> <p> <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#example-16"> Exempel 16  </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

### Exempel 1 {#example-1}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_sid=24, d_sid=26, d_sid=27
```

### Exempel 2 {#example-2}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] diskvalificeringsinformation för [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> d_unsid=24, d_unsid=26, d_unsid=27
```

eller

```
59767559181262060060278870901087098252 <TAB> 24:0, 26:0, 27:0
```

eller

```
59767559181262060060278870901087098252 <TAB> 24:-1, 26:-1, 27:-1
```

### Exempel 3 {#example-3}

Skicka i nyckelvärdepar för att lägga till [!UICONTROL trait] kvalificeringsinformation för [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> product = tablet, product = phone
```

eller

```
59767559181262060060278870901087098252 <TAB> "product" = "tablet", "product" = "phone"
```

### Exempel 5 {#example-4}

Använd prefixet `ic` för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL Audience Manager] [!DNL UUIDs].

```
59767559181262060060278870901087098252 <TAB> 30608,50354,50338,50352,30626
```

eller

```
59767559181262060060278870901087098252 <TAB> ic=52,ic=55
```

### Exempel 5 {#example-5}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL Android]-enheter.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Exempel 6 {#example-6}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] information om diskvalificering för [!DNL Android] enheter.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

eller

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:0, 26:0, 27:0
```

eller

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 24:-1, 26:-1, 27:-1
```

### Exempel 7 {#example-7}

Skicka i nyckelvärdepar för att lägga till [!UICONTROL trait] kvalificeringsinformation för [!DNL Android]-enheter.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> product = tablet, product = phone
```

eller

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> "product" = "tablet", "product" = "phone"
```

### Exempel 8 {#example-8}

Använd `ic`-prefixet för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL Android]-enheter.

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> 30608,50354,50338,50352,30626
```

eller

```
e4fe9bde-caa0-47b6-908d-ffba3fa184f2 <TAB> ic=52,ic=55
```

### Exempel 9 {#example-9}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL iOS]-enheter.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Exempel 10 {#example-10}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] information om diskvalificering för [!DNL iOS] enheter.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

eller

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:0, 26:0, 27:0
```

eller

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 24:-1, 26:-1, 27:-1
```

### Exempel 11 {#example-11}

Skicka i nyckelvärdepar för att lägga till [!UICONTROL trait] kvalificeringsinformation för [!DNL iOS]-enheter.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> product = tablet, product = phone
```

eller

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> "product" = "tablet", "product" = "phone"
```

### Exempel 12 {#example-12}

Använd `ic`-prefixet för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL iOS]-enheter.

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> 30608,50354,50338,50352,30626
```

eller

```
6D92078A-8246-4BA4-AE5B-76104861E7DC <TAB> ic=52,ic=55
```

### Exempel 13 {#example-13}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_sid=24, d_sid=25, d_sid=26
```

### Exempel 14 {#example-14}

Använd [!UICONTROL trait IDs] för att skicka [!UICONTROL trait] diskvalificeringsinformation för [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> d_unsid=24, d_unsid=25, d_unsid=26
```

eller

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:0, 26:0, 27:0
```

eller

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 24:-1, 26:-1, 27:-1
```

### Exempel 15 {#example-15}

Skicka i nyckelvärdepar för att lägga till [!UICONTROL trait] kvalificeringsinformation för [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> product = tablet, product = phone
```

eller

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> "product" = "tablet", "product" = "phone"
```

### Exempel 16 {#example-16}

Använd prefixet `ic` för att skicka [!UICONTROL trait] kvalificeringsinformation för [!DNL DPUUIDs].

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> 30608,50354,50338,50352,30626
```

eller

```
DBwFoc3dhfMNCFBh2M4F9ZkJEXMNnRDh2PXvnI1 <TAB> ic=52,ic=55
```

>[!MORELIKETHIS]
>
>* [Trait Builder ](../../../features/traits/about-trait-builder.md)

