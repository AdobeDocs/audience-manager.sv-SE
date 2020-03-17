---
description: Processen för inkommande data i realtid använder en serie HTTP-begäranden från en användares webbläsare för att skicka data till Audience Manager.
seo-description: Processen för inkommande data i realtid använder en serie HTTP-begäranden från en användares webbläsare för att skicka data till Audience Manager.
seo-title: Ingående datainmatning i realtid
solution: Audience Manager
title: Ingående datainmatning i realtid
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Ingående datainmatning i realtid {#real-time-inbound-data-ingestion}

Processen för inkommande data i realtid använder en serie `HTTP` förfrågningar från en användares webbläsare för att skicka data till Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Inkommande data ska formateras som nyckelvärdepar som kallas signaler. Vanligtvis mappas varje signal till ett segment som skapas eller hanteras via användargränssnittet eller [!DNL API].

## URL-strängparametrar och syntax {#url-string-syntax}

Inkommande [!DNL URL] dataöverföring ska innehålla de variabler som beskrivs nedan. Kom ihåg att [skapa egenskaper](../../../features/traits/create-onboarded-rule-based-traits.md) och en [mappstruktur](../../../features/traits/trait-storage.md#create-trait-storage-folder) i [!DNL Audience Manager] användargränssnittet innan du konfigurerar dataöverföringar i realtid.

>[!NOTE]
>
>Ersätt kursivt innehåll med faktiska parametervärden.

| Parameter | Beskrivning |
|---|---|
| `<KEY>` | En unik identifierare i ett nyckelvärdepar (t.ex. kön, färg, pris). |
| `<VAL>` | En variabel som tillhör den datauppsättning som definieras av nyckeln (t.ex. kön=man, color=green, price=100) |

### URL-syntax

Under en process för inkommande datainmatning i realtid använder en korrekt formaterad [!DNL URL] sträng följande syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
