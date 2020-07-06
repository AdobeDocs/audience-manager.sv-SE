---
description: Med Audience Manager kan ni samla in och hantera data från första part, andra part och tredje part.
seo-description: Med Audience Manager kan ni samla in och hantera data från första part, andra part och tredje part.
seo-title: Typer av insamlade data
solution: Audience Manager
title: Typer av insamlade data
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 73%

---


# Typer av insamlade data {#types-of-data-collected}

[!DNL Audience Manager]Med kan ni samla in och hantera data från första part, andra part och tredje part.

Att frigöra informationstillgångar om kunder som lagrats på flera platser är en av de största utmaningarna som företag står inför idag. From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] hjälper er att låsa upp isolerad kundinformation och hantera datainsamling från flera källor. Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] är utformat för att hjälpa er att hantera följande typer av data:

| Datatyper | Datakälla |
|---|---|
| **Första part** | Kunder. Data samlas in online (från kundinteraktioner på era webbplatser) eller offline. |
| **Andra part** | Strategiska partners och annonsörer. |
| **Tredje part** | Dataleverantörer och/eller bytesplattformar. Data kan innehålla information som avsikt, demografi, socialt/livsstil, psykografi med mera. |

## Insamling av data från första part {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. Denna huvudfunktion tillgodoser behoven hos våra kunder (utgivare och annonsörer) som vill använda egna data som hörnstenar i marknadsföringsprogram eller för målinriktning och modellering mot andra datakällor.

[!DNL Audience Manager] hjälper kunderna att förstå sin datastrategi och mappar sedan den strategin i en anpassad datainsamlingsplan. Vårt Partner Solutions-team arbetar tillsammans med er för att utvärdera webbplatser, rådatasignaler och andra användarinteraktioner på era webbplatser. Med den här informationen kan vi hjälpa er att skapa en skräddarsydd datainsamlingsstrategi som hämtar datasignaler på användarnivå från olika sidor i ert lager. Insamlade data lagras och mappas tillbaka i en fördefinierad taxonomi som kan uppdateras när som helst när företagets behov förändras.

Följande exempel visar hur potentiella dataelement kan hämtas från en shoppingsida.

![kundvagnsdata](assets/shopping-cart-data.png)

| Objekt | Beskrivning |
|---|---|
| 1 | **Kön**. En köpares förnamn indikerar vanligtvis kön. I vårt exempel är köparens förnamn Mary, så vi vet att köparen är en kvinna. Namn lagras aldrig av Audience Manager. |
| 2 | **Intressen**. Artiklarna i kundvagnen kan visa olika intressen. I vårt exempel spenderar Mary mycket pengar på träningsutrustning. |
| 3 | **Bostadstyp**. Baserat på frakt- och/eller faktureringsadress kan vi ta reda på om Mary köper träningsutrustning åt sig själv eller ett företag. |
| 4 | **Plats**. [!DNL ZIP] koder är tillförlitligare än [!DNL IP] adresser när det gäller att identifiera en plats. |
| 5 | **Prismedvetenhet**. Om en kund använder kampanjkoder eller presentkort är hen förmodligen en köpare som letar efter bra erbjudanden. |
| 6 | **Köpkraft**. Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. Både taxonomin och datamappningarna kan justeras när som helst utan att datainsamlingskoden ändras.

## Insamling av data från andra part {#second-party-data}

Andrapartsdata kommer från en strategisk affärspartner (det är inte utgivarens data). Den här informationen samlas in och hanteras precis som förstapartsdata.

I ett scenario med andrapartsdata skickar annonsörer sina datatillgångar till utgivare så att de kan kombinera informationen med utgivarens data och genomföra ett målinriktat annonsprogram. Dessutom kan utgivare utöka sin målgruppspool genom att samarbeta med sina annonsörer. In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

Ett exempel på andrapartsdatainsamling och återmarknadsföring kan vara en klädåterförsäljare som samlar in data om sina produkter och sedan delar informationen med viktiga partners. In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## Insamling av data från tredje part {#third-party-data}

Tredjepartsdata är information som samlas in och delas av leverantörer utanför [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] fungerar med många tredjepartsleverantörer av data och hjälper er att förstå vilken typ av data som dessa dataleverantörer samlar in så att ni kan göra lämpliga strategiska affärer med varje leverantör.

>[!NOTE]
>
>En fullständig lista över tredjepartsleverantörer av data som stöds av [!DNL Audience Manager] finns i [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] integreras med andra dataleverantörer baserat på deras tillgängliga [!DNL APIs] och datauppsättningar. Datainsamling fungerar i realtid när en användare surfar på webbplatsen eller via separata metoder där ID:n synkroniseras mellan partners och data överförs mellan servrar när en användare har lämnat webbplatsen. In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. Det ökar räckvidden och minskar antalet serveranrop från sidan.

## Matchningspartners {#match-partners}

Många kunder väljer att samarbeta med tredjeparts datamatchningspartners. De har kontakter med webbplatser som kräver registrering och kan bearbeta kunddatafiler genom att matcha dem (i realtid) baserat på deras registreringsnätverk.

![dataleverantörsmatchning](assets/data-provider-match.png)
