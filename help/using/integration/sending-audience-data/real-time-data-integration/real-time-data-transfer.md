---
description: Processen för inkommande data i realtid använder en serie HTTP-begäranden från en användares webbläsare för att skicka data till Audience Manager.
seo-description: The real-time inbound data ingestion process uses a series of HTTP requests from a user's browser to pass in data to Audience Manager.
seo-title: Real-Time Inbound Data Ingestion
solution: Audience Manager
title: Inkommande datainmatning i realtid
uuid: 43cb0ebc-6c36-4391-bbfb-6b203d63c69a
feature: Inbound Data Transfers
exl-id: d243c74c-3a29-4dbf-a4c7-43ea526a9d7b
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 5%

---

# Inkommande datainmatning i realtid {#real-time-inbound-data-ingestion}

Processen för inkommande data använder en serie `HTTP` en begäran från en användares webbläsare att skicka data till Audience Manager.

<!-- c_rt_inbound_real_time.xml -->

Inkommande data ska formateras som nyckelvärdepar som kallas signaler. Vanligtvis mappas varje signal till ett segment som skapas eller hanteras via användargränssnittet eller [!DNL API].

## URL-strängparametrar och syntax {#url-string-syntax}

The [!DNL URL] för en inkommande dataöverföring ska innehålla de variabler som beskrivs nedan. Kom ihåg [skapa egenskaper](../../../features/traits/create-onboarded-rule-based-traits.md) och [mappstruktur](../../../features/traits/trait-storage.md#create-trait-storage-folder) i [!DNL Audience Manager] Gränssnitt innan du konfigurerar dataöverföringar i realtid.

>[!NOTE]
>
>Ersätt kursivt innehåll med faktiska parametervärden.

| Parameter | Beskrivning |
|---|---|
| `<KEY>` | En unik identifierare i ett nyckelvärdepar (t.ex. kön, färg, pris). |
| `<VAL>` | En variabel som tillhör den datauppsättning som definieras av nyckeln (t.ex. kön=man, color=green, price=100) |

### URL-syntax

Under en process för inkommande data i realtid är en korrekt formaterad [!DNL URL] strängen har följande syntax:

```
https://client.demdex.net/event?KEY1=VALA&KEY2=VALB&KEY3=VALC
```
