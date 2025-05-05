---
description: Hämtar en partnerspecifik DIL-instans.
keywords: målgruppshanterare api;aam api;målgruppshanterare apis;aam apis
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%

---

# getDil{#getdil}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av tillägget [!DNL Data Integration Library (DIL)] och [!DNL DIL].
>
>Befintliga kunder kan fortsätta använda sin [!DNL DIL]-implementering. Adobe kommer dock inte att utveckla [!DNL DIL] efter den här punkten. Kunder uppmuntras att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) för sin långsiktiga datainsamlingsstrategi.
>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=sv-SE) i stället.

Hämtar en partnerspecifik DIL-instans.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametrar

| Namn | Typ | Beskrivning |
|---|---|---|
| `partner` | Sträng | Partnernamnet som ska sökas efter. |
| `containerNSID` | Heltal | Standardvärdena är `0`. NSID för behållaren som du söker efter. Valfritt. |

## Svar

En partner- och behållar-NSID-matchning returnerar en partnerspecifik [!UICONTROL DIL]-instans. Om det inte finns någon matchning returnerar API (utlöser inte) ett fel med meddelandet `The DIL instance with partner <name> and containerNSID <ID> was not found.`

## Exempelkod

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
