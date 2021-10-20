---
description: Lägg till Audience Management Module i Adobe Analytics AppMeasurement för att vidarebefordra analysdata till Audience Manager i stället för att låta Audience Manager Data Integration Library-koden (DIL) skicka en pixel från sidan.
keywords: målgruppsanalys, Analyser. ssf; vidarebefordran på serversidan
seo-description: Add the Audience Management Module to Adobe Analytics AppMeasurement to forward Analytics data to Audience Manager instead of having the Audience Manager Data Integration Library (DIL) code send a pixel from the page.
seo-title: Implement the Audience Management Module
solution: Audience Manager
title: Implementera modulen för målgruppshantering
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Så här vidarebefordrar du data från [!DNL Adobe Analytics] till [!DNL Audience Manager] {#implement-the-audience-management-module}

Följ stegen i den här självstudiekursen för att gå vidare [!DNL Analytics] data till [!DNL Audience Manager] i stället för att ha [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL]) skickar du en pixel från sidan.

>[!TIP]
>
>Vi rekommenderar att du använder [!DNL Adobe Experience Platform Tags] vidarebefordra [!UICONTROL Analytics] data till [!DNL Audience Manager]. Genom att använda [!UICONTROL Tags]behöver du inte kopiera kod manuellt till [!DNL AppMeasurement], som på den här sidan.

## Förutsättningar {#prereqs}

Förutom att aktivera tilläggen eller implementera koden som beskrivs i det här dokumentet måste du också:

* Implementera [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
* Aktivera [Vidarebefordran på serversidan](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) för rapportsviter i [!UICONTROL Adobe Analytics Admin Console].

## Implementering {#implementation}

Det finns två metoder att implementera dataöverföring från [!DNL Adobe Analytics] till [!DNL Audience Manager], beroende på vilken tagghanteringslösning du använder.

### Implementering med [!DNL Adobe Experience Platform Tags]

[!DNL Adobe] rekommenderar att du använder [Taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) utvidgning till instrument [!DNL Adobe Analytics] och [!DNL Audience Manager] på era egenskaper. I så fall behöver du inte kopiera kod manuellt. I stället måste du aktivera datadelning i [!DNL Analytics] som i bilden nedan. Se även [Adobe Analytics Extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html#adobe-audience-manager) dokumentation.

>[!TIP]
>
>Om du installerar [!DNL Adobe Analytics] tillägg, *inte* installera även [!DNL Audience Manager] tillägg. Vidarebefordra data från [!DNL Analytics] tillägget ersätter [!DNL Audience Manager] tilläggsfunktioner.

![Så här aktiverar du datadelning från Adobe Analytics-tillägget till Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Definierade kodelement {#code-elements-defined}

I följande tabell definieras viktiga variabler i kodexemplet.

| Parameter | Beskrivning |
|--- |--- |
| `partner` | Obligatoriskt. Det här är ett partnernamn som du har tilldelats av [!DNL Adobe]. Det kallas ibland för [!UICONTROL partner ID] eller partnerunderdomän.  Kontakta [!DNL Adobe] konsult eller [Kundtjänst](https://helpx.adobe.com/marketing-cloud/contact-support.html) om du inte känner till ditt partnernamn. |
| `containerNSID` | Obligatoriskt. De flesta kunder kan bara sätta  `"containerNSID":0` . Om ditt företag behöver anpassa ID-synkronisering med en annan behållare kan du ange detta behållar-ID här. |
| `uuidCookie` | Valfritt. Med den här konfigurationen kan du ange en [!DNL Adobe] cookie i förstahandsdomänen. Detta [!DNL cookie] innehåller [UUID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obligatoriskt. The `namespace` -parametern krävs om du använder [!DNL AudienceManagement] modul som paketerats med [!UICONTROL AppMeasurement] version 2.10 eller senare. Detta [!UICONTROL AudienceManagement] kräver att du använder [!UICONTROL Adobe Experience Platform Identity Service] 3.3 eller senare. <br><br>The [!UICONTROL Experience Cloud Organization ID] är det ID som ett företag får när det registrerar sig för [!UICONTROL Experience Cloud]. Ta reda på ditt företags organisations-ID i [Organisationer och kontolänkning](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html). |

## Resultat: Vidarebefordra data till [!DNL Audience Manager] {#results-data-forwarding}

Dina [!DNL Analytics] implementeringen skickar data till [!DNL Audience Manager] efter att du har:

* Aktiverad [!UICONTROL Server-Side Forwarding] (tala med din konsult om denna funktion);
* Implementerat [!DNL Adobe Experience Platform Identity Service];
* Följ implementeringsstegen i den här självstudiekursen.

Den här processen skickar data till [!DNL Audience Manager]:

* On page view call;
* Från spårade länkar.
* Från videomilstolpe och videomaterial som pulsar.

>[!NOTE]
>
>Variabler som skickas till [!DNL Audience Manager] från [!DNL Analytics] använda specialprefix. Du måste förstå och ta hänsyn till dessa prefix när du skapar [!DNL Audience Manager] egenskaper. Mer information om dessa prefix finns i [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md).
