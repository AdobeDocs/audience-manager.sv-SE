---
description: Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.
seo-description: Your company may desire to obfuscate IP address in many countries due to global privacy regulations. Audience Manager allows you to obfuscate visitor IP addresses on a global or country-by-country basis.
solution: Audience Manager
title: IP-adressofficering
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
source-git-commit: ae074cdeb8dcf6f6a224c2ede5f3bb704b28f49f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 0%

---

# IP-adressofficering {#ip-obfuscation}

Använd den här funktionen för att dölja IP-adresser som samlats in i Audience Manager.

## Översikt och metod {#overview-and-methodology}

Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.

### IP-faktureringsmetod

I enlighet med principerna för&quot;Integritet via design&quot; tillåter Adobe Audience Manager kunderna att aktivera IP-förfalskning från användargränssnittet, antingen globalt i alla geografiska regioner eller för specifika länder. När du aktiverar den här inställningen ignoreras den sista oktetten (den sista delen) i IP-adressen omedelbart när IP-adressen importeras till Audience Manager. Audience Manager ignorerar den här delen av IP-adressen före bearbetning (inklusive före eventuell geografisk sökning eller loggning av IP-adressen). Exempel:

* Före förvrängning: `255.255.255.255`
* Efter förvrängning: `255.255.255.0`

Se även Samla in IP-adresser och IP-adressofficering i avsnittet [Dataintegritet](/help/using/overview/data-security-and-privacy/data-privacy.md).

### Prioritet för IP-obefuscation {#precedence}

[IP-ojämnheter på datastranaminivå](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=en#create) har företräde framför IP-ofuskeringsalternativ som har angetts i Audience Manager, och de tillämpas på alla IP-adresser. Alla sökningar efter geopositionering som görs av Audience Manager påverkas av alternativet [!UICONTROL IP obfuscation] på datastream-nivå. En sökning efter geopositionering i Audience Manager, som baseras på en helt okomplicerad IP-adress, resulterar i en okänd region och eventuella segment som baseras på den resulterande geopositioneringsinformationen inte realiseras.

## Krav för IP-adressofficering {#ip-obfuscation-requirements}

IP-adressofficering är bara tillgängligt för Audience Manager administratörskonton. Mer information om hur du tilldelar administratörsbehörighet för en användare finns i [Skapa användare](/help/using/features/administration/administration-overview.md#create-users).

>[!NOTE]
>
> På grund av den stora datamängden som bearbetas av Audience Manager kan det ta upp till 4 timmar innan ändringar av IP-kompabiliteten börjar gälla, från det att du uppdaterar inställningarna.

## Konfigurera IP-adressofuscation {#configure-ip-obfuscation}

Följ stegen nedan för att konfigurera IP-adressofficering.

1. Logga in på Audience Manager med ett administratörskonto och gå till **Administration > Sekretess**.
2. Välj den typ av IP-förfalskning som du vill använda.
   1. **Förhindra alla IP-adresser:** Välj det här alternativet om du vill att Audience Manager ska dölja den sista oktetten för alla IP-adresser för besökare, oavsett vilket område de kommer från.
   2. **Begränsa IP-adresser för specifika länder:** Välj det här alternativet om du vill att Audience Manager ska dölja den sista oktetten med IP-adresser för besökare för specifika länder. Använd **listan över länder** eller motsvarande **sökfält** för att hitta de länder där IP-förfalskning ska aktiveras och klicka på plusikonen (+) för att lägga till dem i listan **Markerade för förfalskning** . När du har lagt till alla de länder som krävs i listan **Vald för obfuktion** klickar du på **Spara**.

![](assets/ip-obfuscation.png)

## Inaktivera IP-adressfel {#disable-ip-obfuscation}

Om du vill inaktivera IP-adressförfalskning globalt går du till **Administration > Sekretess**, väljer **Begränsa inte IP-adresser** och klickar på **Spara**.

Om du vill inaktivera IP-adressofficering för specifika länder söker du efter länderna i listan **Markerade för förfalskning** och klickar sedan på motsvarande **X** -ikon. Klicka på **Spara** när du är klar.

## Relaterade begrepp {#related-concepts}

* [Dataintegritet](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Videodemonstration om IP-adressofuscation
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
