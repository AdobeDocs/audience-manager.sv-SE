---
description: Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
seo-description: Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
seo-title: Söksignaler efter nyckelvärdepar
title: Söksignaler efter nyckelvärdepar
uuid: 2a38d0d4-4a2e-4ca5-b9ec-af9d4963d876
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 0%

---


# Söksignaler efter nyckelvärdepar {#search-signals-by-key-value-pairs}

Sök efter en eller flera signaler baserat på deras respektive nyckelvärdepar.
Om du vill söka efter fler än en signal klickar du på knappen ![Lägg till](assets/icon_add.png) . Ange de nyckelvärdepar som du vill söka efter och använd sedan följande filter för att begränsa resultatet.

* **Signalstatus**: söka efter signaler som finns i traits, oanvända signaler eller både och.
* **Visa poster för**: Ange tidsintervallet för sökning efter mottagna signaler.
* **Minsta antal**: visar endast signaler med det angivna minsta totala antalet i det valda intervallet.

>[!IMPORTANT]
>
>För en smidig användarupplevelse baseras sökresultaten för nyckelvärdepar på datainsamling. Se [Datainsamling och Felfrekvens](/help/using/reporting/report-sampling.md) för mer ingående information om hur datainsamling [!DNL Audience Manager] används och varför små resultatvariationer kan visas när nyckelvärdessökning jämförs med allmänna sökningar.

När du söker efter signaler med hjälp av flera nyckelvärdepar, [!DNL Audience Manager] länkar paren med den logiska **operatorn AND** . Anta att du gör en sökning med följande nyckelvärdepar:

* [!DNL c_creative == "12345"]
* [!DNL c_product == "smartphone"]
* [!DNL c_location == "europe"]

Sökningen returnerar endast resultat som uppfyller villkoren för alla tre filtren i samma anrop: `c_creative == "12345"` `AND` `c_product == "smartphone"` `AND` `c_location == "europe"`.

![](assets/signals-search.png)

## Signaler som inte ingår i den signala sökningen {#excluded-signals}

Nyckelvariabler som används av Audience Manager och som prefixas av `d_` och `h_` prefix visas inte av [!UICONTROL Signals Search]. Mer information finns i [Prefixkrav för nyckelvariabler](../../traits/trait-variable-prefixes.md) .

## Skiftlägesokänslighet och automatisk sökning {#case-insensitivity}

Nyckel- och värdesökfälten är skiftlägeskänsliga. Nyckelsökfältet innehåller automatiskt ifyllda förslag.

![](assets/signal-search-suggestions.png)

Låt oss säga [!DNL Audience Manager] att vi har fått följande signaler:

* `productCategory == smartphone`
* `newProduct == iPhone`
* `PRODUCT == phone`
* `product == PHONE`

När du anger `product` i nyckelsökfältet får du automatiska förslag för `productCategory`, `newProduct`, `PRODUCT`och `product`.

När du söker efter `product == phone`returneras [!UICONTROL Data Explorer] resultat för både `PRODUCT == phone` och `product == PHONE`.
Omfattande implementeringar av egenskaper är inte skiftlägeskänsliga. Ett drag som innehåller signalen med nyckelvärdepar `PRODUCT == SMARTPHONE` kvalificerar också signalen med nyckel/värde-paret `product == smartphone`.