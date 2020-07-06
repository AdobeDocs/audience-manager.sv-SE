---
description: Audience Manager tar datasäkerhet och integritet på stort allvar. Vi arbetar för att skydda våra system och skydda dina värdefulla data.
seo-description: Audience Manager tar datasäkerhet och integritet på stort allvar. Vi arbetar för att skydda våra system och skydda dina värdefulla data.
seo-title: 'Datasäkerhet i Audience Manager '
solution: Audience Manager
title: Datasäkerhet i Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 98%

---


# Datasäkerhet i Audience Manager {#data-security}

Audience Manager tar datasäkerhet och integritet på stort allvar. Vi arbetar för att skydda våra system och skydda dina värdefulla data.

Säkerhetsrutinerna för Audience Manager omfattar externa och interna revisioner, loggning av aktiviteter, utbildning och andra procedurer som utformats för att skydda våra system och era värdefulla data. Vi anser att en säker produkt hjälper till att bygga upp och underhålla det förtroende kunderna visar oss.

I Audience Manager indelar vi säkerhet i tre huvudkategorier:

| Typ av säkerhet | Har stöd för |
|---|---|
| **Informationssäkerhet** | Rutiner för autentisering, kryptering och datalagring på företagsnivå |
| **Dataläckage/transparens** | Djupgående och åtgärdbara insikter om webbplatsaktiviteter som utgör eller bidrar till dataläckage |
| **Förbättringar av processer/principer** | Klienter, genom att tillämpa branschledande praxis för sekretess och datasäkerhet |

## System, utbildning och åtkomst {#systems-training-access}

Processer som håller vårt system och era data säkra.

**Extern säkerhetsvalidering:**  Audience Manager testar säkerheten på års- och kvartalsbasis.

* Årsvis: En gång om året genomgår Audience Manager ett fullständigt penetrationstest som utförs av ett oberoende tredjepartsföretag. Testet är utformat för att identifiera säkerhetsluckor i programmet. Testerna omfattar sökning efter webbplatsövergripande skriptning (cross-site scripting), SQL-inmatningar, hantering av formulärparametrar och andra sårbarheter på programnivå.
* Kvartalsvis: En gång varje kvartal söker interna team efter säkerhetsluckor. Dessa tester omfattar nätverkssökningar efter öppna portar och sårbarheter i tjänster.

**Systemsäkerhet:**  För att skydda data kan Audience Manager:

* Blockera förfrågningar från obehöriga IP-adresser.
* Skydda data bakom brandväggar, VPN:er och med Virtual Private Cloud-lagring.
* Spåra ändringar i kund- och kontrollinformationsdatabaser med utlösarbaserad granskningsloggning. Dessa loggar spårar alla ändringar på databasnivå, inklusive användar-ID och IP-adress som används för ändringarna.

**Säkerhetsresurser:**  Audience Manager har ett dedikerat nätverksteam som övervakar brandväggar och enheter för intrångsdetektering. Endast nyckelpersonal har tillgång till vår säkerhetsteknik och våra data.

**Säkerhetsutbildning:**  Internt gäller vårt säkerhetsåtagande även utvecklare som arbetar med produkten. Adobe ger utvecklare formell utbildning i hur man skapar säkra program och tjänster.

**Säker åtkomst:**  Audience Manager kräver starka lösenord för att logga in på systemet. Se [lösenordskrav](../../reference/password-requirements.md).

## Integritet och personligt identifierbar information (PII) {#pii}

Processer som skyddar personuppgifter. Mer sekretessinformation finns i [Adobes sekretesscenter](https://www.adobe.com/se/privacy/advertising-services.html).

**PII-data:**  I Audience Manager-avtalet förbjuds kunder och datapartners att skicka PII-information till vårt system. Unika användar-ID:n (UUID) får inte innehålla eller använda PII-data som en del av ID-genereringsalgoritmen.

**IP-adresser:**  Audience Manager samlar in IP-adresser. IP-adresser används för databehandling och aggregering av loggar. De krävs också för geografiska/platsinriktade sökningar och målgruppsinriktning. Alla IP-adresser i de lagrade loggfilerna döljs inom 90 dagar.

## Datapartitionering {#data-partitioning}

Processer som hjälper till att skydda data som ägs av enskilda klienter.

**Trait Data Partitioning:**  Dina data ([!UICONTROL traits]ID, etc.) partitioneras av klienten. Detta förhindrar att information oavsiktligt exponeras för olika kunder. Till exempel trait-data i cookies partitioneras av kunden och lagras i en klientspecifik underdomän. De kan inte läsas eller användas av misstag av en annan Audience Manager-klient. Dessutom partitioneras trait-data som lagras i [!UICONTROL Profile Cache Servers (PCS)] också av kunden. Det förhindrar att andra klienter oavsiktligt använder dina data i händelseanrop eller andra förfrågningar.

**Datapartitionering i rapporter:**  Klient-ID:n är en del av identifieringsnyckeln i alla rapporttabeller och rapportfrågor filtreras efter ID. Det förhindrar att data visas i rapporter för en annan Audience Manager-kund.

## Inkommande server-till-server-överföringar (S2S) {#inbound-s2s}

Adobe Audience Manager har stöd för två huvudsakliga metoder för överföring av S2S-datafiler direkt till våra system:

Båda metoderna är utformade med hänsyn till kundens och partnerns säkerhet när data överförs mellan deras system och vårt system.

**SFTP:** För alternativet SFTP väljer de flesta kunder att leverera filer via SFTP-protokollet (Secure FTP), som använder SSH-protokollet (Secure Shell). Med den här metoden krypteras filerna när de överförs mellan kundens system och Adobes system. För varje kund skapar vi en skyddad inkorg på våra SFTP-servrar som är kopplad till ett användarkonto i det systemet. Det är bara kundens inloggade och behöriga interna systemanvändare som har åtkomst till den skyddade inkorgen. Den skyddade platsen är inte tillgänglig för andra kunder.

**[!UICONTROL Amazon Web Services S3]via HTTPS:**För leveransalternativet S3 rekommenderar vi att alla kunder konfigurerar sina S3-klienter så att de använder HTTPS-krypteringsmetoden för filöverföringar (den är inte standard så den måste konfigureras manuellt). Alternativet HTTPS stöds både av kommandoradsverktyget s3cmd och de S3-bibliotek som finns i alla större programmeringsspråk. När det här HTTPS-alternativet är aktiverat krypteras kundens data när de överförs till våra system. För varje kund skapar vi en separat S3-bucket underkatalog som bara kan nås med kundens och våra interna systemanvändares autentiseringsuppgifter.

Information om hur du lägger till PGP-kryptering i datafiler finns i [PGP-filkryptering för inkommande datatyper](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Skydda data med dubbla undantagstecken {#escaping-data}

Observera att [!DNL Audience Manager] data inte skyddas av dubbla undantagstecken för att förhindra eventuell XSS (cross-site scripting) osv. Det är kundens ansvar att skydda inkommande data med dubbla undantagstecken.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] är en branschövergripande webbsäkerhetsmekanism som skyddar mot cookie-kapning och protokollnedgraderingsattacker.

Principen instruerar webbläsaren att när ett säkert [!DNL HTTPS]-anrop har gjorts till en viss domän får inga efterföljande osäkra anrop ([!DNL HTTP]) tillåtas till den domänen. Det skyddar mot man-in-the-middle-attacker, där en angripare kan försöka nedgradera [!DNL HTTPS]-anrop till osäkra [!DNL HTTP]-anrop.

Principen förbättrar datasäkerheten mellan klienter och Adobe [Edge](../../reference/system-components/components-edge.md)-servrar.

### Exempel på {#hsts-example}

Let&#39;s say the `yourcompany.demdex.com` domain sends traffic to the [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] uppgraderar anropen till [!DNL HTTPS] och alla efterföljande [!DNL DCS]-anrop som kommer från `yourcompany.demdex.com` använder [!DNL HTTPS] i stället för [!DNL HTTP].

Mer information om HSTS finns i [HTTP Strict Transport Security – Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security).
