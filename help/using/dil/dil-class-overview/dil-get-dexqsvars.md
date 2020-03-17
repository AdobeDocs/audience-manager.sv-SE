---
description: Hämtar ett specifikt värde från en annonsserver.
seo-description: Hämtar ett specifikt värde från en annonsserver.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
translation-type: tm+mt
source-git-commit: f682194b60b7a11a3b5cac9912147471f4b30bd4

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
| `containerNSID` | Heltal | The [!DNL NSID] of the container you are searching for. Standardvärdena är `0`. |

**Svar**

Returnerar variabelvärdet för en [!UICONTROL DIL] instans.

**Exempelkod**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
