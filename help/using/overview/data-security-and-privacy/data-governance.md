---
description: Det här dokumentet förklarar hur kunddata regleras i Audience Manager.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: GDPR-gränssnitt, GDPR API, CCPA, sekretess, samtycke, obfuskation, styrning
title: Datastyrning
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 90%

---

# Datastyrning

## Översikt {#overview}

Datastyrning i Audience Manager avser livscykeln för era kunddata i Audience Manager och omfattar [insamling och döljande av IP-adresser](data-governance.md#collecting-ip-addresses), [datalagring](data-governance.md#data-retention) och [gränsöverskridande dataöverföringar](data-governance.md#data-transfers).

## Samlar in IP-adresser och IP-adressofficering {#collecting-ip-addresses}

[!DNL IP]-adressen till en person som besöker kundens webbplats skickas till Adobe [!DNL Data Processing Center] ([!DNL DPC]) där [!DNL IP]-adressen kan lagras. Beroende på vilken nätverkskonfiguration besökaren har kan det hända att [!DNL IP]-adressen inte nödvändigtvis representerar [!DNL IP]-adressen till besökarens dator. Adressen kan till exempel vara den externa [!DNL IP]-adressen till en NAT-brandvägg (Network Address Translation) [!DNL IP], en [!DNL HTTP]-proxy eller en internetgateway.

**Metod för att dölja IP-adress:** I enlighet med principerna för Privacy By Design kan Adobe Audience Manager-kunder dölja [!DNL IP] i användargränssnittet, antingen globalt i alla geografiska regioner eller för specifika länder. När du aktiverar den här inställningen ignoreras den sista oktetten (den sista delen) i [!DNL IP]-adressen omedelbart när [!DNL IP]-adressen hämtas till Audience Manager. Audience Manager tar bort den här delen av [!DNL IP]-adressen innan den bearbetas (inklusive före valfri geografisk sökning eller loggning av [!DNL IP]-adressen). Exempel:

* Före: `255.255.255.255`
* Efter: `255.255.255.0`

>[!NOTE]
>
>Mer information om hur du aktiverar [-adressofficering i Audience Manager-användargränssnittet finns i ](../../features/administration/ip-obfuscation.md)IP-adressofficering[!DNL IP].

Titta på videon nedan för att få veta mer om hur du döljer [!DNL IP]-adresser i Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geografisk segmentering:** Om du aktiverar dolda [!DNL IP]-adresser kan de återstående oktetterna i [!DNL IP]-adressen fortfarande användas för geosegmentering och rapportering i Audience Manager. Om du inte aktiverar dolda [!DNL IP]-adresser använder Audience Manager den fullständiga [!DNL IP]-adressen. Du kan i båda fallen använda funktionen för geografisk segmentering när du vill identifiera en [!DNL IP]-plats efter geografiskt område, men med lite sämre precision när dolda [!DNL IP]-adresser används. Information på ortsnivå påverkas sannolikt mycket när [!DNL IP]-adresserna döljs. Information på regions- och landsnivå påverkas förmodligen bara en aning. Geografiska segmenteringsdata är bara granulära på orts- eller postnummernivå, inte på individnivå. Läs mer om [geografisk målanpassning](../../features/traits/trait-geotarget-keys.md) och hur du ställer in traits med geografiska variabler.

## Datalagring i Audience Manager {#data-retention}

Att tillämpa lämpliga, säkra och tidsanpassade principer för datalagring är en viktig del av att följa dataskyddsreglerna. Audience Manager-kunder kan ange anpassade lagringsperioder för traits och segment genom att definiera det TTL-värde (time to live) som krävs. Mer information om lagringsperioder finns i [vanliga frågor om datalagring](../../faq/faq-privacy.md).

## Gränsöverskridande dataöverföringar {#data-transfers}

När Audience Manager överför personuppgifter från kunder över nationsgränser gör Audience Manager det i enlighet med tillämplig lag. Läs mer på [Adobes sekretesscenter](https://www.adobe.com/se/privacy/eudatatransfers.html).
