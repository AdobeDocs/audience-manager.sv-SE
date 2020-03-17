---
description: GDPR-beredskapsvägledning för kunder med Audience Manager
seo-description: GDPR-beredskapsvägledning för kunder med Audience Manager
seo-title: GDPR-beredskapsvägledning för kunder med Audience Manager
solution: Audience Manager
title: GDPR-beredskapsvägledning för kunder med Audience Manager
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# GDPR-beredskapsvägledning för Audience Manager-kunder (datakontroller) {#gdpr-readiness-guidance}

Audience Manager rekommenderar att man är proaktiv när det gäller datastyrning och organisationsberedskap. Detta hjälper er att se till att era konsumentdata ordnas för processer som rör förfrågningar om åtkomst eller radering, att era team är aktiverade och kan hantera dessa förfrågningar, och att era konsumenter (registrerade) har en positiv, differentierad upplevelse av ert varumärke.

Som databehandlare kan Adobe inte ge juridisk rådgivning om GDPR-krav och processen för att få samtycke från era registrerade. Kontakta ditt juridiska ombud för att få hjälp med hur er organisation uppfyller GDPR.

## Datastyrning: Börja fundera på hur era konsumentdata hanteras i era Audience Manager-instanser

* Granska de olika kund-ID:n som era marknadsföringsteam använder för att identifiera användare i Audience Manager, tillsammans med de datakällor som de lagras i. Detta kommer att effektivisera processen för förfrågningar (till exempel borttagning eller åtkomst) eftersom vissa datatyper hashas av era team innan de hämtas till Audience Manager.
* ID:n för mobila enheter i IDFA/GAID används för flera användningsområden i Audience Manager. Om du använder Adobe Mobile SDK måste du skicka in Experience Cloud ID (MID) tillsammans med IDFA/GAID för att vara säker på att GDPR-svaren är fullständiga.
* I och med att definitionen av personuppgifter blir mer omfattande kan IP-adresser betraktas som personuppgifter i din region. Håll ett proaktivt samarbete med Adobe Consulting för att dölja den sista oktetten.
* Bestäm en policy och process för validering/autentisering för att bekräfta identiteten på en registrerade när de gör en GDPR-begäran.
* Överväg att använda [dataexportkontroller](../../features/data-export-controls.md) för att blockera målgruppsaktivering för tekniker som lagrar personuppgifter. Segment med data från tredje part bör till exempel inte syndikeras till e-postleverantörer. Ange ett värde [!UICONTROL Data Export Control] för att säkerställa att ingen i organisationen kan aktivera dessa data av misstag.
* Börja använda [rollbaserade åtkomstkontroller](../../features/administration/administration-overview.md) för att säkerställa att rätt team har tillgång till önskade data.
* Tänk på lämpliga [kvarhållningsperioder](../../faq/faq-privacy.md#data-retention-faq) för uppgifterna.
* Granska identitetslänkning, integritetspolicyer och juridiska krav för att se när och var det är lämpligt att knyta samman identitetsuppsättningar. använda på rätt sätt via Audience Managers regler [för](../../features/profile-merge-rules/merge-rules-overview.md)profilsammanslagning.

## Organisationsberedskap: Skapa en affärsprocess

* Identifiera en process för att ta emot/besvara förfrågningar från registrerade personer. Överväg att skapa ett automatiskt verktyg för att skicka förfrågningar till Audience Manager.
* Utse en kontaktpunkt för integritetsfrågor i ert högklassiga datahanteringscenter. Koppla samman organisationens kontaktpunkt för integritetsskydd med Audience Manager-produktteamet för att förstå hur du kan hantera dina krav på indata-ID.
* Genomför en granskning av uppgifterna innan de delas med den registrerade. Dokumentera de steg som ni inför för att hjälpa er att etablera ansvarighet.
