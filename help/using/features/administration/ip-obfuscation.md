---
description: Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.
seo-description: Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.
solution: Audience Manager
title: Dölja IP-adresser
feature: Data Governance & Privacy
exl-id: 8c976d1e-f4ba-4892-bd68-d4e74bdb4d9b
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '473'
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

Se även Samla in IP-adresser och IP-adressofficering i [avsnittet Dataintegritet](/help/using/overview/data-security-and-privacy/data-privacy.md).

## Krav för IP-adressofficering {#ip-obfuscation-requirements}

IP-adressofficering är bara tillgängligt för administratörskonton i Audience Manager. Se [Skapa användare](/help/using/features/administration/administration-overview.md#create-users) om du vill veta mer om hur du tilldelar administratörsbehörighet för en användare.

>[!NOTE]
>
> På grund av den stora datamängden som bearbetas av Audience Manager kan det ta upp till 4 timmar innan ändringar av IP-döljning börjar gälla, från det att du uppdaterar inställningarna.

## Konfigurera IP-adressofficering {#configure-ip-obfuscation}

Följ stegen nedan för att konfigurera IP-adressofficering.

1. Logga in på Audience Manager med ett administratörskonto och gå till **Administration > Sekretess**.
2. Välj den typ av IP-förfalskning som du vill använda.
   1. **Begränsa alla IP-adresser:** välj det här alternativet om du vill att Audience Manager ska dölja den sista oktetten för alla IP-adresser för besökare, oavsett varifrån de kommer.
   2. **Begränsa IP-adresser för specifika länder:** välj det här alternativet om du vill att Audience Manager ska dölja den sista oktetten med IP-adresser för besökare för specifika länder. Använd fältet **Lista över länder** eller motsvarande **Sök** för att hitta de länder som IP-förfalskning ska aktiveras för och klicka på ikonen + för att lägga till dem i listan **Markerad för falering**. När du har lagt till alla nödvändiga länder i listan **Vald för Obfuscation** klickar du på **Spara**.

![](assets/ip-obfuscation.png)

## Inaktivera IP-adressfel {#disable-ip-obfuscation}

Om du vill inaktivera IP-adressförfalskning globalt går du till **Administration > Sekretess**, väljer **Begränsa inte IP-adresser** och klickar på **Spara**.

Om du vill inaktivera IP-adressofficering för specifika länder ska du leta reda på länderna i listan **Markerad för faltning** och sedan klicka på motsvarande **X**-ikon. Klicka på **Spara** när du är klar.

## Relaterade begrepp {#related-concepts}

* [Datasekretess](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Videodemonstration om IP-adressofuscation
>[!VIDEO](https://video.tv.adobe.com/v/27218/)
