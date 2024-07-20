---
description: I den här artikeln beskrivs de namnkonventioner som används av nyckelvariabeln i ett nyckelvärdepar.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Namnkrav för nyckelvariabler
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Namnkrav för nyckelvariabler {#name-requirements-for-key-variables}

I den här artikeln beskrivs de namnkonventioner som används av nyckelvariabeln i ett nyckelvärdepar.

## Namngivningskrav för nycklar

<!-- c_tb_key_name_requirements.xml -->

I [!UICONTROL Expression Builder] kan namnet på en nyckelvariabel i ett nyckelvärdepar bestå av ett valfritt antal siffror följt av 1 (eller flera) bokstäver, ett bindestreck, ett understreck och ytterligare siffror.

* Giltiga nyckelnamn: `price123`, `123price`, `price-123`, `c_price123`.

* Ogiltiga nyckelnamn: `123`, `price!123`.

## Prefixnyckelvariabler med `c_`

Prefixet `c_` är *always* som krävs om parametrarna som skickar in data på en URL för ett händelseanrop använder den syntaxen.
