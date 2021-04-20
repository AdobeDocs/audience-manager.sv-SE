---
description: Med Audience Manager kan ni samla in och hantera data från första part, andra part och tredje part.
seo-description: Med Audience Manager kan ni samla in och hantera data från första part, andra part och tredje part.
seo-title: Typer av insamlade data
solution: Audience Manager
title: Typer av insamlade data
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: Overview
exl-id: cfb587da-ceac-425f-8334-e961eba6fad2
translation-type: tm+mt
source-git-commit: 15e36d2847627b5e5ccef11f8073ce5124f14815
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 73%

---

# Typer av insamlade data {#types-of-data-collected}

[!DNL Audience Manager]Med kan ni samla in och hantera data från första part, andra part och tredje part.

Att frigöra informationstillgångar om kunder som lagrats på flera platser är en av de största utmaningarna som företag står inför idag. Från [!DNL CRM]-databaser, registreringssystem, annonsservrar osv., företag behöver verktyg som kan centralisera värdefulla data och hantera kund-/målgruppsinformation som en enda strategisk dataresurs. [!DNL Audience Manager] hjälper er att låsa upp isolerad kundinformation och hantera datainsamling från flera källor. Insamlade data kan hanteras baserat på dataelementets time-to-live-värden ([!DNL TTL]), vilket gör att utgivaren kan kontrollera förfallodatum för data från alla källor. [!DNL Audience Manager] är utformat för att hjälpa er att hantera följande typer av data:

| Datatyper | Datakälla |
|---|---|
| **Första part** | Kunder. Data samlas in online (från kundinteraktioner på era webbplatser) eller offline. |
| **Andra part** | Strategiska partners och annonsörer. |
| **Tredje part** | Dataleverantörer och/eller bytesplattformar. Data kan innehålla information som avsikt, demografi, socialt/livsstil, psykografi med mera. |

## Insamling av data från första part {#first-party-data}

Första parts datainsamling är en [!DNL Audience Manager]-huvudfunktion. Denna huvudfunktion tillgodoser behoven hos våra kunder (utgivare och annonsörer) som vill använda egna data som hörnstenar i marknadsföringsprogram eller för målinriktning och modellering mot andra datakällor.

[!DNL Audience Manager] hjälper kunderna att förstå sin datastrategi och mappar sedan den strategin i en anpassad datainsamlingsplan. Vårt Partner Solutions-team arbetar tillsammans med er för att utvärdera webbplatser, rådatasignaler och andra användarinteraktioner på era webbplatser. Med den här informationen kan vi hjälpa er att skapa en skräddarsydd datainsamlingsstrategi som hämtar datasignaler på användarnivå från olika sidor i ert lager. Insamlade data lagras och mappas tillbaka i en fördefinierad taxonomi som kan uppdateras när som helst när företagets behov förändras.

Följande exempel visar hur potentiella dataelement kan hämtas från en shoppingsida.

![kundvagnsdata](assets/shopping-cart-data.png)

| Objekt | Beskrivning |
|---|---|
| 1 | **Kön**. En köpares förnamn indikerar vanligtvis kön. I vårt exempel är köparens förnamn Mary, så vi vet att köparen är en kvinna. Namn lagras aldrig av Audience Manager. |
| 2 | **Intressen**. Artiklarna i kundvagnen kan visa olika intressen. I vårt exempel spenderar Mary mycket pengar på träningsutrustning. |
| 3 | **Bostadstyp**. Baserat på frakt- och/eller faktureringsadress kan vi ta reda på om Mary köper träningsutrustning åt sig själv eller ett företag. |
| 4 | **Plats**. [!DNL ZIP] koder är mer tillförlitliga än  [!DNL IP] adresser när det gäller att fästa en plats. |
| 5 | **Prismedvetenhet**. Om en kund använder kampanjkoder eller presentkort är hen förmodligen en köpare som letar efter bra erbjudanden. |
| 6 | **Köpkraft**. Prisdata som korreleras med [!DNL ZIP+4]-koder anger att en viss plats har förbrukningskraft. |

När rådata har samlats in mappas de tillbaka till kunddefinierade egenskaper inom [!DNL Audience Manager]-plattformen. Både taxonomin och datamappningarna kan justeras när som helst utan att datainsamlingskoden ändras.

## Insamling av data från andra part {#second-party-data}

Andrapartsdata kommer från en strategisk affärspartner (det är inte utgivarens data). Den här informationen samlas in och hanteras precis som förstapartsdata.

I ett scenario med andrapartsdata skickar annonsörer sina datatillgångar till utgivare så att de kan kombinera informationen med utgivarens data och genomföra ett målinriktat annonsprogram. Dessutom kan utgivare utöka sin målgruppspool genom att samarbeta med sina annonsörer. I de flesta fall omfattar dessa arrangemang avtalsförhållanden som begränsas till att placera behållartaggen [!DNL Audience Manager] på partnerwebbplatsen för att underlätta datainsamling och delning.

Ett exempel på andrapartsdatainsamling och återmarknadsföring kan vara en klädåterförsäljare som samlar in data om sina produkter och sedan delar informationen med viktiga partners. I det här fallet kan handlarna leverera olika annonser på en [!DNL Audience Manager]-partnerwebbplats för konsumenter som väljer olika färger och storlekar för jackan.

![](assets/shopping-cart-traits.png)

## Insamling av data från tredje part {#third-party-data}

Tredjepartsdata är information som samlas in och delas av leverantörer utanför [!DNL Audience Manager].

Data från tredje part kan användas för att kvalificera befintliga data [!UICONTROL segments] (t.ex. ålder, hushållsinkomst o.s.v.), tillhandahålla data som är på begäran men som inte är tillgängliga på annat sätt eller användas i lookalike-modellering mot en känd användarbas från data från första part och andra part. [!DNL Audience Manager] fungerar med många tredjepartsleverantörer av data och hjälper er att förstå vilken typ av data som dessa dataleverantörer samlar in så att ni kan göra lämpliga strategiska affärer med varje leverantör.

>[!NOTE]
>
>En fullständig lista över tredjepartsleverantörer av data som stöds av [!DNL Audience Manager] finns i [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] integreras med andra dataleverantörer baserat på deras tillgängliga  [!DNL APIs] och datauppsättningar. Datainsamling fungerar i realtid när en användare surfar på webbplatsen eller via separata metoder där ID:n synkroniseras mellan partners och data överförs mellan servrar när en användare har lämnat webbplatsen. Oavsett vilket får [!DNL Audience Manager]-klienter fördelen av att tredjepartsdata synkroniseras på vår plattform, vilket innebär att varje klient, eller domän, inte behöver utföra sin egen synkronisering. Det ökar räckvidden och minskar antalet serveranrop från sidan.

## Matchningspartners {#match-partners}

Många kunder väljer att samarbeta med tredjeparts datamatchningspartners. De har kontakter med webbplatser som kräver registrering och kan bearbeta kunddatafiler genom att matcha dem (i realtid) baserat på deras registreringsnätverk.

![dataleverantörsmatchning](assets/data-provider-match.png)
