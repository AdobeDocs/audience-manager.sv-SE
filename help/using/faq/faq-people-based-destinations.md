---
description: 'Svar på vanliga frågor om personbaserade destinationer.  '
seo-description: 'Svar på vanliga frågor om personbaserade destinationer.  '
seo-title: Vanliga frågor om personbaserade destinationer
solution: Audience Manager
title: Vanliga frågor om personbaserade destinationer
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 100%

---


# Vanliga frågor om personbaserade destinationer {#people-based-destinations-faq}

Svar på vanliga frågor om [!DNL People-Based Destinations].

## Tillgänglighet {#availability}

**Jag kan inte se [!DNL People-Based Destinations] på mitt Audience Manager-konto. Vad behöver jag veta om tillgänglighet?**

[!DNL People-Based Destinations] är en premiumfunktion i Audience Manager som kan köpas. Kontakta din Adobe-återförsäljare för mer information om priser och tillgänglighet.

## Dataregistrering {#data-onboarding}

**Hur registrerar jag e-postadresser till kunder i Audience Manager så att jag kan använda dem i [!DNL People-Based Destinations]?**

Det finns två sätt att överföra offlinedata till Audience Manager för [!DNL People-Based Destinations].

* **Filbaserad ID-synkronisering**. Mer information om hur filer för ID-synkronisering ska se ut finns i [Namn- och innehållskrav för ID-synkroniseringsfiler](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). När du använder den här metoden kan du rikta dig till alla hash-kodade e-postadresser från din [!DNL CRM]-databas.
* **Deklarerade ID:n** kan användas för att deklarera hash-kodade e-postadresser när autentiserade kund-ID skickas. När du använder den här metoden aktiverar Audience Manager bara de hash-kodade e-postadresserna för användare som har autentiserat online. E-postadresser som aktiveras via Facebook är bara de som finns i deklarerade ID-händelseanrop. Andra e-postadresser som är kopplade till kund-ID:n aktiveras inte i realtid.

**Kan jag samla in hash-kodade e-postadresser via ett webbformulär eller en mobilapp eller måste de överföras i kommandofiler?**

Du kan samla in hash-kodade e-postadresser via webbautentisering med [!DNL ECID] och [deklarerade ID:n](../features/declared-ids.md). Med kommandofilen kan du även samla in hash-kodade e-postadresser som inte kan skickas via autentisering (t.ex. vilande användare i ([!DNL CRM]) och aktivera dem i personbaserade destinationer.

**Hur skiljer sig inmatningen av hash-kodade e-postadresser via webbformulär från överföringen av hash-kodade e-postadresser via kommandofiler?**

Inmatning av offlinedata är utformat för användningsområden utan autentisering och en ny regel för profilsammanslagning ([!UICONTROL All Cross-Device Profiles]) som körs på alla [!DNL CRM]-offlineprofiler oavsett autentisering är tillgänglig som en del av [!DNL People-Based Destinations]. Denna metod är avsedd att komplettera inmatning av autentiserade målgrupper från onlinekällor.

**Hur ofta kan jag skicka/uppdatera hash-kodade e-postadresser?**

* När du använder deklarerade ID:n skickar Audience Manager de hash-kodade e-postadresserna till destinationen i realtid.
* När data hämtas via ID-synkroniseringsfiler bearbetar Audience Manager dem dagligen.

**Hur vet jag om e-postadresserna hash-kodats korrekt?**

Audience Manager kan inte importera obearbetade e-postadresser och vi kan inte verifiera att hash-kodningen har utförts korrekt. Se [Förutsättningar och överväganden](../features/destinations/people-based-destinations-prerequisites.md) för mer information om hash-kodning av registrerade data.

## Regler för profilsammanslagning {#profile-merge-rules}

**Finns det en ny regel för profilsammanslagning som jag kan använda med [!DNL People-Based Destinations]?**

Ja. Kunder som köper [!DNL People-Based Destinations] får även tillgång till en ny regel för profilsammanslagning för offlinesegmentering. Regeln kallas för [!DNL All Cross-Device Profiles] och används bara för segmentering offline. När du registrerar dig för [!DNL People-Based Destinations] är det den fjärde regeln för profilsammanslagning som du kan skapa, förutom de tre befintliga autentiseringsbaserade reglerna.

**Måste jag kopiera mina befintliga målgruppssegment för att aktivera dem i [!DNL People-Based Destinations]?**

Det beror på ert användningsområde. Om ni planerar att aktivera befintliga förstapartssegment i personbaserade kanaler behöver ni inte skapa nya segment. Ni behöver bara mappa segmenten till en personbaserad destination.

Om ni planerar att aktivera nya offlinemålgrupper i personbaserade kanaler måste ni skapa nya förstapartssegment med regeln [!DNL All Cross-Device Profiles] för sammanslagning.
>[!NOTE]
>
> Ni kan bara mappa segment med förstapartsdata till [!DNL People-Based Destinations]. Våra destinationsplattformar accepterar inte segment med data från andra- eller tredjepartsleverantörer.

## Matchningsfrekvenser {#match-rates}

**Har [!DNL People-Based Destinations] insyn i matchningsfrekvenser eller adresserbara målgrupper?**

Nej. När målgruppssegment skickas till [!DNL People-Based Destinations] sker målgruppsmatchning på partnersidan. Adobe har inte tillgång till dessa mätvärden. Audience Manager visar den maximala delbara målgruppen för varje destination och antalet personer som tillhör ett segment i realtid. Den här informationen kan hjälpa er med kampanjplanering och prognoser.

**Hur skulle matchningsfrekvenser med [!DNL People-Based Destinations] teoretiskt kunna jämföras med andra metoder för att skicka målgrupper till destinationsplattformar?**

Så länge e-postadressen är hash-kodad och korrekt inmatad bör det inte vara någon skillnad i matchningsfrekvensen mellan [!DNL People-Based Destinations] och andra metoder. Den enda anledningen till att en matchningsfrekvens är under 100 % är om e-postadresserna som hämtas till Audience Manager inte kan matchas med en e-postadress i destinationsplattformens användardatabas.

**Jag samlar in e-postadresser till arbetet från mina kunder och de skiljer sig från de personliga e-postadresserna som används i sociala nätverk. Hur matchar ni identiteter för flera e-postadresser?**

Audience Manager kan samla in och skicka upp till 10 e-postadresser per användare till destinationsplattformar, men e-postadresserna måste hämtas via synkroniseringsfiler. När Audience Manager har skickat e-postadresserna till destinationsplattformarna är det upp till plattformarna att matcha e-postadresserna mot sin egen användardatabas. Vissa plattformar kan ha ytterligare e-postadressdiagram som matchar adresser som skickas från Audience Manager med användarprofiler.

## Kontroller vid dataexport {#data-export-controls}

**Hur fungerar [!DNL Data Export Controls] med [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] kommer att blockera segment som innehåller data från andra och tredje part som användare försöker skicka till [!DNL People-Based Destinations]. Endast förstapartsdata tillåts för målinriktning i [!DNL People-Based Destinations]. [!DNL Data Export Controls] blockerar även segment med [!DNL Profile Merge Rules] med enhetsdiagram. [!DNL People-Based Destinations] skapas med lämpliga etiketter för dataexport markerade och du kan inte skriva över exportinställningarna.

## Partnerspecifika frågor {#partner-specific-questions}

### [!DNL Facebook]

**Vad behöver jag göra innan jag kan skicka målgruppssegment till [!DNL Facebook]?**

Innan du kan använda [!DNL People-Based Destinations] för att skicka målgruppssegment till [!DNL Facebook] måste du konfigurera följande:

1. Lägg till Adobe Experience Cloud-företagskontot som annonspartner i [!DNL Facebook Ad Account]. Använd `business ID=206617933627973`. Mer information finns i Lägg till partners i Business Manager.

   >[!IMPORTANT]
   >
   > När du konfigurerar behörigheter för Adobe Experience Cloud måste du aktivera behörighet att hantera kampanjer. Det krävs för [!DNL People-Based Destinations]-integreringen.

1. Läs och signera [!DNL Facebook Custom Audiences Terms of Service]. Gör det genom att gå till `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, där `accountID` är din [!DNL Facebook Ad Account ID].

**Har [!DNL People-Based Destinations] stöd för målgruppsanpassning i andra [!DNL Facebook]-appar som [!DNL Instagram]?**

Du kan använda [!DNL People-Based Destinations] i alla [!DNL Facebook]-appar som stöds av [!DNL Custom Audiences], inklusive [!DNL Facebook], [!DNL Instagram], [!DNL Audience Network] och [!DNL Messenger]. Det program som ni valt att köra kampanjen mot anges av placeringsnivån i [!DNL Facebook Ads Manager].

**Vad är skillnaden mellan [!DNL People-Based Destinations] och [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] utnyttjar [!DNL Custom Audiences (CA)]-integreringen med [!DNL Facebook]. Skillnaden mellan [!DNL WCA]- och [!DNL CA]-integreringarna är nyckeln som kunderna använder när de skickar målgrupper till [!DNL Facebook]. [!DNL WCA] använder [!DNL Facebook]-pixeln (som kan vara ett användar-ID för en webbplats) medan [!DNL People-Based Destinations] använder hash-kodade e-postadresser för integrering med [!DNL CA].

Ni kan använda Audience Managers [!DNL Facebook]-integrering [!DNL WCA] via funktionen [!DNL URL Destinations] utan extra kostnad.

Dessa två integreringar kompletterar varandra och ni kan använda båda för att få bättre målgruppstäckning. Som exempel kan [!DNL WCA] användas för prospektering när ett företag söker efter webbplatsbesökare som inte har registrerat ett konto, medan [!DNL People-Based Destinations] kan hjälpa er att rikta er till befintliga kunder som har angett sin e-postadress men kanske inte besökt webbplatsen.
