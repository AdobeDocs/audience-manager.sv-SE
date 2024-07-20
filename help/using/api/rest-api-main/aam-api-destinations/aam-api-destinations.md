---
description: Metoder som gör att du kan arbeta programmatiskt med målfunktioner.
seo-description: Methods that let you work programmatically with destination features.
seo-title: Destination API Methods
solution: Audience Manager
title: Mål-API-metoder
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
exl-id: 38dea854-2b7b-417e-9d56-919b65807628
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 0%

---

# Mål-API-metoder {#destination-api-methods}

Metoder som gör att du kan arbeta programmatiskt med målfunktioner.

<!-- c_destinations_api.xml -->

I Audience Manager är en destination vilket annat system som helst (annonsserver, [!DNL DSP], annonsnätverk, utbyte, egen cookie från första part osv.) som du vill dela data med.

## Måltyper: URL och cookie {#destination-types}

Visar de variabler som används av parametern `destinationType`. Ange `push` eller `ADS` om du vill arbeta med en [!UICONTROL URL] eller [!UICONTROL cookie destination]. Du kan inte skapa [!UICONTROL server-to-server destinations] med de tillgängliga [!DNL API]-målmetoderna.

<!-- r_destination_types.xml -->

| Måltyp för API | Måltyp för användargränssnitt |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Så här väljer du en måltyp](../../../features/destinations/destinations.md)
