---
description: Använd personbaserade destinationer för att skicka förstahandssegment till personbaserade miljöer. Dessa miljöer är slutna ekosystem som tillhör en enhet som kontrollerar innehållet som visas i den. De innehåller sociala plattformar som Facebook och andra plattformar som använder kundkonton för att personalisera det visade innehållet.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Översikt och användningsexempel
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Översikt och användningsexempel {#overview-use-cases}

Använd [!DNL People-Based Destinations] om du vill skicka förstapartssegment till personbaserade miljöer. Dessa miljöer är slutna ekosystem som tillhör en enhet som kontrollerar innehållet som visas i den. De innehåller sociala plattformar som [!DNL Facebook] och andra plattformar som förlitar sig på kundkonton för att anpassa det visade innehållet.

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

## Översikt {#overview}

Med [!DNL People-Based Destinations] kan du använda segmentering på online- och offlinedata för att skapa målgruppssegment baserat på [hashade identifierare](people-based-destinations-prerequisites.md#hashing-requirements), till exempel e-postadresser. Sedan kan du skicka de här segmenten till &quot;trädgårdar&quot;, till exempel [!DNL Facebook], där du kan rikta in dig på publiken på de sociala plattformarna. [!DNL People-Based Destinations] kan hjälpa dig att:

* Rikta er till målgrupper offline och online på plattformar som [!DNL Facebook], baserat på hash-kodade e-postadresser;
* Komplettera Audience Manager befintliga målgruppsfunktioner för enheter och cookies.
* Eliminera kostnaderna för lösningar för datainhämtning från tredje part.
* Eliminera kostnader i samband med utveckling av anpassade arbetsflöden för datainhämtning.
* Målgrupper i cookie-fria miljöer.
* Rikta målgrupper genom att deduplicera hash-kodade e-postadresser som matchar kund-ID:n.

Du kan använda [!DNL People-Based Destinations] för att segmentera och inrikta dig på värdefulla kunder som kanske inte besökt din webbplats, eller sluta inrikta dig på dem som redan har konverterat offline. Dessutom kan du utnyttja [!DNL Profile Merge Rules] för att kombinera dina egna offlinedata med dina egna onlinedata, inklusive kunddata från andra Adobe Experience Cloud-lösningar, för att optimera annonseringen i sociala medier.

![pbd-overview](assets/pbd-overview.png)

## Tillgänglighet {#availability}

[!DNL People-Based Destinations] är en integrering med Premium Audience Manager. Kontakta din Adobe-representant för att få tillgång till denna premiumfunktion.

## Varför ska du använda [!UICONTROL People-Based Destinations]? {#why-use}

**Ge era kunder enhetliga flerkanalsupplevelser genom att hantera hela er målgruppssegmentering inifrån Audience Manager.**

Att inte aktivera era målgruppssegment i personbaserade kanaler via Audience Manager leder till osammanhängande upplevelser mellan vad kunderna ser på er webbplats och vad de till exempel ser i sina [!DNL Facebook]-flöden. En konsekvent målinriktning över alla kanaler kan öka annonsintäkterna samtidigt som ni optimerar annonsutgifterna.

**Nå ut till målgrupper i personbaserade kanaler utan att behöva en dedikerad lösning för datakonvertering eller anpassade arbetsflöden för att skicka målgrupper.**

Det mer&quot;traditionella&quot; sättet att rikta in er på målgrupper över olika personbaserade kanaler innebär att ni måste exportera era kunddata i ett format som accepteras av den plattform ni vill annonsera på och sedan använda plattformens särskilda metod för att lägga in kunddata på ert annonserarkonto. Det här är allt manuellt arbete som du behöver göra för varje plattform som du vill annonsera på. Dessutom kan olika plattformar ha olika krav på dataformat, vilket gör processen ännu mer krävande.

![pbd-overview](assets/pbd-diagram.png)

Genom [!DNL People-Based Destinations] kan Audience Manager hjälpa er att centralisera era kunddata, bygga målgruppssegment och aktivera dem i flera personbaserade kanaler. Du kan göra allt detta inifrån användargränssnittet i Audience Manager, och slippa det extraarbete som med manuell överföring av data till varje plattform innebär, vilket sparar värdefull tid i processen.

**Skapa och aktivera målgruppssegment från helt offline-profiler.**

[!DNL People-Based Destinations] löser problemet som tidigare bara kunde aktivera målgruppssegment baserat på enhetsaktivitet. Med [!DNL People-Based Destinations] kan du skapa segment från enbart offlinedata från din egen [!DNL CRM] och aktivera dem på personbaserade plattformar. Dessutom kan du korrelera offlinedata med enhetsdata som du redan har i Audience Manager.

**Använd Audience Manager datastyrning och sekretesskontroller för att hantera kunddata på ett säkert sätt.**

[!DNL People-Based Destinations] kräver att du bara använder oåterkalleligt hash-kodade identifierare. Detta minskar riskerna med att manuellt överföra kunddata till respektive målplattform.

Titta på videon nedan för att få en översikt över dataflödet när du använder [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Användningsexempel {#use-cases}

För att du bättre ska förstå hur och när du ska använda [!DNL People-Based Destinations] finns det två exempel på användning som Audience Manager-kunder kan lösa med den här funktionen.

### Användningsfall 1 {#use-case-1}

En webbutik vill nå befintliga kunder via sociala plattformar och visa dem personaliserade erbjudanden baserat på deras tidigare order. Med [!DNL People-Based Destinations] kan onlinehandlaren importera hashas-e-postadresser från sin egen [!DNL CRM] till Audience Manager, skapa segment utifrån sina egna offlinedata och skicka dessa segment till de sociala plattformar som de vill annonsera på, vilket optimerar deras annonsutgifter.

### Användningsfall nr 2 {#use-case-2}

Ett flygbolag har olika kundnivåer (Bronze, Silver och Gold) och vill kunna erbjuda varje nivå personaliserade erbjudanden via sociala plattformar. Företaget använder Audience Manager för att analysera kundaktiviteter på webbplatsen. Alla kunder använder dock inte flygbolagets mobilapp, och vissa av dem har inte loggat in på företagets webbplats. De enda identifierare företaget har för dessa kunder är medlems-ID och e-postadresser.

För att rikta in dem på sociala medier och liknande personbaserade kanaler kan de lägga in kunddata från sina [!DNL CRM] i Audience Manager, med hjälp av de hash-kodade e-postadresserna som identifierare.

Därefter kan de kombinera sina offlinedata med sina befintliga egenskaper för onlineaktivitet för att skapa nya målgruppssegment som de kan rikta sig mot via [!DNL People-Based Destinations].
