---
description: Audience Manager användarhantering övergår till Adobe Admin Console. I den här artikeln beskrivs vad du behöver göra för att förbereda för användarmigrering och vad som ska ändras när migreringen är klar.
keywords: rbac;RBAC;rollbaserad;rollbaserad;rollbaserad;rollbaserad åtkomstkontroll
seo-description: Audience Manager användarhantering övergår till Adobe Admin Console. I den här artikeln beskrivs vad du behöver göra för att förbereda för användarmigrering och vad som ska ändras när migreringen är klar.
seo-title: Migrering från Audience Manager till Admin Console
solution: Audience Manager
title: Migrering från Audience Manager till Admin Console
feature: Administration
translation-type: tm+mt
source-git-commit: 2e01abab2616daccd7581cdaa18417650951d139
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 2%

---


# [!DNL Audience Manager] användarmigrering till  [!DNL Admin Console] {#user-migration}

## Översikt {#overview}

[!DNL Audience Manager] Hanteringen av användarkonton går över till  [Adobe Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html) för en smidigare upplevelse över alla era Adobe-lösningar.

Fördelarna med att använda [!DNL Admin Console] är:

| Fördel | Beskrivning |
|---|---|
| Samlad inloggning i olika lösningar | [!DNL Audience Manager] -användare kan logga in på  [!DNL Experience Cloud] och alla andra lösningar med sina  [!DNL Adobe ID] eller  [!DNL Enterprise ID]. Denna inloggning ger tillgång till integrerade lösningar och bastjänster i [!DNL Experience Cloud]. Efter migreringen omdirigeras användare som försöker logga in via äldre inloggningar (`bank.demdex.com`) till `experiencecloud.adobe.com`. |
| Hantera användare och grupper | När migreringen är klar hanterar [!DNL Audience Manager]-administratörer endast användare och grupper i [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/). |
| Hantera produkter och tjänster | Från [[!DNL Admin Console]](http://adminconsole.adobe.com/enterprise/) kan administratörer: <ul><li>Skapa, uppdatera och ta bort användare</li><li>Ge åtkomst till lösningar och tjänster</li></ul> |

För att underlätta användarmigreringen ber vi alla [!DNL Audience Manager]-administratörer att börja migrera sina användarkonton till [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) så snart som möjligt genom att följa stegen som beskrivs i den här artikeln.

## Vad användare behöver göra {#what-to-do-users}

Som Audience Manager-användare behöver du bara kontakta din [!DNL Audience Manager]-administratör och be honom/henne att skapa ett nytt användarkonto åt dig i [!DNL Admin Console].

## Vad administratörer behöver göra {#what-to-do-admins}

Administratörer för Audience Manager bör följa stegen nedan för att migrera användare till [!DNL Admin Console].

1. Gå till [https://adminconsole.adobe.com](https://adminconsole.adobe.com) och logga in med ditt Adobe ID eller Enterprise ID. Om du inte har tillgång till [!DNL Admin Console] kontaktar du kundtjänst eller din Adobe-konsult.
2. I [!DNL Adobe Admin Console] [hjälpen](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/users.ug.html) finns detaljerade anvisningar om hur du skapar och hanterar användarkonton.
3. Skapa nya användarkonton för alla dina befintliga Audience Manager-användare.
4. Informera användarna om de nya användarkontona. När användare har migrerats till [!DNL Admin Console] bör de sluta använda äldre inloggningar.

## Överväganden om användarmigrering {#considerations}

Både användare och administratörer bör tänka på följande när det gäller migrering av Audience Manager-användare:

* När nya användarkonton har skapats i Admin Console gäller fortfarande deras behörigheter från de äldre användarkontona.
* Uppdateringar av användarbehörigheter hanteras fortfarande från [!DNL Audience Manager]. [!DNL Admin Console] omfattar endast användar- och grupphantering.
* Administratörer behöver inte inaktivera äldre användarkonton. Gamla användarkonton sammanfogas automatiskt i de migrerade.
