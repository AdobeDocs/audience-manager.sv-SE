---
description: Det här dokumentet behandlar de typer av Audience Manager-ID som du kan använda i datasekretessförfrågningar.
seo-description: This document covers the types of Audience Manager IDs that you can use in data privacy requests.
seo-title: Audience Manager Identifiers (IDs)
solution: Audience Manager
keywords: GDPR-gränssnitt, GDPR API, CCPA, sekretess, AAM-ID
title: Identifierare för Audience Manager (ID)
feature: Data Governance & Privacy
exl-id: 5f18ed0a-c875-4596-a4d1-f9a7fe871d1b
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 96%

---

# Identifierare för Audience Manager (ID) {#aam-ids}

När du skickar [datasekretessförfrågningar](data-privacy-requests.md) till Adobe Audience Manager måste du inkludera en av de identifierare (ID) som anges nedan. Mer information om ID-format finns i vårt [index över Audience Manager ID:n](../../reference/ids-in-aam.md).

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
>Du kan också använda namnområdet [!DNL CORE].

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
* **Definition**: [!DNL Adobe Experience Cloud ID], kallades tidigare [!DNL Visitor ID] eller [!DNL Marketing Cloud ID]
* **Namnområdes-ID**: 4

>[!NOTE]
>
>Du kan också använda namnområdet [!DNL ECID]. Se det andra [!DNL JSON]-exemplet.

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

**Definition**: Kund-ID, till exempel en cookie som du anger för anonyma webbplatsbesökare eller ett [!DNL CRM]-ID från ett offlinesystem eller ett hash-kodat användarnamn.

**Namnområdes-ID**: Kundspecifikt. Du hittar det i din Audience Manager-instans.

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

**Definition**: ID:n för mobilreklam.

**Namnområdes-ID**:

* [!DNL IDFA:] 20915
* [!DNL GAID:] 20914

Mer information finns i [Globala datakällor](../../features/global-data-sources.md).

>[!IMPORTANT]
>
> Om du använder mobila [!DNL SDK] ska du också skicka Experience Cloud ID (`MID`) tillsammans med ID för mobilreklam för fullständiga svar om åtkomst och radering.

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

**Definition**: En integrationskod för datakällan. Den kan användas i stället för datakällans ID/namnområdes-ID i [!DNL API]-begäran till [!DNL Adobe Experience Cloud Privacy Core Service].

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
