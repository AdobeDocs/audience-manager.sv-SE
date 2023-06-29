---
description: Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 2%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av [!DNL Data Integration Library (DIL)] och [!DNL DIL] tillägg.
><br>
>Befintliga kunder kan fortsätta använda sina [!DNL DIL] implementering. Adobe kommer dock inte att utvecklas [!DNL DIL] bortom denna punkt. Kunder uppmanas att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för deras långsiktiga strategi för datainsamling.
><br>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] är en [!DNL ActionScript] kodbibliotek där du kan arbeta med videouppspelningsdata i Audience Manager. [!DNL Flash DIL] fungerar genom att hämta SWF-innehåll i Adobe [!UICONTROL AppMeasurement] biblioteket överförs till Analytics. [!DNL Flash DIL] skickar dessa data till den separata [!UICONTROL DIL] JavaScript-datainsamlingsmodulen som skickar informationen till Audience Manager. Analysdata ( [!UICONTROL Props], [!UICONTROL eVars], händelser osv.) som hämtats från [!DNL FLA] filen finns i Audience Manager som traits eller oanvända signaler.

## Krav för datainsamling från Flash DIL {#requirements}

Allmänna krav för implementering och kodrelaterade åtgärder.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementeringskrav**

[!UICONTROL Flash] datainsamling kräver:

* The [!UICONTROL DIL] klassbibliotek ( `dil.swc`). Hämta [!UICONTROL DIL] klassbibliotek från din kontaktperson för Partner Solutions.

* JavaScript [!UICONTROL DIL] datakod på sidan.
* [DIL ActionScript bibliotek](../dil/dil-flash.md#flash-dil-actionscript) som läses in i det Flash-objekt som du vill samla in data från.
* Adobe [!DNL AppMeasurement] [!DNL AS] biblioteket (version 3.5.2 eller senare) har läst in [!DNL Flash] objekt som du vill samla in data från.

**Ange AllowScriptAccess till `Always` eller`sameDomain`**

The `AllowScriptAccess` i HTML-kod som läser in en SWF-fil kontrollerar möjligheten att utföra utgående URL-åtkomst inifrån SWF-filen. När du konfigurerar en [!UICONTROL Flash DIL] dataintegrering, se till att Flash `AllowScriptAccess` parametern är inställd på `always` eller `sameDomain`. [!UICONTROL Flash DIL] datainsamlingen fungerar inte om `AllowScriptAccess` är inställd på `never`. Se [Kontrollera åtkomst till skript eller värdwebbsidan](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Kodplacering**

Försök att montera JS [!UICONTROL DIL] datainsamlingsmodulen på sidan så att den läses in före [!DNL FLA] -fil. När [!DNL FLA] filen läses in först, före [!UICONTROL DIL] datainsamlingen är klar kan du missa de initiala datameddelandena om att [!UICONTROL Flash DIL] skickar till den modulen. När den har instansierats [!UICONTROL DIL] datainsamlingsmodulen hämtar alla efterföljande SWF-fildata som skickas in av [!UICONTROL Flash DIL].

## Data som samlats in av Flash DIL {#data-collected}

[!UICONTROL Flash DIL] hämtar sidvy, länkspårning, mediaspårning och andra medievyhändelser från Adobe [!UICONTROL AppMeasurement] bibliotek.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Sidvyhändelser**

Om inte annat anges av `s.trackVars`, [!UICONTROL Flash DIL] samlar in följande data från Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Händelser för länkspårning**

Om inte annat anges av `s.linkTrackVars`, [!UICONTROL Flash DIL] samlar in följande data från Adobe [!UICONTROL AppMeasurement]:

* `pe` (Typ av spårlänk har anropats)
* `pev1` (Länk-URL)
* `pev2`(Länktext)

**Mediespårningshändelser**

Om inte annat anges av `s.Media.trackVars`, [!UICONTROL Flash DIL] samlar in alla data som räknas upp i avsnittet Sidvyhändelser.

**Andra datapunkter**

Data från dessa parametrar samlas in som standard:

* `mediaName` (Namn på medie-/videoelement)
* `mediaAdName` (annonsnamn)
* `mediaAdParentName` (Namnet på det primära mediainnehållet som annonsen är kapslad under)
* `mediaAdParentPod` (Poden eller annonsen bryts i det primära innehållet där annonsen spelas upp)
* `mediaAdParentPodPos` (Den numeriska positionen i rutan där annonsen spelas upp. Fler än en annons kan spelas upp i en ruta.

## Flash DIL data i Audience Manager {#flash-dil-data}

The [!UICONTROL Flash DIL] i ändras data från Adobe AppMeasurement till Audience Manager och oanvända signaler.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyser [!UICONTROL Props], [!UICONTROL eVars]och händelser fungerar som Audience Manager. Fällor är nyckelvärdepar och används för att skapa segment. I en Analytics-propp som `c30=foo`, `c30` är nyckeln (en konstant) och `foo` är värdet (en variabel).

**Matcha Audience Manager-egenskaper mot analysvariabler**

Använda de analysdata som skickas av [!UICONTROL Flash DIL]bör du skapa Audience Manager-egenskaper som har nyckelvärdet prefix med `c_`.

Se tabellen för exempel:

| Analysdataelement | Analysexempel | Som Audience Manager-trait |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **händelser** | `events=event10` | `c_events=event10` |

**DIL/Analysdata som oanvända signaler**

Audience Manager godkänner Analytics [!UICONTROL Props], [!UICONTROL eVars]och händelser även utan motsvarande egenskaper. I det här fallet är data inte tillgängliga för att skapas och visas i [Rapport om oanvända signaler](../reporting/dynamic-reports/unused-signals.md) i stället. För att få ut så mycket som möjligt av den här informationen skapar du Audience Manager-egenskaper som matchar de analysdata som skickas av [!UICONTROL Flash DIL] bibliotek.

## Biblioteket Flash DIL ActionScript {#flash-dil-actionscript}

Kod för [!DNL Flash] objekt för att skicka analysdata till Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* För varje [!DNL Flash] -objekt, koden stöder en partnerinstans ( `d.partner`).
>
>* Kräver Adobe [!UICONTROL AppMeasurement] [!DNL AS] biblioteksversion 3.5.2 eller senare.

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
