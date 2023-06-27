---
description: Hämtar ett specifikt värde från en annonsserver.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 2%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>Från och med juli 2023 har Adobe upphört med utvecklingen av [!DNL Data Integration Library (DIL)] och [!DNL DIL] tillägg.
><br><br>
>Befintliga kunder kan fortsätta använda sina [!DNL DIL] implementering. Adobe kommer dock inte att utvecklas [!DNL DIL] bortom denna punkt. Kunder uppmanas att utvärdera [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) för deras långsiktiga strategi för datainsamling.
><br><br>
>Kunder som vill implementera integreringar för datainsamling efter juli 2023 bör använda [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) i stället.

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
