---
description: 'Svar på vanliga frågor om personbaserade destinationer.  '
seo-description: 'Svar på vanliga frågor om personbaserade destinationer.  '
seo-title: Vanliga frågor om personbaserade destinationer
solution: Audience Manager
title: Vanliga frågor om personbaserade destinationer
translation-type: tm+mt
source-git-commit: a40d0be8ece674c1870e6f27003bfbe9d55d7316

---


# Vanliga frågor om personbaserade destinationer {#people-based-destinations-faq}

Svar på vanliga frågor om [!DNL People-Based Destinations].

## Tillgänglighet {#availability}

**Jag kan inte se[!DNL People-Based Destinations]i mitt Audience Manager-konto. Vad behöver jag veta om tillgänglighet?**

[!DNL People-Based Destinations] är en premiumfunktion för Audience Manager som är tillgänglig vid köp. Kontakta din Adobe-återförsäljare för mer information om priser och tillgänglighet.

## Datainhämtning {#data-onboarding}

**Hur kan jag lägga in e-postadresser till Audience Manager så att jag kan använda dem i[!DNL People-Based Destinations]?**

Det finns två sätt att överföra offlinedata till Audience Manager för [!DNL People-Based Destinations].

* **Använd filbaserad ID-synkronisering**. Mer information om hur ID-synkroniseringsfiler ska se ut finns i [Namn- och innehållskrav för ID-synkroniseringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) . När du använder den här metoden kan du ange alla hash-kodade e-postadresser från din [!DNL CRM] databas som mål.
* **Använd deklarerade ID:n** för att deklarera hashade e-postadresser när autentiserade kund-ID skickas. När du använder den här metoden aktiverar Audience Manager bara de streckade e-postadresserna från användare som har autentiserat online. De e-postadresser som aktiveras via Facebook är bara de som finns i de deklarerade ID-händelseanropen. Andra e-postadresser som är kopplade till kund-ID aktiveras inte i realtid.

**Kan jag samla in hashade e-postadresser via ett webbformulär eller en mobilapp eller måste de gå igenom en gruppfil?**

Du kan samla in hashade e-postadresser via webbautentisering med hjälp [!DNL ECID] av [deklarerade ID:n](../features/declared-ids.md). Med gruppfilen kan du även samla in hash-kodade e-postadresser som inte kan skickas via autentisering (t.ex. vilande användare i ([!DNL CRM]) och aktivera dem i personbaserade mål.

**Hur skiljer sig inmatningen av hash-kodade e-postadresser via webbformulär från överföringen av hash-kodade e-postadresser via batchfiler?**

Inmatning av offlinedata är utformat för att stödja användningsfall utan autentisering, och en ny profilkopplingsregel ([!UICONTROL All Cross-Device Profiles]) som körs på alla offlineprofiler [!DNL CRM] oavsett autentisering är tillgänglig som en del av [!DNL People-Based Destinations]. Denna metod är avsedd att komplettera intag av autentiserade målgrupper från onlinekällor.

**Hur ofta kan jag skicka/uppdatera hashade e-postadresser?**

* När du använder deklarerade ID:n skickar Audience Manager de streckade e-postadresserna till målet i realtid.
* När data hämtas via ID-synkroniseringsfiler bearbetar Audience Manager dem dagligen.

**Hur vet jag om e-postadresshashningen är korrekt?**

Audience Manager kan inte importera den obearbetade e-postadressen och vi kan inte verifiera att hash-konfigurationen har gjorts korrekt. Se [Förutsättningar och överväganden](../features/destinations/people-based-destinations-prerequisites.md) för mer information om hur du bör hash-koda data.

## Regler för profilsammanslagning {#profile-merge-rules}

**Finns det en ny regel för profilsammanslagning som jag kan använda med[!DNL People-Based Destinations]?**

Ja. Kunder som köper [!DNL People-Based Destinations] får även tillgång till en ny profilkopplingsregel för offlinesegmentering. Regeln anropas [!DNL All Cross-Device Profiles] och används för segmentering endast offline. När du registrerar dig för [!DNL People-Based Destinations]är detta den fjärde profilsammanslagningsregeln som du kan skapa, förutom de tre befintliga autentiseringsbaserade reglerna.

**Måste jag duplicera mina befintliga målgruppssegment för att aktivera dem i[!DNL People-Based Destinations]?**

Det beror på ditt användningssätt. Om du planerar att aktivera befintliga förstapartssegment i personbaserade kanaler behöver du inte skapa nya segment. Du kan bara mappa segmenten till ett personbaserat mål.

Om du planerar att aktivera nya offlinemålgrupper i personbaserade kanaler måste du skapa nya förstapartssegment med [!DNL All Cross-Device Profiles] sammanfogningsregeln.
>[!NOTE]
>
> Du kan bara mappa segment med egna data till [!DNL People-Based Destinations]. Våra målplattformar accepterar inte segment med data från andra leverantörer.

## Matcha hastigheter {#match-rates}

**Har ni[!DNL People-Based Destinations]insyn i matchningsfrekvenser eller adresserbara målgrupper?**

Nej. När målgruppssegment skickas till [!DNL People-Based Destinations]sker målgruppsmatchning på partnersidan. Adobe har inte tillgång till dessa mätvärden. Audience Manager visar den maximala delningsbara målgruppen för varje mål och antalet personer som tillhör ett segment i realtid. Den här informationen kan hjälpa er med kampanjplanering och prognoser.

**Hur skulle matcha frekvenser med hjälp av[!DNL People-Based Destinations]teoretiskt jämfört med andra metoder för att skicka målgrupper till målplattformar?**

Så länge e-postadressen är hash-kodad och korrekt inkapslad ska det inte finnas någon skillnad i matchningsfrekvensen mellan [!DNL People-Based Destinations] och andra metoder. Den enda anledningen till att en matchningsfrekvens skulle vara under 100 % är om e-postadresserna som hämtas till Audience Manager inte kan matchas med en e-postadress i målplattformens användarbas.

**Jag samlar in e-postadresser till arbetet från mina kunder, som skiljer sig från de personliga e-postadresser som används i sociala nätverk. Hur matchar ni identiteter för flera e-postadresser?**

Audience Manager kan samla in och skicka upp till 10 e-postmeddelanden per användare till målplattformar, men e-postadresserna måste hämtas via synkroniseringsfiler. När Audience Manager har skickat e-postadresserna till målplattformarna är det upp till plattformarna att matcha e-postadresserna mot sin egen användarbas. Vissa plattformar kan ha ytterligare e-postadressdiagram som matchar adresser som skickats från Audience Manager till användarprofiler.

## Dataexportkontroller {#data-export-controls}

**Hur[!DNL Data Export Controls]fungerar det med[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] kommer att blockera segment som innehåller data från andra leverantörer och tredjepartsdata som användare försöker skicka till [!DNL People-Based Destinations]. [!DNL People-Based Destinations] endast tillåta att egna data används för målinriktning. [!DNL Data Export Controls] blockera även segment med hjälp [!DNL Profile Merge Rules] av enhetsdiagram. [!DNL People-Based Destinations] skapas med rätt etiketter för dataexport markerade och du kan inte skriva över exportinställningarna.

## Partnerspecifika frågor {#partner-specific-questions}

### [!DNL Facebook]

**Vad behöver jag göra innan jag kan skicka målgruppssegment till[!DNL Facebook]?**

Innan du kan använda [!DNL People-Based Destinations] för att skicka målgruppssegment till [!DNL Facebook]måste du utföra följande konfigurationsuppgifter:

1. Lägg till Adobe Experience Cloud-företagskontot som annonspartner i ert företag [!DNL Facebook Ad Account]. Använd `business ID=206617933627973`. Mer information finns i Lägg till partners i din Business Manager.

   >[!IMPORTANT]
   >
   > När du konfigurerar behörigheter för Adobe Experience Cloud måste du aktivera behörigheten Hantera kampanjer. Detta krävs för [!DNL People-Based Destinations] integreringen.

1. Läs och signera [!DNL Facebook Custom Audiences Terms of Service]. För att göra detta, gå till `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, var `accountID` är din [!DNL Facebook Ad Account ID].

**Stöder[!DNL People-Based Destinations]målgruppsanpassning i andra[!DNL Facebook]appar, som[!DNL Instagram]?**

Du kan använda [!DNL People-Based Destinations] i alla [!DNL Facebook]de appar som stöds av [!DNL Custom Audiences], inklusive [!DNL Facebook], [!DNL Instagram]och [!DNL Audience Network] [!DNL Messenger]. Valet av det program som du vill köra kampanjen mot anges på placeringsnivån i [!DNL Facebook Ads Manager].

**Vad är skillnaden mellan[!DNL People-Based Destinations]och[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] utnyttjar integreringen [!DNL Custom Audiences (CA)] med [!DNL Facebook]. Skillnaden mellan [!DNL WCA] och [!DNL CA] integreringar är nyckeln kunderna använder när de skickar målgrupper till [!DNL Facebook]. [!DNL WCA] använder [!DNL Facebook] pixeln (som skulle vara ett användar-ID för en webbplats) medan hash- [!DNL People-Based Destinations] e-postadresser används för integrering med [!DNL CA].

Ni kan använda Audience Managers [!DNL Facebook] integrering [!DNL WCA] via [!DNL URL Destinations] funktionen utan extra kostnad.

Dessa två integreringar kompletterar varandra. ni kan använda båda för att få bättre täckning. Som exempel kan [!DNL WCA] de användas för prospektering när ett företag söker efter besökare på en webbplats som inte har registrerat ett konto, medan [!DNL People-Based Destinations] kan hjälpa er att rikta er till befintliga kunder som har angett sin e-postadress men kanske inte besökt webbplatsen.
