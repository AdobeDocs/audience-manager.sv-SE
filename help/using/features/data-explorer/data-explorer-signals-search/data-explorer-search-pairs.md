---
description: Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Söksignaler efter nyckelvärdepar
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 0%

---

# Sök signaler med nyckelvärdepar {#search-signals-by-key-value-pairs}

Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
Om du vill söka efter fler än en signal klickar du på knappen ![Lägg till](assets/icon_add.png) . Ange de nyckelvärdepar som du vill söka efter och använd sedan följande filter för att begränsa resultatet.

* **Signalstatus**: sök efter signaler som ingår i egenskaper, oanvända signaler eller båda.
* **Visa poster för**: välj det tidsintervall inom vilket du vill söka efter mottagna signaler.
* **Minsta antal**: visa endast signaler med det angivna minsta totala antalet i det valda intervallet.

>[!IMPORTANT]
>
>För en smidig användarupplevelse baseras sökresultaten för nyckelvärdepar på datainsamling. Se [Datainsamling och Felfrekvens](/help/using/reporting/report-sampling.md) för mer information om hur [!DNL Audience Manager] använder datainsamling och varför små resultatvariationer kan visas när nyckelvärdessökning jämförs med allmänna sökningar.

När [!DNL Audience Manager] söker efter signaler med hjälp av flera nyckelvärdepar länkar **paren med den logiska operatorn**. Anta att du gör en sökning med följande nyckelvärdepar:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Den här sökningen returnerar endast resultat som är kvalificerade för alla tre filtren i samma anrop: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signaler som inte ingår i signalsökning {#excluded-signals}

Nyckelvariabler som används av Audience Manager och som prefixas av prefixen `d_` och `h_` visas inte av [!UICONTROL Signals Search]. Mer information finns i [Prefixkrav för nyckelvariabler](../../traits/trait-variable-prefixes.md).

## Skiftlägeskänslighet och automatisk sökning {#case-insensitivity}

Nyckel- och värdesökfälten är skiftlägeskänsliga. Nyckelsökfältet innehåller automatiskt ifyllda förslag.

![](assets/signal-search-suggestions.png)

[!DNL Audience Manager] fick följande signaler:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

När du anger `product` i nyckelsökfältet får du automatiska förslag för `productCategory` och `product`.

När du söker efter `product == PHONE` returnerar [!UICONTROL Data Explorer] på liknande sätt bara resultat för `product == PHONE`.

Verkställigheten av bakåtfyllda traits är också skiftlägeskänslig. Ett drag som innehåller signalen med nyckel/värde-paret `PRODUCT == SMARTPHONE` kvalificerar inte signalen med nyckel/värde-paret `product == smartphone`.
