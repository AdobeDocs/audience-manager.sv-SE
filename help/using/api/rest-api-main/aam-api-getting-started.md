---
description: Information om allmänna krav, autentisering, valfria frågeparametrar, begäran-URL:er och andra referenser.
seo-description: Information om allmänna krav, autentisering, valfria frågeparametrar, begäran-URL:er och andra referenser.
seo-title: Komma igång med REST API:er
solution: Audience Manager
title: Komma igång med REST API:er
uuid: af0e527e-6eec-449c-9709-f90e57cd188d
translation-type: tm+mt
source-git-commit: af43becaf841909174fad097f4d4d5040c279b47

---


# Komma igång med REST API:er {#getting-started-with-rest-apis}

Information om allmänna krav, autentisering, valfria frågeparametrar, begäran-URL:er och andra referenser.

<!-- c_rest_api_overview.xml -->

## Krav och rekommendationer för API {#api-requirements-recommendations}

Saker som ni måste och bör göra när ni arbetar med Audience Manager [!DNL API]s.

<!-- aam-api-requirements.xml -->

Observera följande när du arbetar med [Audience Manager API](https://bank.demdex.com/portal/swagger/index.html#/) -kod:

* **Begäranparametrar:** Alla frågeparametrar är obligatoriska om inte annat anges.
* **[!DNL JSON]innehållstyp:**Ange`content-type: application/json`och **`accept: application/json`i koden.

* **Förfrågningar och svar:** Skicka begäranden som ett korrekt formaterat [!DNL JSON] objekt. [!DNL Audience Manager] svarar med [!DNL JSON] formaterade data. Serversvar kan innehålla begärda data, en statuskod eller båda.

* **Åtkomst:** Din [!DNL Audience Manager] konsult kommer att förse dig med ett klient-ID och en nyckel som gör att du kan göra [!DNL API] förfrågningar.

* **Exempel på dokumentation och kod:** Text i *kursiv stil* representerar en variabel som du anger eller skickar in när du skapar eller tar emot [!DNL API] data. Ersätt *kursiv* text med egen kod, egna parametrar eller annan obligatorisk information.

## Rekommendationer: Skapa en allmän API-användare {#requirements}

Vi rekommenderar att du skapar ett separat, tekniskt användarkonto för att arbeta med Audience Manager [!DNL API]. Det här är ett generiskt konto som inte är kopplat till eller kopplat till en viss användare i organisationen. Den här typen av [!DNL API] användarkonto hjälper dig att uppnå två saker:

* Identifiera vilken tjänst som anropar [!DNL API] (t.ex. samtal från appar som använder våra [!DNL API]eller andra verktyg som gör [!DNL API] förfrågningar).
* Ge dig tillgång till [!DNL API]dina kunder utan avbrott. Ett konto som är knutet till en viss person kan tas bort när de lämnar företaget. Detta förhindrar dig från att arbeta med den tillgängliga [!DNL API] koden. Ett generiskt konto som inte är kopplat till en viss medarbetare hjälper dig att undvika det här problemet.

Ett exempel eller ett användningsexempel för den här typen av konto är att du vill ändra många segment samtidigt med [grupphanteringsverktygen](../../reference/bulk-management-tools/bulk-management-intro.md). För att göra detta behöver ditt användarkonto [!DNL API] åtkomst. I stället för att lägga till behörigheter till en viss användare skapar du ett icke-specifikt, användarkonto som har rätt autentiseringsuppgifter, nyckel och hemlighet för att ringa [!DNL API] [!DNL API] samtal. Detta är också användbart om du utvecklar egna program som använder Audience Manager [!DNL API].

Samarbeta med er Audience Manager-konsult för att skapa ett generiskt, [!DNL API]enbart användarkonto.

## OAuth-autentisering {#oauth}

Audience Manager [!UICONTROL REST API] följer [!DNL OAuth 2.0] standarderna för tokenautentisering och förnyelse. Avsnitten nedan beskriver hur du autentiserar och börjar arbeta med [!DNL API]dem.

## Lösenordsautentisering {#password-authentication-workflow}

<!-- oath-authentication.xml -->

Lösenordsautentisering ger säker åtkomst till våra [!DNL REST API]. Stegen nedan visar arbetsflödet för lösenordsautentisering från en [!DNL JSON] klient i webbläsaren.

>[!TIP]
>
>Kryptera åtkomst- och uppdateringstoken om du lagrar dem i en databas.

### Steg 1: Begär API-åtkomst

Kontakta din Partner Solutions Manager. De ger dig ett [!DNL API] klient-ID och en hemlighet. ID:t och hemligheten autentiserar dig för [!DNL API]användaren.

Obs! Om du vill få en uppdateringstoken anger du det när du begär [!DNL API] åtkomst.

### Steg 2: Begär token

Skicka en tokenbegäran med den önskade [!DNL JSON] klienten. När du skapar begäran:

* Använd en `POST` anropsmetod `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Inloggningsuppgifterna `testId : testSecret` konverteras till exempel till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka in [!DNL HTTP] rubrikerna `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded` . Sidhuvudet kan till exempel se ut så här: <br/>`Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/>`Content-Type: application/x-www-form-urlencoded`
* Ställ in begärandetexten enligt följande:
   <br/> `grant_type=password&username=<your-AudienceManager-user-name>&password=<your-AudienceManager-password>`

### Steg 3: Ta emot token

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

Nyckeln representerar antalet sekunder tills åtkomsttoken upphör att gälla `expires_in` . Som bästa praxis bör du använda korta förfallotider för att begränsa exponeringen om token någonsin exponeras.

## Uppdatera token {#refresh-token}

Uppdatera tokens förnya [!DNL API] åtkomsten när den ursprungliga token har upphört att gälla. Om det efterfrågas innehåller svaret [!DNL JSON] i lösenordsarbetsflödet en uppdateringstoken. Om du inte får någon uppdateringstoken skapar du en ny under lösenordsautentiseringsprocessen.

Du kan också använda en uppdateringstoken för att generera en ny token innan den befintliga åtkomsttoken upphör att gälla.

Om din åtkomsttoken har upphört att gälla får du ett `401 Status Code` och följande huvud i svaret:

`WWW-Authenticate: Bearer realm="oauth", error="invalid_token", error_description="Access token expired: <token>"`

I följande steg beskrivs arbetsflödet för att använda en uppdateringstoken för att skapa en ny åtkomsttoken från en [!DNL JSON] klient i webbläsaren.

### Steg 1: Begär ny token

Skicka en begäran om en uppdateringstoken till den önskade [!DNL JSON] klienten. När du skapar begäran:

* Använd en `POST` anropsmetod `https://api.demdex.com/oauth/token`.
* Konvertera ditt klient-ID och hemlighet till en base-64-kodad sträng. Separera ID:t och hemligheten med ett kolon under konverteringsprocessen. Inloggningsuppgifterna `testId : testSecret` konverteras till exempel till `dGVzdElkOnRlc3RTZWNyZXQ=`.
* Skicka HTTP-rubrikerna `Authorization:Basic <base-64 clientID:clientSecret>` och `Content-Type: application/x-www-form-urlencoded`. Sidhuvudet kan till exempel se ut så här: <br/> `Authorization: Basic dGVzdElkOnRlc3RTZWNyZXQ=` <br/> `Content-Type: application/x-www-form-urlencoded`
* I den begärande texten anger du `grant_type:refresh_token` och skickar den uppdateringstoken som du fick i din tidigare åtkomstbegäran. Begäran ska se ut så här: <br/> `grant_type=refresh_token&refresh_token=b27122c0-b0c7-4b39-a71b-1547a3b3b88e`

### Steg 2: Ta emot den nya token

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

## Auktoriseringskod och implicit autentisering {#authentication-code-implicit}

Audience Manager [!UICONTROL REST API] stöder auktoriseringskod och implicit autentisering. Om du vill använda dessa åtkomstmetoder måste användarna logga in för `https://api.demdex.com/oauth/authorize` att få åtkomst till och uppdatera tokens.

## Skapa autentiserade API-begäranden {#authenticated-api-requests}

Krav för att anropa [!DNL API] metoder när du har fått en autentiseringstoken.

<!-- c_oauth_call_methods.xml -->

Så här anropar du de tillgängliga [!DNL API] metoderna:

* Ställ in i `HTTP` sidhuvudet `Authorization: Bearer <token>`.
* Anropa den önskade [!DNL API] metoden.

## Ytterligare API-frågeparametrar {#optional-api-query-parameters}

Ange de valfria parametrar som är tillgängliga för metoder som returnerar alla egenskaper för ett objekt.

<!-- c_rest_api_optional.xml -->

Du kan använda dessa valfria parametrar med [!DNL API] metoder som returnerar *alla* egenskaper för ett objekt. Ange dessa alternativ i begärandesträngen när du skickar frågan till [!DNL API].

| Parameter | Beskrivning |
|--- |--- |
| page | Returnerar resultat per sidnummer. Numreringen börjar vid 0. |
| pageSize | Anger antalet svarsresultat som returneras av begäran (10 är standard). |
| sortBy | Sorterar och returnerar resultat enligt den angivna [!DNL JSON] egenskapen. |
| fallande | Sorterar och returnerar resultat i fallande ordning. Stigande är standard. |
| sök | Returnerar resultat baserat på den angivna strängen som du vill använda som sökparameter. Anta att du vill hitta resultat för alla modeller som har ordet &quot;Test&quot; i något av värdefälten för det objektet. Din exempelbegäran kan se ut så här:   `GET https://api.demdex.com/v1/models/?search=Test`.  Du kan söka efter alla värden som returneras av en get all-metod. |
| folderId | Returnerar alla ID:n för egenskaper i den angivna mappen. Inte tillgängligt för alla metoder. |
| behörigheter | Returnerar en lista med segment baserat på den angivna behörigheten.  LÄS är standard. Behörigheterna är:<ul><li>`READ` : Returnera och visa information om ett segment.</li><li>`WRITE` : Används `PUT` för att uppdatera ett segment.</li><li>`CREATE` : Används `POST` för att skapa ett segment.</li><li>`DELETE` : Ta bort ett segment. Kräver åtkomst till eventuella underliggande egenskaper. Du måste till exempel ha behörighet att ta bort de egenskaper som tillhör ett segment om du vill ta bort det.</li></ul><br>Ange flera behörigheter med separata nyckelvärdepar. Om du till exempel vill returnera en lista med segment med endast `READ` och `WRITE` behörigheter skickar du `"permissions":"READ"`, `"permissions":"WRITE"` . |
| includePermissions | (Boolean) Ange som true om du vill returnera dina behörigheter för segmentet. Standardvärdet är false. |

### En anteckning om sidalternativ

När sidinformation inte ** har angetts returnerar begäran oformaterade [!DNL JSON] resultat i en array. Om sidinformation *anges* kapslas den returnerade listan in i ett [!DNL JSON] objekt som innehåller information om det totala resultatet och den aktuella sidan. Din exempelbegäran med sidalternativ kan se ut ungefär så här:

```
GET https://api.demdex.com/v1/models/?page=1&pageSize=2&search=Test
```

## API-URL:er {#api-urls}

[!DNL URLs] för förfrågningar, staging- och produktionsmiljöer samt versioner.

<!-- r_rest_urls.xml -->

## Begär URL:er {#request-urls}

I följande tabell visas URL:er för begäran som används för att skicka [!DNL API] begäranden per metod.

| [!DNL API] Metoder | Begäran [!DNL URL] |
|--- |--- |
| Algoritmisk modellering | `https://api.demdex.com/v1/models/` |
| Datakälla | `https://api.demdex.com/v1/datasources/` |
| Härledda signaler | `https://api.demdex.com/v1/signals/derived/` |
| Mål  | `https://api.demdex.com/v1/destinations/` |
| Domäner | `https://api.demdex.com/v1/partner-sites/` |
| Mappar | Traits:  `https://api.demdex.com/v1/folders/traits /`<br>Segment:  `https://api.demdex.com/v1/folders/segments /` |
| Schema | `https://api.demdex.com/v1/schemas/` |
| Segment | `https://api.demdex.com/v1/segments/` |
| Traits | `https://api.demdex.com/v1/traits/` |
| Trait Types | `https://api.demdex.com/v1/customer-trait-types` |
| Taxonomi | `https://api.demdex.com/v1/taxonomies/0/` |

## Miljö {#environments}

Via [!DNL Audience Manager] dessa får du [!DNL API]tillgång till olika arbetsmiljöer. Dessa miljöer hjälper dig att testa kod mot separata databaser utan att påverka livs- och produktionsdata. I följande tabell visas tillgängliga [!DNL API] miljöer och motsvarande resursvärdnamn.

| Miljö | Värdnamn |
|---|---|
| **Produktion** | `https://api.demdex.com/...` |
| **Beta** | `https://api-beta.demdex.com/...` |

>[!NOTE]
>
>Audience Manager beta-miljön är en mindre, fristående version av produktionsmiljön. Alla data som du vill testa måste anges och samlas in i den här miljön.

## Versioner {#versions}

Nya versioner av dessa [!DNL API]släpps regelbundet. En ny release ökar [!DNL API] versionsnumret. Versionsnumret refereras i den begärande URL:en `v<version number>` enligt följande exempel:

`https://<host>/v1/...`

## Definierade svarskoder {#response-codes-defined}

`HTTP` statuskoder och svarstext som returneras av Audience Manager [!UICONTROL REST API].

<!-- r_api_http_response_codes.xml -->

| Svarskod-ID | Svarstext | Definition |
|---|---|---|
| 200 | OK | Begäran har bearbetats. Returnerar förväntat innehåll eller data om det behövs. |
| 201 | Skapad | Resursen skapades. Returnerar `PUT` och `POST` begär. |
| 204 | Inget innehåll | Resursen har tagits bort. Svarstexten är tom. |
| 400 | Felaktig begäran | Servern förstod inte begäran. Vanligtvis på grund av felaktig syntax. Kontrollera din begäran och försök igen. |
| 403 | Förbjuden | Du har inte åtkomst till resursen. |
| 404 | Hittades inte | Det gick inte att hitta resursen för den angivna sökvägen. |
| 409 | Konflikt | Begäran kunde inte slutföras på grund av en konflikt med resursens tillstånd. |
| 500 | Serverfel | Servern påträffade ett oväntat fel som gjorde att den inte kunde utföra begäran. |

>[!MORELIKETHIS]
>
>* [OAuth-autentisering](../../api/rest-api-main/aam-api-getting-started.md#oauth)
>* [OAuth 2.0](https://oauth.net/2/)
>* [OAuth 2 - förenklad](https://aaronparecki.com/articles/2012/07/29/1/oauth2-simplified#browser-based-apps)

