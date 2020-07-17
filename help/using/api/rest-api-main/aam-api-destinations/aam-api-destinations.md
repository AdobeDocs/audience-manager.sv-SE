---
description: Metoder som gör att du kan arbeta programmatiskt med målfunktioner.
seo-description: Metoder som gör att du kan arbeta programmatiskt med målfunktioner.
seo-title: 'API-metoder för destinationer '
solution: Audience Manager
title: 'API-metoder för destinationer '
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 15%

---


# API-metoder för destinationer {#destination-api-methods}

Metoder som gör att du kan arbeta programmatiskt med målfunktioner.

<!-- c_destinations_api.xml -->

I Audience Manager är en destination vilket annat system som helst (annonsserver, [!DNL DSP]annonsnätverk, utbyte, egen cookie från första part osv.) som du vill dela data med.

## Måltyper: URL och cookie {#destination-types}

Visar de variabler som används av `destinationType` parametern. Ange `push` eller `ADS` arbeta med en [!UICONTROL URL] eller [!UICONTROL cookie destination]. Du kan inte skapa [!UICONTROL server-to-server destinations] med de tillgängliga [!DNL API] målmetoderna.

<!-- r_destination_types.xml -->

| Måltyp för API | Måltyp för användargränssnitt |
|---|---|
| `PUSH` | [!UICONTROL URL] |
| `ADS` | [!UICONTROL Cookie] |

>[!MORELIKETHIS]
>
>* [Så här väljer du en måltyp](../../../features/destinations/destinations.md)

