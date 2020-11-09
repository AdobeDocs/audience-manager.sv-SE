---
description: Definierar och beskriver standardpar och serialiserade nyckelvärdepar.
keywords: integration code
seo-description: Definierar och beskriver standardpar och serialiserade nyckelvärdepar.
seo-title: Förklaring av nyckelvärdespar
solution: Audience Manager
title: Förklaring av nyckelvärdespar
uuid: f1435742-81ca-4964-8370-accf2f1c47a5
feature: reference
translation-type: tm+mt
source-git-commit: 5d6983f5308f1dfd4560ee1b38bcaee3ca6e422f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 3%

---


# Förklaring av nyckelvärdespar{#key-value-pairs-explained}

Definierar och beskriver standardpar och serialiserade nyckelvärdepar.

<!-- 

c_key_value_explained.xml

 -->

Ett nyckelvärdepar består av två relaterade dataelement: En nyckel, som är en konstant som definierar datauppsättningen (t.ex. kön, färg, pris) och ett värde, vilket är en variabel som tillhör uppsättningen (t.ex. man/kvinna, grön, 100). Ett nyckelvärdepar kan ha följande format:

* `gender = male`
* `color = green`
* `price > 100`

## Standard and Serialized Key-Value Pairs {#standard-serialized-pairs}

Destinationer tar emot nyckelvärdesdata i *`standard`* eller *`serialized`* format. Med standardformatering ordnas data i separata nyckelvärdepar. Varje nyckel anges explicit, även om den används igen för att definiera ett annat värde. Vid serialiserad formatering komprimeras däremot flera värden till en uppsättning som definieras av en enda tangent. I ett serialiserat par används dessutom en specialindikator för att separera värdena i nyckelvärdesmängden. Slutligen kan standardvärden och serialiserade nyckelvärden innehålla ett eller flera värden. Följande tabell innehåller exempel på standardformat och serienyckelformat.

| Formatering | Enkel nyckel | Nyckelvärdepar |
|---|---|---|
| **Standard** | `x=1&x=2` | `x=1&x=2&y=3&y=4` |
| **Serialiserad** | `x=1;2` | `x=1;2&y=3;4` |



## Tangenter, avgränsare och avgränsare {#keys-delimiters-separators}

När du arbetar med serialiserade data måste du ange tecknen som avgränsar värden *inom* och *mellan* nyckelvärdepar. Element i nyckelvärdepar definieras enligt följande:

* **Nyckel:** En unik identifierare i nyckelvärdepar.
* **Värdeavgränsare:** Separerar enskilda nyckelvärdepar.
* **Avgränsare för nyckelvärde:** Separerar en nyckel från värdena i ett nyckelvärdepar.
* **Serieavgränsare:** Separerar enskilda värden inom serialiserade nyckelvärdepar.

## Standard- och serialiserade nyckelvärdeselement {#standard-serialized-key-value-elements}


| Typ | Exempel | Nyckel | Avgränsare för nyckelvärde | Avgränsare för nyckelvärde | Serieavgränsare |
---------|----------|---------|---------|----------|---------
| **Enkel tangent** (standard) | `x=1&x=2` | `x` | `=` | `&` | n/a |
| **Nyckelvärdepar** (standard) | `x=1&x=2&y=3&y=4` | `x,y` | `=` | `&` | n/a |
| **En nyckel** (seriell) | `x=1;2;3` | `x` | `=` | n/a | `;` |
| **Nyckelvärdepar** (seriella) | `x=1;2&y=3;4` | `x,y` | `=` | `&` | `;` |
