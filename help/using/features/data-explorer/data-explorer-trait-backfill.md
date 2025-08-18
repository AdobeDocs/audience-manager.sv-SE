---
description: Återfyll implementeringar av trait-egenskaper för att fånga in historiska målgrupper och undvika förlust av relevanta data före datumet då trait skapades.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: Realiseringar av bakåtfyllnad
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Realiseringar av bakåtfyllnad {#backfill-trait-realizations}

Återfyll implementeringar av trait-egenskaper för att fånga in historiska målgrupper och undvika förlust av relevanta data före datumet då trait skapades.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] är en premiumfunktion som förbättrar Audience Manager-upplevelsen genom att låsa upp ytterligare användningsfall. Bakgrundsfyllning kräver extra processorkraft och är tillgänglig för alla Audience Manager-kunder till en tillkommande kostnad. Kontakta din Adobe-återförsäljare för mer information.

När du skapar egenskaper utifrån oanvända signaler kan du välja att fylla i trait-implementeringarna igen under en viss tidsperiod. [!DNL Audience Manager] samlar in historiska data om målgrupper som kvalificerar sig för det nya varumärket och lagrar dem på motsvarande profil. Du kan se **[!UICONTROL Backfill Options]** i avsnittet [!UICONTROL Trait Expression] i **[Trait Builder](../../features/traits/about-trait-builder.md)**.

>[!NOTE]
>
>Ni kan omvända implementeringen av trait-egenskaper för regelbaserade och onboardbaserade egenskaper.

Så här fyller du i trait-implementeringar baklänges:

1. Gå till [!UICONTROL Audience Data > Signals > Search] och kör en signalsökning eller använd [signalkontrollpanelen](../../features/data-explorer/data-explorer-signals-dashboard.md) för att identifiera de signaler som ska användas i det nya traktet.
1. Skapa ett nytt spår baserat på de önskade signalerna.
1. Använd **[!UICONTROL Backfill Options]** i avsnittet **[!UICONTROL Trait Expression]** för att välja det tidsintervall för vilket du vill återfylla trait-realisationer. Fördefinierade intervall för bakgrundsfyllning omfattar 1, 7, 14 och 30 dagar. Du kan också välja ett anpassat datumintervall på upp till 30 dagar.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Valfritt) Klicka på **[!UICONTROL Estimate Realizations]** i avsnittet **[!UICONTROL Estimated Trait Realizations]** om du vill se de uppskattade [!UICONTROL Unique Trait Realizations] - och [!UICONTROL Total Trait Population]-värdena för den efterfyllda egenskapen under de senaste 7 dagarna.

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

## Svarstid för bakåtfyllnad av fack {#trait-backfilling-latency}

Nyligen skapade egenskaper som börjar fånga målgrupper två till tre timmar efter att de skapats. På grund av den stora datavolym som [!DNL Audience Manager] utför dagligen återspeglas emellertid inte den efterfyllda populationen omedelbart i diagrammen [!UICONTROL Unique Trait Realizations] och [!UICONTROL Total Trait Population].

Audience Manager uppdaterar [!UICONTROL Trait Graph] med den inmatade fyllningen inom 48 timmar efter att egenskaperna har skapats.

## Gräns för bakåtfyllnad av trait {#trait-backfilling-limit}

Med [!UICONTROL Data Explorer] kan du fylla upp till 50 traits per månad med en backfill-räknare som återställs den 1 dagen i varje månad.

>[!NOTE]
>
>Kvoten för bakåtfyllnad av trait överförs inte från tidigare månader. Om du t.ex. fyller 30 traits bakåt den här månaden återställs kvoten för bakåtfyllnad av trait för nästa månad till 50, inte 70.

## Inverkan på rapportering {#reporting-impact}

Omvända implementeringar av trait-egenskaper återspeglas i [!UICONTROL Unique Trait Realizations]- och [!UICONTROL Total Trait Population]-mätvärdena, eftersom [!DNL Audience Manager] omvandlar historiska signaler till trait-realiseringar.

[!UICONTROL Trait Graph], [!UICONTROL General Reports] och [!UICONTROL Trend Reports] uppdateras dock inte retroaktivt med historiska värden som är förifyllda innan det att egenskaperna skapades.
