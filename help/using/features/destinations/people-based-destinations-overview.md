---
description: 'Använd personbaserade destinationer för att skicka förstahandssegment till personbaserade miljöer. Dessa miljöer är slutna ekosystem som tillhör en enhet som kontrollerar innehållet som visas i den. De innehåller sociala plattformar som Facebook och andra plattformar som förlitar sig på kundkonton för att personalisera det visade innehållet. '
seo-description: 'Använd personbaserade destinationer för att skicka förstahandssegment till personbaserade miljöer. Dessa miljöer är slutna ekosystem som tillhör en enhet som kontrollerar innehållet som visas i den. De innehåller sociala plattformar som Facebook och andra plattformar som förlitar sig på kundkonton för att personalisera det visade innehållet.  '
seo-title: Översikt över och användningsfall för personbaserade destinationer
solution: Audience Manager
title: Översikt och användningsexempel
translation-type: tm+mt
source-git-commit: d70b77b082078d4122f8b902b089d8c4a3fb923a

---


# Översikt och användningsexempel {#overview-use-cases}

Används [!DNL People-Based Destinations] för att skicka förstahandssegment till personbaserade miljöer. Dessa miljöer är slutna ekosystem som tillhör en enhet som kontrollerar innehållet som visas i den. De omfattar sociala plattformar som [!DNL Facebook]och andra plattformar som förlitar sig på kundkonton för att personalisera det visade innehållet.

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

## Översikt {#overview}

[!DNL People-Based Destinations] gör det möjligt att använda segmentering på online- och offlinedata för att skapa målgruppssegment baserat på [hashas-identifierare](people-based-destinations-prerequisites.md#hashing-requirements), som e-postadresser eller telefonnummer. Sedan kan ni skicka dessa segment till &quot;trädgårdar&quot;, t.ex. [!DNL Facebook]där ni kan inrikta er på publiken på de sociala plattformarna. [!DNL People-Based Destinations] kan hjälpa dig att:

* Rikta er till målgrupper offline och online på plattformar som [!DNL Facebook]hash-baserade e-postadresser.
* Komplettera befintliga målgruppsfunktioner för enheter och cookies i Audience Manager.
* Eliminera kostnaderna för lösningar för datainhämtning från tredje part.
* Eliminera kostnader i samband med utveckling av anpassade arbetsflöden för datainhämtning.
* Målgrupper i cookie-fria miljöer.
* Rikta målgrupper genom att deduplicera hash-kodade e-postadresser som matchar kund-ID:n.

Ni kan använda [!DNL People-Based Destinations] för att segmentera och inrikta er på värdefulla kunder som kanske inte besökt er webbplats, eller sluta inrikta er på dem som redan har konverterat offline. Dessutom kan ni utnyttja möjligheten [!DNL Profile Merge Rules] att kombinera era era egna offlinedata med era egna onlinedata, inklusive kunddata från andra Adobe Experience Cloud-lösningar, för att optimera era annonsinsatser i sociala medier.

![pbd-overview](assets/pbd-overview.png)

## Tillgänglighet {#availability}

[!DNL People-Based Destinations] är en förstklassig integrering med Audience Manager. Kontakta din Adobe-representant för att få tillgång till denna premiumfunktion.

## Varför ska du använda personbaserade mål? {#why-use}

**Ge era kunder enhetliga flerkanalsupplevelser genom att hantera hela er målgruppssegmentering inifrån Audience Manager.**

Att inte aktivera era målgruppssegment i personbaserade kanaler via Audience Manager leder till osammanhängande upplevelser mellan vad kunderna ser på er webbplats och vad de till exempel ser i sina [!DNL Facebook] flöden. En konsekvent målinriktning över alla kanaler kan öka annonsintäkterna samtidigt som ni optimerar annonsutgifterna.

**Nå ut till era målgrupper i personbaserade kanaler utan att behöva en dedikerad lösning för datainhämtning eller anpassade arbetsflöden för att skicka ut målgrupper.**

Det mer&quot;traditionella&quot; sättet att rikta in er på målgrupper över olika personbaserade kanaler innebär att ni måste exportera era kunddata i ett format som accepteras av den plattform ni vill annonsera på och sedan använda plattformens särskilda metod för att lägga in kunddata på ert annonserarkonto. Det här är allt manuellt arbete som du behöver göra för varje plattform som du vill annonsera på. Dessutom kan olika plattformar ha olika krav på dataformat, vilket gör processen ännu mer krävande.

![pbd-overview](assets/pbd-diagram.png)

Via [!DNL People-Based Destinations]Audience Manager kan ni centralisera era kunddata, bygga målgruppssegment och aktivera dem i flera personbaserade kanaler. Du kan göra allt detta inifrån användargränssnittet i Audience Manager och slippa extraarbetet med att manuellt överföra data till varje plattform, vilket sparar värdefull tid i processen.

**Skapa och aktivera målgruppssegment utifrån helt offline-profiler.**

[!DNL People-Based Destinations] lösa problemet som tidigare bara kunde aktivera målgruppssegment baserat på enhetsaktivitet. Med [!DNL People-Based Destinations]kan ni skapa segment utifrån helt offline-data från era egna [!DNL CRM]och aktivera dem på personbaserade plattformar. Dessutom kan ni korrelera offlinedata med enhetsdata som ni redan har i Audience Manager.

**Använd Audience Managers datastyrning och sekretesskontroller för att hantera kunddata på ett säkert sätt.**

[!DNL People-Based Destinations] kräver att du bara använder oåterkalleligt hash-kodade identifierare. Detta minskar riskerna med att manuellt överföra kunddata till respektive målplattform.

Titta på videon nedan för att få en översikt över dataflödet när du använder [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Användningsexempel {#use-cases}

För att ni bättre ska förstå hur och när ni bör använda [!DNL People-Based Destinations]finns det två exempel på användningsområden som Audience Manager-kunder kan lösa med den här funktionen.

### Användningsfall 1 {#use-case-1}

En webbutik vill nå befintliga kunder via sociala plattformar och visa dem personaliserade erbjudanden baserat på deras tidigare order. Med [!DNL People-Based Destinations]onlinebutiken kan webbutiken importera hashas-e-postadresser från sin egen [!DNL CRM] till Audience Manager, bygga segment utifrån sina egna offlinedata och skicka dessa segment till de sociala plattformar som de vill annonsera på, vilket optimerar annonsutgifterna.

### Användningsfall nr 2 {#use-case-2}

Ett flygbolag har olika kundnivåer (Bronze, Silver och Gold) och vill kunna erbjuda varje nivå personaliserade erbjudanden via sociala plattformar. Företaget använder Audience Manager för att analysera kundaktiviteter på webbplatsen. Alla kunder använder dock inte flygbolagets mobilapp, och vissa av dem har inte loggat in på företagets webbplats. De enda identifierare företaget har för dessa kunder är medlems-ID och e-postadresser.

För att rikta in dem på sociala medier och liknande personbaserade kanaler kan de lägga in kunddata från sina kunder [!DNL CRM] i Audience Manager, med hjälp av de hash-kodade e-postadresserna som identifierare.

Sedan kan de kombinera sina offlinedata med sina befintliga egenskaper för onlineaktiviteter för att skapa nya målgruppssegment som de kan inrikta sig på [!DNL People-Based Destinations].
