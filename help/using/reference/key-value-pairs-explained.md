---
description: Definierar och beskriver standard- och serialiserade nyckelvärdepar.
keywords: integrationskod
seo-description: Defines and describes standard and serialized key-value pairs.
seo-title: Key-Value Pairs Explained
solution: Audience Manager
title: Förklaring av nyckelvärdepar
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: Reference
exl-id: de4e6fdb-2d6d-4fed-9255-9438b42b2570
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Förklaring av nyckelvärdepar{#key-value-pairs-explained}

Definierar och beskriver standard- och serialiserade nyckelvärdepar.

<!-- 

c_key_value_explained.xml

 -->

Ett nyckelvärdepar består av två relaterade dataelement: en nyckel, som är en konstant som definierar datauppsättningen (t.ex. kön, färg, pris), och ett värde, som är en variabel som tillhör uppsättningen (t.ex. man/kvinna, grön, 100). Ett nyckelvärdepar kan ha följande format:

* `gender = male`
* `color = green`
* `price > 100`

## Standardpar och serialiserade nyckelvärdepar {#standard-serialized-pairs}

Destinationer accepterar nyckelvärdesdata i formatet *`standard`* eller *`serialized`*. Med standardformatering ordnas data i separata nyckelvärdepar. Varje nyckel anges explicit, även om den används igen för att definiera ett annat värde. Vid serialiserad formatering komprimeras däremot flera värden till en uppsättning som definieras av en enda tangent. I ett serialiserat par används dessutom en specialindikator för att separera värdena i nyckelvärdesmängden. Slutligen kan standardvärden och serialiserade nyckelvärden innehålla ett eller flera värden. Följande tabell innehåller exempel på standardformat och serienyckelformat.

| Formatering | Enkel nyckel | Nyckelvärdepar |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialiserad** | `x=1;2` | `x=1;2&y=3;4` |



## Tangenter, avgränsare och avgränsare {#keys-delimiters-separators}

När du arbetar med serialiserade data måste du ange tecknen som avgränsar värdena *inom* och *mellan* nyckelvärdepar. Element i nyckelvärdepar definieras enligt följande:

* **Nyckel:** En unik identifierare i nyckelvärdepar.
* **Värdeavgränsare:** Separerar enskilda nyckelvärdepar.
* **Nyckelvärdesavgränsare:** Separerar en nyckel från värdena i ett nyckelvärdepar.
* **Seriell avgränsare:** Separerar enskilda värden inom serialiserade nyckelvärdepar.

## Standard- och serialiserade nyckelvärdeselement {#standard-serialized-key-value-elements}


| Typ | Exempel | Nyckel | Avgränsare för nyckelvärde | Avgränsare för nyckelvärde | Serieavgränsare |
|---------|----------|---------|---------|----------|---------|
| **En nyckel** (standard) | `x=1&x=2` | `x` | `=` | `&` | n/a |
| **Nyckelvärdepar** (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/a |
| **En nyckel** (seriell) | `x=1;2;3` | `x` | `=` | n/a | `;` |
| **Nyckelvärdepar** (seriella) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
