---
description: Metoder som gör att du kan arbeta programmatiskt med målfunktioner.
seo-description: Metoder som gör att du kan arbeta programmatiskt med målfunktioner.
seo-title: Mål-API-metoder
solution: Audience Manager
title: Mål-API-metoder
uuid: 048bcdb9-2b31-46f4-8b80-4ba25bf06640
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Mål-API-metoder {#destination-api-methods}

Metoder som gör att du kan arbeta programmatiskt med målfunktioner.

<!-- c_destinations_api.xml -->

I Audience Manager är målet vilket annat system som helst (annonsserver, annonsnätverk, utbyte, egen cookie från första part osv.) [!DNL DSP] som du vill dela data med.

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

