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
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 5%

---

# getDil{#getdil}

Hämtar en partnerspecifik DIL-instans.

**Funktionssignatur:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parametrar

| Namn | Typ | Beskrivning |
|---|---|---|
| `partner` | Sträng | Partnernamnet som ska sökas efter. |
| `containerNSID` | Heltal | Standardvärdena är `0`. NSID för behållaren som du söker efter. Valfritt. |

## Svar

En lyckad partner- och behållar-NSID-matchning returnerar en partnerspecifik [!UICONTROL DIL] -instans. Om det inte finns någon matchning returnerar API:t (utlöser inte) ett fel med meddelandet &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Exempelkod

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
