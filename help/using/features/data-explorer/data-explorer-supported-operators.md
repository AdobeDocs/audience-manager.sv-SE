---
description: Använd logiska operatorer för att gruppera nyckelvärdepar och bakgrundsfyllningsegenskaper.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Logiska operatorer som stöds
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 3%

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
| **[!UICONTROL Endswith]** | Värdet i ett nyckelvärdepar *slutar med* de tecken som anges av den här operatorn. |

## Operatorer som stöds för trait Backfilling and Estimation {#supported-operators-backfilling}

Du kan använda bakåtfyllnadsegenskaper som innehåller uttryck som innehåller någon av de operatorer som stöds av [!UICONTROL Signal Search]. Förutom dessa operatorer stöder även bakåtfyllnad och uppskattning av trait-egenskaper [!UICONTROL AND], [!UICONTROL OR]och [!UICONTROL AND NOT] logiska operatorer, som används för att kombinera nyckelvärdepar i uttryck med bakgrundsfyllning.
