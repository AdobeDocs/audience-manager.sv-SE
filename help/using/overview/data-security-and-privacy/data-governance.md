---
description: Det här dokumentet förklarar hur kunddata styrs i Audience Manager.
seo-description: Det här dokumentet förklarar hur kunddata styrs i Audience Manager.
seo-title: Datastyrning
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Datastyrning
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# Datastyrning

## Översikt {#overview}

Datastyrning i Audience Manager avser livscykeln för era kunddata i Audience Manager, och omfattar [insamling och fakturering av IP-adresser](data-governance.md#collecting-ip-addresses), [datalagring](data-governance.md#data-retention)och [gränsöverskridande dataöverföringar](data-governance.md#data-transfers).

## Samlar in IP-adresser och IP-adressofficering {#collecting-ip-addresses}

Besökarens [!DNL IP] adress till kundens webbplats skickas till Adobe [!DNL Data Processing Center] ([!DNL DPC]) där [!DNL IP] adressen kan lagras. Beroende på vilken nätverkskonfiguration besökaren har kan det hända att [!DNL IP] adressen inte nödvändigtvis representerar [!DNL IP] adressen till besökarens dator. Adressen kan till exempel vara den externa [!DNL IP] adressen till en NAT-brandvägg (Network Address Translation), [!DNL IP] [!DNL HTTP] proxy eller Internet gateway.

**IP-faktureringsmetod:** I enlighet med principerna för&quot;Integritet via design&quot; kan kunder med Adobe Audience Manager möjliggöra [!DNL IP] obfuktioner från användargränssnittet, antingen globalt i alla geografiska regioner eller för specifika länder. När du aktiverar den här inställningen ignoreras den sista oktetten (den sista delen) i [!DNL IP] adressen omedelbart när [!DNL IP] adressen hämtas till Audience Manager. Audience Manager tar bort den här delen av [!DNL IP] adressen innan den bearbetas (inklusive före valfri geografisk sökning eller loggning av [!DNL IP] adressen). Exempel:

* Före: `255.255.255.255`
* Efter: `255.255.255.0`

>[!NOTE]
>
>Se [IP-adressofficering](../../features/administration/ip-obfuscation.md) om du vill veta mer om hur du aktiverar [!DNL IP] adressofuschering i gränssnittet för Audience Manager.

Se videon nedan för att förstå hur [!DNL IP] adressofuscation fungerar i Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geografisk segmentering:** Om du aktiverar [!DNL IP] adressokation kan de återstående oktetterna i [!DNL IP] adressen fortfarande användas för geosegmentering och rapportering i Audience Manager. Om du inte aktiverar [!DNL IP] adressofficering använder Audience Manager den fullständiga [!DNL IP] adressen. Du kan använda funktionen Geografisk segmentering som gör att du kan identifiera en [!DNL IP] plats efter geografiskt område i båda fallen, men med en viss minskad precision när [!DNL IP] förvrängning används. Att få information på stadsnivå påverkas sannolikt avsevärt av att [!DNL IP] adressen döljs. Att få information på region- och landnivå bör endast få en liten inverkan. Geografiska segmenteringsdata är endast detaljerade för postnummer eller postnummernivå och inte för enskilda nivåer. Läs mer om [geoanpassning](../../features/traits/trait-geotarget-keys.md) och hur du ställer in egenskaper med geografiska variabler.

## Datalagring i Audience Manager {#data-retention}

Att tillämpa lämpliga, säkra och lägliga regler för datalagring är en viktig del av att följa reglerna för datasekretess. Audience Manager-kunder kan ange anpassade kvarhållningsperioder för egenskaper och segment genom att definiera den TTL-värde som krävs (time to live). Mer information om kvarhållningsperioder finns i Vanliga frågor om [datalagring](../../faq/faq-privacy.md) .

## Gränsöverskridande dataöverföringar {#data-transfers}

När Audience Manager överför personuppgifter från kunder över nationsgränser gör Audience Manager det i enlighet med tillämplig lag. Läs mer på [Adobes sekretesscenter](https://www.adobe.com/privacy/eudatatransfers.html) .