---
description: En översikt på hög nivå över hur Audience Manager utbyter information med andra dataleverantörer och system.
seo-description: En översikt på hög nivå över hur Audience Manager utbyter information med andra dataleverantörer och system.
seo-title: Metoder för dataintegrering
solution: Audience Manager
title: Metoder för dataintegrering
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Metoder för dataintegrering {#data-integration-methods}

En översikt på hög nivå över hur Audience Manager utbyter information med andra dataleverantörer och system.

## Dataintegreringsmetoder som stöds: Realtid och server-till-server {#supported-methods}

Vilken integreringsmetod som passar bäst beror på en kombination av affärskrav och den tekniska kapaciteten hos din datapartner. Audience Manager utbyter besökarinformation med andra dataleverantörer på något av följande sätt:

* **Realtid:** Överför data direkt när en användare besöker webbplatsen. Den här metoden kallas även för en *`synchronous`* integrering.
* **Grupp (server till server):** Överför data mellan servrar enligt ett angivet schema när en besökare har lämnat sidan. Den här metoden kallas även för en *`out-of-band`* eller *`asynchronous`* integration.

## Förutsättningar: Skapa en egen taxonomi {#prereqs}

Kom ihåg att [skapa egenskaper](../features/traits/create-onboarded-rule-based-traits.md) och en [mappstruktur](../features/traits/trait-storage.md#create-trait-storage-folder) i [!DNL Audience Manager] användargränssnittet innan integreringsprocessen börjar. Taxonomin innehåller alla egenskaper som är ordnade i en logisk hierarki.

## Användningsexempel för integrering {#integration-use-cases}

En sammanfattning av dataintegreringsmetoderna i Audience Manager och fördelarna och nackdelarna med dem.

### Integrering mellan server och server i realtid

<!-- c_int_types_use_cases.xml -->

Dataintegrering mellan servrar och servrar i realtid synkroniserar snabbt användardata mellan Audience Manager-servrar och ett annat målsystem. I de flesta fall sker datautbyte inom några sekunder eller minuter, beroende på målinriktningssystemets uppdateringsfrekvens. Observera dock att målsystemet bestämmer det här uppdateringsintervallet, inte Audience Manager. Dessutom kan uppdateringsfrekvensen variera mellan olika system. En realtidsintegrering mellan servrar och servrar är den bästa integrationstypen för datautbyte. Audience Manager använder den här metoden när målgruppspartners kan stödja den.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Fördelar: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Gör att du kan kvalificera användare för segment utan att visa dem igen på sidan, i en videospelare osv. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Minskar antalet HTTP-anrop från sidan. Färre samtal hjälper till att bevara användarupplevelsen. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Hjälper er med tidskänslig målinriktning så att ni snabbt kan vidta åtgärder mot en kvalificerad användare. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Användbart när du går över till en DSP för målgruppsanpassning utanför webbplatsen. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nackdelar:</td>
  <td class="stentry"> Mindre användbar för målgruppsanpassning på plats när du behöver rikta in dig på användaren på samma sida, eller på nästa sida, baserat på om användaren kvalificerar sig för segmentet.</td>
 </tr>
</table>

### Batchintegrering mellan servrar

En server-till-server-batchintegrering paketerar data och skickar dem till andra system vid bestämda intervall i stället för i nära realtid. Dataöverföringsintervallen startar från 24 timmar. Vissa dataleverantörer stöder endast den här integrationstypen. Vi har dock sett en allmän trend från gruppintegreringar till realtidsintegreringsmetoder.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Fördelar: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Gör att du kan kvalificera användare för segment utan att visa dem igen på sidan, i en videospelare osv. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Användbar för målgruppsanpassning som inte är tidskänslig. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nackdelar:</td>
  <td class="stentry"> Synkroniseringsintervallet kan fördröja mål mot de senaste data.</td>
 </tr>
</table>

### Realtidsanrop

Realtidsanrop utbyter data med Audience Manager direkt när en användare besöker er webbplats eller vidtar åtgärder på sidan. Med den här metoden får målgruppssystem den senaste informationen om segmentkvalificering och kan ta hänsyn till den informationen vid beslut om innehåll eller annonsleverans. Den här processen fungerar även med utgivarannonsservrar där vi uppdaterar kvalificerade segment till en cookie som läses in i ett annonsanrop som nyckelvärdepar. För närvarande använder Audience Manager anrop i realtid för att integrera med [!DNL Target] och andra system för innehållshantering.

<table> 
 <tr>
  <td> <p>Fördelar: </p></td>
  <td> <p> Gör att du kan rikta in dig på nästa sida, innehållsområde eller annonsvisning baserat på den senaste segmentkvalificeringen. </p></td> 
 </tr> 
 <tr>
  <td> <p>Nackdelar: </p></td>
  <td> <p>Lägger till ett anrop till Audience Manager från sidan.</p></td>
 </tr> 
</table>


### Pixlar synkroniseras med målsystem

Pixelsynkronisering mappar segment till pixlar på sidan. Pixeln utlöser och överför data när en användare kvalificerar sig för ett visst segment. Pixelsynkronisering är en elementär och otillförlitlig dataöverföringsmekanism. Dataleverantörer och system använder dem sällan.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Fördelar: </p></td>
  <td class="stentry"> <p> Dataöverföringar i realtid. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Nackdelar: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Kan lägga till många klientsamtal från sidan. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Otillförlitlig för dataöverföring. 5 till 20% minskning är normal. </li>
   </ul></td>
 </tr> 
</table>

## Så här väljer du en leveransmetod för data {#data-delivery-choices}

Beskriver tekniska och affärsmässiga orsaker till att skicka data via synkrona (realtid) eller asynkrona (server-till-server) metoder.

<!-- c_int_delivery_choices.xml -->

### Välja en dataleveranstyp

* **Tekniska överväganden:** Leverans av data är beroende av dataparameterns tekniska kapacitet. Audience Manager kan skicka/ta emot data i realtid från webbläsaren eller via batchuppdateringar via kommunikationsprocesser som är offline, från server till server.
* **Business Considerations:** Vilka affärsorsaker du kan använda för att välja en leveransmetod eller en annan beror på den tekniska kapaciteten hos målpartnern och hur du vill använda dessa data. Vanligtvis är synkrona dataöverföringar användbara när du behöver vidta åtgärder mot användardata omedelbart. Asynkrona dataöverföringar kan vara användbara när det inte krävs någon omedelbar åtgärd och när du har tid att skapa djupare användarprofiler för senare bruk.

## Dataöverföringsprocess i realtid {#real-time-data-transfer-process}

En allmän översikt över hur Audience Manager utför ett synkront datautbyte med en tredjepartsleverantör.

### Dataöverföring i realtid

<!-- c_int_overview_sync.xml -->

Dataöverföringar i realtid skickar och tar emot segment-ID:n när en användare besöker eller vidtar åtgärder på webbplatsen. Synkrona dataöverföringar är vanligtvis användbara när du behöver kvalificera eller segmentera användare direkt när de navigerar i lagret.

### Dataintegrering i realtid

Integreringen av data i realtid fungerar på följande sätt:

1. En användare besöker en kunds webbplats som innehåller Audience Manager-kod.
1. Audience Manager läser in en Iframe och anropar [!UICONTROL Data Collection Server] ([!UICONTROL DCS]).
1. Servern [!UICONTROL DCS] anropar tredjepartsservern (i realtid) för att kontrollera om leverantören har någon segmentinformation om användaren.
1. Den tredje parten returnerar segmentinformation om den användaren till Audience Manager.
1. Audience Manager importerar segmentinformation och gör den tillgänglig för målinriktning.

![](assets/rt_reduce70.png)

## Batchdataöverföringsprocess {#batch-data-transfer-process}

En allmän översikt över hur Audience Manager utbyter data synkront (i realtid) med en tredjepartsleverantör.

### Gruppdataintegrering

<!-- c_int_overview_async.xml -->

Batchdataintegreringsprocessen (server-till-server) följer de flesta av de steg som beskrivs i dataöverföringsprocessen i realtid. I stället för att omedelbart returnera segment-ID:n sparas användarinformationen på våra servrar och synkroniseras med en tredjepartsleverantör med regelbundna intervall. Den asynkrona dataöverföringsprocessen är användbar när:

* Omedelbara dataöverföringar krävs inte.
* Samla in data för att skapa en stor grupp segmenterade användare.
* Du vill minska datameddelanden och `HTTP` samtal från webbläsaren.

### Steg för gruppdataintegrering

1. En användare besöker en kundwebbplats.
1. Audience Manager och tredjepartsleverantören av data tilldelar besökaren ett unikt ID (vanligtvis med en cookie).
1. Audience Manager anropar tredjeparts dataleverantör för att matcha besökar-ID:n.
1. En schemalagd begäran utbyter vanligtvis data om besökarsegment dagligen mellan Audience Manager och din tredjepartsleverantör av data.

![](assets/s2s_70.png)

Information som beskriver tidsramarna när Audience Manager bearbetar inkommande och utgående filöverföringar från Server till server ([!UICONTROL S2S]) finns i Riktlinjer [för](../reference/reporting-file-transfer-timeframe.md)rapportering och filöverföring.
