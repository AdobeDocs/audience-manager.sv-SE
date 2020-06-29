---
description: Vanliga API-frågor och problem.
seo-description: Vanliga API-frågor och problem.
seo-title: Vanliga frågor om API
solution: Audience Manager
title: Vanliga frågor om API
uuid: 8222ebf0-b50e-4f48-8021-dbfca2828b7c
feature: API
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 0%

---


# Vanliga frågor om API{#api-faq}

Vanliga API-frågor och problem.

<!-- 

faq_api.xml

 -->

Dokumentationen för [REST API](../api/rest-api-main/rest-api-main.md) innehåller information om specifika metoder och kodexempel.

<br> 

**Varför gör[!UICONTROL DIL]du händelseanrop med[!UICONTROL GET]och[!UICONTROL POST]metoder?**

[!UICONTROL DIL] skickar data till [!DNL Audience Manager] med en `GET` eller `POST` metod baserat på längden på frågesträngen för händelseanropet. Det här beteendet är som standard inbyggt i `GET` och `POST` metoder. Den är inte specifik för [!DNL Audience Manager].

* [!UICONTROL DIL] gör händelseanrop med `GET` när en URL innehåller högst 2 048 tecken. Ett `GET` händelseanrop innehåller data i URL:en som frågesträngsparametrar, som skickas som nyckelvärdepar.

* [!UICONTROL DIL] gör händelseanrop med `POST` när en URL innehåller mer än 2 048 tecken. Ett `POST` händelseanrop innehåller data i förfrågningens innehåll. [!UICONTROL DIL] placerar data i nyckelvärdepar och skickar information som formulärdata i stället för i URL-frågesträngen.

Även om varje metod skickar data på ett annat sätt påverkas inte funktionen. Om du till exempel har båda metoderna skickas data [!DNL Audience Manager] ändå till destinationer, ID-synkronisering fungerar normalt och du kan skapa egenskaper utifrån datasignaler.

<br> 

**Vad får jag[!UICONTROL REST API]göra?**

Med [!UICONTROL REST API]dessa kan du arbeta programmatiskt med de flesta [!DNL Audience Manager] funktioner som är tillgängliga i användargränssnittet.

<br> 

**Hur får jag ett[!UICONTROL REST API]klient-ID och en hemlighet?**

Kontakta din representant för Partner Solutions för att få [!DNL API] åtkomstbehörighet. Våra API:er använder [OAuth 2.0](https://oauth.net/2/) -standarder för tokenautentisering, auktorisering och förnyelse. Mer information finns i [OAuth-autentisering](../api/rest-api-main/aam-api-getting-started.md#oauth) .
