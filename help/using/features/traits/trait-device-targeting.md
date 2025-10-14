---
description: Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med enhetsrelaterade variabler i alla egenskaper på ditt Audience Manager-konto.
seo-description: Describes the common platform-level key-value pairs you can use to target users with device-related variables across all properties in your Audience Manager account.
seo-title: Device Targeting With Platform-level Keys
solution: Audience Manager
title: Målinriktning på enheter med plattformsnivå
uuid: bc048cc5-3df1-49bc-ac78-0ea5d7edd9cc
feature: Traits
exl-id: 85c848e0-a4cf-49b5-9fe9-56f8c565f665
source-git-commit: b299783b993c5d4a1c7738eca82932c20f377ee7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Målinriktning på enheter med plattformsnivå {#device-targeting-with-platform-level-keys}

>[!WARNING]
>
>Google har uppdaterat funktionerna för [!DNL Google Chrome] och alla [!DNL Chromium]-baserade webbläsare för att minimera informationen som samlas in via rubriken `User-Agent`.
>&#x200B;>Från och med mars 2023 stöder Audience Manager dessa uppdateringar genom att utnyttja [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE). Om du vill fortsätta använda trait-information som tillhandahålls via rubriken `User-Agent` måste du använda [Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) och aktivera [High Entropy User-Agent Client Hints](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=sv-SE).
>&#x200B;>Dessa uppdateringar stöds inte av [DIL](../../../using/dil/dil-overview.md), så Audience Manager-kunder som använder [!DNL DIL] kan inte samla in information om egenskaper via rubriken `User-Agent`.

Beskriver de vanliga nyckelvärdepar på plattformsnivå som du kan använda för att rikta in användare med enhetsrelaterade variabler i alla egenskaper på ditt Audience Manager-konto.

## Syfte med variabler på plattformsnivå {#platform-variables}

<!-- c_tb_device_targeting.xml -->

Med plattformsnivåvariabler kan du ta data som skickas från en viss webbplats och göra dem tillgängliga för målinriktning för alla egenskaper i ditt [!DNL Audience Manager]-konto. Variablerna är formade med [nyckel/värde-par](../../reference/key-value-pairs-explained.md) med nyckeln prefix av `d_` enligt nedan.

## Tangenter på plattformsnivå definierade av användaragenten {#keys-user-agent}

[!UICONTROL Data Collection Servers] extraherar värdena för de här nycklarna från [användaragenthuvudet](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html#sec14.43) i `HTTP`-begäranden. Värdena representerar information på enhetsnivå från databasen [!UICONTROL Device Atlas]. Signalerna i tabellen nedan är tillgängliga, som hämtats från användaragentexemplet. [Hämta en lista med de vanligaste tangenterna &#x200B;](assets/device_keys.csv) enligt [!UICONTROL Device Atlas] mått.

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
>Även om en eller flera signaler inte kan hämtas från användaragenthuvudet, kommer de andra signalerna fortfarande att skickas till [!UICONTROL Data Collection Servers].

>[!MORELIKETHIS]
>
>* [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md)
