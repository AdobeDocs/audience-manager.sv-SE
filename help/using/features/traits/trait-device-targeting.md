---
description: Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med enhetsrelaterade variabler i alla egenskaper i ditt Audience Manager-konto.
seo-description: Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med enhetsrelaterade variabler i alla egenskaper i ditt Audience Manager-konto.
seo-title: Device Targeting with Platform-level Keys
solution: Audience Manager
title: Device Targeting with Platform-level Keys
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---


# Device Targeting with Platform-level Keys {#device-targeting-with-platform-level-keys}

Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med enhetsrelaterade variabler i alla egenskaper i ditt Audience Manager-konto.

## Syfte med variabler på Platform-nivå {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Med variabler på Platform-nivå kan ni ta data som skickas från en viss webbplats och göra dem tillgängliga för målinriktning för alla egenskaper i ert [!DNL Audience Manager] konto. Variablerna formateras med [nyckelvärdepar](../../reference/key-value-pairs-explained.md) med nyckeln som prefixeras av `d_` enligt nedan.

## Tangenter på Platform-nivå definierade av användaragent {#keys-user-agent}

Extrahera värdena för dessa nycklar från [!UICONTROL Data Collection Servers] användaragenthuvudet [i](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) `HTTP` begäranden. Värdena representerar information på enhetsnivå från [!UICONTROL Device Atlas] databasen. Signalerna i tabellen nedan är tillgängliga, som hämtats från användaragentexemplet. [Hämta en lista med de vanligaste nycklarna](assets/device_keys.csv)enligt [!UICONTROL Device Atlas] mått.

| [!DNL Signal] | [!DNL Type] | [!DNL Example] |
|---|---|---|
| `d_device_vendor` | [!DNL VENDOR] | [!DNL apple] |
| `d_device_hardware_type` | [!DNL HARDWARE] | [!DNL mobile phone] |
| `d_device_os_version` | [!DNL OS VERSION] | [!DNL 5_0] |
| `d_device_os_name` | [!DNL OS NAME] | [!DNL ios] |
| `d_device_model` | [!DNL MODEL] | [!DNL iphone] |
| `d_device_marketing_name` | [!DNL MARKETING NAME] | [!DNL iphone] |
| `d_device_manufacturer` | [!DNL MANUFACTURER] | [!DNL apple] |

```
 Mozilla/5.0 (iPhone; CPU iPhone OS 5_0 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A334 Safari/7534.48.3
```

>[!NOTE]
>
>Även om en eller flera signaler inte kan hämtas från användaragentens huvud, kommer de andra signalerna fortfarande att skickas till [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)

