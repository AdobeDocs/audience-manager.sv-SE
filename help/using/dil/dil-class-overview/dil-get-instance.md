---
description: Hämtar en partnerspecifik DIL-instans.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Hämtar en partnerspecifik DIL-instans.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

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

En lyckad partner- och behållar-NSID-matchning returnerar en partnerspecifik [!UICONTROL DIL] instans. Om det inte finns någon matchning returnerar API:t (utlöser inte) ett fel med meddelandet &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Exempelkod

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
