---
description: Information om allmänna krav, autentisering, valfria frågeparametrar, begäran-URL:er och andra referenser.
seo-description: Information om allmänna krav, autentisering, valfria frågeparametrar, begäran-URL:er och andra referenser.
seo-title: Kom igång med REST API:er
solution: Audience Manager
title: Kom igång med REST API:er
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
feature: API
translation-type: tm+mt
source-git-commit: ab8745a8ba24154793201893a39a039b5a098833
workflow-type: tm+mt
source-wordcount: '1860'
ht-degree: 2%

---


# Komma igång med [!DNL REST] [!DNL APIs] {#getting-started-with-rest-apis}

Information om allmänna krav, autentisering, valfria frågeparametrar, begäran [!DNL URLs] och andra referenser.

<!-- c_rest_api_overview.xml -->

## Krav och rekommendationer för API {#api-requirements-recommendations}

Saker som du måste och bör göra när du arbetar med [!DNL Audience Manager] [!DNL API]s.

<!-- aam-api-requirements.xml -->

Observera följande när du arbetar med [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/)-kod:

* **Begäranparametrar:** alla begäranparametrar är obligatoriska om inget annat anges.
* **Begäranrubriker**: När du använder  [Adobe I/](https://www.adobe.io/) Otokens måste du ange  `x-api-key` rubriken. Du kan hämta din [!DNL API]-nyckel genom att följa instruktionerna på sidan [Tjänstkontointegrering](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* **[!DNL JSON]innehållstyp:** Ange  `content-type: application/json`  **  `accept: application/json` och i koden.
* **Förfrågningar och svar:** Skicka förfrågningar som ett korrekt formaterat  [!DNL JSON] objekt. [!DNL Audience Manager] svarar med  [!DNL JSON] formaterade data. Serversvar kan innehålla begärda data, en statuskod eller båda.
* **Åtkomst:** Din  [!DNL Audience Manager] konsult ger dig ett klient-ID och en nyckel som gör att du kan göra  [!DNL API] förfrågningar.
* **Dokumentation och kodexempel:** Text i  ** kursiv stil representerar en variabel som du anger eller skickar in när du skapar eller tar emot  [!DNL API] data. Ersätt *kursiv*-text med egen kod, egna parametrar eller annan obligatorisk information.

## Autentisering {#authentication}

[!DNL Audience Manager] [!DNL REST APIs] stöder två autentiseringsmetoder.

* [JWT-](#jwt) autentisering (tjänstkonto) med  [Adobe I/O](https://www.adobe.io/). [!DNL Adobe I/O] är Adobe utvecklares ekosystem och community. Den innehåller [Adobe I/O utvecklingsverktyg och API:er](https://www.adobe.io/apis/experienceplatform.html) och [API:er för alla Adobe-produkter](https://www.adobe.io/apis.html). Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs].
* [OAuth-autentisering (borttagen)](#oauth). Den här metoden är föråldrad, men kunder med befintliga [!DNL OAuth]-integreringar kan fortsätta använda den här metoden.

>[!IMPORTANT]
>
>Beroende på din autentiseringsmetod måste du justera din begäran [!DNL URLs] därefter. Avsnittet [Environment](#environments) innehåller information om värdnamn som du bör använda.

## [!DNL JWT] ([!DNL Service Account]) Autentisering med Adobe I/O  {#jwt}

### Adobe I/O Overview {#adobeio}

[!DNL Adobe I/O] är Adobe utvecklares ekosystem och community. Den innehåller [Adobe I/O utvecklingsverktyg och API:er](https://www.adobe.io/apis/experienceplatform.html) och [API:er för alla Adobe-produkter](https://www.adobe.io/apis.html).

Detta är det rekommenderade sättet att konfigurera och använda [!DNL Adobe] [!DNL APIs].

### Förutsättningar {#prerequisites}

Innan du kan konfigurera [!DNL JWT]-autentisering bör du kontrollera att du har åtkomst till [Adobe Developer Console](https://console.adobe.io/) i [Adobe I/O](https://www.adobe.io/). Kontakta din organisations administratör för åtkomstbegäranden.

### Autentisering {#auth}

Följ stegen nedan för att konfigurera [!DNL JWT (Service Account)]-autentisering med [!DNL Adobe I/O]:

1. Logga in på [Adobe Developer Console](https://console.adobe.io/).
1. Följ stegen i [Anslutning till tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
   * Under [Steg 2: Lägg till ett API i projektet med autentisering av tjänstkonto](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md) och välj alternativet [!DNL Audience Manager] [!DNL API].
1. Prova anslutningen genom att ringa ditt första [!DNL API]-samtal baserat på instruktionerna från [Steg 3](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!NOTE]
>
>Om du vill konfigurera och arbeta med [!DNL Audience Manager] [!DNL REST APIs] automatiskt kan du generera [!DNL JWT] programmatiskt. Mer information finns i [JWT-autentisering (tjänstkonto)](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md).

## [!DNL OAuth] Autentisering (inaktuellt)  {#oauth}

>[!WARNING]
> [!DNL Audience Manager] [!UICONTROL REST API] tokenautentisering och förnyelse via  [!DNL OAuth 2.0] är nu föråldrat.
>
> Använd [JWT-autentisering (tjänstkonto)](#jwt-service-account-authentication-jwt) i stället.

[!DNL Audience Manager] [!UICONTROL REST API] följer [!DNL OAuth 2.0]-standarder för tokenautentisering och förnyelse. I avsnitten nedan beskrivs hur du autentiserar och börjar arbeta med [!DNL API]s.

### Skapa en allmän [!DNL API] användare {#requirements}

Vi rekommenderar att du skapar ett separat, tekniskt användarkonto för att arbeta med [!DNL Audience Manager] [!DNL API]s. Det här är ett generiskt konto som inte är kopplat till eller kopplat till en viss användare i organisationen. Med den här typen av [!DNL API]-användarkonto kan du uppnå två saker:

* Identifiera vilken tjänst som anropar [!DNL API] (t.ex. samtal från appar som använder våra [!DNL API]s eller från andra verktyg som gör [!DNL API]-förfrågningar).
* Ge oavbruten åtkomst till [!DNL API]s. Ett konto som är knutet till en viss person kan tas bort när de lämnar företaget. Detta förhindrar dig från att arbeta med tillgänglig [!DNL API]-kod. Ett generiskt konto som inte är kopplat till en viss medarbetare hjälper dig att undvika det här problemet.

Ett exempel eller ett användningsexempel för den här typen av konto är att du vill ändra många segment samtidigt med [grupphanteringsverktygen](../../reference/bulk-management-tools/bulk-management-intro.md). För att göra detta behöver ditt användarkonto åtkomsten till [!DNL API]. I stället för att lägga till behörigheter till en viss användare skapar du ett icke-specifikt [!DNL API]-användarkonto som har rätt autentiseringsuppgifter, nyckel och hemlighet för att göra [!DNL API]-anrop. Detta är också användbart om du utvecklar egna program som använder [!DNL Audience Manager] [!DNL API]s.

Samarbeta med din [!DNL Audience Manager]-konsult för att skapa ett generiskt, [!DNL API]-specifikt användarkonto.

### Lösenordsautentisering {#password-authentication-workflow}

Lösenordsautentisering ger säker åtkomst till vår [!DNL REST API]. Stegen nedan visar arbetsflödet för lösenordsautentisering från en [!DNL JSON]-klient i webbläsaren.

>[!TIP]
>
>Kryptera åtkomst- och uppdateringstoken om du lagrar dem i en databas.

#### Steg 1: Begär åtkomst till [!DNL API]

Kontakta din Partner Solutions Manager. De ger dig ett [!DNL API] klient-ID och hemlighet. ID:t och hemligheten autentiserar dig för [!DNL API].

Obs! Om du vill få en uppdateringstoken anger du det när du begär [!DNL API]-åtkomst.

#### Steg 2: Begär token

Skicka en tokenbegäran med den [!DNL JSON]-klient du föredrar. När du skapar begäran:

* Använd en `POST`-metod för att anropa `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Autentiseringsuppgifterna `testId : testSecret` konverteras till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka [!DNL HTTP] [!DNL headers] `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded`. Sidhuvudet kan till exempel se ut så här: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Ställ in begärandetexten enligt följande:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

#### Steg 3: Ta emot token

[!DNL JSON]-svaret innehåller din åtkomsttoken. Svaret bör se ut så här:

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

Uppdatera tokens förnya åtkomsten [!DNL API] när den ursprungliga token har upphört att gälla. Om det efterfrågas innehåller svaret [!DNL JSON] i lösenordsarbetsflödet en uppdateringstoken. Om du inte får någon uppdateringstoken skapar du en ny under lösenordsautentiseringsprocessen.

Du kan också använda en uppdateringstoken för att generera en ny token innan den befintliga åtkomsttoken upphör att gälla.

Om din åtkomsttoken har upphört att gälla får du ett `401 Status Code`-meddelande och följande rubrik i svaret:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I följande steg beskrivs arbetsflödet för att använda en uppdateringstoken för att skapa en ny åtkomsttoken från en [!DNL JSON]-klient i webbläsaren.

#### Steg 1: Begär ny token

Skicka en begäran om uppdateringstoken med den önskade [!DNL JSON]-klienten. När du skapar begäran:

* Använd en `POST`-metod för att anropa `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Autentiseringsuppgifterna `testId : testSecret` konverteras till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka HTTP-rubrikerna `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded`. Sidhuvudet kan till exempel se ut så här: <br> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br> `Content-Type: application/x-www-form-urlencoded`
* Ange `grant_type:refresh_token` i begärandetexten och skicka den uppdateringstoken som du fick i din tidigare åtkomstbegäran. Begäran ska se ut så här: <br> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

#### Steg 2: Ta emot den nya token

[!DNL JSON]-svaret innehåller din nya åtkomsttoken. Svaret bör se ut så här:

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

[!DNL Audience Manager] [!UICONTROL REST API] stöder auktoriseringskod och implicit autentisering. Om du vill använda dessa åtkomstmetoder måste användarna logga in på `https://api.demdex.com/oauth/authorize` för att få åtkomst till och uppdatera tokens.

## Gör autentiserade [!DNL API]-begäranden {#authenticated-api-requests}

Krav för att anropa [!DNL API]-metoder när du har fått en autentiseringstoken.

Så här anropar du de tillgängliga [!DNL API]-metoderna:

* Ange `Authorization: Bearer <token>` i rubriken `HTTP`.
* När du använder [JWT-autentisering (tjänstkonto)](#jwt) måste du ange rubriken `x-api-key`, som är densamma som din `client_id`. Du kan hämta din `client_id` från [Adobe I/O-integreringssidan](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).
* Anropa den obligatoriska [!DNL API]-metoden.

## Valfria [!DNL API]-frågeparametrar {#optional-api-query-parameters}

Ange de valfria parametrar som är tillgängliga för metoder som returnerar alla egenskaper för ett objekt.

Du kan använda de här valfria parametrarna med [!DNL API]-metoder som returnerar *alla*-egenskaper för ett objekt. Ange dessa alternativ i begärandesträngen när du skickar frågan till [!DNL API].

| Parameter | Beskrivning |
|--- |--- |
| `page` | Returnerar resultat per sidnummer. Numreringen börjar vid 0. |
| `pageSize` | Anger antalet svarsresultat som returneras av begäran (10 är standard). |
| `sortBy` | Sorterar och returnerar resultat enligt den angivna [!DNL JSON]-egenskapen. |
| `descending` | Sorterar och returnerar resultat i fallande ordning. `ascending` är standard. |
| `search` | Returnerar resultat baserat på den angivna strängen som du vill använda som sökparameter. Anta att du vill hitta resultat för alla modeller som har ordet &quot;Test&quot; i något av värdefälten för det objektet. Din exempelbegäran kan se ut så här:   `GET https://aam.adobe.io/v1/models/?search=Test`.  Du kan söka efter alla värden som returneras av en [!DNL get all]-metod. |
| `folderId` | Returnerar alla ID:n för [!UICONTROL traits] i den angivna mappen. Inte tillgängligt för alla metoder. |
| `permissions` | Returnerar en lista med segment baserat på den angivna behörigheten. `READ` är standard. Behörigheterna är:<ul><li>`READ` : Returnera och visa information om ett segment.</li><li>`WRITE` : Används   `PUT`  för att uppdatera ett segment.</li><li>`CREATE` : Används   `POST`  för att skapa ett segment.</li><li>`DELETE` : Ta bort ett segment. Kräver åtkomst till eventuella underliggande egenskaper. Du måste till exempel ha behörighet att ta bort de egenskaper som tillhör ett segment om du vill ta bort det.</li></ul><br>Ange flera behörigheter med separata nyckelvärdepar. Om du till exempel vill returnera en lista med segment med endast behörigheterna `READ` och `WRITE` skickar du `"permissions":"READ"`, `"permissions":"WRITE"`. |
| `includePermissions` | ([!DNL Boolean]) Ange `true` för att returnera dina behörigheter för segmentet. Standardvärdet är `false`. |

### En anteckning om sidalternativ

När sidinformationen *inte* har angetts returnerar begäran det rena [!DNL JSON] resultatet i en matris. Om sidinformationen *är* angiven kapslas den returnerade listan in i ett [!DNL JSON]-objekt som innehåller information om det totala resultatet och den aktuella sidan. Din exempelbegäran med sidalternativ kan se ut ungefär så här:

```
GET https://aam.adobe.io/v1/models/?page=1&pageSize=2&search=Test
```

## [!DNL API URLs] {#api-urls}

[!DNL URLs] för förfrågningar, staging- och produktionsmiljöer samt versioner.

## Begäran [!DNL URLs] {#request-urls}

I följande tabell visas begäran [!DNL URLs] som används för att skicka [!DNL API]-begäranden per metod.

Beroende på vilken autentiseringsmetod du använder måste du justera din begäran [!DNL URLs] enligt tabellerna nedan.

### Begär [!DNL URLs] för [!DNL JWT] autentisering {#request-urls-jwt}

| [!DNL API] Metoder | Begär [!DNL URL] |
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

### Begär [!DNL URLs] för [!DNL OAuth]-autentisering (borttagen) {#request-urls-oauth}

| [!DNL API] Metoder | Begär [!DNL URL] |
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

## Miljöer {#environments}

[!DNL Audience Manager] [!DNL API]s ger åtkomst till olika arbetsmiljöer. Dessa miljöer hjälper dig att testa kod mot separata databaser utan att påverka livs- och produktionsdata. I följande tabell visas tillgängliga [!DNL API]-miljöer och motsvarande resursvärdnamn.

Beroende på vilken autentiseringsmetod du använder måste du justera miljön [!DNL URLs] enligt tabellen nedan.

| Miljö | Värdnamn för [!DNL JWT]-autentisering | Värdnamn för [!DNL OAuth]-autentisering |
|---|---|---|
| **Produktion** | `https://aam.adobe.io/...` | `https://api.demdex.com/...` |
| **Beta** | `https://aam-beta.adobe.io/...` | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Betamiljön [!DNL Audience Manager] är en mindre, fristående version av produktionsmiljön. Alla data som du vill testa måste anges och samlas in i den här miljön.

## Versioner {#versions}

Nya versioner av dessa [!DNL API]s släpps regelbundet. En ny version ökar versionsnumret för [!DNL API]. Versionsnumret refereras i begäran [!DNL URL] som `v<version number>` enligt följande exempel:

`https://<host>/v1/...`

## Svarskoder definierade {#response-codes-defined}

`HTTP` statuskoder och svarstext som returneras av  [!DNL Audience Manager] [!UICONTROL REST API].

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
>* [OAuth 2 - förenklad](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

