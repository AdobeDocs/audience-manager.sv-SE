---
description: Audience Manager tar datasäkerhet och integritet på stort allvar. Vi arbetar för att skydda våra system och skydda dina värdefulla data.
seo-description: Audience Manager tar datasäkerhet och integritet på stort allvar. Vi arbetar för att skydda våra system och skydda dina värdefulla data.
seo-title: Datasäkerhet i Audience Manager
solution: Audience Manager
title: Datasäkerhet i Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 0869e016d7f80710cb194449c48675b82fdfa865
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 0%

---


# Datasäkerhet i Audience Manager {#data-security}

Audience Manager tar datasäkerhet och integritet på stort allvar. Vi arbetar för att skydda våra system och skydda dina värdefulla data.

Audience Manager säkerhetsrutiner omfattar externa och interna revisioner, loggning av aktiviteter, utbildning och andra procedurer som är utformade för att skydda våra system och era värdefulla data. Vi tror att en säker produkt hjälper till att bygga upp och underhålla det förtroende kunderna har hos oss.

I Audience Manager tänker vi på säkerhet i tre huvudkategorier:

| Säkerhetstyp | Har stöd för |
|---|---|
| **Informationssäkerhet** | Autentisering, kryptering och datalagring på företagsnivå |
| **Dataläckage/genomskinlighet** | Djupgående och åtgärdbara insikter i aktiviteter på plats som utgör eller bidrar till dataläckage |
| **Förbättringar av processer/principer** | Klienter, genom att arbeta med branschens bästa praxis för sekretess och datasäkerhet |

## System, utbildning och åtkomst {#systems-training-access}

Processer som gör vårt system och era data säkra.

**Extern säkerhetsvalidering:**  Audience Manager testar säkerheten på års- och kvartalsbasis.

* Årsvis: En gång om året genomgår Audience Manager ett fullständigt penetrationstest som utförs av ett oberoende tredjepartsföretag. Testet är utformat för att identifiera säkerhetsluckor i programmet. Testerna omfattar sökning efter serveröverskridande skriptning (cross-site scripting), SQL-injektioner, hantering av formulärparametrar och andra sårbarheter på applikationsnivå.
* Kvartalsvis: En gång varje kvartal söker interna team efter säkerhetsluckor. Dessa tester omfattar nätverkssökningar efter öppna portar och sårbarheter med tjänster.

**Systemsäkerhet:**  För att skydda och skydda data, Audience Manager:

* Blockerar förfrågningar från obehöriga IP-adresser.
* Skyddar data bakom brandväggar, VPN:er och med Virtual Private Cloud-lagring.
* Spåra ändringar i kund- och kontrollinformationsdatabaser med utlösarbaserad granskningsloggning. Dessa loggar spårar alla ändringar på databasnivå, inklusive användar-ID och IP-adress som ändringarna görs från.

**Säkerhetsresurser:**  Audience Manager har ett dedikerat nätverksteam som övervakar brandväggar och enheter för intrångsdetektering. Endast nyckelpersonal har tillgång till vår säkerhetsteknik och våra data.

**Säkerhetsutbildning:**  Internt gäller vårt säkerhetsåtagande även utvecklare som arbetar med vår produkt. Adobe ger utvecklare formell utbildning i hur man skapar säkra program och tjänster.

**Säker åtkomst:**  Audience Manager kräver starka lösenord för att logga in på systemet. Se [lösenordskrav](../../reference/password-requirements.md).

## Integritet och personligt identifierbar information {#pii}

Processer som skyddar personuppgifter. Mer sekretessinformation finns i [Adobes sekretesscenter](https://www.adobe.com/privacy/advertising-services.html).

**PII-data:**  Audience Manager förbjuder avtalsmässigt kunder och datapartners från att skicka PII-information till vårt system. Unikt användar-ID (UUID) innehåller eller använder inte PII-data som en del av ID-genereringsalgoritmen.

**IP-adresser:**  Audience Manager samlar faktiskt in IP-adresser. IP-adresser används i databehandlings- och loggaggregeringsprocesser. De krävs också för geografiska/platsinriktade sökningar och målinriktning. Dessutom är alla IP-adresser i de lagrade loggfilerna dolda inom 90 dagar.

## Datapartitionering {#data-partitioning}

Processer som hjälper till att skydda data som ägs av enskilda klienter.

**Trait Data Partitioning:**  Dina data ([!UICONTROL traits]ID, etc.) partitioneras av klienten. Detta förhindrar oavsiktlig informationsexponering mellan olika kunder. Till exempel partitioneras trait data in cookies av kunden och lagras i en klientspecifik underdomän. Den kan inte läsas eller användas av misstag av en annan Audience Manager-klient. Dessutom partitioneras trait data som lagras i [!UICONTROL Profile Cache Servers (PCS)] dokumentet också av kunden. Detta förhindrar att andra klienter oavsiktligt använder data i ett händelsesamtal eller någon annan begäran.

**Datapartitionering i rapporter:**  Klient-ID:n är en del av identifieringsnyckeln i alla rapporttabeller och rapportfrågor filtreras efter ID. Detta förhindrar att data visas i rapporter från en annan Audience Manager-kund.

## Ankommande server-till-server-överföringar (S2S) {#inbound-s2s}

Adobe Audience Manager har stöd för två huvudsakliga metoder för överföring av S2S-data ombord till våra system:

Båda metoderna är utformade med hänsyn till kundens och partnerns säkerhet när data är på väg mellan deras system och vårt system.

**SFTP:** För alternativet SFTP väljer de flesta kunder att leverera filer via SFTP-protokollet (Secure FTP), som använder SSH-protokollet (Secure Shell). Med den här metoden kan du vara säker på att filerna krypteras när de är på väg mellan kundens system och Adobes system. För varje kund skapar vi en plats för en ifylld drop box på våra SFTP-servrar, som är knuten till ett användarkonto i det systemet. Det är bara kundens inloggade och behöriga interna systemanvändare som har åtkomst till den här platsen för den packade listrutan. Det här fängelset är aldrig tillgängligt för andra kunder.

**[!UICONTROL Amazon Web Services S3]via HTTPS:**För leveransalternativet S3 rekommenderar vi att alla kunder konfigurerar sina S3-klienter så att de använder HTTPS-krypteringsmetoden för filöverföringar (detta är inte standard, så den måste konfigureras explicit). Alternativet HTTPS stöds både av kommandoradsverktyget s3cmd och de S3-bibliotek som finns i alla större programmeringsspråk. När det här HTTPS-alternativet är aktiverat krypteras kundens data när de skickas till våra system. För varje kund skapar vi en separat underkatalog för S3-bucket som bara kan nås av den kundens och våra interna systemanvändares autentiseringsuppgifter.

Information om hur du lägger till PGP-kryptering i datafiler finns i [PGP-kryptering för inkommande datatyper](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Skydda data med Escaping {#escaping-data}

Observera att [!DNL Audience Manager] data inte kringgås för att skydda dem mot eventuell XSS (cross-site scripting) osv. Det är kundens ansvar att kringgå inkommande data.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] är en branschövergripande webbsäkerhetsmekanism som skyddar mot cookie-kapning och protokollnedgraderingsattacker.

Principen instruerar webbläsaren att när ett säkert [!DNL HTTPS] anrop har gjorts till en viss domän, ska inga efterföljande osäkra anrop ([!DNL HTTP]) tillåtas till den domänen. Detta skyddar mot man-in-the-middle-attacker, där en angripare kan försöka nedgradera [!DNL HTTPS] samtal till osäkra [!DNL HTTP] samtal.&quot;

Denna policy förbättrar datasäkerheten mellan klienter och Adobe [Edge](../../reference/system-components/components-edge.md) -servrar.

### Exempel {#hsts-example}

Låt oss säga att `yourcompany.demdex.com` domänen skickar trafik till [!DNL DCS] via [!DNL HTTP]. [!DNL HSTS] uppgraderar samtalen som ska användas [!DNL HTTPS] i stället, och alla efterföljande [!DNL DCS] samtal som kommer från `yourcompany.demdex.com` använder [!DNL HTTPS] istället för [!DNL HTTP].

Mer information om HSTS finns i [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) .
