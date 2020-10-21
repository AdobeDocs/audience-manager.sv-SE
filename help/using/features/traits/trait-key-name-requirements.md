---
description: I den här artikeln beskrivs de namnkonventioner som används av nyckelvariabeln i ett nyckelvärdepar.
seo-description: I den här artikeln beskrivs de namnkonventioner som används av nyckelvariabeln i ett nyckelvärdepar.
seo-title: Namnkrav för nyckelvariabler
solution: Audience Manager
title: Namnkrav för nyckelvariabler
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%

---


# Namnkrav för nyckelvariabler {#name-requirements-for-key-variables}

I den här artikeln beskrivs de namnkonventioner som används av nyckelvariabeln i ett nyckelvärdepar.

## Namngivningskrav för nycklar

<!-- c_tb_key_name_requirements.xml -->

I [!UICONTROL Expression Builder]kan namnet på en nyckelvariabel i ett nyckelvärdepar bestå av ett valfritt antal siffror följt av 1 (eller flera) bokstäver, ett bindestreck, ett understreck och ytterligare siffror.

* Giltiga nyckelnamn: `price123`, `123price`, `price-123`, `c_price123`.

* Ogiltiga nyckelnamn: `123`, `price!123`.

## Prefix Key Variables with `c_`

Prefixet `c_` är *alltid* obligatoriskt om parametrarna som skickar in data på en URL för ett händelseanrop använder den syntaxen.