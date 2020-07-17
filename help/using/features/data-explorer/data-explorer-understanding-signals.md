---
description: Signaler är den minsta informationsenheten inom Audience Manager. De representerar användarinteraktioner eller användaraktivitet i dina onlineegenskaper och skickas vidare till Audience Manager för att användas i varumärkesregler.
seo-description: Signaler är den minsta informationsenheten inom Audience Manager. De representerar användarinteraktioner eller användaraktivitet i dina onlineegenskaper och skickas vidare till Audience Manager för att användas i varumärkesregler.
seo-title: Förstå signaler
title: Förstå signaler
uuid: 04a0554e-954e-484a-8838-9161ef416872
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 2%

---


# Förstå signaler

Signaler är den minsta informationsenheten inom Audience Manager. De representerar användarinteraktioner eller användaraktivitet i onlineegenskaperna och skickas vidare till Audience Manager för att användas i varumärkesregler.

[!DNL Audience Manager] använder nyckelvärdepar för att representera signaler. Följande signal kan till exempel indikera att en besökare har nått en webbsida som innehåller elektronik:

* `page = electronics`

På [signalkontrollpanelen](../../features/data-explorer/data-explorer-signals-dashboard.md) visas flera typer av signalattribut som du kan använda för att skapa nya egenskaper. Här följer en detaljerad bild av de tillgängliga signalegenskaperna:

* *Nyckelvärdepar* visar nyckelvärdepar för signalen som tas emot av [!DNL Audience Manager].
* *Signaltypen* beskriver varje signals kategori. Signaler tillhör en av följande kategorier:
   * [Loggfiler](/help/using/integration/media-data-integration/actionable-log-files.md)som kan användas: realtidssignaler som tas emot från dina loggfiler för mediaprestanda,
   * [!DNL Adobe Analytics]: realtidssignaler som tas emot från ditt [!DNL Adobe Analytics] konto;
   * Allmänna onlinedata: realtidsdata som genererats av målgruppsaktiviteten och som inte ingår i loggfiler och [!DNL Adobe Analytics];
   * Registrering ombord: data som tagits emot via batchdataöverföringar.
* *Signalkällan* beror på signaltypen:
   * För signerade signaler är signalkällan datakällans namn.
   * För signaler som kommer från [!DNL Adobe Analytics]är datakällan alltid en rapportserie.
   * För loggfiler som kan användas och allmänna online-data visas ingen information om signalkällan.
* *Totalt antal* visar det totala antalet gånger som en realtidssignal tagits emot av [!DNL Audience Manager] de senaste 7 dagarna.
* *I Traits* visas om signalen är en del av något av egenskaperna. Klicka på pilen för att se vilka egenskaper som innehåller motsvarande signal. För signaler som inte ingår i någon egenskap ändras kolumnvärdet till [!UICONTROL Create Onboarded Trait] eller [!UICONTROL Create Rule-Based Trait].

## Uppdateringsfrekvens för signaldata

På grund av den stora mängd data som Audience Manager dagligen behandlar, uppdaterar [!UICONTROL Data Explorer] signaldata som visas med fasta tidsintervall, beroende på signaltypen:

* Signaldata i realtid (användbara loggfiler, [!DNL Adobe Analytics] data och allmänna online-data) uppdateras var 4:e till 6:e timme.
* Signaldata uppdateras var 24: e timme.

## Relaterade begrepp

[Signaler, traits och segment](/help/using/reference/signal-trait-segment.md)