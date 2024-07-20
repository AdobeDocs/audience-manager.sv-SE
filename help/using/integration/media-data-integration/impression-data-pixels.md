---
description: Ett tillvägagångssätt för att skicka mediedata till Audience Manager använder annonsservermakron för att skicka kampanjattribut till Audience Manager.
seo-description: One approach for sending media data to Audience Manager uses ad server macros to send campaign attributes to Audience Manager.
seo-title: Capturing Campaign Impression Data via Pixel Calls
solution: Audience Manager
title: Samla in data för kampanjexponering via pixelanrop
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 18%

---

# Samla in data för kampanjexponering via pixelanrop{#capturing-campaign-impression-data-via-pixel-calls}

Ett tillvägagångssätt för att skicka mediedata till Audience Manager använder annonsservermakron för att skicka kampanjattribut till Audience Manager.

Den här metoden kallas ofta&quot;pixelering av den kreativa&quot;. Dessa datapunkter infogas dynamiskt i [!DNL Audience Manager]-pixelkoden av tredjeparts- och servermakron, som används för att mappa och rapportera alla visningar och klickningar baserat på kampanjens huvudrapporteringsattribut. De aggregerade data ger en enhetlig bild av kampanjens resultat, hjälper till att identifiera anpassade konverteringsvägar och hjälper kunderna att förbättra sekvensen av annonsserverhändelser som leder till konverteringar.

## Syntax för händelseanrop

>[!NOTE]
>
>Textformaten (`monospaced text`, *kursiv*, parenteser `[ ]` `( )` etc.) anger kodelement och alternativ. Mer information finns i [Formatkonventioner för kod- och textelement](../../reference/code-style-elements.md).

Händelseanropet samlar in visnings- och konverteringsdata och skickar dem till [!DNL Audience Manager] [datainsamlingsservrarna](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Den här processen bygger på externa annonsservrar som placerar anropet i annonsmaterialet för att styra vilket innehåll som ska infogas i koden. De externa annonsservrarna (till exempel [!DNL DFA]) kan placera den här koden i alla annonsvisningar. Dessutom använder ett annonsanrop inte [!DNL JavaScript] eller s.k. frame bursting-teknik för att komma åt utgivardata utanför annonstaggen.

Händelseanrop består av nyckelvärdepar med följande syntax:

```
https://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

I nyckelvärdepar är värdevariabeln ett ID eller makro som infogats av annonsservern. När annonstaggen läses in ersätts den `%macro%` med de nödvändiga motsvarande värdena. Det här anropet returnerar inget svar.

## Nyckelvärdepar som stöds {#supported-key-value-pairs}

Impression-händelseanrop accepterar data som har formats till nyckelvärdepar. I följande tabell visas och beskrivs de tangenter som används för att lagra dessa variabler. Många av dessa krävs om du vill hämta och analysera data i [Audience Optimization-rapporter](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckel </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>Numeriskt annonsgrupps-ID från annonsservern. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>Datakällans ID eller integreringskod för annonsören. </p> <p>Krävs för <span class="wintitle"> Audience Optimization </span>-rapporter. </p> <p>Valfritt.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>ID för datakälla eller integreringskod för din affärsenhet. </p> <p>Krävs för <span class="wintitle"> Audience Optimization </span>-rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Cachebuffertvärde. <span class="keyword"> Audience Manager </span> skickar automatiskt cachekontrollhuvuden som stöds av de flesta webbläsare och proxies. Om du vill utföra ytterligare cachepublicering tar du med den här parametern i ett händelseanrop, följt av en slumpmässig sträng. </p> <p> Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numeriskt kampanj-ID från annonsservern. </p> <p>Krävs för <span class="wintitle"> Audience Optimization </span>-rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>I det här sammanhanget skapar <code> d_cid </code> ett nyckelvärdepar som gör att du kan koppla en mobilenhetstyp till ett unikt användar-ID (DPUID). Ett fast ID avgör mobilenhetstypen. Värdet, som är användar-ID, kan variera. Avgränsa nyckel/värde-paret med <code> %01 </code>, som inte är ett kontrolltecken för utskrift. Parametern accepterar följande nycklar: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">2014: Identifierar en Android-enhet (GAID). <code> d_cid = 20914 %01 1234 </code> säger till exempel att användare 1234 är kopplad till en Android-enhet. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">2015: Identifierar en iOS-enhet (IDFA). <code> d_cid = 20915 %01 5678 </code> säger till exempel att användare 5678 är kopplad till en iOS-enhet. </li> 
    </ul> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numeriskt kreativt ID från annonsservern. </p> <p>Krävs för <span class="wintitle"> Audience Optimization </span>-rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Identifierar ett händelseanrop som en intryckshändelse. </p> <p>Obligatoriskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Numeriskt placerings-ID från annonsservern. </p> <p> Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Numeriskt plats-ID från annonsservern. </p> <p>Krävs för <span class="wintitle"> Audience Optimization </span>-rapporter. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Datakällans ID eller integrationskod för den plattform som tillhandahåller metadata (t.ex. DFA, Atlas, GBM, Media Math). </p> <p>Krävs för <span class="wintitle"> Audience Optimization </span>-rapporter. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Rör plugin-programmet <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF.</a></p> <p><code>gdpr</code> kan vara 0 (GDPR gäller inte) eller 1 (GDPR gäller).</p> <p>Standardvärdet är 0.</p><p>Valfritt.</p><p>Om <code>gdpr=1</code>, ska parametern <code>gdpr_consent</code> innehålla IAB TC-medgivandeparametern för att bearbeta data. Annars tas alla data bort.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Rör plugin-programmet <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF.</a></p><p> Om <code>gdpr=1</code> ersätts <code>${gdpr_consent_XXXX}</code> av strängen <code>gdpr_consent</code> och leverantörs-ID (se <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB-specifikation </a>).</p> <p>Standardvärdet är 0.</p><p>Valfritt.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Kontakta Adobe Audience Manager konsult- eller kontoansvarig för att få en exakt URL som är specifik för klientdomänen.

## Ytterligare funktioner - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

Du kan använda pixelanrop för att aktivera [Audience Optimization-rapporter](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Se [Översikt och mappningar för metadatafiler](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) om du vill använda pixlar som stöd för rapporterna.

>[!MORELIKETHIS]
>
>* [Data- och metadatafiler för Audience Optimization-rapporter](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)
