---
description: Kodexempel och beskrivningar för specifika fall för användning i DIL.
seo-description: Code samples and descriptions for specific DIL use cases.
seo-title: DIL Use Cases and Code Samples
solution: Audience Manager
title: DIL-användningsexempel och kodexempel
uuid: 27995c2d-6572-438e-af99-b5477f090ae9
feature: DIL Implementation
exl-id: 001710be-b377-460a-9e29-7268d25a6305
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 2%

---

# DIL-användningsexempel och kodexempel{#dil-use-cases-and-code-samples}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av [!DNL Data Integration Library (DIL)] och [!DNL DIL] tillägg.
>
>Befintliga kunder kan fortsätta använda sina [!DNL DIL] implementering. Adobe kommer dock inte att utvecklas [!DNL DIL] bortom denna punkt. Kunder uppmanas att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för deras långsiktiga strategi för datainsamling.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

Kodexempel och beskrivningar för specifika fall för användning i DIL.

<!-- 

c_dil_use_case.xml

 -->

## Skicka dataelement till Audience Manager med DIL {#send-data-elements-dil}

Skapa en objektvariabel som skickar information om sidelement till Audience Manager. Detta är användbart för allmän datainsamling eller som ett alternativ till att samla in data med Analytics-variabler.

<!-- 

c_dil_send_page_objects.xml

 -->

**Beskrivning**

I följande kod visas hur du samlar in siddata och skickar dem till Audience Manager med [!UICONTROL DIL]. I de här exemplen används en variabel för att lagra dataelement i en platt lista eller en array. Kom ihåg, skicka in variabler som [nyckelvärdepar](../reference/key-value-pairs-explained.md). Observera även `c_` prefix före tangenten i nyckelvärdepar. Detta [obligatoriskt prefix](../features/traits/trait-variable-prefixes.md) identifierar information som användardefinierade data. I det första exemplet måste du lägga till manuellt `c_` till nyckeln. I det andra exemplet [!UICONTROL DIL] gör detta automatiskt åt dig.

**Behåll konsekventa värdeegenskaper**

Tänk på att värdeegenskaperna förblir desamma när du skickar data. Om du till exempel har två identiska nycklar med olika värden, prioriteras värdet för det sista nyckel/värde-paret framför föregående värdeobjekt. Skicka till exempel in `color:blue` och `color:red` anger det returnerade värdet till rött (skriver över blått).

**Exempel 1: Skicka data som nyckelvärdepar**

I det här grundläggande exemplet skickas färg- och prisdata till Audience Manager i form av nyckelvärdepar. Koden kan se ut ungefär så här:

<pre class="java"><code>
var sample_dil = DIL.create({partner:"<i>partner name</i>"}); 
sample_dil.api.signals({ 
   c_color:"blue", 
   c_price:"900" 
}); 
sample_dil.api.submit();
</code></pre>

**Exempel 2: Skicka data i ett objekt**

I det här avancerade exemplet visas hur du skickar data i ett objekt till Audience Manager. När du arbetar med den här metoden [!UICONTROL DIL] gör att du kan skicka ett objekt som en funktionsparameter till [!DNL signals()] -metod. [!UICONTROL DIL] Koden kan se ut ungefär så här:

<pre class="java"><code>
var my_object = { 
   color : "blue", 
   price : "900" 
}; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
//Load the object and append "c_" to all keys in the key-value pairs and send data to AudienceManager. 
sample_dil.api.signals(my_object,"c_").submit();
</code></pre>

**Exempel 3: Skicka siddata i en array**

I det här fallet är variabeln `my_object` använder en array för att lagra data. Det här exemplet bygger på den information som skickas med den rekommenderade metoden ovan, men lägger till ytterligare ett lager för en produkttyp och modell. Koden kan se ut ungefär så här:

<pre class="java"><code>
var my_objects = [{ 
   color : "blue", 
   price : "900" 
}, { 
   type : "acura", 
   model : "tl" 
}]; 
 
var sample_dil = DIL.create({ partner : "<i>partner name</i>" }); 
 
for (var i = 0; i < my_objects.length; i++) 
//Load the object and append "c_" to all the keys in the key-value pairs.  
{ 
    sample_dil.api.signals(my_objects[i], "c_"); 
} 
sample_dil.api.submit();
</code></pre>

## Hämta referens-URL {#capture-referring-url}

Hämta och skicka en refererande URL till Audience Manager.

<!-- 

c_dil_hrefer_over_https.xml

 -->

>[!NOTE]
>
>Den här metoden fungerar bara när användare flyttar mellan sidor med liknande protokoll (HTTP eller HTTPS). Webbläsaren behåller till exempel en refererande URL när du navigerar från en säker plats till en annan säker plats. Webbläsare behåller inte den refererande URL:en när du förflyttar dig mellan säkra och osäkra webbplatser. Detta beteende är normal webbläsarfunktionalitet och kan inte kringgås av [!UICONTROL DIL].

**Exempel på kod**

Koden kan se ut ungefär så här:

<pre class="java"><code>
var adobe_dil = DIL.create({ partner : "<i>partner name</i>" }); 
adobe_dil.api.signals({ d_referer : document.referrer }).submit();
</code></pre>

## Hämta sökmotortyper och sökvillkor för nyckelord {#capture-search-engine-types}

Skicka information om sökmotortyp och sökord till Audience Manager.

>[!IMPORTANT]
>
>I det här avsnittet beskrivs äldre funktioner, som inte stöds i de senaste versionerna av DIL.

**Sökmotorer som stöds**

Som standard `DIL.getSearchReferrer` känner igen sökningar från dessa sökmotorer (inklusive internationella varianter):

* [!DNL AOL]
* [!DNL Ask]
* [!DNL Bing]
* [!DNL Google]
* [!DNL Yahoo!]

**Beskrivning**

I följande kod visas hur du hämtar sökreferenten för någon av de sökmotorer som stöds. I det här fallet antar vi att en användare sökte efter termen &quot;hem&quot; från [!DNL Google] Kanada ( `www.google.ca`). Med den här koden kan du hämta de söktermerna och skicka dem till Audience Manager.

**Grundläggande kod**

Grundläggande kod för att hämta sökreferenten (från `google.com`, till exempel) ser ut så här:

```java
var search_referrer = DIL.tools.getSearchReferrer();
```

**Kodexempel för listad sökmotor**

I det här fallet antar vi att en användare sökte efter termen &quot;hem&quot; från [!DNL Google] Kanada ( `www.google.ca`). Observera hur koden prefixar det som krävs `c_` parameter till sökmotor ( `c_se`) och sökord ( `c_st`). `c_` är en [obligatoriskt prefix](../features/traits/trait-variable-prefixes.md) som identifierar dessa som kunddefinierade variabler för Audience Manager.

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

**Kodexempel för ej listad sökmotor**

I det här fallet antar vi att en användare sökte efter termen &quot;hem&quot; från `dogpile.com`. För [!DNL Dogpile] som standard inte stöds kan du konfigurera DIL så att sökmotorn identifieras och söktermerna returneras till Audience Manager. Koden kan se ut ungefär så här:

<pre class="java"><code>
var adobe_dil = DIL.create({partner:"<i>partner name</i>"}); 
var search_referrer = DIL.tools.getSearchReferrer(document.referrer, {  
    hostPattern:/dogpile\./, 
    queryParam:"q" 
}); 
 
if (search_referrer && search_referrer.valid) { 
  adobe_dil.api.signals({ 
    c_se : se.name, 
    c_st : se.keywords 
  }).submit(); 
}
</code></pre>

## Mappa nyckelvärden till andra nycklar {#map-key-values}

Associera värdet från ett nyckelvärdepar till en annan nyckel.

<!-- 

c_dil_map_keys.xml

 -->

**Beskrivning**

I ett nyckelvärdepar `c_` som läggs till nyckeln identifierar signalen som kunddefinierade data. Kunddefinierade data används för målanpassning på den specifika webbplats som skickade data i ett händelseanrop. Ibland vill du dock att den här informationen ska vara tillgänglig för alla egenskaper på ditt Audience Manager-konto. Det gör du genom att mappa värdet i en `c_` nyckelvärdepar till en plattformsnivå. En plattformsnivånyckel har prefixet `d_` och gör signalen tillgänglig för målinriktning över alla egenskaper i ditt konto.

Du kan till exempel samla in ZIP-koddata från en viss plats men vill rikta dem till alla dina Audience Manager-egenskaper. För att ZIP-koden ska vara tillgänglig på plattformsnivå kan du mappa en kunddefinierad postnummernyckel (t.ex. `c_zip`) till en plattformsdefinierad nyckel enligt nedan.

**Exempel på kod**

Koden kan se ut ungefär så här:

```java
var adobe_dil = DIL.create({ 
    partner : "adobe", 
    mappings : { 
        c_zip : 'd_zip', 
        d_key2 : 'h_dil_key2' 
    } 
}); 
adobe_dil.api.signals({c_zip : '10010'}).submit(); 
// Request will look like /event?c_zip=10010&d_zip=10010
```

## Traffic DIL in Google Tag Manager (GTM) {#traffic-dil-gtm}

Konfigurera och serva DIL med en GTM-tagg.

<!-- 

t_dil_google_tagmanager.xml

 -->

Den här proceduren förutsätter att du har en [!DNL Google Tag Manager] konto, viss kunskap om produkten och Audience Manager `dil.js` -fil.

För att köra `dil.js` fil i GTM:

1. Skapa en ny behållare eller öppna en befintlig behållare.
1. Lägg till en ny tagg i behållaren.
1. Öppna taggen för att redigera den och:

   * Ge taggen ett namn.
   * Välj **[!UICONTROL Custom HTML Tag]** från **[!UICONTROL Tag Type]** listruta.
   * Placera HTML i fältet [!UICONTROL DIL] kod (bibliotek + den anpassade koden) i script-taggar `<script>DIL code</script>`.
   * Klicka på **[!UICONTROL Save]**.

1. Publicera behållaren.
1. Generera behållartaggkod och placera den i lagret.

>[!MORELIKETHIS]
>
>* [Google Tag Manager Help Center](https://support.google.com/tagmanager#topic=3441530)
>* [Signaler](../dil/dil-instance-methods.md#signals)
>* [Prefixkrav för nyckelvariabler](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/traits/trait-variable-prefixes.html#prefix-requirements-for-key-variables)
