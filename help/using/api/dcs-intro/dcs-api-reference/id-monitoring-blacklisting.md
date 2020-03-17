---
description: DCS övervakar de ID som tas emot och svartlistar de som skickas med en ovanligt hög hastighet under en kort tidsperiod.
keywords: id;monitoring;blacklisting;dcs
seo-description: DCS övervakar de ID som tas emot och svartlistar de som skickas med en ovanligt hög hastighet under en kort tidsperiod.
seo-title: ID-övervakning och svartlistning
solution: Audience Manager
title: ID-övervakning och svartlistning
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID-övervakning och svartlistning

De ID:n som [!UICONTROL DCS] de tar emot övervakas och de som skickas med en ovanligt hög hastighet visas svarta under en kort tidsperiod.

## Översikt

För att skydda Audience Manager-infrastrukturen mot skadlig aktivitet [!UICONTROL DCS] använder man en avancerad algoritm för att övervaka de ID som den tar emot. Dessa kan vara [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) eller [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Se [Index med ID:n i Audience Manager](../../../reference/ids-in-aam.md) för detaljerade förklaringar av de ID:n som stöds av Audience Manager.

Den övervakar hur ofta den tar emot dessa ID:n för att upptäcka eventuell skadlig aktivitet. [!UICONTROL DCS] När användaren upptäcker ett ovanligt stort antal [!UICONTROL DCS] [!UICONTROL DCS] begäranden för ett visst ID på kort tid, blir detta ID svartlistat.

## Felkoder

Du kan identifiera svartlistade ID:n med hjälp av felkoderna som tas emot från [!UICONTROL DCS]. Följande felkoder kan tas emot:

* 303: Blockerat kund-ID;
* 306: Blockerat deklarerat enhets-ID;
* 307: Spärrad profilåtgärd för ID.

Mer information om felkoder som du kan få finns i [Felkoder, meddelanden och exempel](dcs-error-codes.md) för DCS.

## Ej svartlistning

Svartlistade ID:n bör inte användas i framtida förfrågningar eftersom de leder till felaktig datarapportering. Det finns [!UICONTROL DCS] inte stöd för avsvartlistning av ID:n.

## Påverkan på ID-synkronisering

[!UICONTROL DCS] anrop kan innehålla en eller flera typer av ID:n. Anrop som innehåller ett enda ID ignoreras helt om det ID:t är svartlistat och ingen ID-synkronisering sker i den här situationen.

När ett anrop med flera ID även innehåller ett svartlistat ID, ignoreras det svartlistade ID:t och endast de kvarvarande, ej svartlistade ID:n används för synkronisering. [!UICONTROL DCS]

## Orsaker till och korrigeringar för ID-svartlistning

Den vanligaste orsaken till att ID:n svartlistas är den felaktiga integreringen mellan kundinfrastruktur och Audience Manager. När du identifierar ett svartlistat ID ska du noga granska dina Audience Manager-integreringar. Se **Implementerings- och integreringsguider** för detaljerade förklaringar av hur du bör konfigurera Audience Manager så att det fungerar med andra Experience Cloud-lösningar eller externa system.

En annan vanlig orsak till svartlistade ID:n är indexering av botar (web crawlers), som vanligtvis orsakar ökad trafik, vilket leder till att samma ID skickas till [!UICONTROL DCS] flera gånger. Om du identifierar indexering som orsaken till svartlistning av ID bör du begränsa båda åtkomsten till webbplatsen.

Om du har svårt att identifiera integreringsproblem kan du kontakta kundsupport. Innan du öppnar en supportförfrågan måste du se till att `.har` webbläsarens `HTTP` arkiv är klart. Detta arkiv hjälper supportteamet att identifiera varför ID:t blev svartlistat.