---
description: Vanliga frågor och problem som rör målinriktning.
seo-description: Vanliga frågor och problem som rör målinriktning.
seo-title: Vanliga frågor om målgruppsanpassning
solution: Audience Manager
title: Vanliga frågor om målgruppsanpassning
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
translation-type: tm+mt
source-git-commit: 27ce94084e35ffa770858027d12235ca9f1f8430
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 0%

---


# Vanliga frågor om målgruppsanpassning{#targeting-faq}

Vanliga frågor och problem som rör målinriktning.

<br> 

<!-- 

faq_targeting.xml

 -->

**Var finns en fullständig lista över tredjepartsleverantörer som stöds av Audience Manager?**

På [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) finns en fullständig lista över tredjepartsleverantörer av data som [!DNL Audience Manager] stöds.

<br> 

**För att rikta in mig på användare som jag aldrig sett på min webbplats med data från tredje part, bör jag använda data från tredje part i Audience Manager eller i en DSP?**

Svaret beror på era mål. Om kampanjen till exempel är utformad för att hitta nya kunder med data från tredje part kan du arbeta direkt med en DSP. Kom ihåg att Audience Manager endast synkroniserar data med en tredjepartsleverantör när vi ser den användaren. Om vi aldrig har sett någon användare tidigare har vårt system ingen information för besökaren. För kampanjer som bara vill använda data från tredje part för att rikta sig till användare som aldrig besökt någon av era egenskaper skapar du dessa segment via DSP.

<br> 

**Kan jag marknadsföra till enskilda personer?**

Med Audience Manager kan du samla användare och marknadsföra dem baserat på delade attribut eller egenskaper. Men för att följa branschens regler får [!DNL Audience Manager] kunderna inte skicka personligt identifierbar information (PII) till våra system. Därför kan du inte använda e-postadresser, enskilda namn, fysiska adresser osv. för målinriktning.

<br> 

**Hur kan jag behålla återmarknadsföring av data på ett säkert sätt?**

Vi rekommenderar att du använder en server-till-server-anslutning för att utbyta data med den retargetingplattform du föredrar. Audience Manager utbyter data med de flesta vanliga DSP:er via server-till-server-anslutningar. Dataöverföringar från server till server förhindrar att andra aktörer fångar upp era data och säljer den målgruppsinformationen på nytt.

<br> 

**Är Audience Manager unika användar-ID (UUID) kopplat till en annonsservers unika användar-ID genom att ID synkroniseras direkt på sidan?**

Nej. ID-synkroniseringar görs inte på sidan för utgivare eller servrar på plats. Audience Manager UUID infogas i fältet `u=` för annonsserverns loggfiler. Detta inträffar när segment skickas in för målinriktning. DIL-kodmodulen utför den här funktionen. Detta är samma mekanism som gör att vi kan mappa serverns användar-ID till en Audience Manager-användare för rapportering av segmentprestanda. Om det finns en annonsserver på platsen synkroniserar vi ID:n direkt på sidan.

<br> 

**Räknar Audience Manager en användare som loggar in från olika enheter som en unik användare eller olika unika användare?**

[Deklarerad ID-målgruppsanpassning](../features/declared-ids.md#declared-id-targeting) hjälper Audience Manager att identifiera en besökare på flera enheter med en enda unik identifierare. Från ett mål- eller målperspektiv är detta dock fortfarande två (eller fler) användare eftersom DSP inte kan matcha dessa flera ID:n.

<br> 

**Kan Audience Manager identifiera en användare från en skärm och mobila enheter.**

Ja. Se [Deklarerat ID-mål](../features/declared-ids.md#declared-id-targeting).

<br> 

**Kan jag poängsätta användare med data som samlats in online och rikta om dem baserat på detta modellresultat?**

Ja. Audience Manager kan tillhandahålla datafiler för att hjälpa dig att få användarna att sticka ut, men du måste arbeta med andra leverantörer eller program för att kunna analysera och rangordna informationen. Skicka dessa data till Audience Manager i form av nyckelvärdepar. Vi kan använda den här informationen och lägga till den i befintliga användarprofiler. Kontakta en representant för Partner Solutions om du vill granska processen.

<br> 

**Hur många borttagningar av cookies under en given 1-2-månadersperiod?**

Det är svårt att mäta hur mycket cookie-filen har tagits bort. De flesta cookie-borttagningar kommer från ett fåtal besökare som tar bort cookies ofta. De flesta cookies är dock stabila i minst 30 dagar, även om vissa har en begränsad livslängd. Vissa studier tyder på att målgruppsanpassning som är större än 30 dagar i praktiken skulle eliminera 7 % av målgruppen i webbläsaren under en 30-dagarsperiod. Som ni vet är 30-dagars kampanjer för ett visst kreativt budskap standard i branschen. Av det vi har sett är det 7 % färre att släppa.

Borttagning av cookies har en negativ effekt på beräkning av räckvidd och frekvens. Därför betonar vi värdet av beteendedata när vi försöker förstå den verkliga karaktären hos konsumenttrender för planering av displaykampanjer. Våra kunder kan utnyttja rapporter om överlappande Audience Manager-segment, optimala visningsfrekvenser och unika användartrender över specifika datumintervall för att vara mer vetenskapliga om kampanjplanering och optimala datumintervall för kampanjkampanjer.

<br> 

**Hur länge gäller Audience Manager cookies?**

I användargränssnittet kan du bestämma förfallointervallet för cookie. Du kan ange att cookies ska upphöra efter *ett* antal dagar eller aldrig.

<br> 

**Kostar implementeringen av en kampanj som är kreativ i ett eventsamtal mer oss?**

Det beror på. Kostnaden baseras på unika användare. Om en kampanj resulterar i nya användare, ja, kommer det att kosta mer. Om er kampanj når platser där vi redan samlar in data finns det ingen extra kostnad. Om kampanjen körs på relaterade webbplatser där det förekommer betydande överlappningar, kommer det att bli extra kostnader för de nya unika användare vi ser.

<br> 

**Audience Manager visar endast[!UICONTROL Addressable Audiences]mått och matchningsfrekvenser för[!UICONTROL Server-to-Server]destinationer. Kan du förklara varför vi inte ser de här siffrorna för Cookie- och URL-destinationer?**

Det handlar om ID-synk. För [!UICONTROL Server-to-Server] destinationer överför vi data offline (antingen i realtid eller i batch) och vi måste skicka det ID som målpartnern förstår, så att de kan mappa tillbaka det till webbläsaren. Segmentets adresserbara nummer är en delmängd av den totala segmentpopulationen.

När det gäller cookie-mål och URL-mål finns användaren redan i webbläsaren, och vad som [!DNL Audience Manager] skickas är bara de segment som användaren är berättigad till. Målpartnern kan bara hämta segmentmappningarna och arbeta med den informationen. Så tänk på matchningsfrekvenserna för Cookie- och URL-mål alltid 100 %.
