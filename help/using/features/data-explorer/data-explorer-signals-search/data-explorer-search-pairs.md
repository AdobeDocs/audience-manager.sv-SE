---
description: Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
seo-description: Search for one or multiple signals, based on their respective key-value pairs.
seo-title: Search Signals by Key-Value Pairs
title: Söka efter signaler med nyckelvärdespar
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
exl-id: d598da6b-8dc0-47ce-8389-1973b1803711
source-git-commit: 6f8f82062403831e5b99525c4f3c3512c67d71bf
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 1%

---

# Sök signaler med nyckelvärdepar {#search-signals-by-key-value-pairs}

Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
Om du vill söka efter fler än en signal klickar du på knappen ![Lägg till](assets/icon_add.png) -knappen. Ange de nyckelvärdepar som du vill söka efter och använd sedan följande filter för att begränsa resultatet.

* **Signalstatus**: söka efter signaler som finns i traits, oanvända signaler eller både och.
* **Visa poster för**: Ange tidsintervallet för sökning efter mottagna signaler.
* **Minsta antal**: visar endast signaler med det angivna minsta totala antalet i det valda intervallet.

>[!IMPORTANT]
>
>För en smidig användarupplevelse baseras sökresultaten för nyckelvärdepar på datainsamling. Se [Datainsamling och felfrekvens](/help/using/reporting/report-sampling.md) för mer information om hur [!DNL Audience Manager] använder datainsamling och varför små resultatvariationer kan visas när nyckelvärdessökning jämförs med allmänna sökningar.

När du söker efter signaler med hjälp av flera nyckelvärdepar [!DNL Audience Manager] länkar paren med hjälp av **OCH** -operator. Anta att du gör en sökning med följande nyckelvärdepar:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Sökningen returnerar endast resultat som uppfyller villkoren för alla tre filtren i samma anrop: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signaler som inte ingår i signalsökning {#excluded-signals}

Nyckelvariabler som används av Audience Manager och som föregås av `d_` och `h_` prefix inte visas av [!UICONTROL Signals Search]. Se [Prefixkrav för nyckelvariabler](../../traits/trait-variable-prefixes.md) för mer information.

## Skiftlägeskänslighet och automatisk sökning {#case-insensitivity}

Nyckel- och värdesökfälten är skiftlägeskänsliga. Nyckelsökfältet innehåller automatiskt ifyllda förslag.

![](assets/signal-search-suggestions.png)

Låt oss säga [!DNL Audience Manager] fick följande signaler:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

När du skriver `product` i nyckelsökfältet får du förslag på `productCategory` och `product`.

På samma sätt när du söker efter `product == PHONE`, [!UICONTROL Data Explorer] returnerar endast resultat för `product == PHONE`.

Verkställigheten av bakåtfyllda egenskaper är också skiftlägeskänsliga. Ett drag som innehåller signalen med nyckel/värde-paret `PRODUCT == SMARTPHONE` kvalificerar inte signalen med nyckelvärdepar `product == smartphone`.
