---
description: Audience Manager hjälper er att samla in och hantera data från första part, andra part och tredje part.
seo-description: Audience Manager hjälper er att samla in och hantera data från första part, andra part och tredje part.
seo-title: Typer av insamlade data
solution: Audience Manager
title: Typer av insamlade data
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 0%

---


# Typer av insamlade data {#types-of-data-collected}

[!DNL Audience Manager] hjälper er att samla in och hantera data från första part, andra part och tredje part.

Att frigöra kundinformationsresurser som lagrats i flera lokaler är en av de största datamängderna som företag står inför idag. Från [!DNL CRM] databaser, registreringssystem, annonsservrar och så vidare, företag behöver verktyg som kan centralisera värdefulla data och hantera kund-/målgruppsinformation som en enda strategisk dataresurs. [!DNL Audience Manager] hjälper er att låsa upp isolerad kundinformation och hantera datainsamling från flera källor. Insamlade data kan hanteras baserat på dataelementets time-to-live-värden ([!DNL TTL]), vilket gör att utgivaren kan kontrollera förfallodatum för alla källor. [!DNL Audience Manager] har utformats för att hjälpa dig att hantera följande typer av data:

| Datatyp | Varifrån data kommer |
|---|---|
| **Förste part** | Kunder. Data samlas in online (från konsumentinteraktioner på era webbplatser) eller offline. |
| **Andra part** | Strategiska partners och annonsörer. |
| **Tredje part** | Dataleverantörer och/eller utbyten. Data kan innehålla information som återgivning, demografi, social/livsstil, psykografi och mycket annat. |

## Insamling av data från första part {#first-party-data}

Första parts datainsamling är en [!DNL Audience Manager] huvudfunktion. Denna kärnkompetens tillgodoser behoven hos våra kunder (utgivare eller annonsörer) som vill använda egna data som hörnstenar i sina marknadsföringsprogram eller för målinriktning och modellering mot andra datakällor.

<!-- 

c_1st_party_data.xml

 -->

[!DNL Audience Manager] arbetar med kunderna för att förstå deras datastrategi och sedan mappar tillbaka den strategin till en anpassad datainsamlingsplan. Vårt Partner Solutions-team arbetar tillsammans med er för att utvärdera webbplatser, signaler för rådata och andra användarinteraktioner på era webbplatser. Med den här informationen kan vi hjälpa er att skapa en skräddarsydd datainsamlingsstrategi som hämtar datareddelanden på användarnivå från olika sidor i ert lager. Insamlade data lagras och mappas tillbaka till en fördefinierad taxonomi, som kan uppdateras när som helst när ditt företags behov förändras.

Följande exempel visar hur potentiella dataelement kan hämtas från en exempelshoppingsida.

![kundvagnsdata](assets/shopping-cart-data.png)

| Objekt | Beskrivning |
|---|---|
| 1 | **Kön**. En köpares förnamn indikerar vanligtvis deras kön. I vårt exempel är köparens förnamn Mary, så vi vet att shopparen är en kvinna. Namn lagras aldrig av Audience Manager. |
| 2 | **Intressen**. Artiklarna i kundvagnen kan visa olika intressen. I vårt exempel spenderar Mary mycket på friskvårdsutrustning. |
| 3 | **Bostadstyp**. Baserat på frakt- och/eller faktureringsadresserna kan du ta reda på om Mary köper lämplig utrustning för sig själv eller för ett företag. |
| 4 | **Plats**. [!DNL ZIP] koder är tillförlitligare än IP-adresser när det gäller att identifiera en plats. |
| 5 | **Kampanjnärhet**. Om en kund använder kampanjkoder eller presentkort är de förmodligen en köpare som letar efter de bästa erbjudandena. |
| 6 | **Utnyttjar energi**. Prisdata som korreleras med [!DNL ZIP+4] koder visar att en viss plats förbrukar energi. |

När rådata har samlats in mappas de tillbaka till kunddefinierade egenskaper inom [!DNL Audience Manager] plattformen. Både taxonomin och datamappningar kan justeras när som helst utan att datainsamlingskoden ändras.

## Insamling av data från andra part {#second-party-data}

Andra parts data kommer från en strategisk affärspartner (det är inte utgivardata). Den här informationen samlas in och hanteras precis som förstahandsdata.

<!-- 

c_2nd_party_data.xml

 -->

I ett datascenario från en annan part skickar annonsörer sina egna datatillgångar till utgivare så att de kan kombinera informationen med utgivarens data och sedan genomföra ett mer målinriktat annonsprogram. Dessutom kan utgivare utöka sin målgruppspool genom att samarbeta med sina annonsörer. I de flesta fall handlar dessa arrangemang om avtalsförhållanden som begränsas till att placera [!DNL Audience Manager] behållartaggen på partnerwebbplatsen för att underlätta datainsamling och delning.

Ett exempel på datainsamling och återmarknadsföring från andra leverantörer kan innebära att en klädåterförsäljare samlar in data om sina produkter och sedan delar denna information med viktiga partner. I det här fallet kan handlarna leverera olika annonser på en partnerwebbplats för kunder som väljer olika färger och storlekar för jackan. [!DNL Audience Manager]

![](assets/shopping-cart-traits.png)

## Insamling av data från tredje part {#third-party-data}

Tredjepartsdata är information som samlas in och delas av leverantörer utanför Audience Manager.

<!-- 

c_3rd_party_data.xml

 -->

Data från tredje part kan användas för att kvalificera befintliga datasegment (t.ex. ålder, hushållsinkomst o.s.v.), tillhandahålla data som är i behov men inte på annat sätt tillgängliga eller användas i lookalike-modellering mot en känd användarbas från data från första part och andra part. [!DNL Audience Manager] arbetar med många tredjepartsleverantörer av data och hjälper er att förstå vilken typ av data dessa dataleverantörer samlar in så att ni kan göra rätt strategiska affärer med varje leverantör.

>[!NOTE]
>
>En fullständig lista över tredjepartsleverantörer av data som stöds av [!DNL Audience Manager]finns i [Adobe Audience Finder](https://www.adobe-audience-finder.com/).

[!DNL Audience Manager] integreras med andra dataleverantörer baserat på deras tillgängliga [!DNL APIs] och datauppsättningar. Datainsamling fungerar i realtid när en användare surfar på webbplatsen, eller via out-of-band-metoder där ID:n synkroniseras mellan partner och data överförs mellan servrar när en användare har lämnat webbplatsen. I båda fallen får [!DNL Audience Manager] kunderna fördelen av att tredjepartsdata synkroniseras på vår plattform, vilket innebär att varje klient, eller domän, inte behöver utföra sin egen synkronisering. Detta ökar räckvidden och minskar antalet serveranrop från sidan.

## Matcha partners {#match-partners}

Många kunder väljer att arbeta med tredjeparts datamatchningspartners. Dessa enheter har relationer med webbplatser som har registreringskrav och kan bearbeta kunddatafiler genom att matcha dem (i realtid) baserat på deras registreringsnätverk.

![data-provider-match](assets/data-provider-match.png)
