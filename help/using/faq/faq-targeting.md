---
description: Vanliga frågor och problem som rör målinriktning.
seo-description: Common targeting-related questions and issues.
seo-title: Targeting FAQ
solution: Audience Manager
title: Vanliga frågor om målinriktning
uuid: ee96ef71-b903-4953-afc4-8ec8e48bd49e
feature: Match Rates
exl-id: e5f761fd-dfc8-4859-a81e-89abbd7f2914
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 100%

---

# Vanliga frågor om målinriktning{#targeting-faq}

Vanliga frågor och problem som rör målinriktning.

<br>

<!-- 

faq_targeting.xml

 -->

**Var hittar jag en fullständig lista över tredjepartsdataleverantörer som stöds i Audience Manager?**

På [Adobe Exchange Marketplace](https://exchange.adobe.com/experiencecloud.html) finns en fullständig lista över tredjepartsdataleverantörer som stöds i [!DNL Audience Manager].

<br>

**Bör jag använda data från tredje part i Audience Manager eller i en DSP om jag vill rikta in mig på användare som aldrig besökt vår webbplats?**

Svaret beror på era mål. Om kampanjen till exempel är utformad för att hitta nya kunder med data från tredje part kan du arbeta direkt med en DSP. Kom ihåg att Audience Manager bara synkroniserar data med en tredjepartsdataleverantör när användaren gör ett besök. Vårt system har ingen information om personer som inte besökt webbplatsen. Skapa segment via en DSP om kampanjen bara använder data från tredje part för att rikta sig till användare som aldrig besökt någon av era webbplatser.

<br>

**Kan jag marknadsföra till enskilda personer?**

Med Audience Manager kan ni aggregera användare och marknadsföra till dem baserat på delade attribut eller traits. För att följa branschens regler får [!DNL Audience Manager]-kunderna inte skicka personligt identifierbar information (PII) till våra system. Därför kan du inte använda e-postadresser, enskilda namn, fysiska adresser osv. för målinriktning.

<br>

**Hur lagrar jag data för återmarknadsföring på ett säkert sätt?**

Vi rekommenderar att ni använder en server-till-server-anslutning för att utbyta data med den återmarknadsföringsplattform som används. Audience Manager utbyter data med de flesta ledande DSP:er via server-till-server-anslutningar. Dataöverföringar från server till server förhindrar att andra aktörer fångar upp era data och säljer den målgruppsinformationen på nytt.

<br>

**Är Audience Managers unika användar-ID (UUID) kopplat till en annonsservers unika användar-ID genom att ID:n synkroniseras direkt på sidan?**

Nej. ID-synkronisering sker inte på sidan för webbplatsutgivare eller servrar. Audience Managers UUID infogas i fältet `u=` i annonsserverns loggfiler. Det inträffar när segment skickas för målinriktning. DIL-kodmodulen utför funktionen. Det är samma mekanism som gör att vi kan mappa serverns användar-ID till en Audience Manager-användare för rapportering av segmentprestanda. Om det finns en annonsserver på webbplatsen synkroniseras ID:n direkt på sidan.

<br>

**Räknar Audience Manager en användare som loggar in från olika enheter som en unik användare eller olika unika användare?**

[Deklarerad ID-målinriktning](../features/declared-ids.md#declared-id-targeting) hjälper Audience Manager att identifiera en besökare på flera enheter med en enda unik identifierare. Från ett målinriktnings- eller destinationsperspektiv är personen fortfarande två (eller fler) användare eftersom DSP:erna inte kan hantera flera ID:n.

<br>

**Kan Audience Manager identifiera en användare via bildskärmar och mobila enheter?**

Ja. Se [Deklarerad målinriktning](../features/declared-ids.md#declared-id-targeting).

<br>

**Kan jag poängsätta användare med data som samlats in online och återmarknadsföra till dem baserat på modellens poäng?**

Ja. Audience Manager kan tillhandahålla datafiler som hjälper er att poängsätta användare, men ni måste samarbeta med andra leverantörer eller program för att analysera och rangordna informationen. Skicka dessa data till Audience Manager i form av nyckelvärdespar. Vi kan lägga till informationen i befintliga användarprofiler. Kontakta din Partner Solutions-representant för en genomgång av processen.

<br>

**Hur ofta raderas cookies under en viss 1 till 2-månadersperiod?**

Det är svårt att mäta cookie-radering. De flesta cookie-raderingar kommer från ett fåtal besökare som tar bort cookies ofta. De flesta cookies är dock stabila i minst 30 dagar, även om vissa har en begränsad livslängd. Vissa studier tyder på att målinriktning i den övre tratten som överstiger 30 dagar i praktiken skulle eliminera 7 % av målgruppen i webbläsaren under en 30-dagarsperiod. 30-dagarskampanjer för ett visst budskap är standard i branschen. Som vi kan se är avfallet på 7 % ganska korrekt.

Borttagning av cookies har en negativ inverkan på beräkning av räckvidd och frekvens. Därför betonar vi värdet av beteendedata när ni försöker förstå den verkliga karaktären hos konsumenttrender för planering av displaykampanjer. Våra kunder kan använda rapporter om överlappande Audience Manager-segment, rapporter om optimala annonsvisningsfrekvenser och unika användartrender över specifika datumintervall för att hantera kampanjplanering och optimala datumintervall för kampanjer på ett mer vetenskapligt sätt.

<br>

**Hur länge gäller cookies i Audience Manager?**

I användargränssnittet kan du ange utgångstiden för cookies. Du kan ange att cookies ska upphöra efter *X* antal dagar eller aldrig.

<br>

**Kostar implementeringen av en kreativ kampanj i ett händelseanrop mer?**

Det beror på. Kostnaden baseras på unika användare. Om en kampanj resulterar i nya användare så kommer det att kosta mer. Om er kampanj når platser där vi redan samlar in data blir det ingen extra kostnad. Om kampanjen körs på relaterade webbplatser där det finns en betydande överlappning, kommer det att bli extra kostnader för de nya unika användare som tillkommer.

<br>

**Audience Manager visar bara [!UICONTROL Addressable Audiences] mätvärden och matchningsfrekvenser för [!UICONTROL Server-to-Server]-destinationer. Varför ser vi inte dessa värden för cookie- och URL-destinationer?**

Det beror på ID-synkroniseringen. För [!UICONTROL Server-to-Server]-destinationer överför vi data offline (antingen i realtid eller satsvis) och vi måste skicka ett ID som destinationen förstår så att den kan mappa det till webbläsaren. Segmentets adresserbara nummer är en delmängd av den totala segmentpopulationen.

När det gäller cookie- och URL-destinationer finns användaren redan i webbläsaren och [!DNL Audience Manager] skickar bara de segment som användaren kvalificerat för. Destinationspartnern behöver bara hämta segmentmappningarna och arbeta med den informationen. Så du kan tänka dig att matchningsfrekvenserna för cookies- och URL-destinationerna alltid är 100 %.
