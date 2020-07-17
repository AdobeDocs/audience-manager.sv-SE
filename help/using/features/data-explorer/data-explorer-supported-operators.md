---
description: Använd logiska operatorer för att gruppera nyckelvärdepar och bakgrundsfyllningsegenskaper.
seo-description: Använd logiska operatorer för att gruppera nyckelvärdepar och bakgrundsfyllningsegenskaper.
seo-title: Logiska operatorer som stöds
title: Logiska operatorer som stöds
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 5%

---


# Logiska operatorer som stöds {#supported-logical-operators}

Använd logiska operatorer för att gruppera nyckelvärdepar och bakgrundsfyllningsegenskaper.

## Operatorer som stöds för signalsökning {#supported-operators-search}

Använd följande logiska operatorer som stöds för att söka efter nyckelvärdepar:

### Jämförelseoperatorer

| Operator | Definition |
|---|---|
| **==** | Lika med |
| **>** | Större än |
| **&lt;** | Mindre än |
| **=>** | Större än/lika med |
| **&lt;=** | Mindre än/lika med |

### Namngivna operatorer

| Operator | Utvärderar till [!DNL True] När |
|---|---|
| **[!UICONTROL Contains]** | Värdet i ett nyckelvärdepar *innehåller* tecken som anges av den här operatorn. |
| **[!UICONTROL Startswith]** | Värdet i ett nyckelvärdepar *börjar med* tecken som anges av den här operatorn. |
| **[!UICONTROL Endswith]** | Värdet i ett nyckelvärdepar *avslutas med* de tecken som anges av operatorn. |

## Operatorer som stöds för trait Backfilling and Estimation {#supported-operators-backfilling}

Du kan bakåtfylla egenskaper som innehåller uttryck som innehåller någon av de operatorer som stöds av [!UICONTROL Signal Search]. Förutom dessa operatorer stöder även bakåtfyllnad och uppskattning av trait-egenskaper operatorerna [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL AND NOT] logical, som används för att kombinera nyckelvärdepar inom uttryck för det omvända trait-uttrycket.