---
description: DCS övervakar ID:n som tas emot och lägger till ID:n som skickas med en ovanligt hög hastighet under en kort tidsperiod till blockeringslista.
keywords: id;monitoring;dcs
seo-description: DCS övervakar ID:n som tas emot och lägger till ID:n som skickas med en ovanligt hög hastighet under en kort tidsperiod till blockeringslista.
seo-title: ID-övervakning och Blockeringslistning
solution: Audience Manager
title: ID-övervakning och Blockeringslistning
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-övervakning och Blockeringslistning

Kontrollerar de ID:n som [!DNL DCS] tas emot och lägger till dem som skickas med ett ovanligt högt pris till ett blockeringslista under en kort tidsperiod.

## Översikt

För att skydda Audience Manager-infrastrukturen mot skadlig aktivitet [!DNL DCS] använder man en avancerad algoritm för att övervaka de ID som den tar emot. Dessa kan vara [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) eller [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Se [Index med ID:n i Audience Manager](../../../reference/ids-in-aam.md) för detaljerade förklaringar av de ID:n som stöds av Audience Manager.

Den övervakar hur ofta den tar emot dessa ID:n för att upptäcka eventuell skadlig aktivitet. [!DNL DCS] När ett ovanligt stort antal [!DNL DCS] [!DNL DCS] begäranden för ett visst ID upptäcks på kort tid, läggs detta ID till i blockeringslista.

## Felkoder

Du kan identifiera ID:n som läggs till i ett blockeringslista med hjälp av de felkoder som tas emot från [!DNL DCS]. Följande felkoder kan tas emot:

* 303: Blockerat kund-ID;
* 306: Blockerat deklarerat enhets-ID;
* 307: Spärrad profilåtgärd för ID.

Mer information om felkoder som du kan få finns i [Felkoder, meddelanden och exempel](dcs-error-codes.md) för DCS.

## Tar bort ID:n från blockeringslista

ID:n som har lagts till i blockeringslista bör inte användas i framtida förfrågningar eftersom de leder till felaktig rapportering av data. Det går [!DNL DCS] inte att ta bort ID:n från blockeringslista.

## Påverkan på ID-synkronisering

[!DNL DCS] anrop kan innehålla en eller flera typer av ID:n. Samtal som innehåller ett enda ID ignoreras fullständigt om det ID:t läggs till i blockeringslista och ingen ID-synkronisering görs i den här situationen.

När ett anrop med flera ID även innehåller ett blocklist ID:n, ignoreras det [!DNL DCS] och endast de återstående, tillåtna ID:n används för synkronisering.

## Orsaker och korrigeringar för ID-Blockeringslistning

Den vanligaste orsaken till att ID:n läggs till i blockeringslista är den felaktiga integreringen mellan kundinfrastrukturen och Audience Manager. När du identifierar ett blocklist ID måste du noga granska dina Audience Manager-integreringar. Se **Implementerings- och integreringsguider** för detaljerade förklaringar av hur du bör konfigurera Audience Manager för att arbeta med andra Experience Cloud-lösningar eller externa system.

En annan vanlig orsak till att ID:n läggs till i blockeringslista är indexering av botar (web crawlers), som vanligtvis leder till ökad trafik, vilket leder till att samma ID:n skickas till [!DNL DCS] flera gånger. Om du identifierar att indexeringsobjekt är orsaken till att ID:n läggs till i blockeringslista bör du begränsa båda åtkomsten till webbplatsen.

Om du har svårt att identifiera integreringsproblem kan du kontakta kundsupport. Innan du öppnar en supportförfrågan måste du se till att `.har` webbläsarens `HTTP` arkiv är klart. Detta arkiv hjälper supportteamet att identifiera varför ID:t lades till i en blockeringslista.