---
description: Med loggfiler som kan användas kan du hämta mediesignaler från och serverloggfiler för att skapa egenskaper i Audience Manager. Fånga visningar, klick och konverteringar från annonsservrar som egenskaper utan att behöva lägga till pixlar.
keywords: loggar som kan åtgärdas, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Verkställbara loggfiler
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 869bbe657072255e5ea3f0e68294f8f0e6cc966a
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 2%

---

# Verkställbara loggfiler {#actionable-log-files}

[!UICONTROL Actionable Log Files] gör att du kan hämta mediedata från annonsserverns loggfiler och använda data för att skapa egenskaper i Audience Manager. Fånga visningar, klick och konverteringar från annonsservrar som egenskaper utan att behöva lägga till något [pixlar](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>Textformaten (`monospaced text`, *kursiv*, parenteser `[ ]` `( )` etc.) i det här dokumentet anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../reference/code-style-elements.md).

## Syfte {#purpose}

[!UICONTROL Actionable Log Files] effektivisera sättet att hämta in visningar, klickningar och konverteringar från annonsservrar. Använd den här informationen för användarsegmentering utan att manuellt behöva använda pixelmedia för att skicka kampanjattribut till [!DNL Audience Manager].

## Komma igång {#getting-started}

Så här kommer du igång med [!UICONTROL Actionable Log Files]måste du importera loggdata till [!DNL Audience Manager]. Följande länkar hjälper dig att komma igång:

* För [!UICONTROL Google Campaign Manager] loggar, se [Importera Google Campaign Manager-datafiler till Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *och* kontakta [!DNL Audience Manager] konsult.
* För [!UICONTROL Google Ad Manager] (tidigare Google DFP) loggar, se [Importera Google Ad Manager-datafiler till Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *och* kontakta [!DNL Audience Manager] konsult.
* Andra annonsserverloggar finns på [Data- och metadatafiler](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *och* kontakta [!DNL Audience Manager] konsult.

Om du redan importerar loggdata till [!DNL Audience Manager]frågar du [!DNL Audience Manager] konsult eller [Kundtjänst](https://helpx.adobe.com/se/contact/enterprise-support.ec.html) för att aktivera [!UICONTROL Actionable Log Files] för dig.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Arbeta med körbara loggfiler {#working-with-actionable-log-files}

Med [!UICONTROL Actionable Log Files], hämtas information från annonsserverloggar i [!DNL Audience Manager] på samma sätt som ni hämtar data från webbplatsinteraktioner i realtid. [!DNL Audience Manager] ansluter till annonsserverns logglagring, tolkar informationen från loggarna och skickar loggdata som användbara signaler till [Datainsamlingsservrar](../../reference/system-components/components-data-collection.md#dcs-pcs).

Du måste fortfarande ställa in regelbaserade egenskaper för att fånga upp de åtgärdbara signalerna. Se hur du ställer in regelbaserade egenskaper i [Audience Manager användargränssnitt](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) eller med [Masshanteringsverktyg](../../reference/bulk-management-tools/bulk-create.md). Bläddra nedåt till [Användbara signaler](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) om du vill visa en lista med alla tangenter som du kan använda i regelbaserade egenskaper.

>[!IMPORTANT]
>
>Vi rekommenderar implementering [!UICONTROL Actionable Log Files] *i stället för*  [Pixelanrop](../../integration/media-data-integration/impression-data-pixels.md). Vi avråder från att använda båda alternativen eftersom det leder till att antalet frekvenser ökar för egenskaperna.

## Användbara signaler {#actionable-signals}

Signalerna är [minsta dataenheter](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] kan ni samla in annonsörs-, affärsenhet-, kreativitets- och kampanjvärden i tryckhändelser, klickhändelser och konverteringshändelser som signaler från annonsserverloggar.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] stöds för följande annonsservrar:
> 
> * [Google Campaign Manager](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalk och Sizmek](#generic-logs-signals)


Kom ihåg att om du vill använda den här informationen för att skapa och segmentera målgrupper måste du själv skapa regelbaserade egenskaper.

### Användbara signaler från loggar i Google Campaign Manager {#dcm-logs-signals}

Tabellen innehåller en lista med de användbara signalerna från [!DNL Google Campaign Manager] loggfiler:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rubriknamn i loggfil </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
   <th colname="col4" class="entry"> Exempelvärde </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Endast tillgängligt för konverteringshändelser. </p> <p>Representerar det numeriska ID:t för konverteringsaktiviteten i Google Campaign Manager. Det här fältet mappar till aktivitets-ID:t från Google Campaign Manager. </p> <p> <p>Tips: Du kan hämta flera eller specifika konverteringsaktiviteter från Google Campaign Manager. Skapa traits med <code> d_conversion = activity ID</code> för varje konverteringsaktivitet från Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Endast tillgängligt för konverteringshändelser. </p> <p>Det här fältet mappar till konverterings-ID:t i Google Campaign Manager. Anger aktiviteten före användarkonverteringen från Google Campaign Manager. </p> <p>Godkända värden är: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> för konverteringar efter klickning. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> för konverteringar efter exponering. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> för omatchade konverteringar. Konverteringen kan inte matchas mot en tidigare aktivitet. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Ett UTC-datum och en UTC-tid för intrycket, klickningen eller konverteringshändelsen. Finns i mikrosekunder sedan 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>En integrationskod för annonsörens datakälla. Observera att detta inte är relaterat till datakällor i Audience Manager.</p> <p>Det här fältet mappar till Advertiser Group ID från Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Affärsenhets-ID. Det här fältet mappar till annons-ID:t från Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Kampanj-ID som tillhandahålls av Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Det kreativa ID som tillhandahålls av Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Försäljningsbeloppet i USD, till styrkan -6. Multiplicera med 1.000.000 om du vill se det som ett dollarbelopp.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Anger händelsetypen. Audience Manager läser händelsetypen från Google Campaign Managers loggfilsnamn och omvandlar den till en användbar signal. </p> <p>Godkända värden är: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> för intryck. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> för klickningar. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> för konverteringar. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID:t för datakällan som du använder för att hämta data från Google Campaign Manager. Se <a href="../../features/manage-datasources.md#create-data-source"> Så här skapar du en datakälla</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Signalerna som beskrivs i tabellen fångas in i [!DNL Audience Manager] som i realtid `HTTP` ring. Exempelanropet nedan innehåller information om en konverteringshändelse från [!DNL Google Campaign Manager]. Samtal behöver inte nödvändigtvis innehålla *alla* signalerna i exempelanropet.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

För medelstor [!DNL Google Campaign Manager] loggfil på 2 miljoner rader, realiseras alla egenskaper som skapats av användbara signaler inom cirka en timme efter det att loggarna bearbetats.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>Händelsens tidsstämpel finns i [!DNL Google Campaign Manager] loggarna respekteras och skickas till [!UICONTROL Data Collection Servers].
>
>* Om en tidsstämpel inte är tillgänglig för en datarad i [!DNL Google Campaign Manager] loggfil, används tiden för `HTTP` anrop som händelsens tidsstämpel.
>* Om dataraden i [!DNL Google Campaign Manager] loggfilen innehåller en felaktig tidsstämpel. Hela raden ignoreras.


<br>

### Användbara signaler från [!DNL Google Ad Manager] loggar {#ad-manager-logs-signals}

Tabellen innehåller en lista med de användbara signalerna från [!DNL Google Ad Manager] loggfiler:


| Rubriknamn i loggfil | Signal | Beskrivning |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | Det numeriska ID:t för det levererade radobjektet för annonshanteraren |
| `OrderId` | `d_orderid` | Det numeriska ID:t för Ad Manager-ordern som innehöll det levererade radobjektet och det kreativa ID:t. |
| `CreativeId` | `d_creative` | Det numeriska ID:t för den levererade annonshanterarens creative. |
| `-` | `d_event` | Anger händelsetypen. Audience Manager läser händelsetypen från Ad Manager-loggfilens namn och omvandlar den till en användbar signal. Godkända värden är: <br> <ul><li>d_event = imp för visningar.</li><li>d_event = click for clicks.</li><li>d_event = conv för konverteringar och aktiviteter.</li></ul> |
| `-` | `d_src` | ID:t för datakällan som du använder för att hämta Ad Manager-data. Se [Så här skapar du en datakälla](/help/using/features/manage-datasources.md). |

Signalerna som beskrivs i tabellen fångas i Audience Manager som ett HTTP-anrop i realtid. Exempelsamtalet nedan innehåller information om en konverteringshändelse från Google Ad Manager. Samtal behöver inte nödvändigtvis innehålla alla signaler i exempelanropet.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>Händelsens tidsstämpel finns i [!DNL Google Ad Manager] loggarna respekteras och skickas till [!UICONTROL Data Collection Servers].
>
>* Om en tidsstämpel inte är tillgänglig för en datarad i [!DNL Google Ad Manager] loggfil, används tiden för `HTTP` anrop som händelsens tidsstämpel.
>* Om dataraden i [!DNL Google Ad Manager] loggfilen innehåller en felaktig tidsstämpel. Hela raden ignoreras.


<br> 

### Signaler som kan användas från Adobe Advertising Cloud, Flashtalk och Sizmek-annonsservrar {#generic-logs-signals}

Först måste ni lagra era annonsserverloggar i våra Amazon S3-bucket. Läs för att uppnå detta [Datafiler för Audience Optimization-rapporter och åtgärdsloggfiler](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *och* kontakta [!DNL Audience Manager] konsult. Tabellen innehåller en lista med de användbara signalerna från annonsserverns loggfiler:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rubriknamn i loggfil </th> 
   <th colname="col2" class="entry"> Signal </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
   <th colname="col4" class="entry"> Exempelvärde </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Anger om en konvertering matchar eller inte. Alternativen är: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impression </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Klicka på </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Okänd eller okänd </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Ett UTC-datum och en UTC-tid för intrycket, klickningen eller konverteringshändelsen. Använd <code>yyyy-MM-dd HH:mm:ss</code> format. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>En integrationskod för annonsörens datakälla. Observera att det här fältet inte är relaterat till <a href="../../features/datasources-list-and-settings.md">Audience Manager datakällor.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Affärsenhets-ID.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>Kampanj-ID från loggfilen.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>Creative ID från loggfilen. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Inköp eller annat konverteringsbelopp. Datatyp: Flyt. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Anger händelsetypen. Audience Manager läser händelsetypen från loggfilens namn och omvandlar den till en användbar signal. Se <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">namngivningskonventioner för loggfiler</a>. </p> <p>Godkända värden är: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> för intryck. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> för klickningar. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> för konverteringar. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>ID:t för datakällan som du använder för att hämta loggdata. Se <a href="../../features/manage-datasources.md#create-data-source"> Så här skapar du en datakälla</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

Signalerna som beskrivs i tabellen fångas in i [!DNL Audience Manager] som i realtid `HTTP` ring. Samtal behöver inte nödvändigtvis innehålla *alla* signalerna i exempelanropet.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Arbeta med körbara signaler i användargränssnittet i Audience Manager {#actionable-signals-in-ui}

Du kan visa dina inkommande åtgärdbara signaler i [Signalsökning](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) gränssnitt.

Gå till **Målgruppsdata** (1) > **Signaler** (2) > **Sök** (3) och väljer **Åtgärdsbara loggfiler** (4).

![Användbara signaler i användargränssnittet](/help/using/integration/assets/alf-in-signals.png)

Om du vill skapa regelbaserade egenskaper med dina åtgärdbara signaler väljer du **Åtgärdsbara loggfiler** (1) väljer du de signaler som du vill använda som dragningsregler (2) och trycker på **Skapa egenskap från markerade signaler** (3).

![Skapa egenskaper från signaler](/help/using/integration/assets/alf-create-trait.png)


## Användningsexempel {#use-cases}

En fördel med att implementera [!UICONTROL Actionable Log Files] är ett alternativ att använda [senaste och frekvenser](../../features/segments/recency-and-frequency.md) till alla [regelbaserade egenskaper](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) som innehåller användbara signaler. Detta gör att du till exempel kan ange antalet gånger som en användare visas som en viss kreativ i en mediekampanj. Läs [Direkt undertryckning av olika enheter](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) för att lära sig hur man gör detta. Andra användningsområden:

### Återmarknadsföringsanvändare

Återmarknadsför användare som såg creative 123 men som inte klickade eller konverterade och visade dem creative 456. Gör så här:

1. Skapa ett varumärke för att fånga användare som såg den kreativa sidan. Säg att du har rätt [!DNL Creative Trait 123]. Använd trait-regeln:

   `d_creative == 123 AND d_event == imp`

2. Skapa en egenskap för att fånga in användare som klickar eller konverterar. Säg att du heter den här [!DNL Click and Converter]. Använd trait-regeln:

   `d_event == click OR d_event=conv`

3. Skapa ett segment för användare som såg creative 123 men inte klickade eller konverterade. Ge den ett namn [!DNL Retarget Users] och använd segmentregeln:

   `Creative Trait 123 AND NOT Click and Converter`

4. Mappa segmentet [!DNL Retarget Users] till en destination och målanvändare i destinationen med creative 456.

### Använd Google Campaign Manager Floodlight Activity i Audience Optimization Reports eller i Audience Lab

[Floodlight-taggar](https://support.google.com/dcm/partner/answer/4293719?hl=en) gör det möjligt för annonsörer att spåra användarkonverteringar. Med [!UICONTROL Actionable Log Files]kan du spåra [!DNL Google Campaign Manager] konverteringar i [Audience Optimization-rapporter](../../reporting/audience-optimization-reports/audience-optimization-reports.md) eller in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Skapa ett spår och använd följande trait-regel för att hämta en konvertering från annonsserverloggarna:

   `d_event == conv AND d_conversion == 123`

   När du skapar ett spår i Audience Manager [!UICONTROL UI], markera [!UICONTROL Conversion] som [!UICONTROL Event Type].

2. När du har skapat egenskapen börjar konverteringen rapporteras i [!UICONTROL Audience Optimization Reports] och in [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Importera Google Campaign Manager-datafiler till Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization-rapporter](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

