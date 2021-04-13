---
description: Placera data i rapportloggfiler för leveransresultat i register som endast innehåller ID. Lägg in icke-ID-metadata i separata uppslagstabeller för att minska filstorleken och bearbetningstiden.
seo-description: Placera data i rapportloggfiler för leveransresultat i register som endast innehåller ID. Lägg in icke-ID-metadata i separata uppslagstabeller för att minska filstorleken och bearbetningstiden.
seo-title: Förbättra bearbetningstiden för loggfiler med sökregister
solution: Audience Manager
title: Förbättra bearbetningstiden för loggfiler med sökregister
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
feature: Rapporteringsreferens
exl-id: bab51406-21e9-4033-90d4-6100daf6a311
translation-type: tm+mt
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 13%

---

# Förbättra bearbetningstiden för loggfiler med sökregister{#improve-log-file-processing-times-with-lookup-tables}

Placera data i rapportloggfiler för leveransresultat i register som endast innehåller ID. Lägg in icke-ID-metadata i separata uppslagstabeller för att minska filstorleken och bearbetningstiden.

<!-- 

c_lookup_tables.xml

 -->

## Loggfilens metadata ökar filstorleken och bearbetningstiden

En vanlig loggfil som används av [!UICONTROL Delivery Performance]-rapporten innehåller vanligtvis tusentals rader och dussintals kolumner. Det består av numeriska ID:n och läsbar information, t.ex. namn för kreatörer, annonsörer, infogningsorder osv.

Denna icke-ID-information kallas *`metadata`* (dvs. information om annan information) och skrivs i varje rad i loggfilen.

Däremot fungerar [!UICONTROL Delivery Performance]-rapporten huvudsakligen med ID:n i loggfilen. Metadata är användbara, men repetitiva. Det ökar filstorleken och tar längre tid att hämta data.

## Minska filstorleken och förkorta behandlingstiden med indextabeller

För att förbättra prestandan bör din huvuddatafil endast innehålla ID:n. Lägg in metadata i en separat uppslagstabell (eller indextabell) och länka dessa poster till huvudfilen med en nyckelvariabel som är gemensam för båda.

## Hur uppslagstabeller minskar filstorleken

Säg att du har en datafil som ser ut ungefär som den nedan.

| Användar-ID | Annons-ID | Annonsnamn | Order-ID | Ordernamn | Annonsörs-ID | Advertiser-namn |
|---|---|---|---|---|---|---|
| 1 | 111 | Shoe A | 456 | Sneakers | 27 | Företag A |
| 2 | 111 | Shoe A | 456 | Sneakers | 27 | Företag A |
| 3 | 111 | Shoe A | 456 | Sneakers | 27 | Företag A |
| 4 | 222 | Sot B | 789 | Vattna | 14 | Företag B |
| 5 | 222 | Sot B | 789 | Vattna | 14 | Företag B |

<br>

Här är samma loggfil med metadata borttagna. Filen är mindre och enklare att bearbeta om den bara består av ID:n.

| Användar-ID | Annons-ID | Order-ID | Annonsörs-ID |
|---|---|---|---|
| 3 | 111 | 456 | 27 |
| 2 | 111 | 456 | 27 |
| 3 | 111 | 456 | 27 |
| 4 | 222 | 789 | 14 |
| 5 | 222 | 789 | 14 |

<br> 

Sökfilen nedan innehåller metadata och kan länkas tillbaka till huvudfilen med ID:t. Notera även storleken. I stället för att upprepa varje annonsör flera gånger behöver du bara en referens för varje.

| Annons-ID | Annonsnamn | Ordernamn | Advertiser-namn |
|---|---|---|---|
| 111 | Shoe A | Sneakers | Företag A |
| 222 | Sot B | Vattna | Företag B |

## API:er kan eliminera behovet av uppslagstabeller

Om ert annonssystem har ett API kanske ni inte behöver skicka metadata i en sökfil. Vi kan kanske få den informationen via API:t. I så fall bör loggfilerna endast innehålla ID:n. Vi arbetar tillsammans med dig för att avgöra om metadata kan hämtas via ett API.
