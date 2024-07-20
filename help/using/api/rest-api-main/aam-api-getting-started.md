---
description: Information om allmänna krav, autentisering, valfria frågeparametrar, URL:er för förfrågningar och andra referenser.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Kom igång med REST API:er
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 622664170f2a76039bcf2333bde43ce9e60b6af2
workflow-type: tm+mt
source-wordcount: '2558'
ht-degree: 0%

---

# Komma igång med [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Information om allmänna krav, autentisering, valfria frågeparametrar, begäran [!DNL URLs] och andra referenser.

## API-krav och Recommendations {#api-requirements-recommendations}

Observera följande när du arbetar med [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) -kod:

* **Begäranparametrar:** alla begäranparametrar är obligatoriska om inte annat anges.
* **Begäranrubriker**: När du använder [Adobe Developer](https://www.adobe.io/)-tokens måste du ange `x-api-key`-rubriken. Du kan hämta nyckeln [!DNL API] genom att följa instruktionerna på sidan [Integrering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]innehållstyp:** Ange `content-type: application/json` *och* `accept: application/json` i koden.
* **Begäranden och svar:** Skicka begäranden som ett korrekt formaterat [!DNL JSON] -objekt. [!DNL Audience Manager] svarar med [!DNL JSON] formaterade data. Serversvar kan innehålla begärda data, en statuskod eller båda.
* **Åtkomst:** Din [!DNL Audience Manager]-konsult kommer att förse dig med ett klient-ID och en nyckel som gör att du kan göra [!DNL API] förfrågningar.
* **Dokumentation och kodexempel:** Text i *kursiv* representerar en variabel som du anger eller skickar in när du skapar eller tar emot [!DNL API]-data. Ersätt *kursiv*-text med din egen kod, parametrar eller annan obligatorisk information.

## Autentisering {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] har stöd för tre autentiseringsmetoder.

* [!BADGE Rekommenderas]{type=positive}[OAuth Server-till-Server-autentisering](#oauth-adobe-developer) med [Adobe-utvecklarkonsolen](https://www.adobe.io/). [!DNL Adobe Developer] är Adobe utvecklares ekosystem och community. Den innehåller [API:er för alla Adobe-produkter](https://developer.adobe.com/apis/). Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs]. Läs mer om [OAuth Server-till-Server-autentisering](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/) i utvecklardokumentationen för Adobe.
* [!BADGE Föråldrat]{type=negative}[JWT-autentisering (tjänstkonto)](#jwt) med [Adobe-utvecklarkonsolen](https://www.adobe.io/). [!DNL Adobe Developer] är Adobe utvecklares ekosystem och community. Den innehåller [API:er för alla Adobe-produkter](https://developer.adobe.com/apis/).
* [!BADGE Föråldrat]{type=negative}[Äldre OAuth-autentisering](#oauth-deprecated). Den här metoden är föråldrad, men kunder med befintliga [!DNL OAuth]-integreringar kan fortsätta använda den här metoden.

>[!IMPORTANT]
>
>Beroende på din autentiseringsmetod måste du justera din begäran [!DNL URLs] därefter. I avsnittet [Miljö](#environments) finns mer information om värdnamnen som du bör använda.

## OAuth Server-till-Server-autentisering med Adobe Developer {#oauth-adobe-developer}

I det här avsnittet beskrivs hur du samlar in de inloggningsuppgifter som krävs för att autentisera Audience Manager API-anrop, vilket beskrivs i nedanstående flödesschema. Du kan samla de flesta nödvändiga autentiseringsuppgifter i den första engångsinställningen. Åtkomsttoken måste dock uppdateras var 24:e timme.

![Audience Manager autentiseringsflödesdiagram.](/help/using/api/rest-api-main/assets/aam-authentication-flow.png)

### Adobe Developer - översikt {#developer-overview}

[!DNL Adobe Developer] är Adobe utvecklares ekosystem och community. Den innehåller [API:er för alla Adobe-produkter](https://developer.adobe.com/apis).

Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs].

### Förutsättningar {#prerequisites-server-to-server}

Innan du kan konfigurera [!DNL OAuth Server-to-Server]-autentisering måste du kontrollera att du har åtkomst till [Adobe Developer Console](https://developer.adobe.com/console/home) i [Adobe Developer](https://developer.adobe.com/). Kontakta din organisations administratör för åtkomstbegäranden.

### Autentisering {#oauth}

Följ stegen nedan för att konfigurera [!DNL OAuth Server-to-Server]-autentisering med [!DNL Adobe Developer]:

1. Logga in på [Adobe Developer Console](https://developer.adobe.com/console/home).
1. Följ stegen i implementeringsguiden för autentiseringsuppgifter för [OAuth Server-till-server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/).
   * Under [Steg 2: Lägg till ett API i projektet med autentisering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), välj alternativet [!DNL Audience Manager] [!DNL API] .
1. Prova anslutningen genom att ringa ditt första [!DNL API]-samtal baserat på instruktionerna från [Steg 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Om du vill konfigurera och arbeta med [!DNL Audience Manager] [!DNL REST APIs] automatiskt kan du rotera klienthemligheter programmatiskt. Mer information finns i [utvecklardokumentationen](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#rotating-client-secrets-programmatically).

### Lägga till Audience Manager API i ett projekt {#add-aam-api-to-project}

Gå till [Adobe Developer Console](https://www.adobe.com/go/devs_console_ui) och logga in med din Adobe ID. Följ sedan stegen som beskrivs i självstudiekursen om att [skapa ett tomt projekt](https://developer.adobe.com/developer-console/docs/guides/projects/projects-empty/) i Adobe Developer Console-dokumentationen.

När du har skapat ett nytt projekt väljer du **[!UICONTROL Add API]** på skärmen **[!UICONTROL Project Overview]**.

>[!TIP]
>
>Om du har etablerat dig för flera organisationer använder du organisationsväljaren i det övre högra hörnet av gränssnittet för att kontrollera att du är i den organisation du behöver.

![Developer Console-skärmen med alternativet Lägg till API markerat.](/help/using/api/rest-api-main/assets/add-api.png)

Skärmen **[!UICONTROL Add an API]** visas. Markera produktikonen för Adobe Experience Cloud och välj sedan **[!UICONTROL Audience Manager API]** innan du väljer **[!UICONTROL Next]**.

![Välj Audience Manager-API.](/help/using/api/rest-api-main/assets/audience-manager-api.png)

>[!TIP]
>
>Välj alternativet **[!UICONTROL View docs]** om du vill navigera i ett separat webbläsarfönster till den fullständiga [Audience Manager API-referensdokumentationen](https://bank.demdex.com/portal/swagger/index.html#).

### Välj autentiseringstypen OAuth Server-till-server {#select-oauth-server-to-server}

Välj sedan autentiseringstypen för att generera åtkomsttoken och få åtkomst till Audience Manager-API:t.

>[!IMPORTANT]
>
>Välj metoden **[!UICONTROL OAuth Server-to-Server]** eftersom det här är den enda metod som stöds för att gå framåt. Metoden **[!UICONTROL Service Account (JWT)]** är föråldrad. Även om integreringar med JWT-autentiseringsmetoden fortsätter att fungera fram till 1 januari 2025 rekommenderar Adobe starkt att du migrerar befintliga integreringar till den nya OAuth Server-till-Server-metoden före detta datum.

![Välj OAuth-autentiseringsmetod.](/help/using/api/rest-api-main/assets/select-oauth-authentication-method.png)

### Välj produktprofiler för integreringen {#select-product-profiles}

Välj produktprofiler på skärmen **[!UICONTROL Configure API]**. Integreringens tjänstkonto får tillgång till detaljerade funktioner via de produktprofiler som väljs här.

![Välj produktprofiler för din integrering.](/help/using/api/rest-api-main/assets/select-product-profiles.png)

Välj **[!UICONTROL Save configured API]** när du är klar.

### Samla in inloggningsuppgifter {#gather-credentials}

När API:t har lagts till i projektet visar **[!UICONTROL Audience Manager API]**-sidan för projektet följande autentiseringsuppgifter som krävs i alla anrop till API:er för Audience Manager:

![Integreringsinformation när du har lagt till ett API i Developer Console.](/help/using/api/rest-api-main/assets/api-integration-information.png)

* `{API_KEY}` ([!UICONTROL Client ID])
* `{ORG_ID}` ([!UICONTROL Organization ID])

## Generera en åtkomsttoken {#generate-access-token}

Nästa steg är att generera en `{ACCESS_TOKEN}`-autentiseringsuppgift som kan användas i API-anrop från Audience Manager. Till skillnad från värdena för `{API_KEY}` och `{ORG_ID}` måste en ny token genereras var 24:e timme för att du ska kunna fortsätta använda Audience Manager API:er. Välj **[!UICONTROL Generate access token]** enligt nedan.

![Visa hur du genererar åtkomsttoken](/help/using/api/rest-api-main/assets/generate-acces-token.gif)

## Testa ett API-anrop {#test-api-call}

När du har hämtat din token för autentisering av innehavare utför du ett API-anrop för att testa att du nu kan komma åt API:er för Audience Manager.

1. Navigera till [API-referensdokumentationen](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_).
2. Välj **[!UICONTROL Authorize]** och klistra in åtkomsttoken som du fick i steget [Generera åtkomsttoken](#generate-access-token).

   ![Auktorisera API-anrop](/help/using/api/rest-api-main/assets/authorize-api-calls.gif)

3. Utför ett GET-anrop till API-slutpunkten `/datasources` för att hämta en lista över alla globalt tillgängliga datakällor, vilket anges i [API-referensdokumentationen](https://bank.demdex.com/portal/swagger/index.html#/Data%20Source%20API/get_datasources_). Välj **[!UICONTROL Try it out]**, följt av **[!UICONTROL Execute]**, så som visas nedan.

   ![Utför API-anrop](/help/using/api/rest-api-main/assets/perform-api-calls.gif)


>[!BEGINSHADEBOX]

>[!BEGINTABS]

>[!TAB API-begäran]

```shell
curl -X 'GET' \
  'https://api.demdex.com/v1/datasources/' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer your-access-token'
```


>[!TAB API-svar om rätt innehavartoken används]


När du använder en arbetsåtkomsttoken returnerar API-slutpunkten ett 200-svar tillsammans med ett svarstext som innehåller alla globala datakällor som din organisation har tillgång till.

```json
[
  {
    "pid": 1794,
    "name": "testdatasource1",
    "description": "Test data source",
    "status": "ACTIVE",
    "integrationCode": "test_ds1",
    "dataExportRestrictions": [],
    "updateTime": 1595340792000,
    "crUID": 0,
    "upUID": 15910,
    "linkNamespace": false,
    "type": "GENERAL",
    "subIdType": "CROSS_DEVICE_PERSON",
    "inboundS2S": true,
    "outboundS2S": true,
    "useAudienceManagerVisitorID": false,
    "allowDataSharing": true,
    "masterDataSourceIdProvider": true,
    "uniqueTraitIntegrationCodes": false,
    "uniqueSegmentIntegrationCodes": false,
    "marketingCloudVisitorIdVersion": 0,
    "idType": "CROSS_DEVICE",
    "samplingEndTime": 1596550392825,
    "allowDeviceGraphSharing": false,
    "supportsAuthenticatedProfile": true,
    "deviceGraph": false,
    "authenticatedProfileName": "testdatasource1",
    "deviceGraphName": "",
    "customNamespaceId": 29769,
    "customNamespaceCode": "silviu_ds1",
    "customerProfileDataRetention": 62208000,
    "samplingStartTime": 1595340792825,
    "dataSourceId": 29769,
    "containerIds": [],
    "samplingEnabled": false
  },
  {
    "pid": 1794,
    "name": "AAM Test Company Audiences",
    "description": "Automatically generated trait data source",
    "status": "ACTIVE",
    "integrationCode": "adobe-provided",
    "dataExportRestrictions": [
      "PII"
    ],

    [...]
```

>[!ENDTABS]

>[!ENDSHADEBOX]

## [!BADGE Föråldrat]{type=negative}[!DNL JWT] ([!DNL Service Account]) Autentisering med Adobe Developer {#jwt}

+++ Visa information om den borttagna [!DNL JWT] ([!DNL Service Account])-metoden för att hämta autentiseringstoken.

### Adobe Developer - översikt {#adobeio}

[!DNL Adobe Developer] är Adobe utvecklares ekosystem och community. Den innehåller [API:er för alla Adobe-produkter](https://www.adobe.io/apis.html).

Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs].

### Förutsättningar {#prerequisites}

Innan du kan konfigurera [!DNL JWT]-autentisering måste du kontrollera att du har åtkomst till [Adobe Developer Console](https://console.adobe.io/) i [Adobe Developer](https://www.adobe.io/). Kontakta din organisations administratör för åtkomstbegäranden.

### Autentisering {#auth}

Följ stegen nedan för att konfigurera [!DNL JWT (Service Account)]-autentisering med [!DNL Adobe Developer]:

1. Logga in på [Adobe Developer Console](https://console.adobe.io/).
1. Följ stegen i [Anslutning till tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Under [Steg 2: Lägg till ett API i projektet med autentisering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md), välj alternativet [!DNL Audience Manager] [!DNL API] .
1. Prova anslutningen genom att ringa ditt första [!DNL API]-samtal baserat på instruktionerna från [Steg 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Om du vill konfigurera och arbeta med [!DNL Audience Manager] [!DNL REST APIs] automatiskt kan du generera [!DNL JWT] programmatiskt. Mer information finns i [JWT-autentisering (tjänstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md).

### RBAC-behörigheter för tekniskt konto

Om ditt Audience Manager-konto använder [rollbaserad åtkomstkontroll](../../features/administration/administration-overview.md) måste du skapa ett Audience Manager-tekniskt användarkonto och lägga till det i Audience Manager RBAC-gruppen som gör API-anropen.

Följ stegen nedan för att skapa ett tekniskt användarkonto och lägga till det i en RBAC-grupp:

1. Ring `GET` till `https://aam.adobe.io/v1/users/self`. Anropet skapar ett tekniskt användarkonto som du kan se på sidan [!UICONTROL Admin Console] på sidan [!UICONTROL Users].

   ![tekniskt konto](assets/technical-account.png)

1. Logga in på ditt Audience Manager-konto och [lägg till det tekniska användarkontot](../../features/administration/administration-overview.md#create-group) i användargruppen som ska göra API-anropen.

+++

## [!BADGE Föråldrat]{type=negative}[!DNL OAuth]-autentisering (inaktuell) {#oauth-deprecated}

+++ Visa information om den inaktuella, gamla autentiseringsmetoden [!DNL OAuth] för att hämta autentiseringstoken.

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenautentisering och förnyelse via [!DNL OAuth 2.0] är nu föråldrat.
>
> Använd [JWT-autentisering (tjänstkonto)](#jwt-service-account-authentication-jwt) i stället.

[!DNL Audience Manager] [!UICONTROL REST API] följer [!DNL OAuth 2.0] standarder för tokenautentisering och förnyelse. I avsnitten nedan beskrivs hur du autentiserar och börjar arbeta med [!DNL API].

### Skapa en allmän [!DNL API]-användare {#requirements}

Vi rekommenderar att du skapar ett separat, tekniskt användarkonto för att arbeta med [!DNL Audience Manager] [!DNL API]s. Det här är ett generiskt konto som inte är kopplat till eller kopplat till en viss användare i organisationen. Den här typen av [!DNL API]-användarkonto hjälper dig att uppnå två saker:

* Identifiera vilken tjänst som anropar [!DNL API] (t.ex. samtal från dina appar som använder våra [!DNL API] eller från andra verktyg som gör [!DNL API]-förfrågningar).
* Ge oavbruten åtkomst till [!DNL API]. Ett konto som är knutet till en viss person kan tas bort när de lämnar företaget. Detta förhindrar dig från att arbeta med tillgänglig [!DNL API]-kod. Ett generiskt konto som inte är kopplat till en viss medarbetare hjälper dig att undvika det här problemet.

Ett exempel eller ett användningsfall för den här typen av konto är att du vill ändra många segment samtidigt med [grupphanteringsverktygen](../../reference/bulk-management-tools/bulk-management-intro.md). För att göra detta behöver ditt användarkonto [!DNL API] åtkomst. I stället för att lägga till behörigheter till en viss användare skapar du ett icke-specifikt [!DNL API]-användarkonto som har rätt autentiseringsuppgifter, nyckel och hemlighet för att ringa [!DNL API]-anrop. Detta är också användbart om du utvecklar egna program som använder [!DNL Audience Manager] [!DNL API]s.

Arbeta med din [!DNL Audience Manager]-konsult för att konfigurera ett generiskt, [!DNL API]-skyddat användarkonto.

### Lösenordsautentisering {#password-authentication-workflow}

Lösenordsautentisering ger säker åtkomst till [!DNL REST API]. Stegen nedan visar arbetsflödet för lösenordsautentisering från en [!DNL JSON]-klient i webbläsaren.

>[!TIP]
>
>Kryptera åtkomst- och uppdateringstoken om du lagrar dem i en databas.

#### Steg 1: Begär [!DNL API] åtkomst

Kontakta din Partner Solutions Manager. De ger dig ett [!DNL API] klient-ID och en hemlighet. ID:t och hemligheten autentiserar dig för [!DNL API].

Obs! Om du vill få en uppdateringstoken anger du det när du begär åtkomst till [!DNL API].

#### Steg 2: Begär token

Skicka en tokenbegäran med den önskade [!DNL JSON]-klienten. När du skapar begäran:

* Använd metoden `POST` för att anropa `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Autentiseringsuppgifterna `testId : testSecret` konverteras till exempel till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka in [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded` . Din rubrik kan till exempel se ut så här: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Ställ in begärandetexten enligt följande:
  <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Steg 3: Ta emot token

Svaret [!DNL JSON] innehåller din åtkomsttoken. Svaret bör se ut så här:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

Nyckeln `expires_in` representerar antalet sekunder tills åtkomsttoken upphör att gälla. Som bästa praxis bör du använda korta förfallotider för att begränsa exponeringen om token någonsin exponeras.

### Uppdatera token {#refresh-token}

Uppdatera tokens förnya [!DNL API]-åtkomsten när den ursprungliga token har upphört att gälla. Om det efterfrågas innehåller svaret [!DNL JSON] i lösenordsarbetsflödet en uppdateringstoken. Om du inte får någon uppdateringstoken skapar du en ny under lösenordsautentiseringsprocessen.

Du kan också använda en uppdateringstoken för att generera en ny token innan den befintliga åtkomsttoken upphör att gälla.

Om din åtkomsttoken har upphört att gälla får du ett `401 Status Code` och följande rubrik i svaret:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I följande steg beskrivs arbetsflödet för att använda en uppdateringstoken för att skapa en ny åtkomsttoken från en [!DNL JSON]-klient i webbläsaren.

#### Steg 1: Begär ny token

Skicka en begäran om uppdateringstoken med den önskade [!DNL JSON]-klienten. När du skapar begäran:

* Använd metoden `POST` för att anropa `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Autentiseringsuppgifterna `testId : testSecret` konverteras till exempel till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka HTTP-rubrikerna `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded`. Din rubrik kan till exempel se ut så här: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Ange `grant_type:refresh_token` i begärandetexten och skicka den uppdateringstoken som du fick i din tidigare åtkomstbegäran. Begäran ska se ut så här: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Steg 2: Ta emot den nya token

Svaret [!DNL JSON] innehåller din nya åtkomsttoken. Svaret bör se ut så här:

```json
{
    "access_token": "4fdfc261-2ffc-4fb7-8dbd-64221714c45f",
    "token_type": "bearer",
    "refresh_token": "295fa487-1825-4caa-a715-80b81ac17dae",
    "expires_in": 21922,
    "scope": "read write"
}
```

### Auktoriseringskod och implicit autentisering {#authentication-code-implicit}

[!DNL Audience Manager] [!UICONTROL REST API] stöder auktoriseringskod och implicit autentisering. Om du vill använda de här åtkomstmetoderna måste dina användare logga in på `https://api.demdex.com/oauth/authorize` för att få tillgång till och uppdatera tokens.

+++

## Gör autentiserade [!DNL API] förfrågningar {#authenticated-api-requests}

Krav för att anropa [!DNL API]-metoder när du har tagit emot en autentiseringstoken.

Så här anropar du mot de tillgängliga [!DNL API]-metoderna:

* Ange `Authorization: Bearer <token>` i rubriken `HTTP`.
* När du använder [JWT-autentisering (tjänstkonto)](#jwt) måste du ange rubriken `x-api-key` som är densamma som din `client_id`. Du kan hämta `client_id` från [Adobe Developer-integreringssidan](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Anropa den obligatoriska [!DNL API]-metoden.

## Valfria [!DNL API]-frågeparametrar {#optional-api-query-parameters}

Ange de valfria parametrar som är tillgängliga för metoder som returnerar alla egenskaper för ett objekt.

Du kan använda de här valfria parametrarna med [!DNL API]-metoder som returnerar *all* -egenskaper för ett objekt. Ange dessa alternativ i begärandesträngen när du skickar frågan till [!DNL API].

| Parameter | Beskrivning |
|--- |--- |
| `page` | Returnerar resultat per sidnummer. Numreringen börjar vid 0. |
| `pageSize` | Anger antalet svarsresultat som returneras av begäran (10 är standard). |
| `sortBy` | Sorterar och returnerar resultat enligt den angivna [!DNL JSON]-egenskapen. |
| `descending` | Sorterar och returnerar resultat i fallande ordning. `ascending` är standard. |
| `search` | Returnerar resultat baserat på den angivna strängen som du vill använda som sökparameter. Anta att du vill hitta resultat för alla modeller som har ordet &quot;Test&quot; i något av värdefälten för det objektet. Din exempelbegäran kan se ut så här:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Du kan söka efter alla värden som returneras av en [!DNL get all]-metod. |
| `folderId` | Returnerar alla ID:n för [!UICONTROL traits] i den angivna mappen. Inte tillgängligt för alla metoder. |
| `permissions` | Returnerar en lista med segment baserat på den angivna behörigheten. `READ` är standard. Behörigheterna är:<ul><li>`READ` : Returnera och visa information om ett segment.</li><li>`WRITE` : Använd `PUT` för att uppdatera ett segment.</li><li>`CREATE` : Använd `POST` för att skapa ett segment.</li><li>`DELETE`: Ta bort ett segment. Kräver åtkomst till eventuella underliggande egenskaper. Du måste till exempel ha behörighet att ta bort de egenskaper som tillhör ett segment om du vill ta bort det.</li></ul><br>Ange flera behörigheter med separata nyckelvärdepar. Om du till exempel vill returnera en lista med segment med endast `READ` och `WRITE` behörigheter skickar du in `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Ange `true` om du vill returnera dina behörigheter för segmentet. Standardvärdet är `false`. |

{style="table-layout:auto"}

### En anteckning om sidalternativ

När sidinformationen *inte är* angiven returnerar begäran [!DNL JSON] som resultat i en matris. Om sidinformationen *anges* kapslas den returnerade listan in i ett [!DNL JSON]-objekt som innehåller information om det totala resultatet och den aktuella sidan. Din exempelbegäran med sidalternativ kan se ut ungefär så här:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] för begäranden, mellanlagrings- och produktionsmiljöer samt versioner.

## Begäran [!DNL URLs] {#request-urls}

I följande tabell visas begäran [!DNL URLs] som används för att skicka [!DNL API]-begäranden per metod.

Beroende på vilken autentiseringsmetod du använder måste du justera din begäran [!DNL URLs] enligt tabellerna nedan.

### Begär [!DNL URLs] för [!BADGE Rekommenderad]{type=positive}[!BADGE Föråldrat]{type=negative}Autentisering av [!DNL JWT] via Adobe Developer {#request-urls-jwt}

| [!DNL API]-metoder | Begäran [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Traits: `https://aam.adobe.io/v1/folders/traits /`<br>Segments: `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

{style="table-layout:auto"}

### Begär [!DNL URLs] för [!BADGE borttagen]{type=negative}Autentisering av [!DNL OAuth] {#request-urls-oauth}

| [!DNL API]-metoder | Begäran [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Traits: `https://api.demdex.com/v1/folders/traits /`<br>Segments: `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

{style="table-layout:auto"}

## Miljö {#environments}

[!DNL Audience Manager] [!DNL API] ger åtkomst till olika arbetsmiljöer. Dessa miljöer hjälper dig att testa kod mot separata databaser utan att påverka livedata i produktionen. I följande tabell visas tillgängliga [!DNL API]-miljöer och motsvarande resursvärdnamn.

Beroende på vilken autentiseringsmetod du använder måste du justera miljön [!DNL URLs] enligt tabellen nedan.

| Miljö | Värdnamn för [!DNL JWT]-autentisering | Värdnamn för [!DNL OAuth]-autentisering |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Betamiljön [!DNL Audience Manager] är en mindre, fristående version av produktionsmiljön. Alla data som du vill testa måste anges och samlas in i den här miljön.

## Versioner {#versions}

Nya versioner av dessa [!DNL API] släpps regelbundet. En ny version ökar versionsnumret för [!DNL API]. Versionsnumret refereras i begäran [!DNL URL] som `v<version number>`, vilket visas i följande exempel:

`https://<host>/v1/...`

## Definierade svarskoder {#response-codes-defined}

`HTTP` statuskoder och svarstext som returneras av [!DNL Audience Manager] [!UICONTROL REST API].

| Svarskod-ID | Svarstext | Definition |
|---|---|---|
| `200` | `OK` | Begäran har bearbetats. Returnerar förväntat innehåll eller data om det behövs. |
| `201` | `Created` | Resursen skapades. Returnerar för `PUT`- och `POST`-begäranden. |
| `204` | `No Content` | Resursen har tagits bort. Svarstexten är tom. |
| `400` | `Bad Request` | Servern förstod inte begäran. Vanligtvis på grund av felaktig syntax. Kontrollera din begäran och försök igen. |
| `403` | `Forbidden` | Du har inte åtkomst till resursen. |
| `404` | `Not Found` | Det gick inte att hitta resursen för den angivna sökvägen. |
| `409` | `Conflict` | Begäran kunde inte slutföras på grund av en konflikt med resursens tillstånd. |
| `500` | `Server Error` | Servern påträffade ett oväntat fel som gjorde att den inte kunde utföra begäran. |

>[!MORELIKETHIS]
>
>* [JWT-autentisering (tjänstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
>* [OAuth-autentisering](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 Simplified](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)
