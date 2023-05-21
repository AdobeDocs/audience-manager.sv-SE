---
description: DCS övervakar ID:n som tas emot och lägger till ID:n som skickas med en ovanligt hög hastighet under en kort tidsperiod till blockeringslista.
keywords: id;övervakning;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID-övervakning och Blockeringslistning
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# ID-övervakning och Blockeringslistning

The [!DNL DCS] övervakar ID:n som tas emot och lägger till dem som skickas med ett ovanligt högt pris till ett blockeringslista under en kort tidsperiod.

## Översikt

För att skydda Audience Manager infrastruktur mot skadlig aktivitet ska [!DNL DCS] använder en avancerad algoritm för att övervaka de ID som den tar emot. Dessa kan [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), eller [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Se [Index för ID:n i Audience Manager](../../../reference/ids-in-aam.md) om du vill ha detaljerade förklaringar av de ID:n som stöds av Audience Manager.

The [!DNL DCS] övervakar hur ofta de tar emot dessa ID:n för att upptäcka eventuell skadlig aktivitet. När [!DNL DCS] identifierar en ovanligt stor mängd [!DNL DCS] begäranden om ett visst ID på kort tid, detta ID läggs till i blockeringslista.

## Felkoder

Du kan identifiera ID som har lagts till i en blockeringslista med hjälp av felkoderna som har tagits emot från [!DNL DCS]. Följande felkoder kan tas emot:

* 303: Blockerat kund-ID;
* 306: Blockerat deklarerat enhets-ID;
* 307: Spärrad profilåtgärd för ID.

Se [Felkoder, meddelanden och exempel för DCS](dcs-error-codes.md) om du vill ha information om felkoder som du kan få.

## Tar bort ID:n från blockeringslista

ID:n som har lagts till i blockeringslista bör inte användas i framtida förfrågningar eftersom de leder till felaktig rapportering av data. The [!DNL DCS] stöder inte borttagning av ID:n från blockeringslista.

## Påverkan på ID-synkronisering

[!DNL DCS] anrop kan innehålla en eller flera typer av ID:n. Samtal som innehåller ett enda ID ignoreras fullständigt om det ID:t läggs till i blockeringslista och ingen ID-synkronisering görs i den här situationen.

När ett anrop med flera ID även innehåller ett blocklist ID:n [!DNL DCS] ignorerar det nekade ID:t och använder bara de återstående, tillåtna ID:n för synkronisering.

## Orsaker och korrigeringar för ID-Blockeringslistning

Den vanligaste orsaken till att ID:n läggs till i blockeringslista är den felaktiga integreringen mellan kundinfrastrukturen och Audience Manager. När du identifierar ett blocklist ID måste du noga granska dina Audience Manager-integreringar. Se **Handböcker för implementering och integrering** om du vill ha detaljerade förklaringar om hur du bör konfigurera Audience Manager för att arbeta med andra lösningar från Experience Cloud eller externa system.

En annan vanlig orsak till att ID:n läggs till i blockeringslista är indexering av botar (web crawlers), som vanligtvis leder till ökad trafik, vilket leder till att samma ID:n skickas till [!DNL DCS] flera gånger. Om du identifierar att indexeringsobjekt är orsaken till att ID:n läggs till i blockeringslista bör du begränsa båda åtkomsten till webbplatsen.

Om du har svårt att identifiera integreringsproblem kan du kontakta kundsupport. Innan du öppnar en supportförfrågan måste du se till att `.har` `HTTP` webbläsararkivet är klart. Detta arkiv hjälper supportteamet att identifiera varför ID:t lades till i en blockeringslista.
