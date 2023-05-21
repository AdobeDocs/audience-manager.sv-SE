---
description: Audience Manager användarhantering övergår till Adobe Admin Console. I den här artikeln beskrivs vad du behöver göra för att förbereda för användarmigrering och vad som ska ändras när migreringen är klar.
keywords: rbac;RBAC;rollbaserad;rollbaserad;rollbaserad;rollbaserad åtkomstkontroll
seo-description: Audience Manager user management is moving to Adobe Admin Console. This article explains what you need to do to prepare for user migration, and what will change once the migration is complete.
seo-title: Audience Manager User Migration to Admin Console
solution: Audience Manager
title: Migrering från Audience Manager till Admin Console
feature: Administration
exl-id: d9069cc1-87fa-47b7-ad0c-d69ee37fc91e
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 3%

---

# [!DNL Audience Manager] användarmigrering till [!DNL Admin Console] {#user-migration}

## Översikt {#overview}

[!DNL Audience Manager] hantering av användarkonton går över till [Adobe Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html)för en smidigare upplevelse i alla era Adobe-lösningar.

Fördelarna med att använda [!DNL Admin Console] inkludera:

| Fördel | Beskrivning |
|---|---|
| Samlad inloggning i olika lösningar | [!DNL Audience Manager] användare kan logga in på [!DNL Experience Cloud] och alla andra lösningar som använder [!DNL Adobe ID] eller [!DNL Enterprise ID]. Denna inloggning ger tillgång till integrerade lösningar och bastjänster för [!DNL Experience Cloud]. Efter migreringen försöker användare logga in via äldre inloggningar (`bank.demdex.com`) kommer att omdirigeras till `experiencecloud.adobe.com`. |
| Hantera användare och grupper | När migreringen är klar, [!DNL Audience Manager] administratörer hanterar användare och grupper exklusivt i [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/). |
| Hantera produkter och tjänster | Från [[!DNL Admin Console]](https://adminconsole.adobe.com/enterprise/)kan administratörer: <ul><li>Skapa, uppdatera och ta bort användare</li><li>Ge åtkomst till lösningar och tjänster</li></ul> |

För att underlätta migrering av användare frågar vi alla [!DNL Audience Manager] administratörer för att börja migrera sina användarkonton till [Adobe Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html) så snart som möjligt, genom att följa de steg som beskrivs i den här artikeln.

## Vad användarna behöver göra {#what-to-do-users}

Som Audience Manager-användare behöver du bara kontakta din [!DNL Audience Manager] administratör och be dem att skapa ett nytt användarkonto åt dig i [!DNL Admin Console].

## Vad administratörer behöver göra {#what-to-do-admins}

Administratörer för Audience Manager ska följa stegen nedan för att migrera användare till [!DNL Admin Console].

1. Gå till [https://adminconsole.adobe.com](https://adminconsole.adobe.com) och logga in med ditt Adobe ID eller Enterprise ID. Om du inte har tillgång till [!DNL Admin Console], kontakta kundtjänst eller din Adobe-konsult.
2. Kontrollera [!DNL Adobe Admin Console] [hjälpguide](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) om du vill ha detaljerade anvisningar om hur du skapar och hanterar användarkonton.
3. Skapa nya användarkonton för alla dina befintliga Audience Manager-användare.
4. Informera användarna om de nya användarkontona. När användarna har migrerats till [!DNL Admin Console]bör de sluta använda äldre inloggningar.

## Överväganden om användarmigrering {#considerations}

Både användare och administratörer bör tänka på följande när det gäller migrering av Audience Manager-användare:

* När nya användarkonton har skapats i Admin Console gäller fortfarande deras behörigheter från de äldre användarkontona.
* Uppdateringar av användarbehörigheter hanteras fortfarande från [!DNL Audience Manager]. The [!DNL Admin Console] omfattar endast hantering av användare och grupper.
* Administratörer behöver inte inaktivera äldre användarkonton. Gamla användarkonton sammanfogas automatiskt i de migrerade.
