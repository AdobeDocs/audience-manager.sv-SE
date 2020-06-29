---
description: DCS övervakar de ID som tas emot och lägger till de ID som skickas med ett ovanligt högt pris under en kort tidsperiod till en lista över nekade.
keywords: id;monitoring;dcs
seo-description: DCS övervakar de ID som tas emot och lägger till de ID som skickas med ett ovanligt högt pris under en kort tidsperiod till en lista över nekade.
seo-title: ID-övervakning och Neka-lista
solution: Audience Manager
title: ID-övervakning och Neka-lista
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-övervakning och Neka-lista

Kontrollerar de ID:n som den tar emot och lägger till de ID:n som skickas med en ovanligt hög hastighet under en kort tidsperiod i en nekandelista. [!DNL DCS]

## Översikt

För att skydda Audience Manager-infrastrukturen mot skadlig aktivitet [!DNL DCS] använder man en avancerad algoritm för att övervaka de ID som den tar emot. Dessa kan vara [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s) eller [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Se [Index med ID:n i Audience Manager](../../../reference/ids-in-aam.md) för detaljerade förklaringar av de ID:n som stöds av Audience Manager.

Den övervakar hur ofta den tar emot dessa ID:n för att upptäcka eventuell skadlig aktivitet. [!DNL DCS] När användaren upptäcker ett ovanligt stort antal [!DNL DCS] [!DNL DCS] begäranden för ett visst ID på kort tid, läggs detta ID till i en nekandelista.

## Felkoder

Du kan identifiera ID som har lagts till i en nekandelista med de felkoder som har tagits emot från [!DNL DCS]. Följande felkoder kan tas emot:

* 303: Blockerat kund-ID;
* 306: Blockerat deklarerat enhets-ID;
* 307: Spärrad profilåtgärd för ID.

Mer information om felkoder som du kan få finns i [Felkoder, meddelanden och exempel](dcs-error-codes.md) för DCS.

## Tar bort ID:n från neka-listor

ID:n som har lagts till i neka listor bör inte användas i framtida begäranden eftersom de leder till felaktig datarapportering. Det går [!DNL DCS] inte att ta bort ID:n från neka-listor.

## Påverkan på ID-synkronisering

[!DNL DCS] anrop kan innehålla en eller flera typer av ID:n. Anrop som innehåller ett enda ID ignoreras fullständigt om det ID:t läggs till i en nekandelista och ingen ID-synkronisering sker i den här situationen.

När ett anrop med flera ID även innehåller ett ID som inte finns med, ignoreras det ID som nekas och endast de återstående, tillåtna ID:n används för synkronisering. [!DNL DCS]

## Orsaker till och korrigeringar för ID-neylisting

Den vanligaste orsaken till att ID:n läggs till för att neka listor är den felaktiga integreringen mellan kundinfrastrukturen och Audience Manager. När du identifierar ett identitetsregistrerat ID måste du noga granska dina Audience Manager-integreringar. Se **Implementerings- och integreringsguider** för detaljerade förklaringar av hur du bör konfigurera Audience Manager för att arbeta med andra Experience Cloud-lösningar eller externa system.

En annan vanlig orsak till att ID:n läggs till i Neka-listor är indexeringsobjekt (web crawlers), som vanligtvis orsakar ökad trafik, vilket leder till att samma ID:n skickas till [!DNL DCS] flera gånger. Om du identifierar att indexeringsobjekt är orsaken till att ID:n läggs till i neka listor, bör du begränsa båda åtkomsten till webbplatsen.

Om du har svårt att identifiera integreringsproblem kan du kontakta kundsupport. Innan du öppnar en supportförfrågan måste du se till att `.har` webbläsarens `HTTP` arkiv är klart. Det här arkivet hjälper supportteamet att identifiera varför ID:t lades till i en nekandelista.