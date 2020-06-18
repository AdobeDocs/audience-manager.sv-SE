---
description: Lägg till Audience Management Module i Adobe AppMeasurement för att vidarebefordra Analytics-data till Audience Manager i stället för att få Audience Manager Data Integration Library-koden (DIL) att skicka en pixel från sidan.
keywords: audience analytics; analytics; ssf; server side forwarding
seo-description: Lägg till Audience Management Module i Adobe AppMeasurement för att vidarebefordra Analytics-data till Audience Manager i stället för att få Audience Manager Data Integration Library-koden (DIL) att skicka en pixel från sidan.
seo-title: Implementera modulen för målgruppshantering
solution: Audience Manager
title: Implementera modulen för målgruppshantering
uuid: 08846427-def3-4a15-88e5-08882d8d57ce
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 0%

---


# Så här vidarebefordrar du data från Adobe Analytics till Audience Manager {#implement-the-audience-management-module}

Följ stegen i den här självstudiekursen för att vidarebefordra [!DNL Analytics] data till [!DNL Audience Manager] istället för att få [!DNL Audience Manager][!UICONTROL Data Integration Library] ([!DNL DIL])-koden att skicka en pixel från sidan.

>[!TIP]
>
>Vi rekommenderar att du använder [!DNL Adobe Experience Platform Launch] för att vidarebefordra [!UICONTROL Analytics] data till [!DNL Audience Manager]. Om du använder [!UICONTROL Launch]behöver du inte kopiera kod till manuellt [!DNL AppMeasurement], vilket visas på den här sidan.

## Förutsättningar {#prereqs}

Förutom att aktivera tilläggen eller implementera koden som beskrivs i det här dokumentet måste du också:

* Implementera [identitetstjänsten](https://docs.adobe.com/content/help/en/id-service/using/home.html)Adobe Experience Platform.
* Aktivera vidarebefordran [på](https://docs.adobe.com/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html) serversidan för rapportsviter i [!UICONTROL Adobe Analytics Admin Console].

## Implementering {#implementation}

Det finns två metoder för att implementera datavidarebefordran från [!DNL Adobe Analytics] till [!DNL Audience Manager], beroende på vilken tagghanteringslösning du använder.

### Implementering med Adobe Experience Platform Launch

[!DNL Adobe] rekommenderar att du använder [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html) -tillägget för instrument [!DNL Adobe Analytics] och [!DNL Audience Manager] på dina egenskaper. I så fall behöver du inte kopiera kod manuellt. I stället måste du aktivera datadelning i [!DNL Analytics Launch] tillägget, vilket visas i bilden nedan. Se även dokumentationen för [Adobe Analytics Extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html#adobe-audience-manager) .

>[!TIP]
>
>Om du installerar [!DNL Adobe Analytics] tillägget ska du *inte* installera [!DNL Audience Manager] tillägget också. Om du vidarebefordrar data från tillägget [!DNL Analytics] ersätts [!DNL Audience Manager] tilläggsfunktionen.

![Möjliggör delning av data från Adobe Analytics-tillägget till Audience Manager](/help/using/integration/assets/analytics-to-aam.png)

### Implementering med Adobe Digital Tag Management (DTM) eller någon annan tagghanteringslösning

>[!WARNING]
>
>[!DNL Adobe] planerar att upphöra [!DNL DTM] i slutet av 2020. Mer information och schemaläggning finns i Planer [!DNL DTM] för en solnedgång i [Adobes användarforum](https://forums.adobe.com/community/experience-cloud/platform/launch/blog/2018/10/05/dtm-plans-for-a-sunset).

Så här implementerar du [!UICONTROL Audience Management Module] med [Adobe DTM](https://docs.adobe.com/content/help/en/dtm/using/dtm-home.html) eller någon annan tagghanteringslösning:

1. Hämta [!UICONTROL AppMeasurement] med [Analytics Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) (kräver version 1.5 eller senare).
1. Uppdatera din [!UICONTROL AppMeasurement] kod till den version som finns i den hämtade zip-filen.
1. Kopiera all kod från `AppMeasurement_Module_AudienceManagement.js` zip-filen. Klistra in den i `appMeasurement.js` filen alldeles ovanför texten, `"DO NOT ALTER ANYTHING BELOW THIS LINE."`
1. Lägg till koden, `s.loadModule("AudienceManagement");``AppMeasurement_Module_AudienceManagement.js` precis ovanför den kod som du nyss lade till i det föregående steget.
1. Uppdatera och kopiera koden nedan och lägg till den i `doPlugins` funktionen i `AppMeasurement.js` filen.

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
>Funktionen `audienceManagement.setup` delar parametrar med [!DNL Audience Manager] funktionen `DIL.create` , som du kan konfigurera i den här koden. Mer information om de här parametrarna finns i [Skapa](../../dil/dil-class-overview/dil-create.md#dil-create)med DIL.

## Definierade kodelement {#code-elements-defined}

I följande tabell definieras viktiga variabler i kodexemplet.

| Parameter | Beskrivning |
|--- |--- |
| `partner` | Obligatoriskt. Det här är ett partnernamn som du har tilldelats av [!DNL Adobe]. Det kallas ibland för din &quot;partner-ID&quot; eller &quot;partnerunderdomän&quot;.  Kontakta din [!DNL Adobe] konsult eller [kundtjänst](https://helpx.adobe.com/marketing-cloud/contact-support.html) om du inte känner till ditt partnernamn. |
| `containerNSID` | Obligatoriskt. De flesta kunder kan bara ställa in `"containerNSID":0` . Om ditt företag behöver anpassa ID-synkronisering med en annan behållare kan du ange detta behållar-ID här. |
| `uuidCookie` | Valfritt. Med den här konfigurationen kan du ange en [!DNL Adobe] cookie i förstahandsdomänen. Denna cookie innehåller [UID](../../reference/ids-in-aam.md) . |
| `visitorService` - `namespace` | Obligatoriskt. Parametern `namespace` krävs om du använder [!DNL AudienceManagement] modulen som medföljer [!UICONTROL AppMeasurement] version 2.10 eller senare. Den här [!UICONTROL AudienceManagement] modulen kräver att du använder [!UICONTROL Adobe Experience Platform Identity Service] 3.3 eller senare. <br> Detta [!UICONTROL Experience Cloud Organization ID] är det ID som ett företag får när det registrerar sig för [!UICONTROL Experience Cloud]. Ta reda på ditt företags organisations-ID i [organisationer och kontolänkning](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html). |

## Resultat: Datavidarebefordran till Audience Manager {#results-data-forwarding}

Implementeringen [!DNL Analytics] skickar data till [!DNL Audience Manager] när du har:

* Aktiverad [!UICONTROL Server-Side Forwarding] (tala med din konsult om den här funktionen);
* Genomfördes [!DNL Adobe Experience Platform Identity Service].
* Följ implementeringsstegen i den här självstudiekursen.

Den här processen skickar data till [!DNL Audience Manager]:

* On page view call;
* Från spårade länkar.
* Från videomilstolpe och videomaterial som pulsar.

>[!NOTE]
>
>Variablerna som skickas till [!DNL Audience Manager] från [!DNL Analytics] använder speciella prefix. Du måste förstå och ta hänsyn till dessa prefix när du skapar [!DNL Audience Manager] egenskaper. Mer information om dessa prefix finns i [Prefixkrav för nyckelvariabler](../../features/traits/trait-variable-prefixes.md).