---
description: Vanliga frågor om datainsamling och integrering.
seo-description: Vanliga frågor om datainsamling och integrering.
seo-title: Vanliga frågor om datainsamling och produktintegrering
solution: Audience Manager
title: Vanliga frågor om datainsamling och produktintegrering
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
translation-type: tm+mt
source-git-commit: 7f9c7b74150682e8e8b839148dcae72f53d3b4ae

---


# Vanliga frågor om datainsamling och produktintegrering{#data-collection-and-product-integration-faq}

Vanliga frågor om datainsamling och integrering.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Hur kan jag särskilja inkommande trafik från[!UICONTROL DCS]trafik i[!UICONTROL DCS]loggfilsexporter?**

Trakter som introduceras via [!UICONTROL Inbound] fylls i på [!UICONTROL Inbound] samma sätt som de fylls av [!UICONTROL DCS]. Det finns olika sätt att se att trafiken kommer från [!UICONTROL Inbound]:

* Fjärr-IP anges till 68.67.173.18
* DomainID ställs in på 5325
* Regionen kommer att anges till 0

<br> 

**Kan du ge mig en lista över IP-adresser som jag kan vitlista för dpm.demdex.net?**

Tyvärr kan vi inte. Dessa IP-adresser tilldelas dynamiskt, per geografisk region, via [!DNL Amazon Web Services]. Detta innebär att [!DNL Audience Manager] inte kontrollerar vilket IP-intervall som kan tilldelas till den här adressen.

<br> 

**Kan du ge mig en IP-adress som jag kan vitlista för din inkommande och utgående FTP-server?**

Ja, se nedan.

| Objekt | Adress |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Vilka är kraven för kodplacering och sidinläsning för en[!UICONTROL DIL]/[!DNL Analytics]dataintegrering?**

Om du vill hämta [!DNL Analytics] data till [!DNL Audience Manager]läser du in [!UICONTROL DIL] efter `s_code` modulen men *före* `s.t()` funktionen. Du kan till exempel placera koden, eller se till att den läses in, i följande ordning:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] modul

3. [!DNL Analytics] `s.t()` function

Ett tips är att konfigurera din [!DNL Audience Manager]- [!DNL Analytics] integration med någon av dessa två metoder:

* Placera [!UICONTROL DIL] direkt i `s_code`.

* Serveras [!UICONTROL DIL] och `s_code` genom [!DNL Adobe Experience Platform Launch] eller [!DNL Adobe DTM].

Se API:t för [dataintegreringsbibliotek (DIL)](../dil/dil-overview.md).

<br> 

**Varför saknas mina[!DNL Analytics]variabler i ett[!DNL Audience Manager]eventsamtal?**

Detta inträffar vanligtvis när:

* Du använder ett tagghanteringssystem [!UICONTROL DIL] som läser in det asynkront med andra kodelement på sidan.
* Funktionen läses in `s.t()` tidigare [!UICONTROL DIL].

<br> 

**Vilka versioner av[!DNL Analytics]fungerar med[!UICONTROL DIL]?**

Du måste använda [!DNL Analytics] version 20.2 (eller senare) och biblioteksversion 3.5.2 (eller senare) för att arbeta med [!DNL Adobe AppMeasurement AS] [!UICONTROL DIL]. Om du inte känner till din [!DNL Analytics] eller [!DNL AppMeasurement] version kan du kontrollera vilket [!DNL Analytics] samtal som görs från sidan. Versionsinformation visas nedan:

Den här kunden använder [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Den här kunden använder [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kan jag samla in siddata om jag inte är en[!DNL Analytics]kund?**

Ja. Modulen [!UICONTROL DIL] hjälper dig att samla in siddata även om du inte använder [!DNL Analytics]. När konfigurationen är korrekt kan [!UICONTROL DIL] hämta in data från och om:

* Metataggar
* URL-adresser och URL-rubriker
* Sökmotortyper
* Nyckelord

Dessutom kan kunderna distribuera ett enkelt objekt på plats och fylla i det med nyckelvärdepar som ni vill samla in data om. [!UICONTROL DIL] På så sätt kan ni lägga till och ta bort specifika målgruppsdatapunkter på er webbplats utan att behöva [!DNL Audience Management] uppdatera dem. Samarbeta med din representant för Partner Solutions för att konfigurera och se till att [!DNL DIL] modulen refererar till sidobjektet korrekt.

<br> 

**Kan[!UICONTROL DIL]samla in data från[!DNL Google Analytics]?**

Ja. [!UICONTROL DIL] kan samla in vissa [!DNL Google Analytics] (GA) element och skicka dessa data till [!DNL Audience Manager]. Se:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Kan jag hämta rådata från[!DNL Audience Manager]och hur detaljerat är det?**

Ja, [!DNL Audience Manager] kan ge dig data som samlats in för användare som vi har sett på din inventering. Detta omfattar följande:

* Det unika användar-ID (UUID) som tilldelats av [!DNL Audience Manager]
* Trait and segment IDs
* Oanvända signaler
* Tidsstämplar
* Sidadresser

<br> 

**Jag vill samla in data på en webbplats och för målanvändare via DFP på en annan webbplats. Måste jag distribuera kod på den andra egenskapen om jag inte vill samla in data från den platsen?**

Nej. Om datainsamling på den andra platsen inte är ett krav behöver du inte distribuera DIL där. Så länge du har tillgång till lagret på den andra webbplatsen via DFP kan du använda datainsamlingen från den första webbplatsen och målet via DFP.

<br> 

**Vilken är den bästa tredjepartsleverantören av data?**

Varje leverantör tillför något unikt till tabellen, så svaret beror på vad du letar efter. Vi kan aktivera överlappningsrapportering (utan kostnad) för att hjälpa dig förstå vilken leverantör som fungerar bäst för dig.

<br> 

**Hur anger[!DNL Audience Manager]du cookies och skickar variabler till DFP?**

[!DNL Audience Manager] anger 2 cookies: Den ena skickar segmentvariabler till annonstaggen i DFP och den andra ställer in vårt unika användar-ID (UUID), som även läses av DFP. Genom att lägga till UUID i annonstaggen kan vi göra rapporter och målgruppsidentifiering på användarnivå.

<br> 

**Kan vi skicka en DSP-information om punkter i konverteringstratten som en användare uppnått?**

Ja. Vi kan skicka trattdata, men DSP måste ha den tekniska förmågan att använda dem. En DSP måste bekräfta att de kan hantera flera segment. Om de inte kan det kan vi behöva skapa specifika segment för att få bort en användare från andra segment baserat på deras konverteringsförlopp (t.ex. slutfört steg 1 och 2 men inte steg 3). Du kanske vill skicka den här informationen till en DSP så att de kan dirigera om användare, dirigera dem till en viss landningssida eller visa specifika kreatörer.

<br> 

**Hur kan jag bekräfta att data som skickas via FTP har hämtats av[!DNL Audience Manager]?**

En fil har hämtats när tillägget ändras från `.sync` till `.processed`. När det inträffar finns filen i kön för inläsning. Kontohanteraren kan också bekräfta när en fil har överförts.

<br> 

**Jag vill testa funktionaliteten i[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Jag skickar eventsamtal som den som visas nedan. Samtalen innehåller[deklarerade ID:n](../features/declared-ids.md)och signaler, som bör förverkliga några egenskaper och segment som jag redan har konfigurerat. Kan jag använda[!UICONTROL General Reports]och[!UICONTROL Trend Reports]verifiera om egenskaperna och segmentpopulationerna ökar?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nej, förlita dig inte på [!UICONTROL General Reports] och [!UICONTROL Trend Reports] i det här fallet.

Rapporterna beräknar populationer baserat på de oautentiserade profilposter (UUID) som vi ser i serverdelen när rapporterna skapas.

Vid ett första anrop till [!UICONTROL DCS]servern är de deklarerade ID:na *inte* länkade till något UUID (dvs. det finns ingen [demdexcookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_am.html) på klientsidan). Användaren [!UICONTROL DCS] genererar ett UUID slumpmässigt och ställer in en [!DNL demdex] cookie och skickar den i svarsanropet, men den skickar inte UUID till serverdelen.

>[!NOTE]
>
>Det genererade UUID:t materialiseras endast i vår datalagring i backend när enheten som cookien är inställd på utlöser ytterligare aktivitet.

Av den anledningen återspeglar rapporterna inte de händelser som utlöses av de deklarerade ID:n i ditt anrop. Vi rekommenderar att du använder UUID, ECID (tidigare MID) eller mobil enhets-ID vid testanrop till [!UICONTROL DCS]. Sedan kan du verifiera trait- och segment-realisationerna i [!UICONTROL General Reports] och i [!UICONTROL Trend Reports].

Se även [Index för Audience Manager-ID:n](../reference/ids-in-aam.md).

<br> 

**Hur lång tid tar det för användarprofiler att synkronisera mellan olika[regioner](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Det tar vanligtvis upp till 24 timmar för en användarprofil att synkronisera mellan regioner. I sällsynta fall kan dock processen ta upp till 48 timmar.
