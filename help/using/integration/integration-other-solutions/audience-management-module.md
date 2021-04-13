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
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '701'
ht-degree: 4%

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

### Implementering med [!DNL Adobe Digital Tag Management (DTM)] eller någon annan tagghanteringslösning

>[!WARNING]
>
>[!DNL Adobe] planerar att upphöra  [!DNL DTM] i slutet av 2020. Mer information och schemaläggning finns i [!DNL DTM] Planer för solnedgång i [Adobe användarforum](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Så här implementerar du [!UICONTROL Audience Management Module] med [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) eller en annan tagghanteringslösning:

1. Hämta [!UICONTROL AppMeasurement] med [Analytics Code Manager](https://docs.adobe.com/content/help/sv-SE/analytics/admin/admin-tools/code-manager-admin.html) (kräver version 1.5 eller senare).
1. Uppdatera din [!UICONTROL AppMeasurement]-kod till den version som finns i den hämtade zip-filen.
1. Kopiera all kod från `AppMeasurement_Module_AudienceManagement.js` från zip-filen. Klistra in den i `appMeasurement.js`-filen alldeles ovanför texten, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Lägg till koden `s.loadModule("AudienceManagement");`, precis ovanför den `AppMeasurement_Module_AudienceManagement.js`-kod som du nyss lade till i föregående steg.
1. Uppdatera och kopiera koden nedan och lägg till den i funktionen `doPlugins` i din `AppMeasurement.js`-fil.

```js
s.AudienceManagement.setup({ 
     "partner":"INSERT-YOUR-PARTNER-NAME-HERE", 
     "containerNSID":0, 
     "uuidCookie": { 
          "name":"aam_uuid", 
          "days":30
     },
     "visitorService": {
          "namespace": "INSERT-EXPERIENCE-CLOUD-ORGID-HERE" 
     } 
});
```

>[!TIP]
>
>Funktionen `audienceManagement.setup` delar parametrar med funktionen [!DNL Audience Manager] `DIL.create` som du kan konfigurera i den här koden. Mer information om de här parametrarna finns i [DIL create](../../dil/dil-class-overview/dil-create.md#dil-create).

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
