---
description: Adobe ger er möjlighet att hantera och förmedla användarnas valfrihet i fråga om integritet via anmälningsfunktionen och stöd för IAB Transparency and Consent Framework (TCF). I den här artikeln beskrivs fall där Audience Manager har stöd för IAB TCF och hur ni implementerar stöd för IAB TCF i Audience Manager.
seo-description: Adobe provides you with the means to manage and communicate your users' privacy choices through the Opt-in functionality and through IAB Transparency and Consent Framework (TCF) support. This article describes the Audience Manager use cases that support the IAB TCF and how to implement IAB TCF support in Audience Manager.
seo-title: Audience Manager Plug-in for IAB TCF
solution: Audience Manager
title: Plugin-program för Audience Manager för IAB TCF
feature: Data Governance & Privacy
exl-id: aa6bc415-e52b-4900-951d-ccf51d907aa2
source-git-commit: 8b370a64d80b40124abee91351cbef09711243d4
workflow-type: tm+mt
source-wordcount: '2173'
ht-degree: 29%

---

# [!DNL Audience Manager Plug-in for IAB TCF] {#aam-iab-plugin}

## Översikt

En viktig aspekt av de integritetsskyldigheter du kan ha gentemot dina användare är att man får tag i och överför användarval över hur deras personuppgifter kan användas (dvs.&quot;syften&quot;) och av vem (dvs.&quot;företag&quot;).

Adobe ger er möjlighet att hantera och förmedla användarnas valmöjligheter i fråga om sekretess genom [anmälningsfunktionen](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=sv-SE) och stöd för [IAB Transparency and Consent Framework (TCF)](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/).

I den här artikeln beskrivs fall där Audience Manager har stöd för IAB TCF och hur ni implementerar stöd för IAB TCF i Audience Manager.

>[!IMPORTANT]
>
>Audience Manager är registrerat i [IAB TCF](https://iabeurope.eu/tcf-for-vendors/) med leverantörs-ID 565.

Audience Manager-plugin-programmet för IAB TCF använder funktionen [Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=sv-SE) som i sin tur är en del av [Adobe Experience Platform Identity Service-biblioteket (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=sv-SE).

## Tillämpningsområde och begränsningar {#scope-and-limitations}

Som utgivare eller Advertiser som arbetar med Audience Manager kan du förmedla användarval till Audience Manager enligt IAB TCF.

>[!IMPORTANT]
>
>Regler för IAB TCF gäller endast för besökare som befinner sig i Europeiska ekonomiska samarbetsområdet.

Audience Manager hjälper er att respektera användarnas valmöjligheter vad gäller integritet och ger er också ett enkelt sätt att kommunicera dessa val till alla partners ni arbetar med.

Audience Manager har för närvarande inte stöd för:

* Arbetsflöden för mobila enheter
* Lägger till samtycke till segmentexport.

## Uppgraderar till [!DNL IAB TCF v2.2] {#upgrading}

Kunder som uppgraderar sin [!DNL Audience Manager Plug-in for IAB TCF]-implementering från [!DNL IAB TCF] v1.1 till [!DNL IAB TCF] v2.2, eller aktiverar [!DNL IAB TCF] v2.2 för första gången, bör alla följa samma riktlinjer för förutsättningar och implementering som beskrivs nedan.

## Förutsättningar {#prerequisites}

>[!IMPORTANT]
>
>Audience Manager stöder IAB TCF v2.2.
>
>Stöd för IAB TCF v1.1 upphör den 15 augusti 2020.
>
> Kunder som vill fortsätta använda Audience Manager-plugin för IAB TCF för samtyckeshantering bör uppgradera till den senaste versionen av [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases) för fortsatt support.
>
> När du har uppgraderat till den senaste [ECID](https://github.com/Adobe-Marketing-Cloud/id-service/releases)-versionen stöds inte längre IAB TCF v1.1-medgivandesträngar. Uppdatera din CMP innan du uppgraderar till den senaste ECID-versionen.

Du måste uppfylla följande krav för att kunna använda Audience Manager-plugin-programmet för IAB TCF med Audience Manager:

1. Du måste använda Adobe Experience Platform Identity Service (ECID) version 5 eller senare. [Ladda ned](https://github.com/Adobe-Marketing-Cloud/id-service/releases) vår senaste ECID-version.
2. Du måste använda Audience Manager [!DNL Data Integration Library] (DIL) version 9.0 eller senare, kan hämtas från [här](https://github.com/Adobe-Marketing-Cloud/dil/releases). Läs om [DIL i Audience Manager-dokumentationen](../../dil/dil-overview.md). Vi rekommenderar att du använder [Adobe Audience Manager-taggtillägget](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/audience-manager/overview.html?lang=sv-SE) för den enklaste DIL-implementeringen av Audience Manager.
3. Om du använder [!DNL Server-Side Forwarding] (SSF) för att importera data till Audience Manager måste du uppgradera till den senaste versionen av AppMeasurement. Hämta AppMeasurement med [Analytics Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=sv-SE).
4. Du måste använda en CMP (Consent Management Platform), antingen kommersiell eller egen, som är integrerad med IAB TCF v2.2 och som är registrerad med IAB TCF. Se listan över [CMP:er som registrerats i IAB-ramverket](https://iabeurope.eu/cmp-list/).

>[!WARNING]
>
>Om du använder en CMP (Consent Management Platform) som inte har stöd för IAB TCF v2.2, skickar Audience Manager automatiskt parametern `gdpr=0` i ID-synk, även om besökarna befinner sig i EU. För att avgöra om din GDPR-validering är aktiv rekommenderar vi att du bekräftar med din CMP (Consent Management Platform) att de stöder IAB TCF v2.2.

## Rekommendationer och hur man implementerar {#recommendations}

Om du vill aktivera stöd för IAB TCF i Audience Manager läser du vår dokumentation om att [konfigurera IAB med anmälan](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/iab.html?lang=sv-SE).

Det enklaste sättet att göra detta är att använda [Adobe Experience Platform-taggar](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=sv-SE) för att lägga till [!DNL ECID Opt-in] i egenskaperna. Läs dokumentationen för tillägget [ECID Opt-in](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=sv-SE) om du vill veta mer om hur du konfigurerar tillägget Taggar.

## Arbetsflöde för användarval när IAB-ramverket används {#user-choice-workflow}

När du besöker en webbegenskap kan dina användare ange hur deras data ska användas av utgivaren och av tredjepartsleverantörer som utgivaren arbetar med.

Användarna kan välja i form av *medgivande* för IAB-syften till *tredjepartsleverantörer* som är registrerade i den globala leverantörslistan.

Bilden nedan visar ett exempel på en CMP-dialogruta som visas för en förstagångsbesökare på en webbplats. Tänk på att den här dialogrutan kan se annorlunda ut beroende på hur kunden implementerar den.

![CMP-dialogruta](assets/cmp-example.png)

Information om de olika syften och behörigheter som ingår i IAB TCF v2.2 finns i [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes).

Användarna kan ge sitt samtycke för en kombination av syften och leverantörer. Användarna kan till exempel ge sitt samtycke till att lagra information på en enhet, utveckla och förbättra produkter och ge sitt samtycke till alla tredjepartsleverantörer som visas av CMP.

Eller, i ett annat exempel, skulle de kunna ge sitt samtycke för alla syften, men bara ge medgivande till ett fåtal av de leverantörer som visas av CMP.

När användaren har valt sina sekretessval registreras användarvalen i IAB TC-strängen. IAB TC-strängen lagrar en kombination av godkända syften och leverantörer, tillsammans med annan metadatainformation (mer information finns på [IAB-sidan](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)).

Alla leverantörer som är registrerade i IAB TCF utvärderar IAB TC-strängen och fattar beslut baserat på användarnas sekretessval. Tänk på att användarnas sekretessval är giltiga för alla leverantörer som är registrerade med IAB TCF.

## Syfte som Audience Manager kräver {#aam-standard-purposes}

Audience Manager utvärderar användarnas val som lagras i IAB TC-strängen för följande syften, som definieras i [IAB Europe Transparency &amp; Consent Framework Policies](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Appendix_A_Purposes_and_Features_Definitions).

* **Syfte 1**: Lagra och/eller få åtkomst till information på en enhet;
* **Syfte 10**: Utveckla och förbättra produkter;
* **Särskilt syfte 1**: Säkerställ säkerhet, förhindra bedrägeri och felsökning.

>[!IMPORTANT]
>
>Audience Manager behöver samtycke för Syfte 1 och Syfte 10, plus leverantörsgodkännande, för att kunna distribuera cookies och initiera eller respektera ID-synkroniseringar.
>
>Enligt [IAB-regler](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#Special_Purpose_1__Ensure_security_prevent_fraud_and_debug_) har specialsyfte 1 (Säkerställ säkerhet, Förebygg bedrägerier och felsökning) alltid medgetts och användarna kan inte motsätta sig det.

## Audience Manager beteende beror på om användaren ger sitt samtycke {#aam-behavior-consent}

Audience Manager fungerar på olika sätt beroende på om IAB TC-strängen innehåller användargodkännande för de två syften (lagra och/eller få åtkomst till information på en enhet samt utveckla och förbättra produkter) eller inte.

Vi kontrollerar också om du har gett användargodkännande för alla mål som du arbetar med i Audience Manager, så länge som dessa mål är registrerade med IAB TCF.

| När användaren *ger sitt medgivande* kommer Audience Manager: | När användaren *inte ger sitt medgivande* kommer Audience Manager: |
|---|---|
| <ul><li>Utföra alla de Audience Manager-funktioner som ni har begärt.</li><li>Medgivande skickas till tredje part i ID-synkroniseringar (genom att `gdpr = 1` och medgivandesträngen skickas som `gdpr_consent` vid ID-synkroniseringsanrop).</li><li>Utvärdera och respektera medgivanden som skickas från annonsserverns pixlar.</li><li>Respektera partnerinitierade ID-synkroniseringar.</li></ul> | <ul><li>Inga nya användardata lagras i er instans. Detta inkluderar partner-ID, signaler, traits och pixeldata.</li><li>ID-synkronisering initieras inte med tredje part.</li><li>Partnerinitierade ID-synkroniseringar respekteras inte.</li><li>Användaren kan inte hämta in ytterligare data.</li></ul> |

## Användningsfall för utgivare {#publisher-use-case}

Genom att implementera Audience Manager-plugin för IAB TCF behöver du inte ha anpassad kod för samtyckeshantering på dina webbegenskaper via en annan mekanism med Adobe eller andra tredjepartsleverantörer. Användningen beskrivs i bilden och i stegen nedan. Börja till vänster i bilden:

1. En användare besöker en av era webbplatser. Så länge ni använder de senaste versionerna av ECID- och DIL-biblioteken (se [Förutsättningar](/help/using/overview/data-security-and-privacy/aam-iab-plugin.md#prerequisites)) aktiveras anmälningsflödet.
2. Audience Manager kontrollerar om IAB-flödet gäller (`isIabContext=true`). Se [Rekommendationer och implementering](aam-iab-plugin.md#recommendations).
3. Audience Manager kontrollerar om GDPR gäller (`gdpr = 1`) och om det finns en CMP, registrerad med IAB TCF, på din webbegenskap. Detta skulle till exempel gälla användare som besöker från EU. Observera att det är ditt ansvar som utgivare att sätta GDPR-flaggan.
4. Om GDPR tillämpas kontrollerar Audience Manager om IAB TC-strängen, som skickas i parametern `gdpr_consent`, har det medgivande som krävs. Audience Manager behöver samtycke för att lagra och/eller komma åt information på en enhet ([IAB TCF purpose 1](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), utveckla och förbättra produkter ([IAB TCF purpose 10](https://iabeurope.eu/iab-europe-transparency-consent-framework-policies/#A_Purposes)), plus Audience Manager leverantörs samtycke till att lagra, bearbeta eller aktivera data.
5. Om IAB TC-strängen finns och den innehåller det samtycke som krävs skickar Audience Manager IAB TC-strängen till våra [datainsamlingsservrar](../../reference/system-components/components-data-collection.md) (DCS).
6. Audience Manager svarar genom att ställa in en [demdex-cookie](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-am.html?lang=sv-SE) i webbläsaren och initierar och respekterar synkroniseringar för tredje parts-ID.
7. Om IAB TC-strängen som skickades i steg 4 inte innehåller alla behörigheter som krävs, samlar Audience Manager inte in, bearbetar eller aktiverar användardata och följer eller initierar inte ID-synkroniseringar. Dessutom väljs användaren bland de mål som du arbetar med.

>[!IMPORTANT]
>
>Om du arbetar med Audience Manager målpartners som kräver IAB TCF-parametrar, men du inte har någon CMP som stöder IAB TCF på webbplatsen, skickar Audience Manager `gdpr=0` i ID-synk. Detta innebär att GDPR inte gäller dessa användare.
>
> Om du inte önskar det bör du aktivera funktionen IAB TCF i Audience Manager för att skicka lämpliga IAB TC-strängar till målpartnern.



![Användningsexempel för utgivare](assets/publisher-use-case.png)

## Handläggarens användningsfall {#advertiser-use-case}

Audience Manager utvärderar och respekterar medgivanden som skickas i [pixelanrop](../../integration/sending-audience-data/real-time-data-integration/pixel-based-data-transfer.md) i enlighet med IAB TCF.

Pixlar kan placeras av Audience Manager-kunder på deras partnersidor eller placeras i annonsservrar som ska inkluderas i annonssvaret. I det första fallet måste er partner hämta medgivandeparametern programmatiskt och lägga till den i pixeln innan den aktiveras. I det andra fallet, som är vanligare och beskrivs i detalj nedan, lägger annonsservrar till de medgivandeparametrar som de tar emot från SSP-plattformen (Supply-Side Platform) eller utgivarens annonsservrar i alla pixlar.

Audience Manager använder två parametrar för att skicka användarmedgivande i pixelanrop:

* `gdpr` kan vara 0 (GDPR gäller inte) eller 1 (GDPR gäller)
* `gdpr_consent` är URL-säker base64-kodad GDPR-medgivandesträng (se [specifikation](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string)). Ett exempel på ett anrop för en annonsvisningspixel med de två parametrarna kan se ut så här:

```
https://yourcompany.demdex.net/event?d_event=imp&gdpr=1&gdpr_consent=consentstring&d_src=datasource_id&d_site=siteID&d_creative=creative_id&d_adgroup=adgroup_id&d_placement=placement_id
```

Användningen beskrivs i bilden och i stegen nedan. Börja till vänster i bilden:

1. En annonsserver visar en annons för användaren. Detta innebär ett [pixelanrop](../../integration/media-data-integration/impression-data-pixels.md) till våra datainsamlingsservrar (DCS).
2. Audience Manager kontrollerar om GDPR-flaggan gäller. Om så inte är fallet lagrar Audience Manager data som skickas i variablerna `gdpr` och `gdpr_consent` i pixelanrop.
3. Om IAB TC-strängen finns och den innehåller de behörigheter som krävs lagrar Audience Manager data som skickas i variablerna `gdpr` och `gdpr_consent` i pixelanrop.
4. Om IAB TC-strängen saknas eller saknar de behörigheter som krävs, utelämnar Audience Manager de data som skickas i variablerna `gdpr` och `gdpr_consent` i pixelanrop.

![Användningsexempel för annonsörer](assets/advertiser-use-case.png)

## Aktiveringspartners som stöder IAB TCF {#aam-activation-partners}

Med Audience Manager-pluginen för IAB TCF kan du vidarebefordra IAB TC-strängen till aktiveringspartners med respekt för användarnas sekretessinställningar. Information om vilka aktiveringspartners som har stöd för IAB TCF finns i vår [lista över enhetsbaserade destinationer](/help/using/features/destinations/device-based-destinations-list.md).

## Bifoga samtycke till URL:er som skickats till URL-mål

Audience Manager-integrationen med IAB TCF v2.2 stöder tillägg av samtycke till information som skickas till [URL-mål](../../features/destinations/create-url-destination.md) som är integrerade med IAB TCF v2.2. Den här processen utförs dock inte automatiskt av Audience Manager för att undvika att vissa URL-format bryts.

Kunder som vill bifoga samtycke till data som skickas till [!DNL URL destinations] måste manuellt lägga till makrona `${GDPR}` och `${GDPR_CONSENT_XXXX}` i URL-formatet och ersätta `XXXX` med målpartner-ID:t.

Exempel: `https://yourdomain.com?gdpr=${GDPR}&gdpr_consent=${GDPR_CONSENT_1234}`.

Mer information om målmakron som stöds finns i [Målmakron definierade](../../features/destinations/destination-macros.md).

## Hantering av enhetsövergripande samtycke

Audience Manager-plugin-programmet för IAB TCF väljer automatiskt ut de ID:n som finns på en begäran när besökarna på platsen inte har tillräcklig behörighet. Om begäran innehåller ett [korsenhets-ID (CRM-ID)](../../reference/ids-in-aam.md), skickar Audience Manager ut ID:t tillsammans med den sista enheten som är länkad till det [korsenhets-ID:t (CRM-ID)](../../reference/ids-in-aam.md).

## Testa implementeringen av IAB {#test-iab-implementation}

Om du vill testa att du har implementerat Audience Manager-plugin-programmet för IAB TCF korrekt läser du [Use Case 4 in Validating Opt-in Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/testing-optin-and-iab-plugin.html?lang=sv-SE#section-64331998954d4892960dcecd744a6d88).

## IAB och avanmälan i Audience Manager. Prioritetsordning. {#iab-and-optout}

Ett annat sekretessalternativ för användarna är möjligheten att välja bort all datainsamling. Adobe ger användarna möjlighet att göra detta på sidan [Your Privacy Choices](https://www.adobe.com/se/privacy/opt-out.html#customeruse).

Avanmälningar i Audience Manager behandlas i en [separat artikel i vår dokumentation](data-privacy-requests.md#opt-out-requests).

>[!IMPORTANT]
>
>Användare som har avanmält sig från all datainsamling efter att de avböjt sitt samtycke kan inte återinsättas.

>[!NOTE]
>
>**Prioritetsordning** – Om användaren väljer bort datainsamling med ett globalt avanmälningsverktyg, som beskrivs i länken ovan, har detta företräde över anmälningar och IAB-verifieringar.

## Ytterligare resurser {#additional-resources}

* [Adobe Experience Platform Identity Service Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=sv-SE)
* [IAB Europe GDPR Transparency and Consent Framework](https://iabtechlab.com/standards/gdpr-transparency-and-consent-framework/)
* [Tekniska specifikationer för IAB Europe GDPR Transparency och Consent Framework](https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/Consent%20string%20and%20vendor%20list%20formats%20v1.1%20Final.md)
* [IAB TCF-plugin – videodemonstration](https://helpx.adobe.com/audience-manager/kt/using/iab-tcf-support-audience-manager-technical-video-implement.html)
