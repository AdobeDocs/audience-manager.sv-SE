---
description: GDPR-vägledning för Audience Manager-kunder
seo-description: GDPR-vägledning för Audience Manager-kunder
seo-title: GDPR-vägledning för Audience Manager-kunder
solution: Audience Manager
title: GDPR-vägledning för Audience Manager-kunder
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# GDPR-vägledning för Audience Manager-kunder (personuppgiftsansvarig) {#gdpr-readiness-guidance}

Audience Manager rekommenderar att man agerar proaktivt när det gäller datastyrning och organisationsberedskap. Det hjälper er att se till att era kunddata organiseras för processer som rör förfrågningar om åtkomst eller radering, att era team kan hantera dessa förfrågningar och att era kunder (registrerade) får en positiv, annorlunda upplevelse av ert varumärke.

Som personuppgiftsansvarig kan Adobe inte ge juridisk rådgivning om GDPR-krav och processen för att få samtycke från era registrerade. Kontakta ert juridiska ombud för vägledning med att uppfylla GDPR.

## Datastyrning: Börja fundera på hur era kunddata hanteras i era Audience Manager-instanser

* Granska de olika kund-ID:n som era marknadsföringsteam använder för att identifiera användare i Audience Manager, tillsammans med de datakällor som de lagras i. Det effektiviserar processen för förfrågningar (till exempel om radering eller åtkomst) eftersom vissa datatyper kan hash-kodas av era team innan de hämtas till Audience Manager.
* IDFA/GAID mobila enhets-ID:n används för flera användningsområden i Audience Manager. Om du använder Adobe Mobile SDK måste du skicka in Experience Cloud ID (MID) tillsammans med IDFA/GAID för att vara säker på att GDPR-svaren är fullständiga.
* I och med att definitionen av personuppgifter blir mer omfattande kanske IP-adresser betraktas som personuppgifter i din region. Samarbeta proaktivt med Adobe Consulting för att dölja den sista oktetten.
* Bestäm en policy och process för validering/autentisering för att bekräfta identiteten på en registrerad person som gör en GDPR-begäran.
* Överväg att använda [dataexportkontroller](../../features/data-export-controls.md) för att blockera målgruppsaktivering för tekniker som lagrar personuppgifter. Segment med data från tredje part bör till exempel inte syndikeras till e-postleverantörer. Ange ett [!UICONTROL Data Export Control]-värde för att säkerställa att ingen i organisationen kan aktivera dessa data av misstag.
* Börja använda [rollbaserade åtkomstkontroller](../../features/administration/administration-overview.md) för att säkerställa att rätt team har tillgång till önskade data.
* Fastställ lämpliga [lagringsperioder](../../faq/faq-privacy.md#data-retention-faq) för uppgifter.
* Granska identitetslänkning, sekretesspolicyer och juridiska krav för att se när och var det är lämpligt att koppla samman identitetsuppsättningar och använda dem på rätt sätt via Audience Managers [regler för profilsammanslagning](../../features/profile-merge-rules/merge-rules-overview.md).

## Organisationsberedskap: Skapa en företagsprocess

* Identifiera en process för att ta emot/svara på förfrågningar från registrerade personer. Överväg att skapa ett automatiskt verktyg för att skicka förfrågningar till Audience Manager.
* Utse en kontaktperson för integritetsfrågor i ert DMP-center. Koppla samman organisationens kontaktperson för sekretess med Audience Manager-produktteamet för att förstå hur ni kan hantera krav på inmatning av ID.
* Granska uppgifterna innan de delas med den registrerade. Dokumentera de steg som ni har infört för att hjälpa er att fastställa redovisningsskyldighet.
