---
description: Vanliga frågor och svar om CDF-filer (Customer Data Feed).
seo-description: Vanliga frågor och svar om CDF-filer (Customer Data Feed).
seo-title: Vanliga frågor om kunddataflöden
solution: Audience Manager
title: Vanliga frågor om kunddataflöden
uuid: 7183b3e2-e999-4e1e-892f-2bab335c13b6
feature: Customer Data Feeds
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 0%

---


# Vanliga frågor om kunddataflöden{#customer-data-feed-faq}

Vanliga frågor och svar om CDF-filer (Customer Data Feed).

## Amazon S3-lagring {#amazon-s3-storage}

**Var lagras min CDF-fil[!DNL Amazon]?**

CDF-filen lagras i `aam-cdf` rotkatalogen på en [!DNL Amazon S3] server. Den här standardbucket hanteras av [!DNL Audience Manager]. Se även [Namngivningskonventioner](../features/cdf-files.md#cdf-naming-conventions)för kunddataflödesfiler.

<br> 

**Är min lagringsklocka säker?**

Ja. Kunderna får endast tillgång till sitt eget lagringsutrymme. Du kommer att ha skrivskyddad åtkomst till din lagringsbucket. Du har inte skrivbehörighet.

<br> 

**Kan jag anpassa min lagringsbucket eller lagra filer i en annan katalog?**

Nej. Anpassning och alternativa lagringsalternativ är inte tillgängliga.

<br> 

**Min katalog saknar en fil under en viss timme. Var är den?**

En saknad fil innebär att [!DNL Audience Manager] det inte gick att bearbeta dina CDF-filer den timmen. Detta händer oftast när våra servrar släpar efter när de bearbetar CDF-filer. I så fall går filen inte förlorad. Den visas i en katalog som ligger senare i timmen när systemet har en chans att komma ifatt. Se även [Bearbetningsmeddelanden](../features/cdf-files.md#cdf-file-processing-notifications)för kunddataflödesfiler.

<br> 

**Hur vet jag när mina CDF-filer är klara?**

Se [Meddelanden](../features/cdf-files.md#cdf-file-processing-notifications)om filbearbetning av kunddatafeed.

<br> 

## Filstorlekar {#file-sizes}

**Vilken filstorlek ska jag förvänta mig? Hur stor är en genomsnittlig CDF-fil?**

Det är svårt att beräkna filstorlekar. Och varje fil kan ha olika storlek. Storleken varierar från timme till timme och dag till dag. Om du ska ta emot CDF-filer är det bra att kunna hantera mycket data.

<br> 

**Hur många filer får jag?**

Återigen är det svårt att uppskatta detta. Men om du ska få CDF-filer är det bra att förbereda dig för att hantera mycket data.

<br> 

## Dataintegritet {#data-integrity}

**Hur kontrollerar jag integriteten hos de data som överförs till Amazon S3?**

[!DNL Amazon] delar upp stora filer i mindre delar och överför dem till [!DNL Amazon S3] med hjälp av flerdelsuppladdningen. Sedan genereras ett `ETag` värde för flerdelsöverföringen. Först beräknas de enskilda MD5-kontrollsummorna för varje överförd del och sedan sammanfogas de till en enda sträng. Sedan beräknas MD5-kontrollsumman för strängen. Den resulterande kontrollsumman ( `ETag`) läggs sedan till med ett bindestreck och det totala antalet delar som används för överföring. Exempelvis kan `ETag` för en fil som delats upp i fem delar under överföringen se ut ungefär så här: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Datalagring {#data-retension}

**Hur länge sparar du CDF-filer?**

Data tas bort efter 8 (åtta) dagar.

<br> 

**Kan jag hämta CDF-filer retroaktivt eller för tidigare dagar?**

Du kan bara generera CDF-filer för de senaste 8 dagarna. CDF-filer för intervall som är äldre än de senaste 8 dagarna kan inte genereras om.

>[!MORELIKETHIS]
>
>* [Kunddataflöden](../features/cdf-files.md)

