---
description: Personbaserade mål erbjuder flera implementeringsstrategier, beroende på hur kunddata är strukturerade. I den här artikeln finns en översikt över de implementeringssteg som du måste följa för personbaserade mål, beroende på ditt scenario.
seo-description: 'Personbaserade mål erbjuder flera implementeringsstrategier, beroende på hur kunddata är strukturerade. I den här artikeln finns en översikt över de implementeringssteg som du måste följa för personbaserade mål, beroende på ditt scenario.  '
seo-title: Implementeringsvägledning för personbaserade destinationer
solution: Audience Manager
title: Implementeringsvägledning
feature: Personbaserade mål
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Implementeringsvägledning {#implementation-guidance}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

[!DNL People-Based Destinations] erbjuder flera implementeringsstrategier, beroende på hur kunddata är strukturerade. I den här artikeln finns en översikt över de implementeringssteg som du måste följa för [!DNL People-Based Destinations], beroende på ditt scenario.

## Översikt {#overview}

Konfigurationen av [!DNL People-Based Destinations] tar dig igenom flera sektioner i Audience Manager och kräver olika inställningar och metoder för att komma igång med data, beroende på vilken typ av kunddata du redan har i Audience Manager och vilken typ av målgruppsanpassning du vill utföra.

>[!IMPORTANT]
> Innan du konfigurerar [!DNL People-Based Destinations] måste du läsa den här artikeln noggrant och fullständigt. När du har läst den här guiden bör du ha en tydlig förståelse för det scenario du aktiverar via [!DNL People-Based Destinations].

Det finns sex implementeringsaspekter som du måste klargöra innan du använder [!DNL People-Based Destinations]. Den här artikeln hjälper dig att förstå vad din nuvarande konfiguration är så att du kan följa implementeringsstegen för ditt scenario korrekt.

![pbd-implementation](assets/pbd-implementation.png)

## 1. Definiera ditt användningsfall {#defining-your-use-case}

Innan du börjar implementera [!DNL People-Based Destinations] måste du tydligt definiera vilket användningsfall du ska använda den här funktionen för. Du kan använda [!DNL People-Based Destinations] för att rikta in målgrupper på två sätt, baserat på målgruppsaktivitet:

**A) Målgruppsanpassning baserat på er kombinerade online- och offlineanvändaraktivitet**. I det här scenariot vill du kombinera befintliga målgruppsdata från Audience Manager med data från ditt interna [!DNL CRM]-system och skicka de resulterande målgruppssegmenten till [!DNL People-Based Destinations]. Här är ett exempel som illustrerar detta scenario:

Ditt företag, ett flygbolag, har olika kundnivåer (Bronze, Silver och Gold) och du vill ge varje nivå skräddarsydda erbjudanden via sociala plattformar. Du använder Audience Manager för att analysera kundaktiviteter på din webbplats. Alla kunder använder dock inte flygbolagets mobilapp, och vissa av dem har inte loggat in på företagets webbplats. Era kunddata är mestadels begränsade till medlemskap-ID och e-postadresser.

Om du vill rikta in dem på sociala medier och liknande personbaserade kanaler kan du föra in dina [hash-kodade e-postadresser](people-based-destinations-prerequisites.md) i Audience Manager och kombinera dem med dina befintliga egenskaper för onlineaktiviteter för att skapa nya målgruppssegment. Därefter kan du använda dessa segment för att rikta in dig på målgruppen via [!DNL People-Based Destinations].

**B) Målgruppsanpassning som enbart bygger på din offlineanvändaraktivitet**. I det här scenariot innehåller ditt [!DNL CRM]-system e-postadresser och andra kundattribut, men kunderna har inte interagerat med din webbplats alls, så du har ingen kundaktivitet i Audience Manager. Här är ett exempel som illustrerar detta scenario:

Ditt företag, en leverantör av teletjänster, lagrar kunddata som e-postadresser och inköpta telefonplaner i en intern [!DNL CRM]. Ni vill rikta er till befintliga kunder på sociala plattformar för att erbjuda dem uppgraderingspaket som baseras på deras befintliga prenumerationer. För att göra detta kan ni lägga in era hashade e-postadresser till Audience Manager och skapa segment baserat på befintliga kundprenumerationer. Sedan kan ni skicka dessa segment till [!DNL People-Based Destinations] för att inrikta er på kunderna med personaliserade erbjudanden.

## 2. Definiera typen av riktade e-postadresser {#define-target-email}

Det andra steget när du definierar implementeringsstrategin är att bestämma vilken typ av e-postadresser du vill ha som mål.

**A) Målgruppsanpassning baserat på era autentiserade e-postadresser**. I det här scenariot har dina användare flera konton som är kopplade till flera e-postadresser, och du vill rikta dem mot personaliserade erbjudanden, baserat enbart på den e-postadress de autentiserar på din webbplats, i realtid.

**B) Målgruppsanpassning baserat på alla era associerade e-postadresser**. I det här scenariot har dina användare flera konton som är kopplade till flera e-postadresser, och du vill ange dem som mål för alla deras associerade e-postadresser, oavsett autentiserad aktivitet.

## 3. Identifiera vilken typ av kund-ID (CRM ID) som du har {#identify-customer-id}

För att rikta in er på målgrupper i [!DNL People-Based Destinations] måste ni skicka [SHA256 hashed](people-based-destinations-prerequisites.md)-versioner av era e-postadresser. Beroende på din befintliga konfiguration av Audience Manager kan du befinna dig i något av följande två scenarier:

**A) Era [DPUID:n](../../reference/ids-in-aam.md) i Audience Manager är redan små och har e-postadresser**. I det här scenariot kan du använda dessa befintliga ID:n för att rikta in dig på målgrupper i [!DNL People-Based Destinations].

**B) Kund-ID:n ([DPUID](../../reference/ids-in-aam.md)) i Audience Manager är inte gemener, hashkodade e-postadresser**. I det här scenariot kan ditt befintliga kund-ID inte skickas till [!DNL People-Based Destinations]. Om du vill använda [!DNL People-Based Destinations] måste du utföra en ID-synkronisering mellan dina befintliga kund-ID:n och gemena, hashas-versioner av kundens e-postadresser. Du gör detta antingen genom [filbaserad ID-synkronisering](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) eller genom att använda [deklarerade ID:n](../declared-ids.md).

## 4. Trait Qualification {#trait-qualification}

För att rikta in er på rätt sätt i [!DNL People-Based Destinations] måste era användare kvalificera sig för regelbaserade eller anpassade egenskaper, beroende på vilken typ av målgruppsanpassning du vill utföra.

**Svar: Kvalificera dina kund-ID:n och enhets-ID:n i realtid för regelbaserade egenskaper**. Det här alternativet gäller för fall A från [1. Definierar ditt användningsfall](people-based-destinations-workflow.md#defining-your-use-case). Om ni planerar att rikta in er på målgrupper baserat på online- och offlineaktiviteter är det troligt att ni redan kvalificerar er målgrupp för [regelbaserade egenskaper](../traits/trait-and-segment-qualification-reference.md).

**B) Integrera egenskaper mot dina kund-ID:n via inkommande datafiler**. Det här alternativet gäller för fall B från [1. Definierar ditt användningsfall](people-based-destinations-workflow.md#defining-your-use-case). När ni riktar er till era målgrupper baserat på enbart offlineaktiviteter måste ni kvalificera er för kundens ID:n för anpassade egenskaper via [inkommande datafiler](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Skapa eller etikettera datakällor och inbyggda hashed-e-postadresser {#create-label-data-sources}

Beroende på vilken typ av kund-ID du har i Audience Manager (se [3. Identifiera vilken typ av kund-ID (CRM-ID) du har](people-based-destinations-workflow.md#identify-customer-id), så hittar du dig själv i något av följande scenarier:

**A) Ange en etikett för en befintlig datakälla**. Det här alternativet gäller det scenario där dina kund-ID:n ([DPUID:n](../../reference/ids-in-aam.md)) i Audience Manager redan är gemener, hash-kodade e-postadresser. I det här fallet behöver du ange för datakällan att du lagrar ID:n som en [!DNL PII]-datakälla. Mer information om inställningar för datakälla finns i [Inställningar för datakälla](../datasources-list-and-settings.md). Vad du behöver göra är att se till att alternativet Kan inte kopplas till personligt identifierbar information inte är markerat.

**B) Skapa en ny datakälla**. Det här alternativet gäller det scenario där dina kund-ID:n ([DPUID:n](../../reference/ids-in-aam.md)) i Audience Manager inte är hashade e-postadresser. I det här fallet måste du skapa en ny datakälla för olika enheter och lägga in dina streckade e-postadresser mot den. Du kan göra detta på två sätt:

* Filbaserad ID-synkronisering. Mer information om hur filer för ID-synkronisering ska se ut finns i [Namn- och innehållskrav för ID-synkroniseringsfiler](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md). När du använder den här metoden kan du ange alla dina hash-kodade e-postadresser som mål från din [!DNL CRM]-databas.
* Använd [deklarerade ID:n](../declared-ids.md) för att deklarera dina hashade e-postadresser när du skickar autentiserade kund-ID:n. När du använder den här metoden anger Audience Manager bara dina hash-kodade e-postadresser från användare som har autentiserats online. E-postadresserna som är avsedda för personbaserade kanaler är bara de som anges i de deklarerade ID-händelseanropen. Andra e-postadresser som är kopplade till kund-ID:n aktiveras inte i realtid.

## 6. Använd en profilkopplingsregel för segmentering {#use-profile-merge-rules}

Beroende på ditt användningssätt (se [1. Det finns två sätt att använda [!DNL Profile Merge Rules] för segmentering när du definierar ditt användningsfall](people-based-destinations-workflow.md#defining-your-use-case)).

**A) Använd befintlig[!DNL Profile Merge Rules]**. Det här alternativet gäller för det första användningsexemplet (målgruppsanpassning baserad på kombinerad online- och offlineanvändaraktivitet). I det här scenariot har du en befintlig kundaktivitet i Audience Manager och du har redan definierat minst en profilkopplingsregel som du har använt vid segmentering. I det här fallet behöver du inte skapa några nya [!DNL Profile Merge Rules].

**B) Skapa en ny  [!DNL All Cross-Device Profiles] kopplingsregel**. Det här alternativet gäller för det andra användningsfallet (målgruppsanpassning som enbart baseras på offlineanvändaraktivitet). I det här scenariot hämtar du kunddata offline från din [!DNL CRM] till Audience Manager och vill skapa segment utifrån dessa data. För att göra detta introducerar [!DNL People-Based Destinations] en ny, fjärde regel för profilsammanslagning som heter **[!DNL All Cross-Device Profiles]**. Det här är regeln som du måste använda när du segmenterar enbart offlinedata.
