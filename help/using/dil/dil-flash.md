---
description: Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.
seo-description: Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.
seo-title: Flash DIL
solution: Audience Manager
title: Flash DIL
uuid: 65833cfd-768e-4b16-95c5-debd8411df38
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Flash DIL{#flash-dil}

Samla in data som skickas från FLA-filer till Analytics och arbeta med den informationen i Audience Manager.

<!-- 

c_flash_dil_toc.xml

 -->

[!UICONTROL Flash DIL] är ett [!DNL ActionScript] kodbibliotek där du kan arbeta med videouppspelningsdata i Audience Manager. [!DNL Flash DIL] arbetar genom att hämta SWF-innehåll som Adobe- [!UICONTROL AppMeasurement] biblioteket skickar in till Analytics. [!DNL Flash DIL] skickar dessa data till den separata [!UICONTROL DIL] JavaScript-datainsamlingsmodulen, som skickar informationen till Audience Manager. Analysdata ( [!UICONTROL Props], [!UICONTROL eVars]händelser, etc.) som hämtats från [!DNL FLA] filen är tillgängliga i Audience Manager som traits eller oanvända signaler.

## Krav för Flash DIL-datainsamling {#requirements}

Allmänna krav för implementering och kodrelaterade åtgärder.

<!-- 

c_flash_dil_intro.xml

 -->

**Implementeringskrav**

[!UICONTROL Flash] datainsamling kräver:

* Klassbiblioteket [!UICONTROL DIL] ( `dil.swc`). Hämta [!UICONTROL DIL] klassbiblioteket från din Partner Solutions-kontakt.

* Kod för JavaScript- [!UICONTROL DIL] datainsamling på sidan.
* [DIL ActionScript-bibliotek](../dil/dil-flash.md#flash-dil-actionscript) som läses in i det Flash-objekt som du vill samla in data från.
* Adobe [!DNL AppMeasurement] [!DNL AS] library (version 3.5.2 eller senare) loaded the [!DNL Flash] object you want to collect data from.

**Ange AllowScriptAccess till`Always`eller`sameDomain`**

I HTML-koden `AllowScriptAccess` som läser in en SWF-fil kontrolleras möjligheten att utföra utgående URL-åtkomst inifrån SWF-filen. När du konfigurerar en [!UICONTROL Flash DIL] dataintegrering kontrollerar du att Flash- `AllowScriptAccess` parametern är inställd på `always` eller `sameDomain`. [!UICONTROL Flash DIL] datainsamlingen fungerar inte om `AllowScriptAccess` den är inställd på `never`. Se [Kontrollera åtkomst till skript eller värdwebbsida](https://helpx.adobe.com/flash/kb/control-access-scripts-host-web.html).

**JS-[!UICONTROL DIL]kodplacering**

Försök att placera JS- [!UICONTROL DIL] datainsamlingsmodulen på sidan så att den läses in före [!DNL FLA] filen. När [!DNL FLA] filen läses in först, innan [!UICONTROL DIL] datainsamlingen är klar, kan du missa de initiala datareddelanden som skickas till den modulen [!UICONTROL Flash DIL] . När datainsamlingsmodulen har instansierats kommer den emellertid att samla in alla efterföljande SWF-fildata som skickas in av [!UICONTROL DIL] [!UICONTROL Flash DIL].

## Data som samlats in av Flash DIL {#data-collected}

[!UICONTROL Flash DIL] hämtar sidvy, länkspårning, mediaspårning och andra medievyhändelser från Adobe- [!UICONTROL AppMeasurement] biblioteket.

<!-- 

r_flash_dil_data_collected.xml

 -->

**Sidvyhändelser**

Om inget annat anges av `s.trackVars`samlar [!UICONTROL Flash DIL] in följande data från Adobe AppMeasurement:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `prop1 - prop75`
* `eVar1 - eVar75`

**Händelser för länkspårning**

Om inget annat anges av `s.linkTrackVars`samlar [!UICONTROL Flash DIL] in följande data från Adobe [!UICONTROL AppMeasurement]:

* `pe` (Typ av spårlänk har anropats)
* `pev1` (Länk-URL)
* `pev2`(Länktext)

**Mediespårningshändelser**

Om inget annat anges av `s.Media.trackVars`samlar [!UICONTROL Flash DIL] in alla data som räknas upp i avsnittet Sidvyhändelser.

**Andra datapunkter**

Data från dessa parametrar samlas in som standard:

* `mediaName` (Namn på medie-/videoelement)
* `mediaAdName` (annonsnamn)
* `mediaAdParentName` (Namnet på det primära mediainnehållet som annonsen är kapslad under)
* `mediaAdParentPod` (Poden eller annonsen bryts i det primära innehållet där annonsen spelas upp)
* `mediaAdParentPodPos` (Den numeriska positionen i rutan där annonsen spelas upp. Fler än en annons kan spelas upp i en ruta.

## Flash DIL-data i Audience Manager {#flash-dil-data}

Modulen omvandlar Adobe AppMeasurement-data till egenskaper för Audience Manager och oanvända signaler. [!UICONTROL Flash DIL]

<!-- 

c_flash_dil_in_aam.xml

 -->

Analyser [!UICONTROL Props], [!UICONTROL eVars]händelser och händelser fungerar som egenskaper i Audience Manager. Fällor är nyckelvärdepar och används för att skapa segment. I en Analytics-propp som `c30=foo`är till exempel `c30` nyckeln (en konstant) och `foo` är värdet (en variabel).

**Matcha Audience Manager-egenskaper mot analysvariabler**

Om du vill använda de analysdata som skickas av [!UICONTROL Flash DIL]bör du skapa Audience Manager-egenskaper som har nyckelvärdet prefix med `c_`.

Se tabellen för exempel:

| Analysdataelement | Analysexempel | Som Audience Manager Trait |
|---|---|---|
| **prop** | `c30=foo` | `c_prop30=foo` |
| **evar** | `v35=bar` | `c_evar35=bar` |
| **händelser** | `events=event10` | `c_events=event10` |

**DIL/Analytics-data som oanvända signaler**

Audience Manager accepterar analyser [!UICONTROL Props][!UICONTROL eVars]och händelser även utan någon motsvarande egenskap. I det här fallet är data inte tillgängliga för att skapa egenskaper och visas i rapporten [](../reporting/dynamic-reports/unused-signals.md) Oanvända signaler i stället. För att få ut så mycket som möjligt av informationen skapar du egenskaper i Audience Manager som matchar de analysdata som skickas av [!UICONTROL Flash DIL] biblioteket.

## Flash DIL ActionScript Library {#flash-dil-actionscript}

Kod för ditt [!DNL Flash] objekt för att skicka Analytics-data till Audience Manager.

<!-- 

r_flash_dil_actionscript.xml

 -->

>[!NOTE]
>
>* För varje [!DNL Flash] objekt har koden bara stöd för en partnerinstans ( `d.partner`).
   >
   >
* Kräver Adobe [!UICONTROL AppMeasurement][!DNL AS] Library version 3.5.2 eller senare.


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
>* [Signaler, egenskaper och segment](../reference/signal-trait-segment.md)
>* [Förklaring av nyckelvärdepar](../reference/key-value-pairs-explained.md)
>* [Prefixkrav för nyckelvariabler](../features/traits/trait-variable-prefixes.md)


<!-- Victor/Vlad: Do we still need this link? It doesn't look like this content has been migrated.
>* [AppMeasurement Flash, Flex, and OSMF Implementation Guide](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/flash/)
-->
