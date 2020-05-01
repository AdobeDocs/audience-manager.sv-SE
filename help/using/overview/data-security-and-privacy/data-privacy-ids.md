---
description: Det här dokumentet innehåller de typer av Audience Manager-ID som du kan använda i dataintegritetsförfrågningar.
seo-description: Det här dokumentet innehåller de typer av Audience Manager-ID som du kan använda i dataintegritetsförfrågningar.
seo-title: Identifierare för Audience Manager (ID)
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, AAM ID
title: Identifierare för Audience Manager (ID)
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Identifierare för Audience Manager (ID) {#aam-ids}

När du skickar [dataintegritetsförfrågningar](data-privacy-requests.md) till Adobe Audience Manager måste du ta med en av de identifierare (ID) som listas nedan. Mer information om ID-format finns i vårt [index för Audience Manager ID](../../reference/ids-in-aam.md).

## Unikt användar-ID för Adobe Audience Manager

* **Användar-ID**: `aam_uuid`
* **Definition**: Unikt användar-ID för Adobe Audience Manager
* **Namnområdes-ID**: 0

**JSON-exempel**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "0",
        "type": "namespaceId",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

>[!NOTE]
>
>Du kan också använda [!DNL CORE] namnutrymmet.

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85302821933904870272023537812382806531"
      },
      {
        "namespace": "CORE",
        "type": "standard",
        "value": "85690090981158357332062532910972162921"
      }
    ]
  }
]
```

## Adobe Experience Cloud ID

* **Användar-ID**: `mid`
* **Definition**: [!DNL Adobe Experience Cloud ID], tidigare kallat [!DNL Visitor ID] eller [!DNL Marketing Cloud ID]
* **Namnområdes-ID**: 4

>[!NOTE]
>
>Du kan också använda [!DNL ECID] namnutrymmet. Se det andra [!DNL JSON] exemplet.

**JSON-exempel**:

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "4",
        "type": "namespaceId",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

```json
 "users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "54893990981158357332062532910972162921"
      },
      {
        "namespace": "ECID",
        "type": "standard",
        "value": "46990090981158357332062532910972162921"
      }
    ]
  }
]
```

## Kund-ID

**Användar-ID**: `cid`

**Definition**: Kund-ID, till exempel en cookie som du anger för anonyma webbplatsbesökare eller ett [!DNL CRM] -ID från ett offlinesystem eller ett hashas-användarnamn.

**Namnområdes-ID**: Kundspecifikt. Du kan hitta den från din Audience Manager-instans.

**JSON-exempel**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"1234567",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-1234567"
      },
      {
        "namespace": "1234567",
        "type": "namespaceId",
        "value": "another-unique-user-id-for-datasource-1234567"
      },
      {
        "namespace":"54321",
        "type": "namespaceId",
        "value": "unique-user-id-for-datasource-54321"
      }
    ]
  }
```

## ID för mobilreklam

**Användar-ID**: `d_cid`

**Definition**: ID för mobilannonsering.

**Namnområdes-ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Mer information finns i [Globala datakällor](../../features/global-data-sources.md) .

>[!IMPORTANT]
>
> Om du använder mobilen [!DNL SDK]ska du också skicka Experience Cloud-ID (`MID`) tillsammans med mobil-ID:n för fullständiga åtkomstsvar och Ta bort-svar.

**JSON-exempel**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace":"20914",
        "type": "namespaceId",
        "value": "e4fe9bde-caa0-47b6-908d-ffba3fa184f2"
      },
      {
        "namespace":"20915",
        "type": "namespaceId",
        "value": "AEBE52E7-03EE-455A-B3C4-E57283966239"
      }
    ]
  }
]
```

## Integrationskod

**Användar-ID**: `d_cid_ic`

**Definition**: En integrationskod för datakällan. Detta kan användas i stället för datakällans ID/namnområdes-ID i den [!DNL API] begäran som ska [!DNL Adobe Experience Cloud Privacy Core Service].

**Namnområdes-ID**: Ej tillämpligt

**JSON-exempel**:

```json
"users": [
  {
    "key": "Example user 1",
    "action": [
      "access"
    ],
    "userIDs": [
      {
        "namespace": "loyaltyCard",
        "type": "integrationCode",
        "value": "272023537812"
      },
      {
        "namespace":"offlineCampaign",
        "type": "integrationCode",
        "value": "9546673332"
      }
    ]
  }
]
```
