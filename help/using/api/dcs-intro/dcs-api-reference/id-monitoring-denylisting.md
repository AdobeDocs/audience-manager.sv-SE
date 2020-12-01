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

[!DNL DCS] övervakar de ID som tas emot och lägger till de som skickas med ett ovanligt högt pris under en kort tidsperiod till ett blockeringslista.

## Översikt

För att skydda Audience Manager-infrastrukturen mot skadlig aktivitet använder [!DNL DCS] en avancerad algoritm för att övervaka de ID som den tar emot. Dessa kan vara [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) eller [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Mer information om vilka ID:n som stöds av Audience Manager finns i [Index för ID:n i Audience Manager](../../../reference/ids-in-aam.md).

[!DNL DCS] övervakar hur ofta de tar emot dessa ID:n för att upptäcka eventuell skadlig aktivitet. När [!DNL DCS] upptäcker ett ovanligt stort antal [!DNL DCS]-begäranden för ett givet ID på kort tid, läggs detta ID till i blockeringslista.

## Felkoder

Du kan identifiera ID:n som läggs till i en blockeringslista med hjälp av felkoderna som tas emot från [!DNL DCS]. Följande felkoder kan tas emot:

* 303: Blockerat kund-ID;
* 306: Blockerat deklarerat enhets-ID;
* 307: Spärrad profilåtgärd för ID.

Se [Felkoder, meddelanden och exempel](dcs-error-codes.md) för mer information om felkoder som du kan få.

## Tar bort ID:n från blockeringslista

ID:n som har lagts till i blockeringslista bör inte användas i framtida förfrågningar eftersom de leder till felaktig rapportering av data. [!DNL DCS] stöder inte borttagning av ID:n från blockeringslista.

## Påverkan på ID-synkronisering

[!DNL DCS] anrop kan innehålla en eller flera typer av ID:n. Samtal som innehåller ett enda ID ignoreras fullständigt om det ID:t läggs till i blockeringslista och ingen ID-synkronisering görs i den här situationen.

När ett anrop med flera ID även innehåller ett blocklist ID:n, ignorerar [!DNL DCS] det nekade ID:t och använder endast de återstående, tillåtna ID:n för synkronisering.

## Orsaker och korrigeringar för ID-Blockeringslistning

Den vanligaste orsaken till att ID:n läggs till i blockeringslista är den felaktiga integreringen mellan kundinfrastrukturen och Audience Manager. När du identifierar ett blocklist ID måste du noga granska dina Audience Manager-integreringar. I **Handböcker om implementering och integrering** finns detaljerade förklaringar om hur du bör konfigurera Audience Manager så att det fungerar med andra Experience Cloud-lösningar eller externa system.

En annan vanlig orsak till att ID:n läggs till i blockeringslista är indexering av botar (web crawlers), som vanligtvis orsakar ökad trafik, vilket leder till att samma ID:n skickas till [!DNL DCS] flera gånger. Om du identifierar att indexeringsobjekt är orsaken till att ID:n läggs till i blockeringslista bör du begränsa båda åtkomsten till webbplatsen.

Om du har svårt att identifiera integreringsproblem kan du kontakta kundsupport. Innan du öppnar en supportförfrågan måste du se till att din webbläsares `.har` `HTTP`-arkiv är klart. Detta arkiv hjälper supportteamet att identifiera varför ID:t lades till i en blockeringslista.