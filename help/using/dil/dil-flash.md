---
description: Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.
seo-description: Collect data sent from FLA files to Analytics and work with that information in Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
feature: DIL Implementation
exl-id: e530d893-db26-4411-8df7-9bb2df84b68e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 1%

---

# Flash DIL{#flash-dil}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) i stället.

Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] är ett [!DNL ActionScript]-kodbibliotek som gör att du kan arbeta med videouppspelningsdata i Audience Manager. [!DNL Flash DIL] fungerar genom att hämta SWF-innehåll som Adobe [!UICONTROL AppMeasurement]-biblioteket skickar in till Analytics. [!DNL Flash DIL] skickar dessa data till den separata datainsamlingsmodulen för [!UICONTROL DIL] JavaScript, som skickar informationen till Audience Manager. Analysdata ( [!UICONTROL Props], [!UICONTROL eVars], händelser osv.) som hämtats från filen [!DNL FLA] finns i Audience Manager som traits eller oanvända signaler.

## Krav för datainsamling från Flash DIL {#requirements}

Allmänna krav för implementering och kodrelaterade åtgärder.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementeringskrav**

[!UICONTROL Flash]-datainsamling kräver:

* Klassbiblioteket [!UICONTROL DIL] ( `dil.swc`). Hämta klassbiblioteket [!UICONTROL DIL] från din kontaktperson för partnerlösningar.

* JavaScript [!UICONTROL DIL]-datainsamlingskod på sidan.
* [DIL ActionScript-biblioteket](../dil/dil-flash.md#flash-dil-actionscript) har lästs in i det dataobjekt som du vill samla in data från.
* Adobe [!DNL AppMeasurement] [!DNL AS]-biblioteket (version 3.5.2 eller senare) läste in det [!DNL Flash]-objekt som du vill samla in data från.

**Ange AllowScriptAccess till `Always` eller`sameDomain`**

Koden `AllowScriptAccess` i HTML som läser in en SWF-fil kontrollerar möjligheten att utföra utgående URL-åtkomst inifrån SWF-filen. När du konfigurerar en [!UICONTROL Flash DIL]-dataintegrering kontrollerar du att Flashen `AllowScriptAccess` är inställd på `always` eller `sameDomain`. Datainsamlingen [!UICONTROL Flash DIL] fungerar inte om `AllowScriptAccess` är inställd på `never`. Se [Kontrollera åtkomst till skript eller värdwebbsidan](https://helpx.adobe.com/se/flash/kb/control-access-scripts-host-web.html).

**JS [!UICONTROL DIL] Kodplacering**

Försök att placera datainsamlingsmodulen JS [!UICONTROL DIL] på sidan så att den läses in före filen [!DNL FLA]. När [!DNL FLA]-filen läses in först, innan [!UICONTROL DIL]-datainsamlingen är klar, kan du missa de initiala datareddelanden som [!UICONTROL Flash DIL] skickar till den modulen. När datainsamlingsmodulen [!UICONTROL DIL] väl har instansierats kommer alla efterföljande SWF-fildata som skickas in av [!UICONTROL Flash DIL] att samlas in.

## Data som samlats in av Flash DIL {#data-collected}

[!UICONTROL Flash DIL] hämtar sidvy, länkspårning, mediespårning och andra medievyhändelser från Adobe [!UICONTROL AppMeasurement]-biblioteket.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Sidvyhändelser**

Om inget annat anges av `s.trackVars`, samlar [!UICONTROL Flash DIL] in följande data från Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Länkspårningshändelser**

Om inget annat anges av `s.linkTrackVars`, samlar [!UICONTROL Flash DIL] in följande data från Adobe [!UICONTROL AppMeasurement]:

* `pe` (typ av spårlänk anropades)
* `pev1` (länk-URL)
* `pev2`(Länktext)

**Mediespårningshändelser**

Om inget annat anges av `s.Media.trackVars`, samlar [!UICONTROL Flash DIL] in alla data som räknas upp i avsnittet Sidvyhändelser.

**Andra datapunkter**

Data från dessa parametrar samlas in som standard:

* `mediaName` (namn på medie-/videoelement)
* `mediaAdName` (annonsnamn)
* `mediaAdParentName` (Namnet på det primära mediainnehållet som annonsen är kapslad under)
* `mediaAdParentPod` (Stället eller annonsen bryts i det primära innehållet där annonsen spelas upp)
* `mediaAdParentPodPos` (Den numeriska positionen i rutan där annonsen spelas upp. Fler än en annons kan spelas upp i en ruta.

## Flash DIL data i Audience Manager {#flash-dil-data}

Modulen [!UICONTROL Flash DIL] förvandlar Adobe AppMeasurement-data till Audience Manager-egenskaper och oanvända signaler.

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyserna [!UICONTROL Props], [!UICONTROL eVars] och händelser fungerar som egenskaper i Audience Manager. Fällor är nyckelvärdepar och används för att skapa segment. I en Analytics-propp som `c30=foo` är till exempel `c30` nyckeln (en konstant) och `foo` värdet (en variabel).

**Matcha Audience Manager-egenskaper mot analysvariabler**

Om du vill använda de analysdata som skickas av [!UICONTROL Flash DIL] bör du skapa Audience Manager-egenskaper som har nyckelvärdet prefix med `c_`.

Se tabellen för exempel:

| Analysdataelement | Analysexempel | Som Audience Manager trait |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **händelser** | `events=event10` | `c_events=event10` |

**DIL/Analysdata som oanvända signaler**

Audience Manager accepterar Analytics [!UICONTROL Props], [!UICONTROL eVars] och händelser även utan någon motsvarande egenskap. I det här fallet är data inte tillgängliga för att skapa egenskaper och visas i rapporten [Oanvända signaler](../reporting/dynamic-reports/unused-signals.md) i stället. Om du vill få ut så mycket som möjligt av den här informationen skapar du Audience Manager-egenskaper som matchar de analysdata som skickas från biblioteket [!UICONTROL Flash DIL].

## ActionScriptet Flash DIL {#flash-dil-actionscript}

Kod för [!DNL Flash]-objektet som ska skicka Analytics-data till Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* För varje [!DNL Flash]-objekt stöder koden endast en partnerinstans ( `d.partner`).
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
>* [Traits](../features/traits/trait-details-page.md)
>* [Signaler, traits och segment](../reference/signal-trait-segment.md)
>* [Förklaring av nyckelvärdespar](../reference/key-value-pairs-explained.md)
>* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)
