---
description: Beskriver metoder i namnutrymmet DIL.modules. Med dessa moduler kan du programmässigt samla in data och arbeta med Audience Manager-objekt.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL Modules
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 0%

---

# DIL Modules{#dil-modules}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

Beskriver metoder i namnområdet `DIL.modules`. Med dessa moduler kan du programmässigt samla in data och arbeta med Audience Manager-objekt.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Fungerar med [!UICONTROL DIL] för att skicka [!DNL Analytics]-taggelement (variabler, props, eVars osv.) till Audience Manager. Returnerar data i en kommaavgränsad lista. Finns i version 2.6.

**Funktionssignatur:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>Du måste placera den här koden på sidan *före* funktionen `s.t();`.

<!-- 

r_dil_sc_init.xml

 -->

**Parametrar**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namn </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> Sträng </td> 
   <td colname="col3"> <p>En matris med strängar som innehåller ouppräknade <span class="keyword"> Analytics </span>-variabler som <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code> osv. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>En array med objekt som innehåller uppräknade <span class="keyword"> Analytics </span>-variabler som props och evar (t.ex. <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Heltal </td> 
   <td colname="col3"> <p>Anger hur många itererade namn du vill returnera. Om du till exempel vill returnera två avhandlingar eller varv anger du <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ett objekt som representerar objektet <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ett objekt som representerar <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Objekt </td> 
   <td colname="col3"> <p>Ytterligare alternativ: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Om du inte anger något annat ersätts punkter med standardunderstrecket ( _ ). </p> <p><code> s.contextData = {abc.def = '123'} </code> skulle till exempel resultera i <code> c_contextData_abc_def=123 </code> i frågesträngen för händelsanropet. </p> <p>Det här alternativet är endast tillgängligt i <span class="wintitle"> DIL </span> version 5.0 eller senare. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p><code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> skulle till exempel resultera i att strängarrayen filtreras från datainsamlingen för kontextdata. Det här alternativet utesluter PII (Personally Identiitable Information). </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Data som samlats in av siteCatalyst.init**

Den här funktionen returnerar information om följande [!DNL Analytics]-egenskaper:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1-75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Exempelkod**

Den här koden skapar en kommaavgränsad lista med [!DNL Analytics] händelser (props, eVars osv.) om det finns värden för dem.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

Om du vill spåra alla övervakade [!DNL Analytics]-datapunkter utan den tilläggsfunktion som visas ovan, anropar du `siteCatalyst.init` separat så här:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

Funktionen `GA.submitUniversalAnalytics();` skickar data från Google [!DNL Universal Analytics] till Audience Manager. Den här [!UICONTROL DIL]-funktionen är utformad för att fungera med `analytics.js`, som är det senaste kodbiblioteket för Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] har ingen insikt i eller kontroll över Google `analytics.js`-kodbiblioteket. Du bör verifiera att datainsamlingen [!UICONTROL DIL] fortfarande fungerar om eller när Google släpper nya versioner av `analytics.js`.
>
>* Du kan inte använda `GA.submitUniversalAnalytics();` om du fortfarande arbetar med spårningskod för tidigare Google-analyser (t.ex. `ga.js` eller `dc.js`). Se [GA.init](../dil/dil-modules.md#ga-init) i stället.
>

**Funktionssignatur:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Egenskaper**

Funktionen `GA.submitUniversalAnalytics();` accepterar följande egenskaper.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Egenskap </th> 
   <th colname="col2" class="entry"> Beskrivning </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>Den globala variabeln för din instans av <span class="keyword"> Google Analytics </span>. Detta är vanligtvis <code> ga </code> som standard, såvida du inte har anpassat din <span class="keyword"> Google Analytics </span> -kod. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>Variabeln som representerar din instans av <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Valfritt)</i> I biblioteket <code> analytics.js </code> är egenskapen internal den minifierade variabeln <code> 'b' </code>. Den här variabeln innehåller <span class="keyword"> Google Analytics </span>-data. </p> <p>Den här egenskapen är valfri eftersom du inte behöver ange den om inte Google ändrar namnet på deras interna variabel. Om den här minifierade variabeln till exempel har ändrats till <code> 'a' </code> anropar du <code> GA.submitUniversalAnalytics(); </code> så här: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Exempel**

Kom ihåg att definiera objektet [!DNL Google Analytics] `ga` först, innan du anropar [!UICONTROL DIL] och `GA.submitUniversalAnalytics();`. Koden kan se ut ungefär så här:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

Funktionen `GA.init()` skickar data från den gamla/ersatta versionen av [!DNL Google Analytics] till Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` fungerar bara med Google äldre analytikspårningskod, `ga.js` eller `dc.js`. Du kan inte anropa den här [!UICONTROL DIL]-funktionen om du använder `analytics.js`, som är det senaste kodbiblioteket för Google [!DNL Universal Analytics]. [!DNL Audience Manager] kunder som använder [!UICONTROL DIL] och [!DNL Universal Analytics] bör läsa [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Funktionssignatur:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parametrar**

| Namn | Typ | Beskrivning |
|---|---|---|
| `_gaq` | Array | En array som innehåller GA-kommandon. |
| `dilInstance` | Objekt | Ett objekt som innehåller DIL-instansen. |
| `trackVars` | Objekt | *(Valfritt)* Ett objekt som består av egenskapen `names`. Den här egenskapen är en array med GA-kommandonamn som du vill spåra. |

**GA-funktionsanrop som stöds**

Som standard hämtar `GA.init` data från följande funktioner:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL skapar nycklar för GA-data**

Audience Manager godkänner data i form av nyckelvärdepar medan GA arbetar med objekt i en array. Om du vill arbeta med GA-data skapar [!UICONTROL DIL] automatiskt ett nyckelvärdepar och skapar en nyckel som den här: `c_ <key name>`. Dessutom visas objekt i GA-arrayer i en viss ordning. Därför måste du ange alla parametrar i den ordningen, även om de inte innehåller några data. [!UICONTROL DIL] mappar nycklar för följande GA-metoder:

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Exempelkod**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Om du vill spåra alla övervakade GA-mått utan den ytterligare funktion som visas ovan, anropar du `GA.init` separat så här:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Exempel på händelseanrop**

URL-händelseanropet till Audience Manager kan se ut ungefär så här:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics Tracking Code](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Fullständig webbuppgradering: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Lägger till analytics.js på din webbplats](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [ga-objektmetodreferens](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
