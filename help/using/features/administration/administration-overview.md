---
description: Med alternativen på menyn Administration kan du skapa Audience Manager-användare och tilldela dem till grupper. Du kan också visa gränser (egenskaper, segment, mål och modeller).
keywords: rbac;RBAC;rollbaserad;rollbaserad;rollbaserad;rollbaserad åtkomstkontroll
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administrering
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: 8ef6e8eb4351c24b55703b1788c68c580f199fc8
workflow-type: tm+mt
source-wordcount: '1159'
ht-degree: 2%

---

# [!UICONTROL Administration] (RBAC-kontroller) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> Hanteringen av användarkonton går över till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). För att starta migreringen av användare måste alla Audience Manager-kunder omedelbart vidta de nödvändiga åtgärder som beskrivs i den här artikeln: [migrering från Audience Manager till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat kommer användarhanteringsavsnitten i det här dokumentet att försvinna.


Alternativen under [!UICONTROL Administration] kan du skapa Audience Manager-användare och tilldela dem till grupper. Du kan också visa gränser (egenskaper, segment, mål och modeller).

Företagskunder som använder [!DNL Audience Manager] behöver en datahanteringsplattform för alla sina data, men måste kunna styra synligheten för de olika dataelementen till specifika affärsenheter. Du kan uppnå detta med gruppbehörigheter, som också kallas [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] använder grupper för att tilldela behörigheter. Behörigheter tilldelas inte på användarnivå. Gruppbehörigheter är knutna till objekt ([!UICONTROL traits], segment osv.) och till åtgärder som du kan utföra på dessa objekt (redigera, visa osv.). Dessa kontroller är också tillgängliga via Audience Manager REST API:er. Se [Användarhantering](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Grupphantering](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md)och [Behörighetshantering](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md) API-metoder.

## Skapa användare {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> Hanteringen av användarkonton går över till [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). För att starta migreringen av användare måste alla Audience Manager-kunder omedelbart vidta de nödvändiga åtgärder som beskrivs i den här artikeln: [migrering från Audience Manager till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat försvinner avsnittet för användarhantering i det här dokumentet.
Skapa användare i [!DNL Audience Manager] och ange användarinformation, inloggningsstatus och tilldela användare till grupper.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Klicka ![](assets/icon_add.png) för att visa [!UICONTROL Create New User] sida.
1. Under **[!UICONTROL User Details]**, fylla i fälten:
   * **[!UICONTROL Username]:** Ange ett unikt användarnamn för Audience Manager.
   * **[!UICONTROL First Name]:** Ange användarens förnamn.
   * **[!UICONTROL Last Name]:** Ange användarens efternamn.
   * **[!UICONTROL Email Address]:** Ange användarens e-postadress. [!DNL Audience Manager] skickar inte vanliga meddelanden till användarna. [!DNL Audience Manager] administratörer har tillgång till användarnas e-postadresser och kan manuellt skicka e-post till användare efter behov. Om en användare t.ex. glömmer sitt lösenord, används den e-postadress som anges i det här fältet för att skicka ett tillfälligt lösenord och instruktioner för att återställa lösenordet.
   * **[!UICONTROL Phone Number]:** Ange användarens telefonnummer.
   * **[!UICONTROL Is Admin]:** Ange om den här användaren är en [!DNL Audience Manager] administratör. Administratörsanvändare kan hantera användare (skapa, redigera osv.) och grupper (skapa, tilldela behörigheter osv.). Användare som inte är administratörer kan bara styra sina egna användarprofiler, inklusive redigera sina e-postadresser och återställa sina egna lösenord. Mer information finns i [Redigera dina kontoinställningar](../../features/administration/edit-account-settings.md).
1. Under **[!UICONTROL Login]** väljer du önskad status:
   * **[!UICONTROL Active]:**  Aktiva användare har åtkomst [!DNL Audience Manager] och har de behörigheter som beviljas genom gruppmedlemskap.
   * **[!UICONTROL Deactivated]:**  Inaktiverade användare kan inte komma åt [!DNL Audience Manager] och har inga behörigheter. Om du inaktiverar användare finns användarinformationen kvar [!DNL Audience Manager] och du kan enkelt återaktivera dem om det behövs. Om du tar bort användare måste du återskapa dem om de behöver använda [!DNL Audience Manager] i framtiden.
   * **[!UICONTROL Expired]:** En användares lösenord är äldre än 90 dagar.
   * **[!UICONTROL Pending]:** Användaren har ett tillfälligt lösenord, antingen efter en lösenordsåterställning eller som ett helt nytt konto, och har ännu inte angett ett permanent lösenord.
   * **[!UICONTROL Locked Out]:** 5 felaktiga inloggningsförsök låser en användare.
1. Under **[!UICONTROL Assigned Groups]**i listrutan väljer du de grupper som du vill tilldela användaren till.
Mer information om grupper och behörigheter finns i [Skapa en grupp](../../features/administration/administration-overview.md#create-group).
1. Klicka på **[!UICONTROL Save]**.

## Skapa en [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> Hanteringen av användarkonton går över till [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Vi rekommenderar alla Audience Manager-kunder att omedelbart vidta de åtgärder som beskrivs i den här artikeln för att starta migreringen av användare: [migrering från Audience Manager till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat försvinner det här avsnittet.

A *grupp* är en samling användare som delar åtkomsträttigheter till [!UICONTROL destination], [!UICONTROL segment]och [!UICONTROL trait] objekt. Du kan begränsa grupper till endast enskilda objekt eller ge dem bred åtkomst till kombinationer av olika objekt.

<!-- t_create_groups.xml -->

Så här skapar du en grupp:

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Klicka  ![](assets/icon_add.png) för att öppna [!UICONTROL Group Settings] sida.
3. I [!UICONTROL Group Details]:
   * Ge gruppen ett namn.
   * Ange en kort gruppbeskrivning.
4. I [!UICONTROL Group Members]klickar du på en användare från **[!UICONTROL Add Users]** alternativ för att lägga till dem i gruppen.
5. I [!UICONTROL Group Permissions]väljer du en [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md), eller [mål](../../features/destinations/destinations.md) från **[!UICONTROL Add Object]**.
Då öppnas ett behörighetsfönster för det markerade objektet.
6. Markera kryssrutan för de behörigheter som du vill att gruppmedlemmar ska ha.
7. *(Valfritt)* Tilldela [Wild Card permissions](../../features/administration/administration-overview.md#wild-card-permissions) till gruppen.
8. Klicka på **[!UICONTROL Save Group]**.

## Förstå [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> Hanteringen av användarkonton går över till [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Vi rekommenderar alla Audience Manager-kunder att omedelbart vidta de åtgärder som beskrivs i den här artikeln för att starta migreringen av användare: [migrering från Audience Manager till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat försvinner det här avsnittet.

Förenkla hanteringen av grupprättigheter med [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] ge gruppmedlemmar automatisk åtkomst till alla datakällor som är kopplade till en [!UICONTROL segment], [!UICONTROL destination], eller [!UICONTROL trait]. Som en jämförelse kan du bara tilldela specifika behörigheter med vanlig behörighet [!UICONTROL data sources] till ett av dessa objekt. Och när du lägger till nya [!UICONTROL data sources], får gruppmedlemmar inte tillgång till de nya källorna.

Du måste öppna gruppbehörigheterna och tilldela dessa nya [!UICONTROL data sources] till gruppen. [!UICONTROL Wild Card Permissions] låt dig undvika den här handboken [!UICONTROL data source] uppdateringsprocess. Grupper med [!UICONTROL Wild Card Permissions] få tillgång till nya [!UICONTROL data sources] utan uttrycklig behörighet.

![](assets/wild-card.png)

Läs nedan för en beskrivning av vad [!UICONTROL wildcard permission] betyder

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Användare kan välja [!UICONTROL traits] som baslinje för [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Användare kan redigera alla [!UICONTROL traits] som har skapats på deras företagskonto.
* `VIEW_ALL_TRAITS` - Användare kan visa alla [!UICONTROL traits] som har skapats på deras företagskonto.
* `DELETE_ALL_TRAITS` - Användare kan ta bort alla [!UICONTROL traits] som har skapats på deras företagskonto.
* `CREATE_ALL_ALGO_TRAITS` - Användare kan skapa [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Användare kan lägga till alla [!UICONTROL traits] tillhör sitt företag till [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Användare kan skapa [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Användare har behörighet att visa [!UICONTROL models] som tillhör deras företag.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Användare kan visa alla [!UICONTROL derived signals] som tillhör deras företag.
* `CREATE_DERIVED_SIGNALS` - Användare kan skapa [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Användare kan redigera alla [!UICONTROL derived signals] som tillhör deras företag.
* `DELETE_DERIVED_SIGNALS` - Användare kan ta bort alla [!UICONTROL derived signals] som tillhör deras företag.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Användare kan redigera alla [!UICONTROL destinations] som har skapats på deras företagskonto.
* `CREATE_DESTINATIONS` - Användare kan skapa [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Användare kan visa alla [!UICONTROL destinations] som har skapats på deras företagskonto.
* `DELETE_ALL_DESTINATIONS` - Användare kan ta bort alla [!UICONTROL destinations] som har skapats på deras företagskonto.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Användare kan göra allt (visa, skapa, redigera, ta bort) på sina [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Användare kan göra allt (visa, skapa, redigera, ta bort) på sina [!UICONTROL Audience Lab] testgrupper.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Användare kan skapa segment.
* `DELETE_ALL_SEGMENTS` - Användare kan ta bort alla segment som har konfigurerats i deras företagskonto.
* `MAP_ALL_TO_DESTINATIONS` - Användare kan mappa alla segment som tillhör deras företag till destinationer.
* `EDIT_ALL_SEGMENTS` - Användare kan redigera alla segment som har konfigurerats i deras företagskonto.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Användare kan välja segment som baslinje för modeller.
* `VIEW_ALL_SEGMENTS` - Användare kan visa alla segment som har konfigurerats i deras företagskonto.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Användare kan visa alla signaler som samlats in i [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Användningsexempel {#use-cases}

### Övervaka användaråtkomst {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] kan hjälpa dig att övervaka inloggningsstatus och ge dig en tydlig bild av vem som har åtkomst till din Audience Manager-instans.

Beroende på dina affärskrav kan du aktivera och inaktivera användarkonton efter behov.

![monitor-user-access](assets/monitor-user-access.png)

### Skydda känslig åtkomst [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Du kan konfigurera [!UICONTROL Role-Based Access Control] på [!UICONTROL trait], segment och [!UICONTROL destination] nivå, för varje användargrupp.

Med den här funktionen kan du hantera hur användarna visar, skapar, läser, skriver och redigerar specifika datauppsättningar och till och med hindra användare från att komma åt datauppsättningar som inte ska vara tillgängliga för dem.

![åtkomstskydd](assets/access-protection.png)
