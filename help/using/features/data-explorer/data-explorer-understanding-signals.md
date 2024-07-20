---
description: Signaler är den minsta informationsenheten inom Audience Manager. De representerar användarinteraktioner eller användaraktivitet i dina onlineegenskaper och skickas vidare till Audience Manager för att användas i varumärkesregler.
seo-description: Signals are the smallest unit of information within Audience Manager. They represent user interactions or user activity on your online properties, and get passed on to Audience Manager to be used in trait rules.
seo-title: Understanding Signals
title: Signaler
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
exl-id: 12ab53e5-302b-4a82-9d8e-07b60139c65e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Signaler

Signaler är den minsta informationsenheten inom Audience Manager. De representerar användarinteraktioner eller användaraktivitet i onlineegenskaperna och skickas vidare till Audience Manager för att användas i varumärkesregler.

[!DNL Audience Manager] använder nyckelvärdepar för att representera signaler. Följande signal kan till exempel indikera att en besökare har nått en webbsida som innehåller elektronik:

* `page = electronics`

[Kontrollpanelen för signaler](../../features/data-explorer/data-explorer-signals-dashboard.md) visar flera typer av signalattribut som du kan använda för att skapa nya egenskaper. Här följer en detaljerad bild av de tillgängliga signalegenskaperna:

* *Nyckelvärdepar* visar nyckelvärdepar för signalen som tas emot av [!DNL Audience Manager].
* *Signaltyp* beskriver kategorin för varje signal. Signaler hör till någon av följande kategorier:
   * [Loggfiler som kan användas](/help/using/integration/media-data-integration/actionable-log-files.md): realtidssignaler som tas emot från dina loggfiler för medieprestanda;
   * [!DNL Adobe Analytics]: realtidssignaler från ditt [!DNL Adobe Analytics]-konto;
   * Allmänna online-data: realtidsdata som genereras av målgruppsaktiviteten och som inte ingår i loggfiler som kan användas och [!DNL Adobe Analytics];
   * Registrerade poster: data som mottagits via batchdataöverföringar.
* *Signal Source* beror på signaturtypen:
   * För signerade signaler är signalkällan datakällans namn.
   * För signaler som kommer från [!DNL Adobe Analytics] är datakällan alltid en rapportserie.
   * För loggfiler som kan användas och allmänna online-data visas ingen information om signalkällan.
* *Totalt antal* visar det totala antalet gånger som en realtidssignal har tagits emot av [!DNL Audience Manager] under de senaste 7 dagarna.
* *Ingår i Traits* och visar om signalen är en del av något av egenskaperna. Klicka på pilen för att se vilka egenskaper som innehåller motsvarande signal. För signaler som inte ingår i någon egenskap ändras kolumnvärdet till [!UICONTROL Create Onboarded Trait] eller [!UICONTROL Create Rule-Based Trait].

## Uppdateringsfrekvens för signaldata

På grund av den stora mängd data som Audience Manager dagligen bearbetar, uppdaterar [!UICONTROL Data Explorer] de visade signaldata med fasta tidsintervall, beroende på signaltypen:

* Signaldata i realtid (hanterbara loggfiler, [!DNL Adobe Analytics]-data och allmänna onlinedata) uppdateras var 4:e till 6:e timme.
* Signaldata uppdateras var 24: e timme.

## Relaterade begrepp

[Signaler, traits och segment](/help/using/reference/signal-trait-segment.md)
