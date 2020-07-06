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
ht-degree: 100%

---


# Vanliga frågor om kunddataflöden {#customer-data-feed-faq}

Vanliga frågor och svar om CDF-filer (Customer Data Feed).

## Amazon S3-lagring {#amazon-s3-storage}

**Var lagras min CDF-fil i [!DNL Amazon]?**

CDF-filen lagras i `aam-cdf`-rotkatalogen på en [!DNL Amazon S3]-server. Denna standardbucket hanteras av [!DNL Audience Manager]. Se även [Namngivningskonventioner för CDF-filer](../features/cdf-files.md#cdf-naming-conventions).

<br> 

**Är min lagringsbucket säker?**

Ja. En kund har bara tillgång till sitt eget lagringsutrymme. Du har skrivskyddad åtkomst till din lagringsbucket. Du har inte skrivbehörighet.

<br> 

**Kan jag anpassa min lagringsbucket eller lagra filer i en annan katalog?**

Nej. Anpassning och alternativa lagringsalternativ är inte tillgängliga.

<br> 

**Min katalog saknar en fil för en viss timme. Var är den?**

En saknad fil innebär att [!DNL Audience Manager] inte kunde bearbeta dina CDF-filer den timmen. Det händer oftast när våra servrar ligger efter med bearbetningen av CDF-filer. Filen har inte gått förlorad. Den visas i en katalog för en senare tid när systemet har kommit i kapp. Se även [Bearbetningsmeddelanden för CDF-filer](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

**Hur vet jag när mina CDF-filer är klara?**

Se [Bearbetningsmeddelanden för CDF-filer](../features/cdf-files.md#cdf-file-processing-notifications).

<br> 

## Filstorlekar {#file-sizes}

**Vilka filstorlekar kan jag förvänta mig? Hur stor är en genomsnittlig CDF-fil?**

Det är svårt att beräkna filstorlekar. Varje fil kan ha olika storlek. Storleken varierar från timme till timme och dag till dag. Om du ska ta emot CDF-filer är det bra att vara förberedd på att hantera mycket data.

<br> 

**Hur många filer får jag?**

Återigen är det svårt att uppskatta det. Men om du ska ta emot CDF-filer är det bra att vara förberedd på att hantera mycket data.

<br> 

## Dataintegritet {#data-integrity}

**Hur kontrollerar jag integriteten hos de data som överförs till Amazon S3?**

[!DNL Amazon] delar upp stora filer i mindre delar och laddar upp dem till [!DNL Amazon S3] i flera delar. Sedan genereras ett `ETag`-värde för hela uppladdningen. Först beräknas de enskilda MD5-kontrollsummorna för varje överförd del och sedan sammanfogas de till en enda sträng. Sedan beräknas MD5-kontrollsumman för strängen. I den beräknade kontrollsumman (`ETag`) läggs sedan ett bindestreck till och det totala antalet delar som laddades upp. Exempelvis kan `ETag` för en fil som delats upp i fem delar under uppladdningen se ut ungefär så här: `2c51427d19021e88cf3395365895b6d4-5`

<br> 

## Datalagring {#data-retension}

**Hur länge sparas CDF-filer?**

Data tas bort efter 8 (åtta) dagar.

<br> 

**Kan jag hämta CDF-filer retroaktivt eller för föregående dagar?**

Du kan bara generera CDF-filer för de senaste 8 dagarna. CDF-filer för intervall som är äldre än de senaste 8 dagarna kan inte genereras på nytt.

>[!MORELIKETHIS]
>
>* [Kunddataflöden](../features/cdf-files.md)

