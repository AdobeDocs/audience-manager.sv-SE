---
description: Datainsamlingskomponenterna omfattar datainsamlingsservrar, DIL-API, inkommande server-till-server-dataöverföringar och loggfiler.
seo-description: Datainsamlingskomponenterna omfattar datainsamlingsservrar, DIL-API, inkommande server-till-server-dataöverföringar och loggfiler.
seo-title: Datainsamlingskomponenter
solution: Audience Manager
title: Datainsamlingskomponenter
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 6%

---

# Datainsamlingskomponenter{#data-collection-components}

Datainsamlingskomponenterna omfattar datainsamlingsservrar, DIL-API, inkommande server-till-server-dataöverföringar och loggfiler.

<!-- 

c_compcollect.xml

 -->

Audience Manager innehåller följande datainsamlingskomponenter:

* [Datainsamlingsservrar (DCS) och profilcacheservrar (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Data Integration Library (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Inkommande server-till-server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Loggfiler](../../reference/system-components/components-data-collection.md#log-files)

## Datainsamlingsservrar (DCS) och profilcacheservrar (PCS) {#dcs-pcs}

DCS och PCS fungerar tillsammans och tillhandahåller separat tjänster som är relaterade till kundanpassning, målgruppssegmentering och datalagring.

**[!UICONTROL Data Collection Servers (DCS)] -funktion**

I [!DNL Audience Manager], DCS:

* Tar emot och utvärderar trait-data från ett händelseanrop. Detta inkluderar information som används för segmentering i realtid och data som skickas in enligt schemalagda intervaller av server-till-server-överföringar.
* Segmentera användare baserat på deras realiserade egenskaper och de kvalificeringsregler du skapar med [Segment Builder](../../features/segments/segment-builder.md).
* Skapar och hanterar enhets-ID och autentiserade profil-ID:n. Detta inkluderar identifierare som DataProvider ID, användar-ID, deklarerade ID:n, integreringskoder osv.
* Kontrollerar om det finns ytterligare egenskaper hos PCS som en användare redan har uppnått före ett händelsesamtal i realtid. På så sätt kan DCS-användarna kvalificera sig baserat på realtidsdata och historiska data.
* Skriver loggfiler och skickar dem till analyssystem för lagring och bearbetning.

**[!DNL DCS]Hanterar efterfrågan via[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS] är ett geografiskt distribuerat och belastningsbalanserat system. Det innebär att [!DNL Audience Manager] kan dirigera begäranden till och från ett regionalt datacenter baserat på den geografiska platsen för en besökare. Denna strategi hjälper till att förbättra svarstiderna eftersom ett [!DNL DCS]-svar går direkt till ett datacenter som innehåller information om besökaren. [!UICONTROL GSLB] gör vårt system effektivt eftersom relevanta data cachas i servrar som ligger närmast användaren.

>[!IMPORTANT]
>
>[!DNL DCS] identifierar bara webbtrafik som kommer från enheter som använder IPv4.

I ett händelseanrop hämtas geografisk plats i ett nyckelvärdepar som returneras i en större mängd JSON-data. Detta nyckelvärdepar är parametern `"dcs_region": region ID`.

![](assets/dcs-map.png)

Som kund interagerar du indirekt med [!DNL DCS] via vår datainsamlingskod. Du kan också arbeta direkt med [!DNL DCS] via en uppsättning API:er. Se [API-metoder för datainsamlingsserver (DCS) och kod](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

[!UICONTROL PCS] är en stor databas (i stort sett en stor cookie på serversidan). Den lagrar data som tas emot för aktiva användare vid server till server-överföringar och [!DNL DCS]. [!UICONTROL PCS]-data består av enhets-ID, autentiserade profil-ID:n och tillhörande traits. När [!DNL DCS] tar emot ett realtidsanrop kontrollerar den [!UICONTROL PCS] om det finns andra egenskaper som en användare kan tillhöra eller vara berättigad till. Och om en egenskap läggs till i ett segment vid ett senare tillfälle läggs dessa trait-ID:n till i [!UICONTROL PCS] och användarna kan kvalificera sig för det segmentet automatiskt, utan att besöka en viss webbplats eller app. [!UICONTROL PCS] ger en djupare förståelse för dina användare eftersom det kan matcha och segmentera användare i realtid eller bakom kulisserna med nya och historiska trait-data. [!DNL Audience Manager] Detta beteende ger en mer fullständig och korrekt bild av era användare än bara med realtidskvalifikationer.

Det finns inga gränssnittskontroller som gör att våra kunder kan arbeta direkt med [!UICONTROL PCS]. Kundåtkomst till [!UICONTROL PCS] är indirekt genom sin roll som datalager och dataöverföringar. [!UICONTROL PCS] körs på Apache Cassandra.

**Tar bort inaktiva ID:n från[!UICONTROL PCS]**

Som tidigare nämnts lagrar [!UICONTROL PCS] trait-ID:n för aktiva användare. En aktiv användare är en användare som har setts av [edge data-servrarna](../../reference/system-components/components-edge.md) från valfri domän under de senaste 14 dagarna. Dessa anrop till [!UICONTROL PCS] håller en användare i ett aktivt tillstånd:

* [!DNL /event] samtal
* [!DNL /ibs] anrop (ID-synk)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

[!UICONTROL PCS] tömmer egenskaper om de är inaktiva i 17 dagar. De här egenskaperna går dock inte förlorade. De är lagrade i Hadoop. Om användaren visas igen vid ett senare tillfälle kommer Hadoopet att överföra alla sina egenskaper tillbaka till [!UICONTROL PCS], vanligtvis inom en 24-timmarsperiod.

**Andra  [!UICONTROL DCS/PCS] processer: Avanmäl dig till sekretess**

Dessa serversystem hanterar förfrågningar om sekretess och avanmälan av användare. Information om användarens cookie samlas inte in i loggfilen om en användare har avanmält sig från datainsamlingen. Mer information om våra integritetspolicyer finns i [Adobe Privacy Center](https://www.adobe.com/se/privacy/advertising-services.html).

## Data Integration Library (DIL)  {#dil}

[!UICONTROL DIL] är kod som du placerar på sidan för datainsamling. Mer information om tillgängliga tjänster och metoder finns i [DIL API](../../dil/dil-overview.md).

## Inkommande server-till-server {#inbound-outbound-server}

Detta är system som tar emot data som skickas in av olika server-till-server-integreringar med våra klienter. Mer information finns i dokumentationen om [sändning av målgruppsdata](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md).

## Loggfiler {#log-files}

Med [!UICONTROL PCS] skapas och skrivs data till loggfilerna. Dessa skickas till andra databassystem för bearbetning, rapportering och lagring.

>[!MORELIKETHIS]
>
>* [Adobes sekretesscenter](https://www.adobe.com/se/privacy.html)

