---
description: Lägg till Audience Management Module i Adobe Analytics AppMeasurement för att vidarebefordra analysdata till Audience Manager i stället för att låta Audience Manager Data Integration Library-koden (DIL) skicka en pixel från sidan.
keywords: målgruppsanalys, Analyser. ssf; vidarebefordran på serversidan
seo-description: Lägg till Audience Management Module i Adobe Analytics AppMeasurement för att vidarebefordra analysdata till Audience Manager i stället för att låta Audience Manager Data Integration Library-koden (DIL) skicka en pixel från sidan.
seo-title: Implementera modulen för målgruppshantering
solution: Audience Manager
title: Implementera modulen för målgruppshantering
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
feature: Adobe Analytics Integration
exl-id: af2449cd-5fc8-454a-adce-0da7cae80548
translation-type: tm+mt
source-git-commit: 1760125bbf5f134415c616f367f0eb96f04c5a3f
workflow-type: tm+mt
source-wordcount: '540'
ht-degree: 2%

---

# Vidarebefordra data från [!DNL Adobe Analytics] till [!DNL Audience Manager] {#implement-the-audience-management-module}

Följ stegen i den här självstudien för att vidarebefordra [!DNL Analytics]-data till [!DNL Audience Manager] i stället för att låta [!DNL Audience Manager] [!UICONTROL Data Integration Library] ([!DNL DIL])-koden skicka en pixel från sidan.

>[!TIP]
>
>Vi rekommenderar att du använder [!DNL Adobe Experience Platform Launch] för att vidarebefordra [!UICONTROL Analytics]-data till [!DNL Audience Manager]. Genom att använda [!UICONTROL Launch] behöver du inte kopiera kod till [!DNL AppMeasurement] manuellt, vilket visas på den här sidan.

## Förutsättningar {#prereqs}

Förutom att aktivera tilläggen eller implementera koden som beskrivs i det här dokumentet måste du också:

* Implementera [Adobe Experience Platform identitetstjänst](https://docs.adobe.com/content/help/sv-SE/id-service/using/home.html).
* Aktivera [Vidarekoppling på serversidan](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) för rapportsviter i [!UICONTROL Adobe Analytics Admin Console].

## Implementering {#implementation}

Det finns två metoder för att implementera datavidarebefordran från [!DNL Adobe Analytics] till [!DNL Audience Manager], beroende på vilken tagghanteringslösning du använder.

### Implementering med [!DNL Adobe Experience Platform Launch]

[!DNL Adobe] rekommenderar att du använder  [](https://docs.adobe.com/content/help/en/launch/using/overview.html) Launchextension för instrument  [!DNL Adobe Analytics] och  [!DNL Audience Manager] på dina egenskaper. I så fall behöver du inte kopiera kod manuellt. I stället måste du aktivera datadelning i tillägget [!DNL Analytics Launch], vilket visas i bilden nedan. Se även dokumentationen för [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager).

>[!TIP]
>
>Om du installerar tillägget [!DNL Adobe Analytics] ska *du inte* installera även tillägget [!DNL Audience Manager]. Om du vidarebefordrar data från tillägget [!DNL Analytics] ersätts tilläggsfunktionen [!DNL Audience Manager].

![Så här aktiverar du datadelning från Adobe Analytics-tillägget till Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

## Kodelement definierade {#code-elements-defined}

I följande tabell definieras viktiga variabler i kodexemplet.

| Parameter | Beskrivning |
|--- |--- |
| `partner` | Obligatoriskt. Det här är ett partnernamn som tilldelats dig av [!DNL Adobe]. Den kallas ibland din [!UICONTROL partner ID] eller partnerunderdomän.  Kontakta din [!DNL Adobe]-konsult eller [kundtjänst](https://helpx.adobe.com/marketing-cloud/contact-support.html) om du inte känner till ditt partnernamn. |
| `containerNSID` | Obligatoriskt. De flesta kunder kan bara ställa in `"containerNSID":0`. Om ditt företag behöver anpassa ID-synkronisering med en annan behållare kan du ange detta behållar-ID här. |
| `uuidCookie` | Valfritt. Med den här konfigurationen kan du ange en [!DNL Adobe]-cookie i förstahandsdomänen. Denna [!DNL cookie] innehåller [UID](../../reference/ids-in-aam.md). |
| `visitorService` -  `namespace` | Obligatoriskt. Parametern `namespace` krävs om du använder modulen [!DNL AudienceManagement] som är paketerad med [!UICONTROL AppMeasurement] version 2.10 eller senare. Den här [!UICONTROL AudienceManagement]-modulen kräver att du använder [!UICONTROL Adobe Experience Platform Identity Service] 3.3 eller senare. <br><br>ID:t  [!UICONTROL Experience Cloud Organization ID] är det ID som ett företag får när det registrerar sig för  [!UICONTROL Experience Cloud]. Ta reda på ditt företags organisations-ID i [Organisationer och Kontolänkning](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultat: Vidarebefordra data till [!DNL Audience Manager] {#results-data-forwarding}

Din [!DNL Analytics]-implementering skickar data till [!DNL Audience Manager] efter att du har:

* Aktiverad [!UICONTROL Server-Side Forwarding] (tala med din konsult om den här funktionen);
* Implementerade [!DNL Adobe Experience Platform Identity Service];
* Följ implementeringsstegen i den här självstudiekursen.

Den här processen skickar data till [!DNL Audience Manager]:

* On page view call;
* Från spårade länkar.
* Från videomilstolpe och videomaterial som pulsar.

>[!NOTE]
>
>Variablerna som skickas till [!DNL Audience Manager] från [!DNL Analytics] använder speciella prefix. Du måste förstå och ta hänsyn till dessa prefix när du skapar [!DNL Audience Manager]-egenskaper. Mer information om dessa prefix finns i [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md).
