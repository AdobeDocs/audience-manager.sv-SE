---
description: 'Personbaserade mål introducerar begreppet Delningsbara målgrupper i Audience Manager. Detta mått hjälper dig att förstå hur många av de hash-kodade e-postadresserna Audience Manager kan dela med målplattformen. '
seo-description: 'Personbaserade mål introducerar begreppet Delningsbara målgrupper i Audience Manager. Detta mått hjälper dig att förstå hur många av de hash-kodade e-postadresserna Audience Manager kan dela med målplattformen. '
seo-title: Delningsbara målgrupper
solution: Audience Manager
title: Delningsbara målgrupper
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Delningsbara målgrupper {#shareable-audiences}

>[!IMPORTANT]
>Den här artikeln innehåller produktdokumentation som ska hjälpa dig att konfigurera och använda den här funktionen. Ingenting i det här är juridisk rådgivning. Vänligen kontakta ditt eget juridiska ombud för att få juridisk rådgivning.

[!DNL People-Based Destinations] ta med begreppet [!DNL Shareable Audiences] till Audience Manager. Detta mått hjälper dig att förstå hur många av de hash-kodade e-postadresserna Audience Manager kan dela med målplattformen.

[!DNL Shareable Audiences] är ett mätresultat som hjälper er att tolka målgruppsdata i sitt sammanhang [!DNL People-Based Destinations]. Mätvärdena visas på [!UICONTROL Destinations] sidan och på [!UICONTROL Segment] sidan.

## Segmentera delningsbara målgrupper {#segment-shareable-audiences}

Mätvärdet på [!DNL Segment Shareable Audience] segmentsidan anger antalet hash-kodade e-postadresser från datakällan med matchande [DPUID:n](../../reference/ids-in-aam.md), som även kvalificerar för det definierade segmentet under den angivna summeringsperioden, med tanke på den profilsammanfogningsregel som används på det, och som Audience Manager kan dela med målplattformen.

Det här måttet har en 1-dagars summeringsperiod. Detta hjälper er att förstå målgruppens räckvidd för segmentet i ett specifikt mål.

## Måldelbar målgrupp {#destination-shareable-audience}

Mätvärdet på en personbaserad målsida anger det totala antalet hash-kodade e-postadresser från datakällan med matchande [!DNL Destination Shareable Audience] DPUID [](../../reference/ids-in-aam.md), som Audience Manager kan dela med målplattformen, från alla segment som är mappade till den destinationen.

![delningsbara målgrupper](assets/dest-shareable-audiences.png)

Det här måttet har en livslång summeringsperiod. Detta hjälper er att förstå hur stor målgrupp ni kan nå från datakällan för hash-kodade e-postadresser.

## Exempel

En Audience Manager-kund har en datakälla med 110 000 [DPUID](../../reference/ids-in-aam.md) (CRM ID). De importerade 100 000 e-postadresser till Audience Manager, för att använda dem med flera personbaserade mål och för att utföra en ID-synkronisering för de 100 000 hashade e-postadresserna mot CRM-ID:n. Kunden kan använda [!DNL All Cross-Device Profiles] sammanfogningsregeln för att skapa tre målgruppssegment:

* Segment A med en befolkning på 10 000, mappad till mål A.
* Segment B med en befolkning på 20 000, mappad till mål A.
* Segment C med ett populationsantal på 50 000, mappat till mål B.

I detta scenario:

* Segment A Shareable Audience = 10 000;
* Segment B Delningsbar publik = 20 000;
* Segment C Delningsbar publik = 50 000;
* mål en delbar publik = segmentera en delbar publik + segment B delbar publik = 30 000;
* Delningsbar målgrupp B = Delningsbar målgrupp i segment C = 50 000.

![shareable-audiences-chart](assets/shareable-audiences.png)

>[!NOTE]
>
>I exemplet ovan betyder det inte att alla de 80 000 hash-kodade e-postadresserna från de tre segmenten matchar befintliga konton på målplattformarna. Det innebär bara att Audience Manager skickar de hash-kodade identifierarna från de tre segmenten till sina respektive destinationer. När målgruppssegment skickas till personbaserade mål sker målgruppsmatchning på partnersidan. Mål A kan ha upp till 30 000 matchande användarkonton, medan mål B kan ha upp till 50 000 matchande användarkonton, men det finns ingen garanti för matchningsfrekvenser. Adobe har inte tillgång till partnerspecifika mätvärden. Se [Matcha frekvenser](../../faq/faq-people-based-destinations.md#match-rates) för vanliga frågor om synlighet för personbaserade destinationer i matchningsfrekvenser.
