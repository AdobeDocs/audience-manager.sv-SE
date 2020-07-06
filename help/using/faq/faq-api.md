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
ht-degree: 100%

---


# Vanliga frågor om API {#api-faq}

Vanliga API-frågor och problem.

<!-- 

faq_api.xml

 -->

Dokumentationen för [REST API](../api/rest-api-main/rest-api-main.md) innehåller information om specifika metoder och kodexempel.

<br> 

**Varför gör [!UICONTROL DIL] händelseanrop med metoderna [!UICONTROL GET] och [!UICONTROL POST]?**

[!UICONTROL DIL] skickar data till [!DNL Audience Manager] med metoden `GET` eller `POST` baserat på längden på frågesträngen för händelseanropet. Det här beteendet är som standard inbyggt i metoderna `GET` och `POST`. Det är inte specifikt för [!DNL Audience Manager].

* [!UICONTROL DIL] gör händelseanrop med `GET` när en URL innehåller högst 2 048 tecken. Ett `GET` händelseanrop inkluderar data i webbadresser som frågesträngsparametrar som skickas som nyckelvärdespar.

* [!UICONTROL DIL] gör händelseanrop med `POST` när en URL innehåller mer än 2 048 tecken. Ett `POST` händelseanrop inkluderar data i förfrågans brödtext. [!UICONTROL DIL] placerar data i nyckelvärdespar och skickar informationen som formulärdata i stället för i URL-frågesträngen.

Även om metoderna skickar data på olika sätt så påverkas inte funktionen. Med båda metoderna skickar [!DNL Audience Manager] fortfarande data till destinationer, ID-synkroniseringen fungerar normalt och du kan skapa traits utifrån datasignaler.

<br> 

**Vad kan jag göra med [!UICONTROL REST API]?**

Med [!UICONTROL REST API] kan du arbeta programmatiskt med de flesta [!DNL Audience Manager]-funktioner som är tillgängliga i användargränssnittet.

<br> 

**Hur får jag ett [!UICONTROL REST API] klient-ID och en hemlighet?**

Kontakta din Partner Solutions-representant för att få autentiseringsuppgifter till [!DNL API]. Våra API:er använder [OAuth 2.0](https://oauth.net/2/)-standarderna för tokenautentisering, auktorisering och förnyelse. Mer information finns i [OAuth-autentisering](../api/rest-api-main/aam-api-getting-started.md#oauth).
