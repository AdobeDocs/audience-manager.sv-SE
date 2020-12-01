---
description: Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.
seo-description: Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 2%

---


# Flash DIL{#flash-dil}

Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] är ett  [!DNL ActionScript] kodbibliotek där du kan arbeta med videouppspelningsdata i Audience Manager. [!DNL Flash DIL] fungerar genom att hämta SWF-innehåll som Adobe- [!UICONTROL AppMeasurement] biblioteket skickar in till Analytics. [!DNL Flash DIL] skickar dessa data till den separata  [!UICONTROL DIL] JavaScript-datainsamlingsmodulen, som skickar informationen till Audience Manager. Analysdata ( [!UICONTROL Props], [!UICONTROL eVars], händelser osv.) som hämtats från [!DNL FLA]-filen är tillgänglig i Audience Manager som traits eller oanvända signaler.

## Krav för datainsamling {#requirements} för Flash DIL

Allmänna krav för implementering och kodrelaterade åtgärder.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementeringskrav**

[!UICONTROL Flash] datainsamling kräver:

* Klassbiblioteket [!UICONTROL DIL] ( `dil.swc`). Hämta [!UICONTROL DIL]-klassbiblioteket från din kontaktperson för Partner Solutions.

* JavaScript [!UICONTROL DIL] datainsamlingskod på sidan.
* [Biblioteket DIL ActionScript ](../dil/dil-flash.md#flash-dil-actionscript) läses in i det Flash-objekt som du vill samla in data från.
* Adobe [!DNL AppMeasurement] [!DNL AS]-biblioteket (version 3.5.2 eller senare) läste in [!DNL Flash]-objektet som du vill samla in data från.

**Ange AllowScriptAccess till  `Always` eller`sameDomain`**

`AllowScriptAccess` i HTML-koden som läser in en SWF-fil kontrollerar möjligheten att utföra utgående URL-åtkomst inifrån SWF-filen. När du konfigurerar en [!UICONTROL Flash DIL]-dataintegrering måste du se till att Flash-parametern `AllowScriptAccess` är inställd på `always` eller `sameDomain`. [!UICONTROL Flash DIL] datainsamlingen fungerar inte om  `AllowScriptAccess` den är inställd på  `never`. Se [Kontrollera åtkomst till skript eller värdwebbsida](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS- [!UICONTROL DIL] kodplacering**

Försök att placera datainsamlingsmodulen för JS [!UICONTROL DIL] på sidan så att den läses in före filen [!DNL FLA]. När [!DNL FLA]-filen läses in först, innan [!UICONTROL DIL]-datainsamlingen är klar, kan du missa de initiala datasignalerna som [!UICONTROL Flash DIL] skickar till den modulen. När datainsamlingsmodulen [!UICONTROL DIL] har instansierats hämtar den dock alla efterföljande SWF-fildata som skickas av [!UICONTROL Flash DIL].

## Data som samlats in av Flash DIL {#data-collected}

[!UICONTROL Flash DIL] hämtar sidvy, länkspårning, mediaspårning och andra medievyhändelser från Adobe- [!UICONTROL AppMeasurement] biblioteket.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Sidvyhändelser**

Om inget annat anges av `s.trackVars` samlar [!UICONTROL Flash DIL] in följande data från Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Händelser för länkspårning**

Om inget annat anges av `s.linkTrackVars`, samlar [!UICONTROL Flash DIL] in följande data från Adobe [!UICONTROL AppMeasurement]:

* `pe` (Typ av spårlänk har anropats)
* `pev1` (Länk-URL)
* `pev2`(Länktext)

**Mediespårningshändelser**

Om inget annat anges av `s.Media.trackVars` samlar [!UICONTROL Flash DIL] in alla data som räknas upp i avsnittet Sidvyhändelser.

**Andra datapunkter**

Data från dessa parametrar samlas in som standard:

* `mediaName` (Namn på medie-/videoelement)
* `mediaAdName` (annonsnamn)
* `mediaAdParentName` (Namnet på det primära mediainnehållet som annonsen är kapslad under)
* `mediaAdParentPod` (Poden eller annonsen bryts i det primära innehållet där annonsen spelas upp)
* `mediaAdParentPodPos` (Den numeriska positionen i rutan där annonsen spelas upp. Fler än en annons kan spelas upp i en ruta.

## Data från Flash DIL i Audience Manager {#flash-dil-data}

Modulen [!UICONTROL Flash DIL] förvandlar Adobe AppMeasurement-data till Audience Manager-egenskaper och oanvända signaler.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyserna [!UICONTROL Props], [!UICONTROL eVars] och händelser fungerar som egenskaper i Audience Manager. Fällor är nyckelvärdepar och används för att skapa segment. I en Analytics-prop som `c30=foo` är `c30` nyckeln (en konstant) och `foo` värdet (en variabel).

**Matcha Audience Manager-egenskaper mot analysvariabler**

Om du vill använda de analysdata som skickas av [!UICONTROL Flash DIL] måste du skapa Audience Manager-egenskaper med nyckelvärdet prefix med `c_`.

Se tabellen för exempel:

| Analysdataelement | Analysexempel | Som Audience Manager-trait |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **händelser** | `events=event10` | `c_events=event10` |

**DIL/Analysdata som oanvända signaler**

Audience Manager accepterar Analytics [!UICONTROL Props], [!UICONTROL eVars] och händelser även utan motsvarande egenskap. I det här fallet är data inte tillgängliga för att skapa egenskaper och visas i [rapporten Oanvända signaler](../reporting/dynamic-reports/unused-signals.md) i stället. För att få ut så mycket som möjligt av den här informationen skapar du Audience Manager-egenskaper som matchar de analysdata som skickas i [!UICONTROL Flash DIL]-biblioteket.

## Bibliotek för Flash-ActionScript{#flash-dil-actionscript}

Kod för [!DNL Flash]-objektet som ska skicka Analytics-data till Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* För varje [!DNL Flash]-objekt stöder koden endast en partnerinstans ( `d.partner`).
   >
   >
* Kräver Adobe [!UICONTROL AppMeasurement] [!DNL AS] biblioteksversion 3.5.2 eller senare.


```js
import com.omniture.AppMeasurement; // Omit this line if it already exists in the code 
import com.adobe.am.DIL; 
  
var s:AppMeasurement = new AppMeasurement(); // Omit this line if it already exists in the code 
var d:DIL = new DIL(); 
d.partner = "<partner>";// Partner name 
d.containerNSID = <container NSID>; // Optional, defaults to 0 
s.loadModule(d);
```

>[!MORELIKETHIS]
>
>* [Traits ](../features/traits/trait-details-page.md)
>* [Signaler, traits och segment](../reference/signal-trait-segment.md)
>* [Förklaring av nyckelvärdespar](../reference/key-value-pairs-explained.md)
>* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)

