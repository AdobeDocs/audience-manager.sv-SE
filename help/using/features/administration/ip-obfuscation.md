---
description: Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.
seo-description: Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.
solution: Audience Manager
title: IP-adressofuscation
translation-type: tm+mt
source-git-commit: f7206fda4b16a22c8a8bfcf97529cdaea24b0898

---


# IP-adressofuscation {#ip-obfuscation}

Använd den här funktionen för att dölja IP-adresser som samlats in i Audience Manager.

## Översikt och metod {#overview-and-methodology}

Ditt företag kanske vill dölja IP-adressen i många länder på grund av globala sekretessbestämmelser. Med Audience Manager kan ni dölja IP-adresser för besökare globalt eller för varje land.

### IP-faktureringsmetod

I enlighet med principerna för&quot;Integritet via design&quot; kan Adobe Audience Manager möjliggöra för kunder att dölja IP-adresser från användargränssnittet, antingen globalt i alla geografiska regioner eller för specifika länder. När du aktiverar den här inställningen ignoreras den sista oktetten (den sista delen) i IP-adressen omedelbart när IP-adressen hämtas till Audience Manager. Audience Manager ignorerar den här delen av IP-adressen före bearbetning (inklusive före eventuell geografisk sökning eller loggning av IP-adressen). Exempel:

* Före obfuskering: `255.255.255.255`
* Efter obfuktion: `255.255.255.0`

Se även Samla in IP-adresser och IP-adressofficering i avsnittet [](/help/using/overview/data-security-and-privacy/data-privacy.md)Dataintegritet.

## Krav för IP-adressofficering {#ip-obfuscation-requirements}

IP-adressofficering är bara tillgängligt för Audience Manager-administratörskonton. Mer information om hur du tilldelar administratörsbehörighet för en användare finns i [Skapa användare](/help/using/features/administration/administration-overview.md#create-users) .

>[!NOTE]
>
> På grund av den stora datamängden som bearbetas av Audience Manager kan det ta upp till 4 timmar innan ändringar av IP-kompabilitet börjar gälla, från det att du uppdaterar inställningarna.

## Konfigurera IP-adressofuscation {#configure-ip-obfuscation}

Följ stegen nedan för att konfigurera IP-adressofficering.

1. Logga in på Audience Manager med ett administratörskonto och gå till **Administration > Sekretess**.
2. Välj den typ av IP-förfalskning som du vill använda.
   1. **Obfuscera alla IP-adresser:** Välj det här alternativet om du vill att Audience Manager ska dölja den sista oktetten för alla IP-adresser för besökare, oavsett varifrån de kommer.
   2. **Obfuscera IP-adresser för specifika länder:** Välj det här alternativet om du vill att Audience Manager ska dölja den sista oktetten med IP-adresser för besökare för specifika länder. Använd **Listan över länder** eller motsvarande **sökfält** för att hitta de länder där IP-förfalskning ska aktiveras och klicka på ikonen + för att lägga till dem i listan **Valda för** förfalskning. När du har lagt till alla de länder som krävs i listan **Valda för** förfalskning klickar du på **Spara**.

![](assets/ip-obfuscation.png)

## Inaktivera IP-adressfel {#disable-ip-obfuscation}

Om du vill inaktivera IP-adressförfalskning globalt går du till **Administration > Sekretess**, väljer **Begränsa inte IP-adresser** och klickar på **Spara**.

Om du vill inaktivera IP-adressofficering för specifika länder ska du leta reda på länderna i listan **Vald för** förfalskning och sedan klicka på motsvarande **X** -ikon. Klicka på **Spara** när du är klar.

## Relaterade begrepp {#related-concepts}

* [Dataintegritet](/help/using/overview/data-security-and-privacy/data-privacy.md)
* Videodemonstration om IP-adressofuscation
>[!VIDEO](https://video.tv.adobe.com/v/27218/)

