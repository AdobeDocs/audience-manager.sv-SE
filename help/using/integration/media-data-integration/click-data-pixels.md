---
description: 'null'
seo-description: 'null'
seo-title: Samla in data för kampanjklickningar via pixelanrop
solution: Audience Manager
title: Samla in data för kampanjklickningar via pixelanrop
uuid: 7c3797f7-9674-493d-972b-38be0584fede
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 5%

---


# Samla in data för kampanjklickningar via pixelanrop {#capturing-campaign-click-data-via-pixel-calls}

Klickspårning möjliggör mätning av besökarnas engagemang under hela kampanjen, eftersom klickbaserade aktiviteter registreras för tredjepartskreatörer. På samma sätt som vid [visningar](/help/using/integration/media-data-integration/impression-data-pixels.md)skickas ett händelseanrop till Audience Manager datainsamlingsservrar ([!DNL DCS]) för behandling. Besökaren omdirigeras sedan till den avsedda webbadressen.

>[!NOTE]
>
>Kontakta din [!DNL Audience Manager] konsult- eller kontoansvarige om du vill ha information om exakt [!DNL URL] vad som gäller för klientdomänen.

## Krav

För spårningsanrop krävs följande parametrar:

* `d_event=click`: Ett nyckelvärdepar som identifierar ett händelseanrop som en klickningshändelse.
* `d_rd=redirect URL`: Ett nyckelvärdepar som innehåller en dubbelkodad omdirigering [!DNL URL]. Om du använder ett onlinekodningsverktyg kör du strängen genom kodaren och kodar sedan resultatet igen för att omdirigeringen ska fungera.

Anropet kan dessutom innehålla nyckelvärdepar som kan användas för kvalificering av egenskaper eller för att tillhandahålla data och metadata för andra rapporter.

## Exempel på begäran

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Svar

Svaret dirigerar om webbläsaren till den [!DNL URL] som anges i `d_rd` parametern. Svarssträngen kan innehålla värden som genererats av något av de makron som stöds som listas nedan.

Baserat på ovanstående exempel omdirigeras webbläsaren till följande [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Makron som stöds

Klickhändelser stöder de makron som anges i följande tabell. Ett makro är en liten enhet med självständig kod som aktiveras när annonstaggen läses in för kampanj- och användarspårning. Makrona skickas tillsammans med målet [!DNL URL]om de är markerade med följande format: `%macro%`. Vissa nycklar har inga makron och accepterar i stället ett hårdkodat ID-värde. Tangenter som accepterar hårdkodade värden krävs om du vill analysera data i [målgruppsoptimeringsrapporter](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nyckel </th> 
   <th colname="col02" class="entry"> Makro </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt annonsgrupps-ID från annonsservern. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Inget makro. </p> <p>Accepterar ett hårdkodat ID-värde. </p> </td> 
   <td colname="col2"> <p>Advertiser-ID.</p> <p>En integrationskod för annonsörens datakälla. Observera att detta inte är relaterat till datakällor i Audience Manager.</p> <p> Krävs för <span class="wintitle"> målgruppsoptimeringsrapporter</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt ID för affärsenheten. </p> <p> Krävs för <span class="wintitle"> målgruppsoptimeringsrapporter</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt kampanj-ID från annonsservern. </p> <p> Krävs för <span class="wintitle"> målgruppsoptimeringsrapporter</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt kreativt ID från annonsservern. </p> <p>Obligatoriskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>DataProvider-ID. </p> <p>Används ofta för <code> d_dpuuid</code> att länka ett dataleverantörs-ID till ett användar-ID. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>Unikt användar-ID från dataleverantören. </p> <p>Används ofta för <code> d_dpid</code> att länka ett användar-ID till ett dataleverantörs-ID. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Experience Cloud</span> -ID (ECID). Mer information om ECID finns i <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies och Experience Cloud ID</a>. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt placerings-ID från annonsservern. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>Det numeriska region-ID:t för det DCS-kluster som hanterar en begäran. Mer information om DCS finns i Komponenter <a href="../../reference/system-components/components-data-collection.md"> för</a>datainsamling. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Slumpmässigt tal som används för cachepublicering. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>Numeriskt plats-ID från annonsservern. </p> <p>Valfritt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID för den källa som Audience Manager hämtar metadata från. </p> <p>Obligatoriskt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Ange besökarens ID direkt i URL:en i stället för att förlita dig på Demdex-cookie. </p> <p>Valfritt. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Rör plugin-programmet <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF.</a> </p><p><code>gdpr</code> kan vara 0 (GDPR gäller inte) eller 1 (GDPR gäller).</p> <p>Standardvärdet är 0.</p><p>Valfritt.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Rör plugin-programmet <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager för IAB TCF.</a></p><p> Om <code>gdpr=1</code>ersätts <code>${gdpr_consent_XXXX}</code> av <code>gdpr_consent</code> strängen och leverantörs-ID:t (se <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB-specifikationen</a>).</p> <p>Standardvärdet är 0.</p><p>Valfritt.</p></td> 
  </tr> 
 </tbody> 
</table>

## Exempel på makron

I det här exemplet visas hur du skickar makrona creative, adgroup och placement. Det förutsätts att värdena för varje parameter skickas i den icke-omdirigerade delen av klickspårningsanropet.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Begäran

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Svar

Baserat på ovanstående exempel omdirigeras webbläsaren till följande [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Ytterligare funktionalitet - rapporter om målgruppsoptimering

Du kan använda pixelanrop för att styra [målgruppsoptimeringsrapporter](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md). Se [Översikt och mappningar för metadatafiler](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) om du vill använda pixlar som stöd för rapporterna.


>[!MORELIKETHIS]
>
>* [Data- och metadatafiler för målgruppsoptimeringsrapporter](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

