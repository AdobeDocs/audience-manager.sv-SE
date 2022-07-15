---
description: Information om allmänna krav, autentisering, valfria frågeparametrar, begäran-URL:er och andra referenser.
seo-description: Information about general requirements, authentication, optional query parameters, request URLs, and other references.
seo-title: Getting Started with REST APIs
solution: Audience Manager
title: Kom igång med REST API:er
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
exl-id: f7d5e52d-ad21-4020-a299-d440f954c51a
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1910'
ht-degree: 1%

---

# Komma igång med [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Information om allmänna krav, autentisering, valfria frågeparametrar, begäran [!DNL URLs]och andra referenser.

<!-- c_rest_api_overview.xml -->

## Krav och rekommendationer för API {#api-requirements-recommendations}

Saker du måste och bör göra när du arbetar med [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Observera följande när du arbetar med [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) kod:

* **Begäranparametrar:** Alla begäranparametrar är obligatoriska om inte annat anges.
* **Begäranrubriker**: när [Adobe Developer](https://www.adobe.io/) variabler måste du ange `x-api-key` header. Du kan få dina [!DNL API] genom att följa instruktionerna i [Integrering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) sida.
* **[!DNL JSON]innehållstyp:** Ange `content-type: application/json`  *och*  `accept: application/json` i koden.
* **Förfrågningar och svar:** Skicka begäranden som korrekt formaterade [!DNL JSON] -objekt. [!DNL Audience Manager] svarar med [!DNL JSON] formaterade data. Serversvar kan innehålla begärda data, en statuskod eller båda.
* **Åtkomst:** Dina [!DNL Audience Manager] konsulten ger dig ett klient-ID och en nyckel som gör att du kan [!DNL API] förfrågningar.
* **Exempel på dokumentation och kod:** Text in *kursiv* representerar en variabel som du anger eller skickar in när du skapar eller tar emot [!DNL API] data. Ersätt *kursiv* text med egen kod, egna parametrar eller annan obligatorisk information.

## Autentisering {#authentication}

The [!DNL Audience Manager] [!DNL REST APIs] har stöd för två autentiseringsmetoder.

* [JWT-autentisering (tjänstkonto)](#jwt) använda [Adobe Developer](https://www.adobe.io/). [!DNL Adobe Developer] är Adobe utvecklares ekosystem och community. Den innehåller [API:er för alla Adobe-produkter](https://www.adobe.io/apis.html). Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs].
* [OAuth-autentisering (borttagen)](#oauth). Den här metoden är föråldrad, men kunder med befintlig [!DNL OAuth] integreringar kan fortsätta med den här metoden.

>[!IMPORTANT]
>
>Beroende på din autentiseringsmetod måste du justera din begäran [!DNL URLs] i enlighet med detta. Se [Miljö](#environments) om du vill ha information om värdnamn som du bör använda.

## [!DNL JWT] ([!DNL Service Account]) Autentisering med Adobe Developer {#jwt}

### Adobe Developer - översikt {#adobeio}

[!DNL Adobe Developer] är Adobe utvecklares ekosystem och community. Den innehåller [API:er för alla Adobe-produkter](https://www.adobe.io/apis.html).

Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs].

### Förutsättningar {#prerequisites}

Innan du kan konfigurera [!DNL JWT] verifiering, se till att du har åtkomst till [Adobe Developer Console](https://console.adobe.io/) in [Adobe Developer](https://www.adobe.io/). Kontakta din organisations administratör för åtkomstbegäranden.

### Autentisering {#auth}

Följ stegen nedan för att konfigurera [!DNL JWT (Service Account)] autentisering med [!DNL Adobe Developer]:

1. Logga in på [Adobe Developer Console](https://console.adobe.io/).
1. Följ stegen i [Tjänstkontoanslutning](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Under [Steg 2: Lägg till ett API i projektet med autentisering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)väljer du [!DNL Audience Manager] [!DNL API] alternativ.
1. Testa anslutningen genom att göra din första [!DNL API] samtal baserat på instruktionerna från [Steg 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Konfigurera och arbeta med [!DNL Audience Manager] [!DNL REST APIs] på ett automatiserat sätt kan du generera [!DNL JWT] programmatiskt. Se [JWT-autentisering (tjänstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md) för detaljerade anvisningar.

### RBAC-behörigheter för tekniskt konto

Om ditt Audience Manager-konto använder [Rollbaserad åtkomstkontroll](../../features/administration/administration-overview.md)måste du skapa ett Audience Manager-användarkonto och lägga till det i Audience Manager RBAC-gruppen som ska göra API-anropen.

Följ stegen nedan för att skapa ett tekniskt användarkonto och lägga till det i en RBAC-grupp:

1. Gör en `GET` ring till `https://aam.adobe.io/v1/users/self`. Samtalet skapar ett tekniskt användarkonto som du kan se i [!UICONTROL Admin Console], i [!UICONTROL Users] sida.

   ![tekniskt konto](assets/technical-account.png)

1. Logga in på ditt Audience Manager-konto och [lägg till det tekniska användarkontot](../../features/administration/administration-overview.md#create-group) till den användargrupp som ska göra API-anropen.

## [!DNL OAuth] Autentisering (inaktuellt) {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenautentisering och förnyelse via [!DNL OAuth 2.0] är nu föråldrat.
>
> Använd [JWT-autentisering (tjänstkonto)](#jwt-service-account-authentication-jwt) i stället.

The [!DNL Audience Manager] [!UICONTROL REST API] följer [!DNL OAuth 2.0] standarder för tokenautentisering och förnyelse. I avsnitten nedan beskrivs hur du autentiserar och börjar arbeta med [!DNL API]s.

### Skapa en allmän [!DNL API] Användare {#requirements}

Vi rekommenderar att du skapar ett separat, tekniskt användarkonto för att arbeta med [!DNL Audience Manager] [!DNL API]s. Det här är ett generiskt konto som inte är kopplat till eller kopplat till en viss användare i organisationen. Den här typen av [!DNL API] Med användarkontot kan du uppnå två saker:

* Identifiera vilken tjänst som anropar [!DNL API] (t.ex. samtal från appar som använder våra [!DNL API]eller andra verktyg som [!DNL API] förfrågningar).
* Oavbruten åtkomst till [!DNL API]s. Ett konto som är knutet till en viss person kan tas bort när de lämnar företaget. Detta förhindrar dig från att arbeta med tillgängliga [!DNL API] kod. Ett generiskt konto som inte är kopplat till en viss medarbetare hjälper dig att undvika det här problemet.

Ett exempel eller ett användningsexempel för den här typen av konto är att du vill ändra många segment samtidigt med [Masshanteringsverktyg](../../reference/bulk-management-tools/bulk-management-intro.md). För att göra detta behöver ditt användarkonto [!DNL API] åtkomst. I stället för att lägga till behörigheter till en viss användare skapar du en icke-specifik, [!DNL API] användarkonto som har rätt autentiseringsuppgifter, nyckel och hemlighet att skapa [!DNL API] samtal. Detta är också användbart om du utvecklar egna program som använder [!DNL Audience Manager] [!DNL API]s.

Arbeta med dina [!DNL Audience Manager] konsult för att skapa en allmän [!DNL API]-only användarkonto.

### Lösenordsautentisering {#password-authentication-workflow}

Lösenordsautentisering - säker åtkomst till [!DNL REST API]. Stegen nedan beskriver arbetsflödet för lösenordsautentisering från en [!DNL JSON] i webbläsaren.

>[!TIP]
>
>Kryptera åtkomst- och uppdateringstoken om du lagrar dem i en databas.

#### Steg 1: Begäran [!DNL API] Åtkomst

Kontakta din Partner Solutions Manager. De ger dig en [!DNL API] klient-ID och hemlighet. ID:t och hemligheten autentiserar dig för [!DNL API].

Obs! Om du vill få en uppdateringstoken anger du det när du begär [!DNL API] åtkomst.

#### Steg 2: Begär token

Skicka en tokenbegäran med din egen inställning [!DNL JSON] klient. När du skapar begäran:

* Använd en `POST` metod att anropa `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Inloggningsuppgifterna `testId : testSecret` konvertera till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka in [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded` . Sidhuvudet kan till exempel se ut så här: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Ställ in begärandetexten enligt följande:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Steg 3: Ta emot token

The [!DNL JSON] -svaret innehåller din åtkomsttoken. Svaret bör se ut så här:

```json
{
    "access_token": "28fed402-eafd-456c-9341-ac753f25bbbc",
    "token_type": "bearer",
    "refresh_token": "b27122c0-b0c7-4b39-a71b-1547a3b3b88e",
    "expires_in": 21922,
    "scope": "read write"
}
```

The `expires_in` representerar antalet sekunder tills åtkomsttoken upphör att gälla. Som bästa praxis bör du använda korta förfallotider för att begränsa exponeringen om token någonsin exponeras.

### Uppdatera token {#refresh-token}

Uppdatera förnyelse av tokens [!DNL API] åtkomst när den ursprungliga token har upphört att gälla. Om det efterfrågas kan svaret [!DNL JSON] i lösenordsarbetsflödet innehåller en uppdateringstoken. Om du inte får någon uppdateringstoken skapar du en ny under lösenordsautentiseringsprocessen.

Du kan också använda en uppdateringstoken för att generera en ny token innan den befintliga åtkomsttoken upphör att gälla.

Om din åtkomsttoken har gått ut får du en `401 Status Code` och följande rubrik i svaret:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

Följande steg beskriver arbetsflödet för att använda en uppdateringstoken för att skapa en ny åtkomsttoken från en [!DNL JSON] i webbläsaren.

#### Steg 1: Begär ny token

Skicka en begäran om en uppdateringstoken till dig [!DNL JSON] klient. När du skapar begäran:

* Använd en `POST` metod att anropa `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Inloggningsuppgifterna `testId : testSecret` konvertera till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka in HTTP-rubriker `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded`. Sidhuvudet kan till exempel se ut så här: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* I begärandetexten anger du `grant_type:refresh_token` och skicka den uppdateringstoken som du fick i din tidigare åtkomstbegäran. Begäran ska se ut så här: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Steg 2: Ta emot den nya token

The [!DNL JSON] -svaret innehåller din nya åtkomsttoken. Svaret bör se ut så här:

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

The [!DNL Audience Manager] [!UICONTROL REST API] stöder auktoriseringskod och implicit autentisering. Om du vill använda dessa åtkomstmetoder måste användarna logga in på `https://api.demdex.com/oauth/authorize` för att få åtkomst till och uppdatera tokens.

## Gör autentiserad [!DNL API] Begäranden {#authenticated-api-requests}

Anropskrav [!DNL API] metoder när du har fått en autentiseringstoken.

Göra anrop mot tillgängliga [!DNL API] metoder:

* I `HTTP` rubrik, ange `Authorization: Bearer <token>`.
* När du använder [JWT-autentisering (tjänstkonto)](#jwt)måste du ange `x-api-key` -huvud, som blir densamma som `client_id`. Du kan få dina `client_id` från [Integrering med Adobe Developer](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) sida.
* Ring upp [!DNL API] -metod.

## Valfritt [!DNL API] Frågeparametrar {#optional-api-query-parameters}

Ange de valfria parametrar som är tillgängliga för metoder som returnerar alla egenskaper för ett objekt.

Du kan använda de här valfria parametrarna med [!DNL API] metoder som returnerar *alla* egenskaper för ett objekt. Ange dessa alternativ i begärandesträngen när frågan skickas till [!DNL API].

| Parameter | Beskrivning |
|--- |--- |
| `page` | Returnerar resultat per sidnummer. Numreringen börjar vid 0. |
| `pageSize` | Anger antalet svarsresultat som returneras av begäran (10 är standard). |
| `sortBy` | Sorterar och returnerar resultat enligt angivet [!DNL JSON] -egenskap. |
| `descending` | Sorterar och returnerar resultat i fallande ordning. `ascending` är standard. |
| `search` | Returnerar resultat baserat på den angivna strängen som du vill använda som sökparameter. Anta att du vill hitta resultat för alla modeller som har ordet &quot;Test&quot; i något av värdefälten för det objektet. Din exempelbegäran kan se ut så här:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Du kan söka efter alla värden som returneras av en[!DNL get all]&quot;. |
| `folderId` | Returnerar alla ID:n för [!UICONTROL traits] inuti den angivna mappen. Inte tillgängligt för alla metoder. |
| `permissions` | Returnerar en lista med segment baserat på den angivna behörigheten. `READ` är standard. Behörigheterna är:<ul><li>`READ` : Returnera och visa information om ett segment.</li><li>`WRITE` : Använd  `PUT`  för att uppdatera ett segment.</li><li>`CREATE` : Använd  `POST`  för att skapa ett segment.</li><li>`DELETE` : Ta bort ett segment. Kräver åtkomst till eventuella underliggande egenskaper. Du måste till exempel ha behörighet att ta bort de egenskaper som tillhör ett segment om du vill ta bort det.</li></ul><br>Ange flera behörigheter med separata nyckelvärdepar. Om du till exempel vill returnera en lista med segment med  `READ`  och  `WRITE`  endast behörigheter, skicka in  `"permissions":"READ"`, `"permissions":"WRITE"` . |
| `includePermissions` | ([!DNL Boolean]) Ange som `true` för att returnera dina behörigheter för segmentet. Standard är `false`. |

### En anteckning om sidalternativ

När sidinformation *är inte* anges returnerar begäran normal [!DNL JSON] resulterar i en array. Om sidinformation *är* anges, radbryts den returnerade listan i en [!DNL JSON] objekt som innehåller information om det totala resultatet och den aktuella sidan. Din exempelbegäran med sidalternativ kan se ut ungefär så här:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] för förfrågningar, staging- och produktionsmiljöer samt versioner.

## Begäran [!DNL URLs] {#request-urls}

I följande tabell visas begäran [!DNL URLs] används för att skicka in [!DNL API] begäranden, per metod.

Beroende på vilken autentiseringsmetod du använder måste du justera din begäran [!DNL URLs] enligt tabellerna nedan.

### Begäran [!DNL URLs] for [!DNL JWT] Autentisering {#request-urls-jwt}

| [!DNL API] Metoder | Begäran [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://aam.adobe.io/v1/models/` |
| [!DNL Data Source] | `https://aam.adobe.io/v1/datasources/` |
| [!DNL Derived Signals] | `https://aam.adobe.io/v1/signals/derived/` |
| [!DNL Destinations] | `https://aam.adobe.io/v1/destinations/` |
| [!DNL Domains] | `https://aam.adobe.io/v1/partner-sites/` |
| [!DNL Folders] | Traits:  `https://aam.adobe.io/v1/folders/traits /`<br>Segment:  `https://aam.adobe.io/v1/folders/segments /` |
| [!DNL Schema] | `https://aam.adobe.io/v1/schemas/` |
| [!DNL Segments] | `https://aam.adobe.io/v1/segments/` |
| [!DNL Traits] | `https://aam.adobe.io/v1/traits/` |
| [!DNL Trait Types] | `https://aam.adobe.io/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://aam.adobe.io/v1/taxonomies/0/` |

### Begäran [!DNL URLs] for [!DNL OAuth] Autentisering (inaktuellt) {#request-urls-oauth}

| [!DNL API] Metoder | Begäran [!DNL URL] |
|--- |--- |
| [!DNL Algorithmic Modeling] | `https://api.demdex.com/v1/models/` |
| [!DNL Data Source] | `https://api.demdex.com/v1/datasources/` |
| [!DNL Derived Signals] | `https://api.demdex.com/v1/signals/derived/` |
| [!DNL Destinations] | `https://api.demdex.com/v1/destinations/` |
| [!DNL Domains] | `https://api.demdex.com/v1/partner-sites/` |
| [!DNL Folders] | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segment:  `https://api.demdex.com/v1/folders/segments /` |
| [!DNL Schema] | `https://api.demdex.com/v1/schemas/` |
| [!DNL Segments] | `https://api.demdex.com/v1/segments/` |
| [!DNL Traits] | `https://api.demdex.com/v1/traits/` |
| [!DNL Trait Types] | `https://api.demdex.com/v1/customer-trait-types` |
| [!DNL Taxonomy] | `https://api.demdex.com/v1/taxonomies/0/` |

## Miljö {#environments}

The [!DNL Audience Manager] [!DNL API]s ger åtkomst till olika arbetsmiljöer. Dessa miljöer hjälper dig att testa kod mot separata databaser utan att påverka livedata. I följande tabell visas de tillgängliga [!DNL API] miljöer och motsvarande resursvärdnamn.

Beroende på vilken autentiseringsmetod du använder måste du justera miljön [!DNL URLs] enligt tabellen nedan.

| Miljö | Värdnamn för [!DNL JWT] autentisering | Värdnamn för [!DNL OAuth] autentisering |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>The [!DNL Audience Manager] betamiljö är en mindre, fristående version av produktionsmiljön. Alla data som du vill testa måste anges och samlas in i den här miljön.

## Versioner {#versions}

Nya versioner av dessa [!DNL API]s släpps regelbundet. En ny release ökar [!DNL API] versionsnummer. Versionsnumret refereras i begäran [!DNL URL] as `v<version number>` som i följande exempel:

`https://<host>/v1/...`

## Definierade svarskoder {#response-codes-defined}

`HTTP` statuskoder och svarstext som returneras av [!DNL Audience Manager] [!UICONTROL REST API].

| Svarskod-ID | Svarstext | Definition |
|---|---|---|
| `200` | `OK` | Begäran har bearbetats. Returnerar förväntat innehåll eller data om det behövs. |
| `201` | `Created` | Resursen skapades. Returnerar för `PUT` och `POST` förfrågningar. |
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
>* [OAuth 2 - förenklad](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

