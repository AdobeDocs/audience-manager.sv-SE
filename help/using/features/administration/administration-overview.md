---
description: Med alternativen på menyn Administration kan du skapa Audience Manager-användare och tilldela dem till grupper. Du kan också visa gränser (egenskaper, segment, mål och modeller).
keywords: rbac;RBAC;rollbaserad;rollbaserad;rollbaserad;rollbaserad åtkomstkontroll
seo-description: The options under the Administration menu let you create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and models).
seo-title: Administration
solution: Audience Manager
title: Administration
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: Administration
exl-id: f23f4294-35d9-4128-bcda-64a3eccbb4e7
source-git-commit: c29e581c736e03066df7d0698d4ea384e14db467
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 0%

---

# [!UICONTROL Administration] (RBAC-kontroller) {#administration}

![](assets/rbac-controls.png)

>[!IMPORTANT]
>
> Hanteringen av användarkonton flyttas till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). För att starta användarmigreringen måste alla Audience Manager-kunder omedelbart vidta de nödvändiga åtgärder som beskrivs i den här artikeln: [Audience Manager-användarmigrering till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat kommer användarhanteringsavsnitten i det här dokumentet att försvinna.

>[!IMPORTANT]
>
> Innan du kan använda [!DNL RBAC] måste den här funktionen aktiveras av Adobe för din organisation. Kontakta ditt kontoteam för att begära aktivering av [!DNL RBAC], eller kontakta kundtjänst.


Med alternativen på menyn [!UICONTROL Administration] kan du skapa Audience Manager-användare och tilldela dem till grupper. Du kan också visa gränser (egenskaper, segment, mål och modeller).

Företagskunder som använder [!DNL Audience Manager] behöver en datahanteringsplattform för alla sina data, men måste kunna styra synligheten för olika dataelement för specifika affärsenheter. Du kan uppnå detta med gruppbehörigheter, som också kallas [!UICONTROL Role-Based Access Control] ([!UICONTROL RBAC]).

[!DNL Audience Manager] använder grupper för att tilldela behörigheter. Behörigheter tilldelas inte på användarnivå. Gruppbehörigheter är knutna till objekt ([!UICONTROL traits], segment osv.) och åtgärder som du kan utföra på dessa objekt (redigera, visa, osv.). Dessa kontroller är också tillgängliga via Audience Manager REST API:er. Se API-metoderna [Användarhantering](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-user.md), [Grupphantering](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-group.md) och [Behörighetshantering](/help/using/api/rest-api-main/aam-api-user-group-permission/aam-api-permissions.md).

## Skapa användare {#create-users}

<!-- t_create_users.xml -->

>[!IMPORTANT]
>
> Hanteringen av användarkonton flyttas till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). För att starta användarmigreringen måste alla Audience Manager-kunder omedelbart vidta de nödvändiga åtgärder som beskrivs i den här artikeln: [Audience Manager-användarmigrering till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat försvinner avsnittet för användarhantering i det här dokumentet.
> 
>Skapa användare i [!DNL Audience Manager] och ange användarinformation, inloggningsstatus och tilldela användare till grupper.

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Users]**.
1. Klicka på ![](assets/icon_add.png) för att visa sidan [!UICONTROL Create New User].
1. Fyll i fälten under **[!UICONTROL User Details]**:
   * **[!UICONTROL Username]:** Ange ett unikt användarnamn för Audience Manager.
   * **[!UICONTROL First Name]:** Ange användarens förnamn.
   * **[!UICONTROL Last Name]:** Ange användarens efternamn.
   * **[!UICONTROL Email Address]:** Ange användarens e-postadress. [!DNL Audience Manager] skickar inte regelbundna meddelanden till användarna. [!DNL Audience Manager] administratörer har åtkomst till användarnas e-postadresser och kan skicka e-post manuellt till användare efter behov. Om en användare t.ex. glömmer sitt lösenord, används den e-postadress som anges i det här fältet för att skicka ett tillfälligt lösenord och instruktioner för att återställa lösenordet.
   * **[!UICONTROL Phone Number]:** Ange användarens telefonnummer.
   * **[!UICONTROL Is Admin]:** Ange om användaren är en [!DNL Audience Manager]-administratör. Administratörsanvändare kan hantera användare (skapa, redigera osv.) och grupper (skapa, tilldela behörigheter osv.). Användare som inte är administratörer kan bara styra sina egna användarprofiler, inklusive redigera sina e-postadresser och återställa sina egna lösenord. Mer information finns i [Redigera dina kontoinställningar](../../features/administration/edit-account-settings.md).
1. Välj önskad status under **[!UICONTROL Login]**:
   * **[!UICONTROL Active]:** Aktiva användare har åtkomst till [!DNL Audience Manager] och behörighet som beviljas genom gruppmedlemskap.
   * **[!UICONTROL Deactivated]:** Inaktiverade användare har inte åtkomst till [!DNL Audience Manager] och har inga behörigheter. Om du inaktiverar användare finns deras användarinformation kvar i [!DNL Audience Manager] och du kan enkelt återaktivera dem om det behövs. Om du tar bort användare måste du återskapa dem om de behöver använda [!DNL Audience Manager] igen i framtiden.
   * **[!UICONTROL Expired]:** En användares lösenord är äldre än 90 dagar.
   * **[!UICONTROL Pending]:** Användaren har ett tillfälligt lösenord, antingen efter en lösenordsåterställning eller som ett helt nytt konto, och har ännu inte angett ett permanent lösenord.
   * **[!UICONTROL Locked Out]:** 5 felaktiga inloggningsförsök låser en användare.
1. Under **[!UICONTROL Assigned Groups]** i listrutan väljer du de grupper som du vill tilldela användaren till.
Mer information om grupper och behörigheter finns i [Skapa en grupp](../../features/administration/administration-overview.md#create-group).
1. Klicka på **[!UICONTROL Save]**.

## Skapa en [!UICONTROL Group] {#create-group}

>[!IMPORTANT]
>
> Hanteringen av användarkonton flyttas till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). För att starta användarmigrering rekommenderar vi alla Audience Manager-kunder att omedelbart vidta de nödvändiga åtgärder som beskrivs i den här artikeln: [Audience Manager-användarmigrering till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat försvinner det här avsnittet.

En *grupp* är en samling användare som delar åtkomsträttigheter till [!UICONTROL destination]-, [!UICONTROL segment]- och [!UICONTROL trait]-objekt. Du kan begränsa grupper till endast enskilda objekt eller ge dem bred åtkomst till kombinationer av olika objekt.

<!-- t_create_groups.xml -->

Så här skapar du en grupp:

1. Klicka på **[!UICONTROL Administration]** > **[!UICONTROL Groups]**.
2. Klicka på ![](assets/icon_add.png) för att öppna sidan [!UICONTROL Group Settings].
3. I [!UICONTROL Group Details]:
   * Ge gruppen ett namn.
   * Ange en kort gruppbeskrivning.
4. I [!UICONTROL Group Members] klickar du på en användare bland **[!UICONTROL Add Users]** alternativ för att lägga till dem i gruppen.
5. I [!UICONTROL Group Permissions] väljer du [trait](../../features/traits/trait-details-page.md), [segment](../../features/segments/segments-purpose.md) eller [mål](../../features/destinations/destinations.md) från **[!UICONTROL Add Object]**.
Då öppnas ett behörighetsfönster för det markerade objektet.
6. Markera kryssrutan för de behörigheter som du vill att gruppmedlemmar ska ha.
7. *(Valfritt)* Tilldela [Wild Card-behörigheter](../../features/administration/administration-overview.md#wild-card-permissions) till gruppen.
8. Klicka på **[!UICONTROL Save Group]**.

## Förstå [!UICONTROL Wild Card Permissions] {#wild-card-permissions}

>[!IMPORTANT]
>
> Hanteringen av användarkonton flyttas till [Admin Console](https://helpx.adobe.com/se/enterprise/using/admin-console.html). För att starta användarmigrering rekommenderar vi alla Audience Manager-kunder att omedelbart vidta de nödvändiga åtgärder som beskrivs i den här artikeln: [Audience Manager-användarmigrering till Admin Console](admin-console-migration.md).
> 
> När alla kunder har migrerat försvinner det här avsnittet.

Förenkla hanteringen av grupprättigheter med [!UICONTROL Wild Card Permissions].

<!-- c_wildcard_permissions.xml -->

[!UICONTROL Wild Card Permissions] ger gruppmedlemmar automatisk åtkomst till alla datakällor som är kopplade till en [!UICONTROL segment], [!UICONTROL destination] eller [!UICONTROL trait]. I vanliga behörigheter kan du bara tilldela specifika [!UICONTROL data sources] till ett av dessa objekt. När du lägger till nya [!UICONTROL data sources] får gruppmedlemmar inte tillgång till de nya källorna.

Du måste öppna gruppbehörigheterna och tilldela gruppen de nya [!UICONTROL data sources]. [!UICONTROL Wild Card Permissions] låter dig undvika den här manuella [!UICONTROL data source]-uppdateringsprocessen. Grupper med [!UICONTROL Wild Card Permissions] får åtkomst till nya [!UICONTROL data sources] utan explicit auktorisering.

![](assets/wild-card.png)

Läs nedan för att få en beskrivning av vad varje [!UICONTROL wildcard permission] betyder:

**[!UICONTROL Trait]**

* `MAP_ALL_TRAITS_TO_MODELS` - Användare kan välja [!UICONTROL traits] som baslinje för [!UICONTROL models].
* `EDIT_ALL_TRAITS` - Användare kan redigera alla [!UICONTROL traits] som har konfigurerats i deras företagskonto.
* `VIEW_ALL_TRAITS` - Användare kan visa alla [!UICONTROL traits] som har konfigurerats i deras företagskonto.
* `DELETE_ALL_TRAITS` - Användare kan ta bort alla [!UICONTROL traits] som har konfigurerats i deras företagskonto.
* `CREATE_ALL_ALGO_TRAITS` - Användare kan skapa [!UICONTROL algorithmic traits].
* `MAP_ALL_TO_SEGMENTS` - Användare kan lägga till alla [!UICONTROL traits] som tillhör deras företag i [!UICONTROL segments].
* `CREATE_ALL_TRAITS` - Användare kan skapa [!UICONTROL traits].

**[!UICONTROL Models]**

* `VIEW_MODELS` - Användare har behörighet att visa [!UICONTROL models] som tillhör deras företag.

**[!UICONTROL Derived Signals]**

* `VIEW_DERIVED_SIGNALS` - Användare kan visa alla [!UICONTROL derived signals] som tillhör deras företag.
* `CREATE_DERIVED_SIGNALS` - Användare kan skapa [!UICONTROL derived signals].
* `EDIT_DERIVED_SIGNALS` - Användare kan redigera alla [!UICONTROL derived signals] som tillhör deras företag.
* `DELETE_DERIVED_SIGNALS` - Användare kan ta bort alla [!UICONTROL derived signals] som tillhör deras företag.

**[!UICONTROL Destination]**

* `EDIT_ALL_DESTINATIONS` - Användare kan redigera alla [!UICONTROL destinations] som har konfigurerats i deras företagskonto.
* `CREATE_DESTINATIONS` - Användare kan skapa [!UICONTROL destinations].
* `VIEW_ALL_DESTINATIONS` - Användare kan visa alla [!UICONTROL destinations] som har konfigurerats i deras företagskonto.
* `DELETE_ALL_DESTINATIONS` - Användare kan ta bort alla [!UICONTROL destinations] som har konfigurerats i deras företagskonto.

**[!UICONTROL Tags]**

* `VIEW_TAGS` - Användare kan göra allt (visa, skapa, redigera, ta bort) på sin [!UICONTROL Tag Containers].

**[!UICONTROL Audience Lab]**

* `MANAGE_SEGMENT_TEST_GROUPS` - Användare kan göra allt (visa, skapa, redigera, ta bort) i sina [!UICONTROL Audience Lab] testgrupper.

**[!UICONTROL Segment]**

* `CREATE_ALL_SEGMENTS` - Användare kan skapa segment.
* `DELETE_ALL_SEGMENTS` - Användare kan ta bort alla segment som har konfigurerats i deras företagskonto.
* `MAP_ALL_TO_DESTINATIONS` - Användare kan mappa alla segment som tillhör deras företag till mål.
* `EDIT_ALL_SEGMENTS` - Användare kan redigera alla segment som har konfigurerats i deras företagskonto.
* `MAP_ALL_SEGMENTS_TO_MODELS` - Användare kan välja segment som baslinje för modeller.
* `VIEW_ALL_SEGMENTS` - Användare kan visa alla segment som har konfigurerats i deras företagskonto.

**[!UICONTROL Signals]**

* `VIEW_ALL_SIGNALS` - Användare kan visa alla signaler som hämtats i [Data Explorer](/help/using/features/data-explorer/data-explorer-overview.md).

## Användningsexempel {#use-cases}

### Övervaka användaråtkomst {#monitoring-user-access}

[!UICONTROL Role-Based Access Control] kan hjälpa dig att övervaka inloggningsstatusen för användare, vilket ger dig en tydlig bild av vem som har åtkomst till din Audience Manager-instans.

Beroende på dina affärskrav kan du aktivera och inaktivera användarkonton efter behov.

![monitor-user-access](assets/monitor-user-access.png)

### Kontrollera åtkomstskydd för känslig [!UICONTROL Data Sources] {#protect-sensitive-data-sources}

Du kan konfigurera [!UICONTROL Role-Based Access Control] på [!UICONTROL trait]-, segment- och [!UICONTROL destination]-nivå för varje användargrupp.

Med den här funktionen kan du hantera hur användarna visar, skapar, läser, skriver och redigerar specifika datauppsättningar och till och med hindra användare från att komma åt datauppsättningar som inte ska vara tillgängliga för dem.

![åtkomstskydd](assets/access-protection.png)
