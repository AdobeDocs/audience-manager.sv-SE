---
description: Placera data i rapportloggfiler för leveransresultat i register som endast innehåller ID. Lägg in icke-ID-metadata i separata uppslagstabeller för att minska filstorleken och bearbetningstiden.
seo-description: Placera data i rapportloggfiler för leveransresultat i register som endast innehåller ID. Lägg in icke-ID-metadata i separata uppslagstabeller för att minska filstorleken och bearbetningstiden.
seo-title: Förbättra bearbetningstiden för loggfiler med uppslagstabeller
solution: Audience Manager
title: Förbättra bearbetningstiden för loggfiler med uppslagstabeller
uuid: ffc77618-474b-455e-9c91-15b32fc151a5
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Förbättra bearbetningstiden för loggfiler med uppslagstabeller{#improve-log-file-processing-times-with-lookup-tables}

Placera data i rapportloggfiler för leveransresultat i register som endast innehåller ID. Lägg in icke-ID-metadata i separata uppslagstabeller för att minska filstorleken och bearbetningstiden.

<!-- 

c_lookup_tables.xml

 -->

## Loggfilens metadata ökar filstorleken och bearbetningstiden

En vanlig loggfil som används av rapporten innehåller vanligtvis tusentals rader och dussintals kolumner. [!UICONTROL Delivery Performance] Det består av numeriska ID:n och läsbar information, t.ex. namn för kreatörer, annonsörer, infogningsorder osv.

Denna icke-ID-information kallas *`metadata`* (dvs. information om annan information) och skrivs i varje rad i loggfilen.

Däremot fungerar rapporten huvudsakligen med ID:n i loggfilen [!UICONTROL Delivery Performance] . Metadata är användbara, men repetitiva. Det ökar filstorleken och tar längre tid att hämta in data.

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
| 1 | 111 | 456 | 27 |
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

>[!MORELIKETHIS]
>
>* [Rapport om leverans och prestanda](../../reporting/dynamic-reports/delivery-performance-report.md)

