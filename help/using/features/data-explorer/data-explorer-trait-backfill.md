---
description: Återfyll implementeringar av trait-egenskaper för att fånga in historiska målgrupper och undvika förlust av relevanta data före datumet då trait skapades.
seo-description: Återfyll implementeringar av trait-egenskaper för att fånga in historiska målgrupper och undvika förlust av relevanta data före datumet då trait skapades.
seo-title: Efteretablering av realiserade traits
title: Efteretablering av realiserade traits
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# Efteretablering av realiserade traits {#backfill-trait-realizations}

Återfyll implementeringar av trait-egenskaper för att fånga in historiska målgrupper och undvika förlust av relevanta data före datumet då trait skapades.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] är en premiumfunktion som förbättrar Audience Manager genom att låsa upp ytterligare användningsfall. Bakgrundsfyllning kräver extra processorkraft och är tillgänglig för alla Audience Manager-kunder till en stegvis kostnad. Kontakta din säljare på Adobe för mer information.

När du skapar egenskaper utifrån oanvända signaler kan du välja att fylla i trait-implementeringarna igen under en viss tidsperiod. [!DNL Audience Manager] samlar in historiska data om målgrupper som kvalificerar sig för det nya varumärket och lagrar dem på motsvarande profil. Du kan se **[!UICONTROL Backfill Options]** i [!UICONTROL Trait Expression]-avsnittet i **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Ni kan återfylla trait-implementeringar för regelbaserade och onboardbaserade egenskaper.

Så här fyller du i trait-implementeringar baklänges:

1. Gå till [!UICONTROL Audience Data > Signals > Search] och kör en signalsökning eller använd kontrollpanelen [Signaler](../../features/data-explorer/data-explorer-signals-dashboard.md) för att identifiera de signaler som ska användas i det nya tradet.
1. Skapa ett nytt spår baserat på de önskade signalerna.
1. Använd **[!UICONTROL Backfill Options]** i **[!UICONTROL Trait Expression]**-avsnittet för att välja det tidsintervall för vilket du vill återfylla trait-realisationer. Fördefinierade intervall för bakgrundsfyllning omfattar 1, 7, 14 och 30 dagar. Du kan också välja ett anpassat datumintervall på upp till 30 dagar.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Valfritt) Klicka på **[!UICONTROL Estimate Realizations]** i **[!UICONTROL Estimated Trait Realizations]**-avsnittet för att se de uppskattade [!UICONTROL Unique Trait Realizations]- och [!UICONTROL Total Trait Population]-värdena för den efterfyllda egenskapen under de senaste 7 dagarna.

   ![estimat-trait-realizations](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Bakåtfyllning och uppskattning av trait är inte tillgängliga för traits med uttryck som använder följande operatorer:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Skapa trait.

När du är klar med att skapa ditt varumärke kommer du att se de efterfyllda realisationerna i implementeringsstatistiken.

Titta på videon nedan om du vill se en videogenomgång av hur du fyller ut traits baklänges.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Svarstid för traits-vikning {#trait-backfilling-latency}

Nyligen skapade egenskaper som börjar fånga målgrupper två till tre timmar efter att de skapats. På grund av den stora datavolym som [!DNL Audience Manager] utför dagligen reflekteras emellertid inte den efterfyllda populationen omedelbart i diagrammen [!UICONTROL Unique Trait Realizations] och [!UICONTROL Total Trait Population].

Audience Manager uppdaterar [!UICONTROL Trait Graph] med den efterfyllda populationen inom 48 timmar efter att egenskaperna har skapats.

## Anpassa gräns för påfyllnad {#trait-backfilling-limit}

[!UICONTROL Data Explorer] Med kan du fylla upp till 50 traits per månad med backfill-räknaren återställd den 1 dagen i varje månad.

>[!NOTE]
>
>Kvoten för bakåtfyllnad av trait överförs inte från tidigare månader. Om du t.ex. fyller 30 traits bakåt den här månaden återställs kvoten för bakåtfyllnad av trait för nästa månad till 50, inte 70.

## Inverkan på rapportering {#reporting-impact}

Omvända implementeringar av egenskaper återspeglas i [!UICONTROL Unique Trait Realizations]- och [!UICONTROL Total Trait Population]-mätvärdena, eftersom [!DNL Audience Manager] förvandlar historiska signaler till trait-realiseringar.

[!UICONTROL Trait Graph], [!UICONTROL General Reports] och [!UICONTROL Trend Reports] uppdateras dock inte retroaktivt med historiska värden som är förifyllda innan värdet skapades.