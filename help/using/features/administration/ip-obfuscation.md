---
description: Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: Dölja IP-adresser
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 2%

---

# Dölja IP-adresser {#ip-obfuscation}

Använd den här funktionen för att dölja IP-adresser som samlats in i Audience Manager.

## Översikt och metod {#overview-and-methodology}

Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.

### IP-faktureringsmetod

I enlighet med principerna för&quot;Integritet via design&quot; tillåter Adobe Audience Manager kunderna att aktivera IP-förfalskning från användargränssnittet, antingen globalt i alla geografiska regioner eller för specifika länder. När du aktiverar den här inställningen ignoreras den sista oktetten (den sista delen) i IP-adressen omedelbart när IP-adressen hämtas till Audience Manager. Audience Manager ignorerar den här delen av IP-adressen före bearbetning (inklusive före eventuell geografisk sökning eller loggning av IP-adressen). Exempel:

* Före obfuskering: `255.255.255.255`
* Efter obfuktion: `255.255.255.0`

Se även Samla in IP-adresser och IP-adressofficering i vår [Avsnittet Dataintegritet](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Prioritet för IP-obefuscation {#precedence}

[IP-obfuskation på datasterivå](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create) har företräde framför alla IP-felsökningsalternativ som har angetts i Audience Manager, och de tillämpas på alla IP-adresser. Alla sökningar efter geopositionering som gjorts av Audience Manager påverkas av datastream-nivån [!UICONTROL IP obfuscation] alternativ. En sökning efter geopositionering i Audience Manager, som baseras på en helt okomplicerad IP-adress, resulterar i en okänd region och inga segment som baseras på resulterande geopositioneringsdata kommer att realiseras.

## Krav för IP-adressofficering {#ip-obfuscation-requirements}

IP-adressofficering är bara tillgängligt för administratörskonton i Audience Manager. Se [Skapa användare](/help/using/features/administration/administration-overview.md#create-users) för att förstå hur du tilldelar administratörsbehörighet för en användare.

>[!NOTE]
>
> På grund av den stora datamängden som bearbetas av Audience Manager kan det ta upp till 4 timmar innan ändringar av IP-döljning börjar gälla, från det att du uppdaterar inställningarna.

## Konfigurera IP-adressofuscation {#configure-ip-obfuscation}

Följ stegen nedan för att konfigurera IP-adressofficering.

1. Logga in på Audience Manager med ett administratörskonto och gå till **Administration > Integritet**.
2. Välj den typ av IP-förfalskning som du vill använda.
   1. **Obfuscera alla IP-adresser:** Markera det här alternativet om du vill att Audience Manager ska dölja den sista oktetten för alla IP-adresser för besökare, oavsett varifrån de kommer.
   2. **Obfuscera IP-adresser för specifika länder:** Markera det här alternativet om du vill att Audience Manager ska dölja den sista oktetten med IP-adresser för besökare för specifika länder. Använd **Förteckning över länder** eller motsvarande **Sök** för att hitta de länder där IP-förfalskning ska aktiveras och klicka på +-ikonen för att lägga till dem i **Markerad för obfuskation** lista. När du har lagt till alla de länder som krävs i **Markerad för obfuskation** lista, klicka på **Spara**.

![](assets/ip-obfuscation.png)

## Inaktivera IP-adressfel {#disable-ip-obfuscation}

Om du vill inaktivera IP-adressofusk globalt går du till **Administration > Integritet**, markera **Tvinga inte bort IP-adresser** och klicka **Spara**.

Om du vill inaktivera IP-adressofficering för specifika länder kan du hitta länderna i **Markerad för obfuskation** klicka sedan på motsvarande **X** -ikon. Klicka **Spara** när du är klar.

## Relaterade begrepp {#related-concepts}

* [Datasekretess](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Videodemonstration om IP-adressofuscation
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
