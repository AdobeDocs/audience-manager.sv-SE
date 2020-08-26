---
description: Vanliga frågor och problem som rör datainsamling och integrering.
seo-description: Vanliga frågor och problem som rör datainsamling och integrering.
seo-title: Vanliga frågor om datainsamling och produktintegrering
solution: Audience Manager
title: Vanliga frågor om datainsamling och produktintegrering
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
feature: Administration
translation-type: tm+mt
source-git-commit: a292f44a63aa1e627d75d37c9ff0c1489f160729
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 86%

---


# Vanliga frågor om datainsamling och produktintegrering {#data-collection-and-product-integration-faq}

Vanliga frågor och problem som rör datainsamling och integrering.

<br> 

**Hur kan jag särskilja inkommande trafik från [!DNL DCS]-trafik i exporterade [!DNL DCS]-loggfiler?**

Traits som registreras via [!UICONTROL Inbound] fylls i av [!UICONTROL Inbound] på samma sätt som de fylls i av [!DNL DCS]. Det finns olika sätt att se var trafiken kommer från [!UICONTROL Inbound]:

* Fjärr-IP ställs in på 68.67.173.18
* DomainID ställs in på 5325
* Region ställs in på 0

<br> 

**Kan du ge mig en lista över IP-adresser som jag kan lägga till i en tillåtelselista för dpm.demdex.net?**

Tyvärr inte. Dessa IP-adresser tilldelas dynamiskt efter geografisk region via [!DNL Amazon Web Services]. Det innebär att [!DNL Audience Manager] inte styr vilket IP-intervall som kan tilldelas till den här adressen.

 

**Kan du ge mig en IP-adress jag kan lägga till i en tillåtelselista för din inkommande och utgående SFTP-server?**

Ja, se nedan.

| Server | IP-adresser |
| ---------|----------|
| ftp-in-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |
| ftp-out-gtw.demdex.com | 3.233.68.222; 52.3.74.119 |

 

SFTP-servrarna nedan är föråldrade. Inga nya konton kommer att etableras med dessa servrar.

| Server | IP-adress |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**Hur konfigurerar jag min Audience Manager-instans så att den använder de nya SFTP-servrarna?**

Kontakta din [!DNL Audience Manager] konsult eller kundtjänst så konfigurerar de dina nya SFTP-konton.

 

**Vilka autentiseringsmetoder stöds för de nya SFTP-servrarna?**

De nya SFTP-servrarna (`ftp-in-gtw` och `ftp-out-gtw`) har stöd [!DNL OpenSSH Key-Based Authentication]. Vi kan generera [!DNL SSH] nycklarna åt dig eller så kan du ge oss en egen offentlig nyckel.

 

**Vilka är kraven för kodplacering och sidinläsning för en [!UICONTROL DIL]/[!DNL Analytics]-dataintegrering?**

Om du vill hämta [!DNL Analytics]-data till [!DNL Audience Manager] läser du in [!UICONTROL DIL] efter `s_code`-modulen men *före* `s.t()`-funktionen. Du kan till exempel placera koden, eller se till att den läses in, i följande ordning:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] modul

3. [!DNL Analytics] `s.t()` funktion

Det bästa är att konfigurera [!DNL Audience Manager] - [!DNL Analytics]-integreringen med en av dessa två metoder:

* Placera [!UICONTROL DIL] direkt i `s_code`.

* Tillämpa [!UICONTROL DIL] och `s_code` via [!DNL Adobe Experience Platform Launch] eller [!DNL Adobe DTM].

Se [API för Data Integration Library (DIL)](../dil/dil-overview.md).

 

**Varför saknas mina [!DNL Analytics]-variabler i ett [!DNL Audience Manager]-händelseanrop?**

Detta inträffar vanligtvis när:

* Du använder [!UICONTROL DIL] via ett tagghanteringssystem som läser in det asynkront med andra kodelement på sidan.
* Funktionen `s.t()` läses in före [!UICONTROL DIL].

 

**Vilka versioner av [!DNL Analytics] fungerar med [!UICONTROL DIL]?**

Du måste använda [!DNL Analytics] version 20.2 (eller senare) och [!DNL Adobe AppMeasurement AS] biblioteksversion 3.5.2 (eller senare) för att arbeta med [!UICONTROL DIL]. Om du inte känner till din [!DNL Analytics]- eller [!DNL AppMeasurement]-version kontrollerar du [!DNL Analytics]-anropet från sidan. Versionsinformation visas nedan:

Kunden använder [!DNL Analytics] version 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Kunden använder [!DNL AppMeasurement] version 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kan jag samla in siddata även om jag inte är [!DNL Analytics]-kund?**

Ja. Modulen [!UICONTROL DIL] hjälper dig att samla in siddata även om du inte använder [!DNL Analytics]. När konfigurationen är korrekt kan [!UICONTROL DIL] samla in data från och om:

* Metataggar
* URL-adresser och URL-sidhuvuden
* Sökmotortyper
* Nyckelord

Dessutom kan en kund använda ett enkelt webbplatsobjekt och fylla det med nyckelvärdespar som ni vill att [!UICONTROL DIL] ska samla in data om. På så sätt kan ni lägga till och ta bort specifika målgruppsdatapunkter på webbplatsen utan att behöva uppdatera [!DNL Audience Management]. Samarbeta med er Partner Solutions-representant för att konfigurera detta och se till att [!DNL DIL]-modulen refererar till sidobjektet korrekt.

<br> 

**Kan [!UICONTROL DIL] samla in data från [!DNL Google Analytics]?**

Ja. [!UICONTROL DIL] kan samla in vissa [!DNL Google Analytics]-element (GA) och skicka dessa data till [!DNL Audience Manager]. Se:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Kan jag hämta rådata från [!DNL Audience Manager] och hur granulära är dessa data?**

Ja, [!DNL Audience Manager] kan tillhandahålla data som samlats in för användare som identifierats i ert datalager. Det inkluderar:

* Det unika användar-ID (UUID) som tilldelats av [!DNL Audience Manager]
* Trait- och segment-ID
* Oanvända signaler
* Tidstämplar
* Sidadresser

<br> 

**[!DNL Google Ad Manager]Jag vill samla in data på en webbplats och rikta mig till användare på en annan webbplats via Måste jag använda kod på den andra webbplatsen om jag inte vill samla in data från den?**

Nej. Om data inte behöver samlas in på den andra webbplatsen behöver du inte distribuera DIL där. As long as you have access to the inventory on the second site via [!DNL Google Ad Manager], you can use the data collection from the initial site and target via [!DNL Google Ad Manager].

<br> 

**Vilken är den bästa tredjepartsleverantören av data?**

Varje leverantör tillför något unikt, så det beror på vad du letar efter. Vi kan aktivera överlappande rapportering (utan extra kostnad) som hjälper dig att förstå vilken leverantör som fungerar bäst för dig.

<br> 

**Hur ställs cookies in i [!DNL Audience Manager] och hur skickas variabler till[!DNL Google Ad Manager]?**

[!DNL Audience Manager][!DNL Google Ad Manager] ställer in 2 cookies: Den ena skickar segmentvariabler till annonstaggen i och den andra ställer in vårt unika användar-ID (UUID) som också läses in av [!DNL Google Ad Manager]. Genom att lägga till UUID i annonstaggen kan vi skapa rapporter och målgruppsidentifiering på användarnivå.

<br> 

**Kan vi skicka DSP-information om punkter i konverteringstratten som en användare nått?**

Ja. Vi kan skicka trattdata, men DSP måste ha de tekniska funktioner som behövs för att använda dem. Er DSP måste bekräfta att de kan hantera flera segment. Om de inte kan det kanske vi måste skapa specifika segment för att få bort användare från andra segment baserat på konverteringsförlopp (t.ex. slutfört steg 1 och 2 men inte steg 3). Du kanske vill skicka den här informationen till en DSP så att de kan återmarknadsföra till användare, dirigera dem till en viss startsida eller visa specifika kampanjer.

<br> 

**Hur kan jag bekräfta att data som skickas via FTP har hämtats av [!DNL Audience Manager]?**

En fil har hämtats när tillägget ändras från `.sync` till `.processed`. När det inträffar står filen i kön för inläsning. Er kontoansvariga kan också bekräfta när en fil har överförts.

<br> 

**Jag vill testa funktionaliteten i [DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md). Jag skickar händelseanrop enligt nedan. Anropen innehåller [deklarerade ID:n](../features/declared-ids.md) och signaler som bör realisera vissa traits och segment som jag redan har konfigurerat. Kan jag använda [!UICONTROL General Reports] och [!UICONTROL Trend Reports] för att kontrollera om trait- och segmentpopulationerna ökar?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nej, förlita dig inte på [!UICONTROL General Reports] och [!UICONTROL Trend Reports] i det här fallet.

Rapporterna beräknar populationer baserat på oautentiserade profilposter (UUID) i serverdelen när rapporterna skapas.

Vid ett första anrop till [!DNL DCS] länkas deklarerade ID:n *inte* till ett UUID (dvs. det finns ingen [demdex-cookie](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) på klientsidan). [!DNL DCS] genererar ett UUID slumpmässigt och ställer in en [!DNL demdex]-cookie och skickar den i svarsanropet, men UUID skickas inte till serverdelen.

>[!NOTE]
>
>Det UUID som genereras materialiseras endast i serverdelens datalagring när ytterligare aktivitet inträffar på enheten som cookien finns på.

Därför återspeglar rapporterna inte händelser som utlöses av deklarerade ID:n i ditt anrop. Vi rekommenderar att ni använder UUID, ECID (tidigare MID) eller mobila enhets-ID när ni testar händelseanrop till [!DNL DCS]. Sedan kan ni kontrollera att traits och segment realiseras i [!UICONTROL General Reports] och [!UICONTROL Trend Reports].

Se även [Index över Audience Manager-ID:n](../reference/ids-in-aam.md).

<br> 

**Hur lång tid tar det innan användarprofiler synkroniseras mellan olika [regioner](../api/dcs-intro/dcs-api-reference/dcs-regions.md)?**

Det tar vanligtvis upp till 24 timmar för en användarprofil att synkroniseras mellan regioner. I sällsynta fall kan processen ta upp till 48 timmar.
