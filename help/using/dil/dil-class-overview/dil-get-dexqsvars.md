---
description: Hämtar ett specifikt värde från en annonsserver.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 4%

---

# dexGetQSVars{#dexgetqsvars}

Hämtar ett specifikt värde från en annonsserver.

**Funktionssignatur:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parametrar**

| Namn | Typ | Beskrivning |
|---|---|---|
| `variableName` | Sträng | Namnet på variabeln som du vill hämta ett värde för. |
| `partner` | Sträng | Partnernamnet som ska sökas efter. |
| `containerNSID` | Heltal | The [!DNL NSID] för behållaren som du söker efter. Standardvärdena är `0`. |

**Svar**

Returnerar variabelvärdet för en [!UICONTROL DIL] -instans.

**Exempelkod**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
